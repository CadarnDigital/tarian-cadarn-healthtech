# Task: Generate Cross-Connection Insights

## Metadata
- **id:** generate-insights
- **agent:** aiox-argos-indexer
- **version:** 2.0
- **elicit:** true
- **description:** Discovers hidden connections between vault notes using 3 strategies (co-occurrence, semantic proximity, bridging nodes). Generates a checklist report for human approval — never auto-links.

---

## CLI-Agnostic Mandate

This task MUST be executed using **native Claude Code tools only** — no shell commands:

| Operation | Use | NOT |
|-----------|-----|-----|
| Read files | `read_file` | `cat`, `head`, `tail` |
| Find files | `glob` | `find`, `ls -R` |
| Search content | `grep_search` | `grep`, `rg`, `awk` |
| Discover wikilinks | `grep_search("\\[\\[")` | `grep`, `rg` |
| Write files | `write_file` / `edit_file` | `echo >`, `sed` |

All metadata extraction MUST read the **12 canonical frontmatter fields**:
`status`, `tipo`, `area`, `tema`, `palavras_chave`, `fonte_principal`, `curso`, `modulo`, `aula`, `created_at`, `title`, `tags_funcionais`

---

## Pre-Conditions
- Vault exists at `{vault_path}` with Cover Notes containing frontmatter.
- Shared Embedding Store at `.aiox/refinery/embeddings/` (for semantic strategy).
- Notes have `tags_funcionais[]` populated (for co-occurrence strategy).

## Inputs
- `vault_path`: Root of the Obsidian vault.
- `strategy`: `co-occurrence` | `semantic` | `bridging` | `all` (default: `all`).
- `min_score`: Minimum confidence score to include (default: `0.7`).

## Elicitation (elicit: true)

### E1: Strategy Selection
```
🧠 Insights Engine — Strategy Selection:
1. Co-occurrence — Notes sharing 2+ tags but no direct link
2. Semantic — Notes with similar meaning (embedding cosine) but no link
3. Bridging — Notes connected through a third note but not to each other
4. All strategies (comprehensive) — recommended

Select [1-4] (default: 4):
```

### E2: Confidence Threshold
```
🧠 Minimum confidence score:
1. High (0.85) — Fewer but more reliable suggestions
2. Medium (0.70) — Balanced (recommended)
3. Low (0.50) — More suggestions, more noise

Select [1-3] (default: 2):
```

---

## Execution Steps

### Step 1: Build Graph Model
```
1. Use glob("**/*.md") to discover all notes in vault
2. Use read_file to extract frontmatter (12 canonical fields) from each note
3. Use grep_search("\\[\\[") to discover all wikilinks across all notes
4. Build structures:
   a. Link Graph: Map<uuid, Set<linked_uuids>> (from wikilinks discovered via grep_search)
   b. Tag Index: Map<tag, Set<uuids>> (from tags_funcionais)
   c. Load Embedding Store: use read_file for vectors.bin + id-map.json (READ-ONLY)
5. Report: "Graph loaded: {note_count} notes, {link_count} links, {tag_count} unique tags"
```

### Step 2: Co-occurrence Analysis
```
FOR each pair of tags (tagA, tagB) in Tag Index:
  notesA = Tag Index[tagA]
  notesB = Tag Index[tagB]
  shared = notesA ∩ notesB (notes with BOTH tags)

  FOR each pair (noteX, noteY) in shared where noteX ≠ noteY:
    IF noteY NOT IN Link Graph[noteX] (no direct link):
      shared_tag_count = count of tags shared by noteX and noteY
      IF shared_tag_count >= 2:
        score = shared_tag_count / max(tags(noteX).length, tags(noteY).length)
        IF score >= min_score:
          Record: { noteA: noteX, noteB: noteY, strategy: "co-occurrence",
                    score, reason: "Share {shared_tag_count} tags: {tag_list}" }
```

### Step 3: Semantic Proximity Analysis
```
1. Load vectors and id-map (READ-ONLY from Shared Store)
2. FOR each note with an embedding:
   a. Compute cosine similarity against ALL other notes
   b. Keep top-K neighbors (K=10) above min_score
   c. Filter: remove pairs already linked in Link Graph
   d. FOR each remaining pair:
      Record: { noteA, noteB, strategy: "semantic",
                score: cosine, reason: "Semantic similarity {cosine:.2f}" }

Optimization: Skip pairs already found by co-occurrence (avoid duplicates).
```

### Step 4: Bridging Node Analysis
```
FOR each note C in vault (candidate bridge):
  outlinks_C = Link Graph[C]
  FOR each pair (A, B) in outlinks_C where A ≠ B:
    IF B NOT IN Link Graph[A] AND A NOT IN Link Graph[B]:
      # A and B are both linked by C but don't know each other
      bridge_count = count of notes linking to BOTH A and B
      score = bridge_count / max(inlinks(A), inlinks(B))
      IF score >= min_score * 0.5 (lower threshold for bridging):
        Record: { noteA: A, noteB: B, strategy: "bridging",
                  score, reason: "Bridged by [[{C.title}]]" + {bridge_count-1} others" }
```

### Step 5: Consolidate & Rank
```
1. Merge candidates from all 3 strategies
2. Deduplicate: same pair from multiple strategies → keep all reasons, use max score
3. Sort by score DESC
4. Categorize:
   - Alta Confiança: score > 0.85
   - Média Confiança: score 0.70 - 0.85
   - Exploratório: score < 0.70 (bridging only)
```

### Step 6: Generate Insights Report
```
Write to: {vault_path}/8 Sistema/.00 Inbox/insights-report-{date}.md

---
id: "{{uuid}}"
tipo: "insights-report"
status: "🗺️ active"
tags_funcionais: ["Argos", "Insights", "Report"]
created_at: "{YYYY-MM-DD HH:mm}"
---

# 🧠 Connection Insights — {date}

> [!INFO] Human Approval Required
> These are SUGGESTIONS based on algorithmic analysis. Mark [x] to create the connection.

## Summary
- Notes analyzed: {total}
- Connections discovered: {total_connections}
- By strategy: Co-occurrence ({count}), Semantic ({count}), Bridging ({count})

## 🔴 Alta Confiança (score > 0.85)
- [ ] Conectar [[Note A]] ↔ [[Note B]]
  📎 Razão: {all reasons for this pair}
  📊 Score: {max_score} | Estratégias: {strategies_list}

## 🟡 Média Confiança (score 0.70-0.85)
- [ ] Investigar [[Note C]] ↔ [[Note D]]
  📎 Razão: {reasons}

## 🔵 Exploratório (Bridging Nodes)
- [ ] [[Note E]] e [[Note F]] são conectados por [[Note G]] mas não se conhecem
  📎 Bridge nodes: [[G]], [[H]]

## 📊 Cluster Map
Top clusters de notas inter-conectadas:
1. Cluster "{inferred_theme}": [[A]], [[B]], [[C]] ({link_density}% conectados)
2. ...
```

---

## Post-Conditions
- Insights report created in `8 Sistema/.00 Inbox/`.
- No wikilinks created in any notes (human must approve and link manually).
- Report serves as actionable checklist for knowledge gardening.

## Output Summary
```
🧠 Insights Analysis Complete
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 Notes analyzed: {total}
🔴 Alta confiança: {count_high} connections
🟡 Média confiança: {count_medium} connections
🔵 Bridging nodes: {count_bridges} connections
📄 Report: 8 Sistema/.00 Inbox/insights-report-{date}.md
⏱️ Time elapsed: {duration}
```

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
