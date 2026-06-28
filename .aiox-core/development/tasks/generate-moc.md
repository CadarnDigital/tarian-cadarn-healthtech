# Task: Generate MOC Dashboard

## Metadata
- **id:** generate-moc
- **agent:** aiox-argos-indexer
- **version:** 2.0
- **elicit:** true
- **description:** Creates a new Map of Content (MOC) Dashboard for a specific topic using the moc-dashboard-tmpl.md template. MOCs use folder-agnostic Dataview queries against frontmatter fields.

---

## CLI-Agnostic Mandate

This task MUST be executed using **native Claude Code tools only** — no shell commands:

| Operation | Use | NOT |
|-----------|-----|-----|
| Read files | `read_file` | `cat`, `head`, `tail` |
| Find files | `glob` | `find`, `ls -R` |
| Search content | `grep_search` | `grep`, `rg`, `awk` |
| Write files | `write_file` / `edit_file` | `echo >`, `sed` |

All Dataview queries and metadata operations use the **12 canonical frontmatter fields**:
`status`, `tipo`, `area`, `tema`, `palavras_chave`, `fonte_principal`, `curso`, `modulo`, `aula`, `created_at`, `title`, `tags_funcionais`

---

## Pre-Conditions
- Vault exists at `{vault_path}` with Cover Notes containing frontmatter.
- Template `moc-dashboard-tmpl.md` is accessible.
- Area `8 Sistema` exists in vault (Modelo Spira).

## Inputs
- `topic`: The theme/subject for the MOC (e.g., "Gestão do Conhecimento", "TypeScript").
- `vault_path`: Root of the Obsidian vault.
- `area` (optional): Override target area (default: `8 Sistema/8.10 MOCs/`).

## Elicitation (elicit: true)

### E1: Topic & Scope
```
🗺️ MOC Creation
Topic: {topic}

Scope for this MOC:
1. Auto-detect — Scan vault for notes matching "{topic}" in title, tags, or content
2. Manual selection — I'll specify which notes to include
3. Area-scoped — Only notes from a specific Spira area

Select [1-3] (default: 1):
```

### E2: Confirm Note Associations
```
🗺️ Found {count} notes related to "{topic}":

1. [[2.10.01-Zettelkasten-Fundamentos]] — Score: 0.95
2. [[2.10.03-Progressive-Summarization]] — Score: 0.88
3. [[7.20.01-Escrita-Atômica]] — Score: 0.72
...

Include all? [Y/n/select specific numbers]
```

---

## Execution Steps

### Step 1: Discover Related Notes
```
1. Use glob("**/*.md") to discover all notes in scope
2. Use read_file to extract frontmatter from each note
3. Score relevance to {topic} using 3 signals:
   a. Title match (exact or partial) → weight 3x
   b. tags_funcionais contains {topic} or similar → weight 2x
   c. Content body first 500 chars mentions {topic} → weight 1x
3. Rank by combined score DESC
4. Present top candidates to user (E2)
```

### Step 2: Tag Associated Notes
```
FOR each confirmed note:
  1. Read frontmatter
  2. Add "MOC/{topic}" to tags_funcionais[] (if not already present)
  3. Write updated frontmatter (preserve body exactly)
```

### Step 3: Apply MOC Template
```
1. Load moc-dashboard-tmpl.md
2. Fill template:
   - id: {generated UUID v4}
   - tipo: "map-of-content"
   - area: "8"
   - status: "🗺️ active"
   - tags_funcionais: ["MOC", "Dashboard", "MOC/{topic}"]
   - title: {topic}

3. Configure Dataview queries (ARCH-4 compliant — folder-agnostic):

   Estruturas Fundamentais:
   ```dataview
   LIST
   WHERE contains(tags_funcionais, "Atômico")
   AND contains(tags_funcionais, "MOC/{topic}")
   AND tipo = "atomic-concept"
   SORT created_at DESC
   ```

   Em Desenvolvimento:
   ```dataview
   TABLE status AS "Maturidade", created_at AS "Data", area AS "Área"
   WHERE contains(tags_funcionais, "MOC/{topic}")
   AND (status = "🌱 seedling" OR status = "🌿 budding")
   SORT created_at DESC
   ```

   Cover Notes com Material Original:
   ```dataview
   TABLE fonte_principal AS "Fonte", curso AS "Curso", modulo AS "Módulo", aula AS "Aula"
   WHERE contains(tags_funcionais, "MOC/{topic}")
   AND fonte_principal != ""
   SORT fonte_principal ASC
   ```

   Por Tema:
   ```dataview
   TABLE tema AS "Tema", palavras_chave AS "Palavras-Chave", title AS "Título"
   WHERE contains(tags_funcionais, "MOC/{topic}")
   AND tema != ""
   SORT tema ASC
   ```
```

### Step 4: Add Insights Section
```
IF insights-report exists for related notes:
  Extract relevant connection suggestions and embed in MOC:

  ## 📉 Insights & Conexões Descobertas
  > Conexões sugeridas pelo Argos para esta área de conhecimento:
  - [ ] [[Note A]] ↔ [[Note B]] — {reason}
```

### Step 5: Place in Vault
```
1. Generate filename: 8.10.{seq}-MOC-{sanitized-topic}.md
2. Write to: {vault_path}/8 Sistema/8.10 MOCs/
3. Create 8.10 MOCs/ subcategory if not exists
4. Verify file written successfully
```

---

## Post-Conditions
- MOC Dashboard created in `8 Sistema/8.10 MOCs/`.
- Associated notes tagged with `MOC/{topic}` in their frontmatter.
- Dataview queries are folder-agnostic (frontmatter-only).

## Output Summary
```
🗺️ MOC Created
━━━━━━━━━━━━━
📄 File: 8.10.{seq}-MOC-{topic}.md
📍 Location: 8 Sistema/8.10 MOCs/
📊 Associated notes: {count}
🏷️ Tag applied: MOC/{topic}
📋 Dataview queries: 4 (fundamentals, in-development, cover-notes, by-tema)
```

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
