# Task: Tag Audit & Auto-Assignment

## Metadata
- **id:** tag-audit
- **agent:** aiox-vesta-custodian
- **version:** 2.0
- **elicit:** true
- **description:** Audits all notes in the vault and auto-assigns functional tags (tags_funcionais) based on rules for status, tipo, and ação. Reports anomalies and tag distribution.

---

## Pre-Conditions
- Vault exists at `{vault_path}` with Modelo Spira structure.
- Notes have frontmatter with all 12 canonical metadata fields (see 12-Field Reference below).

## CLI-Agnostic Mandate

> **NON-NEGOTIABLE:** This task MUST execute using only native Claude Code tools.
> - Use `Glob("**/*.md")` to scan vault directories — NEVER shell commands (`find`, `ls`, `dir`).
> - Use `Read` (read_file) to extract frontmatter from each note — NEVER `cat`, `head`, or `grep` in Bash.
> - Use `Edit` to update frontmatter fields — NEVER `sed`, `awk`, or PowerShell.
> - Use `Write` only for new report files.
> This ensures cross-platform compatibility (Windows, macOS, Linux) without shell dependencies.

## 12-Field Metadata Reference

All notes MUST have these 12 canonical frontmatter fields:

| # | Field | Type | Required | Example |
|---|-------|------|----------|---------|
| 1 | `id` | UUID v4 | YES | `a1b2c3d4-...` |
| 2 | `title` | string | YES | `"Atomic Habits - Chapter 3"` |
| 3 | `tipo` | enum | YES | See Tipo Values below |
| 4 | `status` | enum | YES | `"🌱 seedling"` |
| 5 | `tags_funcionais` | list | YES | `["#refinar", "#conectar"]` |
| 6 | `criado_em` | ISO date | YES | `2026-03-12` |
| 7 | `atualizado_em` | ISO date | YES | `2026-03-12` |
| 8 | `area` | string | YES | `"03 Conhecimento"` |
| 9 | `origin` | string | YES | Template or source |
| 10 | `asset_original` | string | CONDITIONAL | `"![[_assets/file.pdf]]"` |
| 11 | `checksum` | SHA-256 | AUTO | Content hash |
| 12 | `aliases` | list | AUTO | `["UUID-based alias"]` |

## Inputs
- `vault_path`: Root of the Obsidian vault.

## Elicitation (elicit: true)

### E1: Audit Scope
```
🏷️ Tag Audit Scope:
1. Full vault — Audit all notes in all areas
2. Single area — Audit notes in one specific area
3. Inbox only — Audit only .00 Inbox folders across all areas

Select [1-3]:
```

### E2: Auto-Assign Confirmation
```
🏷️ Auto-assignment mode:
1. Report only — Show what WOULD change (dry run)
2. Auto-assign — Apply changes automatically
3. Interactive — Ask for confirmation per note

Select [1-3] (default: 1):
```

---

## Execution Steps

### Step 1: Scan Notes
```
1. Use Glob("**/*.md") to collect all .md files in scope
2. FOR each note:
   a. Use Read (read_file) to load file content
   b. Parse frontmatter YAML block
   c. Extract all 12 canonical fields: { id, title, tipo, status, tags_funcionais,
      criado_em, atualizado_em, area, origin, asset_original, checksum, aliases }
   d. Count: outlinks, inlinks (backlinks), edit count (if detectable)
   e. Check: TL;DR section empty?, Conexões Cruzadas empty?
   f. Flag notes missing any of the 12 required fields
```

### Step 2: Apply Status Rules
```
FOR each note:
  Current status → Proposed status based on rules:

  RULE S1: IF criado_em < 7 days ago AND tipo = "raw-import" → "🌱 seedling"
  RULE S2: IF note has been edited 3+ times → "🌿 budding"
  RULE S3: IF note is linked by 3+ other notes (backlinks) → "🌲 evergreen"
  RULE S4: IF note is in .99 Arquivo/ folder → "📦 archived"
  RULE S5: IF tipo = "map-of-content" → "🗺️ active" (unless archived)

  Priority: S4 > S5 > S3 > S2 > S1 (highest wins)
```

