# Task: Organize Vault (Modelo Spira)

## Metadata
- **id:** organize-vault
- **agent:** aiox-vesta-custodian
- **version:** 1.0
- **elicit:** true
- **description:** Applies the Modelo Spira (Método Morfogênico) structure to an Obsidian vault. Creates the 8-area skeleton, JD subcategories, _assets/ folders, and optionally reclassifies existing notes.

---

## Pre-Conditions
- `{vault_path}` is a valid directory (existing vault or empty folder).
- Agent has write permissions to `{vault_path}`.

## Inputs
- `vault_path`: Root of the Obsidian vault.
- `mode`: `scaffold` (create structure only) | `reorganize` (move existing notes into Spira structure).

## Elicitation (elicit: true)

### E1: Mode Selection
```
🏠 Vault Organization Mode:
1. Scaffold — Create Modelo Spira folder skeleton (non-destructive)
2. Reorganize — Analyze existing notes and propose reclassification

Select [1-2]:
```

### E2: Area Customization (scaffold mode)
```
📋 Modelo Spira — 8 Áreas Padrão:
1. Projetos       — Projetos ativos com prazo
2. Biblioteca     — Referência, cursos, livros
3. Pessoal        — Vida pessoal, reflexões
4. Profissional   — Carreira, networking
5. Finanças       — Gestão financeira
6. Saúde          — Bem-estar
7. Criatividade   — Conteúdo, arte
8. Sistema        — MOCs, Dashboards, Logs

Accept standard areas? [Y/n]
If no: specify custom area names (numbered 1-8).
```

### E3: JD Subcategories (scaffold mode)
```
📁 Pre-create JD subcategories?
For each area, you can define initial subcategories (X.10, X.20, etc.)
Or press Enter to create only .00 Inbox and .99 Arquivo per area.

Area {n} ({name}) subcategories:
> (Enter comma-separated names, or Enter for default)
```

---

## Execution Steps

### Step 1: Analyze Current State
```
1. Scan {vault_path} for existing structure
2. Count: total files, .md files, binary files, existing folders
3. Detect if Modelo Spira is partially applied
4. Report findings to user
```

### Step 2: Create Area Skeleton (scaffold mode)
```
FOR each area (1-8):
  1. Create directory: {vault_path}/{n} {area_name}/
  2. Create: {vault_path}/{n} {area_name}/.00 Inbox/
  3. Create: {vault_path}/{n} {area_name}/.00 Inbox/_assets/
  4. Create: {vault_path}/{n} {area_name}/.99 Arquivo/
  5. Create: {vault_path}/{n} {area_name}/.99 Arquivo/_assets/
  6. FOR each custom JD subcategory:
     a. Create: {vault_path}/{n} {area_name}/{n}.{dezena} {sub_name}/
     b. Create: {vault_path}/{n} {area_name}/{n}.{dezena} {sub_name}/_assets/
```

### Step 3: Create Area Index Notes
```
FOR each area (1-8):
  Create {vault_path}/{n} {area_name}/{n}.00-INDEX.md with:
  ---
  id: "{{uuid}}"
  tipo: "area-index"
  area: "{n}"
  status: "🗺️ active"
  tags_funcionais: ["Índice", "Área-{n}"]
  ---
  # 🗺️ Área {n}: {area_name}
  > Índice automático desta área. Gerenciado pela Vesta.

  ## Subcategorias
  (Dataview query listing subcategories)

  ## Notas Recentes
  (Dataview query listing recent notes in this area)
```

### Step 4: Reorganize Existing Notes (reorganize mode only)
```
1. Scan all .md files in vault
2. FOR each note:
   a. Read frontmatter (if exists)
   b. Infer best area based on: tags, folder name, content keywords
   c. Propose: "{note} → Area {n} / {JD-sub}"
3. Present proposals as numbered list:
   "1. [MOVE] old/path/note.md → 2 Biblioteca/2.10 Frameworks/"
   "2. [KEEP] already-organized/note.md (already in Spira)"
   "3. [INBOX] unknown/note.md → 2 Biblioteca/2.00 Inbox/"
4. ELICIT: "Accept all proposals? [Y/n/edit]"
5. IF accepted:
   a. Move notes to new locations
   b. Move associated assets to new _assets/ folders
   c. Update uuid-registry.yaml paths (acquire lock)
   d. Update Obsidian aliases for redirect
```

### Step 5: Configure Obsidian Settings
```
Report recommended Obsidian settings:
"📋 Recommended Obsidian Settings:
 - Files & Links → Default location for new attachments → Subfolder: _assets
 - Files & Links → Use [[Wikilinks]] → ON
 - Files & Links → Detect all file extensions → ON"
```

---

## Post-Conditions
- Modelo Spira folder skeleton exists with all 8 areas.
- Each area has `.00 Inbox/`, `.99 Arquivo/`, and `_assets/` folders.
- Area index notes created with Dataview queries.
- (reorganize mode) Existing notes reclassified and uuid-registry updated.

## Output Summary
```
🏠 Vault Organization Complete
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📁 Areas created: {count}/8
📁 JD subcategories: {count}
📁 _assets/ folders: {count}
📄 Index notes: {count}
🔄 Notes reorganized: {count} (reorganize mode)
📋 Obsidian settings: See recommendations above
```

---
*Task created by aiox-master (Orion) on 2026-03-12 for aiox-vesta-custodian.*
