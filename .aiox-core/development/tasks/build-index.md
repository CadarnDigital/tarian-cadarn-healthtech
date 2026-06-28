# Task: Build Vault Index (Human + AI)

## Metadata
- **id:** build-index
- **agent:** aiox-argos-indexer
- **version:** 2.0
- **elicit:** true
- **description:** Generates comprehensive vault indexes in dual format — Human-readable Markdown for Obsidian browsing and AI-optimized JSON for LLM context windows.

---

## CLI-Agnostic Mandate

This task MUST be executed using **native Claude Code tools only** — no shell commands:

| Operation | Use | NOT |
|-----------|-----|-----|
| Read files | `read_file` | `cat`, `head`, `tail` |
| Find files | `glob` | `find`, `ls -R` |
| Search content | `grep_search` | `grep`, `rg`, `awk` |
| Write files | `write_file` / `edit_file` | `echo >`, `sed` |

All metadata extraction MUST read the **12 canonical frontmatter fields**:
`status`, `tipo`, `area`, `tema`, `palavras_chave`, `fonte_principal`, `curso`, `modulo`, `aula`, `created_at`, `title`, `tags_funcionais`

---

## Pre-Conditions
- Vault exists at `{vault_path}` with Cover Notes containing frontmatter.
- UUID registry at `.aiox/refinery/uuid-registry.yaml`.

## Inputs
- `vault_path`: Root of the Obsidian vault.
- `format`: `human` | `ai` | `both` (default: `both`).
- `scope`: `full` (entire vault) | `area` (single Spira area) (default: `full`).

## Elicitation (elicit: true)

### E1: Format & Scope
```
📚 Index Builder
Format:
1. Human only — Markdown index for Obsidian
2. AI only — JSON index for LLM context
3. Both (recommended)

Scope:
A. Full vault — All 8 areas
B. Single area — Specify area number (1-8)

Select format [1-3] and scope [A-B] (e.g., "3A"):
```

---

## Execution Steps

### Step 1: Collect Vault Data
```
1. Use glob("**/*.md") to discover all .md files in scope
2. FOR each note with frontmatter (use read_file to extract):
   a. Extract ALL 12 canonical fields:
      { id, title, area, status, tipo, tema, palavras_chave,
        fonte_principal, curso, modulo, aula, created_at, tags_funcionais }
   b. Extract additional: { jd_path, asset_original, asset_type }
   c. Extract: TL;DR from callout block (first 150 chars)
   d. Use grep_search("\\[\\[") to extract outlinks (wikilinks in body)
   e. Count: inlinks (backlinks from other notes)
3. Store in index collection
4. Report: "Collected {count} notes across {area_count} areas"
```

### Step 2: Generate Human Index (if format includes human)
```
Write to: {vault_path}/8 Sistema/8.20 Índices/INDEX-VAULT-{date}.md

---
id: "{{uuid}}"
tipo: "vault-index"
status: "🗺️ active"
tags_funcionais: ["Argos", "Index", "Human"]
created_at: "{YYYY-MM-DD HH:mm}"
---

# 📚 Vault Index — {date}

> [!INFO] Índice Gigante
> {total_notes} notas | {total_assets} assets | Gerado pelo Argos

## 📊 Dashboard Rápido
| Métrica | Valor |
|---------|-------|
| Total de notas | {total} |
| 🌱 Seedlings | {count} |
| 🌿 Budding | {count} |
| 🌲 Evergreen | {count} |
| 📎 Com PDF original | {count} |
| 🔗 Links internos | {total_links} |
| 🏝️ Notas órfãs (sem links) | {count} |

## Por Área (Modelo Spira)

### 1 Projetos ({count} notas)
| Nota | Status | TL;DR | Links |
|------|--------|-------|-------|
| [[1.10.01-Note]] | 🌱 | {tldr_excerpt} | {outlink_count}→ {inlink_count}← |

### 2 Biblioteca ({count} notas)
...

(repeat for all 8 areas)

## Por Status
### 🌱 Seedlings — Precisam de Atenção ({count})
```dataview
LIST
WHERE status = "🌱 seedling"
SORT created_at DESC
```

### 🌲 Evergreen — Conhecimento Consolidado ({count})
```dataview
LIST
WHERE status = "🌲 evergreen"
SORT created_at DESC
```

## Por Tag (Top 20)
| Tag | Notas | % do Vault |
|-----|-------|-----------|
| {tag1} | {count} | {pct}% |
| {tag2} | {count} | {pct}% |

## 📎 Assets Originais
| Nota de Capa | Asset | Tipo | Tamanho |
|-------------|-------|------|---------|
| [[Note]] | [[_assets/file.pdf]] | PDF | {size}MB |
```

### Step 3: Generate AI Index (if format includes ai)
```
Write to: {vault_path}/8 Sistema/8.20 Índices/INDEX-AI-{date}.json

{
  "metadata": {
    "generated": "{ISO-8601}",
    "generator": "aiox-argos-indexer",
    "vault_path": "{vault_path}",
    "total_notes": N,
    "total_assets": N,
    "spira_model": "v1.0"
  },
  "areas": [
    {
      "number": 1,
      "name": "Projetos",
      "note_count": N,
      "subcategories": ["1.10 Sub", "1.20 Sub"]
    }
  ],
  "notes": [
    {
      "id": "uuid-v4",
      "title": "Note Title",
      "area": 2,
      "area_name": "Biblioteca",
      "jd_path": "2.10.01-Note.md",
      "full_path": "2 Biblioteca/2.10 Frameworks/2.10.01-Note.md",
      "status": "🌱 seedling",
      "tipo": "cover-note",
      "tema": "Gestão do Conhecimento",
      "palavras_chave": ["zettelkasten", "PKM"],
      "fonte_principal": "Curso Lendário",
      "curso": "Curso Lendário",
      "modulo": "Módulo 3",
      "aula": "Aula 5",
      "tags_funcionais": ["Atômico", "MOC/Frameworks"],
      "tldr": "TL;DR excerpt (max 200 chars)",
      "has_asset": true,
      "asset_type": "pdf",
      "outlinks": ["uuid-1", "uuid-2"],
      "inlinks": ["uuid-3"],
      "created_at": "2026-03-12"
    }
  ],
  "stats": {
    "by_status": { "seedling": N, "budding": N, "evergreen": N },
    "by_tipo": { "cover-note": N, "atomic-concept": N, "map-of-content": N },
    "by_area": { "1": N, "2": N, "3": N, "4": N, "5": N, "6": N, "7": N, "8": N },
    "top_tags": [{ "tag": "name", "count": N }],
    "orphan_notes": N,
    "total_links": N
  }
}
```

### Step 4: Create Index Subcategory (if not exists)
```
1. Ensure {vault_path}/8 Sistema/8.20 Índices/ exists
2. Ensure {vault_path}/8 Sistema/8.20 Índices/_assets/ exists
```

---

## Post-Conditions
- Human index (MD) and/or AI index (JSON) created in `8 Sistema/8.20 Índices/`.
- Indexes are snapshots — regenerate with `*build-index` after significant changes.
- No vault notes modified.

## Output Summary
```
📚 Index Build Complete
━━━━━━━━━━━━━━━━━━━━━
📊 Notes indexed: {total}
📄 Human index: 8 Sistema/8.20 Índices/INDEX-VAULT-{date}.md
🤖 AI index: 8 Sistema/8.20 Índices/INDEX-AI-{date}.json
📎 Assets cataloged: {count}
⏱️ Time elapsed: {duration}
```

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