### Step 3: Apply Tipo Rules
```
Canonical tipo values:
  - atomic-concept     (knowledge atoms)
  - map-of-content     (MOC/dashboard notes)
  - cover-note         (asset wrapper with asset_original)
  - raw-import         (unprocessed captures)
  - area-index         (.00 INDEX files)
  - diario_dia         (daily journal entries)
  - revisao_semanal    (weekly review notes)
  - revisao_mensal     (monthly review notes)
  - resumo_livro       (book summary notes)

FOR each note:
  RULE T1: IF origin contains "m2m-atomic-note-tmpl" → tipo = "atomic-concept"
  RULE T2: IF origin contains "moc-dashboard-tmpl" → tipo = "map-of-content"
  RULE T3: IF has asset_original field populated → tipo = "cover-note"
  RULE T4: IF in .00 INDEX file → tipo = "area-index"
  RULE T5: IF origin contains "diario-dia-tmpl" → tipo = "diario_dia"
  RULE T6: IF origin contains "revisao-semanal-tmpl" → tipo = "revisao_semanal"
  RULE T7: IF origin contains "revisao-mensal-tmpl" → tipo = "revisao_mensal"
  RULE T8: IF origin contains "resumo-livro-tmpl" → tipo = "resumo_livro"
```

### Step 4: Apply Action Tag Rules
```
FOR each note with tipo in ["atomic-concept", "cover-note", "raw-import"]:
  RULE A1: IF status = "🌱 seedling" AND tipo = "raw-import" → add "#refinar"
  RULE A2: IF Conexões Cruzadas section is empty → add "#conectar"
  RULE A3: IF TL;DR section is empty → add "#resumir"
  RULE A4: IF asset_original = "" AND tipo = "cover-note" → add "#sem-original"

  CLEANUP: Remove action tags when condition no longer true:
  - "#refinar" removed when status upgrades past seedling
  - "#resumir" removed when TL;DR is populated
  - "#conectar" removed when outlinks > 0
```

### Step 5: Generate Report
```
🏷️ Tag Audit Report
━━━━━━━━━━━━━━━━━━

📊 Status Distribution:
  🌱 seedling:  {count} ({pct}%)
  🌿 budding:   {count} ({pct}%)
  🌲 evergreen: {count} ({pct}%)
  🗺️ active:    {count} ({pct}%)
  📦 archived:  {count} ({pct}%)

📊 Action Tags:
  #refinar:      {count} notes need content refinement
  #resumir:      {count} notes need TL;DR
  #conectar:     {count} notes need cross-links
  #sem-original: {count} notes missing original asset

📊 Changes Proposed:
  Status upgrades:   {count}
  Status downgrades: {count}
  Tags added:        {count}
  Tags removed:      {count}

📊 12-Field Completeness:
  Notes with all 12 fields: {count} ({pct}%)
  Notes missing fields:     {count} ({pct}%)
  Most common missing field: {field_name} ({count} notes)

⚠️ Anomalies:
  - Notes without UUID: {count}
  - Notes without frontmatter: {count}
  - Notes with duplicate tags: {count}
  - Notes with unknown tipo value: {count}
```

### Step 6: Apply Changes (if mode = auto-assign or confirmed)
```
FOR each note with proposed changes:
  1. Use Read (read_file) to load current file content
  2. Use Edit to update frontmatter fields (status, tipo, tags_funcionais, atualizado_em)
  3. Preserve body content exactly — only frontmatter changes
  4. Log change to .aiox/refinery/tag-audit-log.yaml
```

---

## Post-Conditions
- All notes in scope have up-to-date tags_funcionais.
- Action tags reflect current state (stale tags removed).
- Audit report generated with distribution and anomalies.

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level) — Updated 2026-03-12*
