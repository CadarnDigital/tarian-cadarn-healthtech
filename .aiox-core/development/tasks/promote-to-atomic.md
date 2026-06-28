# Task: Promote M2M-cru to Cover Note (Atomic)

## Metadata
- **id:** promote-to-atomic
- **agent:** aiox-vesta-custodian
- **version:** 1.0
- **elicit:** true
- **description:** Transforms Echo's M2M-cru output into Obsidian-ready Cover Notes with embedded PDFs, following the Modelo Spira structure.

---

## Pre-Conditions
- M2M-cru files exist at `{source_path}` (output from Echo).
- Vault path `{vault_path}` exists and has Modelo Spira skeleton (or will be scaffolded).
- Template `m2m-atomic-note-tmpl.md` is accessible.
- `.aiox/refinery/` directory exists for registry and embeddings.

## Inputs
- `source_path`: Directory containing M2M-cru files from Echo.
- `vault_path`: Root of the Obsidian vault (Modelo Spira structure).

## Elicitation (elicit: true)

### E1: Confirm Source
```
📂 Source path: {source_path}
Found {count} M2M-cru files.
Proceed with promotion? [Y/n]
```

### E2: Area Assignment
```
🏠 Default area for promoted notes:
1. 1 Projetos
2. 2 Biblioteca
3. 3 Pessoal
4. 4 Profissional
5. 5 Finanças
6. 6 Saúde
7. 7 Criatividade
8. 8 Sistema
0. Auto-detect from source folder name

Select default area [0-8] (default: 0):
```

### E3: Subcategory
```
📁 Default JD subcategory within area {area}:
0. {area}.00 Inbox (classify later)
1. {area}.10 {existing_sub_1}
2. {area}.20 {existing_sub_2}
...
N. Create new subcategory

Select [0-N] (default: 0):
```

---

## Execution Steps

### Step 1: Scan & Validate
```
FOR each file in {source_path}:
  1. Read M2M-cru file
  2. Extract <metadata> block
  3. Check extraction_quality field:
     - "failed" → REJECT: log to exception-report, skip file
     - "partial" → ACCEPT: flag with tag #refinar
     - "full" → ACCEPT: normal promotion
  4. Collect: { filename, origin_path, extraction_quality, content_length }
```

**Output:** List of accepted files + exception report for rejected files.

### Step 2: Generate Identity (per file)
```
1. Generate UUID v4 (crypto.randomUUID())
2. Calculate SHA-256 of content body (exclude metadata tags)
3. Store: { uuid, checksum }
```

### Step 3: Asset Placement (per file)
```
1. Read origin_path from M2M-cru metadata
2. Locate original file at origin_path (PDF, DOCX, etc.)
3. IF original found:
   a. Determine target: {vault_path}/{area}/{JD-sub}/_assets/
   b. Create _assets/ directory if not exists
   c. COPY original file to _assets/ (preserve original filename)
   d. Determine embed type:
      - File size < 20MB AND extension in [pdf, png, jpg, jpeg, gif, svg] → embed: "![[_assets/{filename}]]"
      - File size >= 20MB OR extension not renderable → link: "[[_assets/{filename}]]"
   e. Store: { asset_path, asset_type, embed_string }
4. IF original NOT found:
   a. Log warning: "Original not found at {origin_path}"
   b. Set asset_original: "" (empty — no embed)
   c. Add tag #sem-original to tags_funcionais
```

### Step 4: Apply Template — 12 Canonical Fields (per file)
```
1. Load m2m-atomic-note-tmpl.md
2. Fill ALL 12 canonical frontmatter fields:
   - id: {uuid}
   - checksum: {checksum}
   - version: "1.0"
   - origin_path: {relative path to M2M-cru}
   - asset_original: "{embed_string}"
   - asset_type: "{detected type}"
   - status: "captura"
   - tipo: "cover-note"
   - area: "{inferred from E2 selection or source folder}"
   - tema: "{inferred from filename/content — leave empty if unclear}"
   - palavras_chave: ["{extracted keywords from title and content}"]
   - fonte_principal: "{inferred from source folder or metadata}"
   - curso: "{if source is a course folder}"
   - modulo: "{if detectable from subfolder name}"
   - aula: "{if detectable from filename}"
   - created_at: "{YYYY-MM-DD HH:mm}"
   - title: "{sanitized title from filename or content heading}"
   - tags_funcionais: ["Atômico", "cover-note"] + conditional tags
3. Fill body (Cover Note pattern):
   - TL;DR callout: Leave empty (tagged #resumir for later)
   - Conteúdo: Extract from M2M-cru <content> block
   - 📄 Material Original: Insert embed/link string (![[_assets/...]])
   - Conexões Cruzadas: Leave empty (tagged #conectar)
4. ALTERNATIVE — In-place Promotion body (when user selects in-place mode):
   - De Relance callout (expanded) with: Rascunho mental, 3 pontos-chave, Por que importa, Próximo passo
   - Insights block (collapsed by default)
   - Ficha Temática block (collapsed by default)
5. Generate output filename: {area}.{dezena}.{seq}-{sanitized-title}.md
```

### Step 4b: Detect Source Metadata (CLI-Agnostic)
```
Use native tools to infer metadata from source:
1. read_file on M2M-cru → extract <metadata> block
2. Parse source_path to infer: curso, modulo, aula
   Example: "CURSOS/Lendário/.../02 Evoluindo/03 Tags.pdf"
   → curso: "Dominando Obsidian"
   → modulo: "02 Evoluindo para Além das Notas"
   → aula: "03 Tags"
3. Extract keywords from title + first paragraph
4. If source folder matches Spira area name → auto-assign area
```

### Step 5: Auto-Tag (per file)
```
Apply tag rules to tags_funcionais[]:
- ALWAYS: "Atômico"
- IF extraction_quality = "partial": "#refinar"
- IF TL;DR is empty: "#resumir"
- IF no outlinks: "#conectar"
- IF asset not found: "#sem-original"
```

### Step 6: Calculate Embedding (per file)
```
1. Acquire lock: .aiox/refinery/embeddings/vectors.lock
2. Compute embedding:
   - Input: title + first 512 chars of content
   - Model: all-MiniLM-L6-v2 via @xenova/transformers
   - Output: Float32Array (384 dimensions)
3. Append to vectors.bin (binary append)
4. Update id-map.json: add { uuid: next_index }
5. Release lock
```

### Step 7: Register UUID (per file)
```
1. Acquire lock: .aiox/refinery/uuid-registry.lock
2. Append entry to uuid-registry.yaml:
   - id: {uuid}
   - path: {relative vault path to Cover Note}
   - asset_path: {relative vault path to asset in _assets/}
   - created: {YYYY-MM-DD}
   - checksum: {sha256}
3. Release lock
```

### Step 8: Place in Vault
```
1. Write Cover Note to: {vault_path}/{area}/{JD-sub}/{filename}.md
2. Verify file was written successfully
3. Verify asset exists at _assets/ path
```

### Step 9: Log Promotion
```
Append to .aiox/refinery/promotion-log.yaml:
  - uuid: {uuid}
    source: {M2M-cru path}
    asset_source: {origin_path}
    destination: {vault note path}
    asset_destination: {_assets/ path}
    timestamp: {ISO 8601}
    extraction_quality: {full|partial}
    embedding_index: {index in vectors.bin}
    tags_assigned: [list of tags]
```

---

## Post-Conditions
- Cover Notes exist in vault with full frontmatter metadata.
- Original PDFs copied to `_assets/` and embedded in Cover Notes.
- UUID registry updated with all new entries + asset paths.
- Embedding store updated with new vectors (append-only).
- Promotion log records all operations.
- Exception report lists any rejected or problematic files.

## Output Summary
```
🏠 Promotion Complete
━━━━━━━━━━━━━━━━━━━━
✅ Promoted: {count_success}
⚠️ Partial (needs #refinar): {count_partial}
❌ Rejected (quality=failed): {count_rejected}
📎 Assets placed: {count_assets}
🔢 Embeddings calculated: {count_embeddings}
📍 Area: {area_name}
📁 Subcategory: {jd_sub}
```

---
*Task created by aiox-master (Orion) on 2026-03-12 for aiox-vesta-custodian.*
