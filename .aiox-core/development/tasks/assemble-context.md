# Task: Assemble Context Package

## Metadata
- **id:** assemble-context
- **agent:** aiox-talos-miner
- **version:** 2.0
- **elicit:** true
- **description:** Intelligent context packing that selects and assembles the optimal set of source notes within a token budget. Uses Greedy Diversity Packing to maximize relevance while minimizing redundancy. Produces a reviewable context-package.md.

---

## Pre-Conditions
- Mining brief with `mining_results` and status "mined".
- Enriched candidate list from semantic mining step.

## Inputs
- `brief_id`: ID of the mining brief.

---

## Execution Steps

### Step 1: Load Candidates & Config
```
1. Use read_file on mining brief: mining_results.top_candidates[]
2. Read config: token_budget, max_sources
3. Initialize: selected = [], remaining_budget = token_budget
4. Build tag matrix: Map<candidate_uuid, Set<tags>> for diversity calculation
```

### Step 2: Score Candidates (4 Dimensions)
```
FOR each candidate:
  score = weighted sum of:

  1. RELEVANCE (40%):
     base = candidate.cosine (0.0 - 1.0)
     boosted = candidate.boosted_score (if tag match applied)
     relevance_score = max(base, boosted)

  2. DIVERSITY (25%):
     IF selected is empty → diversity_score = 1.0 (first pick is always diverse)
     ELSE:
       overlap = count of tags shared with ANY already-selected note
       total_tags = candidate.tags.length
       diversity_score = 1.0 - (overlap / max(total_tags, 1))

  3. MATURITY (20%) — mapped from `status` canonical field:
     pronto → 1.0       (equivalent to 🌲 evergreen)
     em_andamento → 0.7  (equivalent to 🌿 budding)
     processar → 0.4     (equivalent to 🌱 seedling)
     captura → 0.2       (equivalent to 📦 raw capture)

  4. RECENCY (15%) — from `criado_em` canonical field:
     date_field = coalesce(criado_em, atualizado_em, file_mtime)  # fallback chain
     days_old = (now - date_field).days
     recency_score = exp(-days_old / 90)  # half-life: 90 days

  FINAL = (relevance × 0.40) + (diversity × 0.25) + (maturity × 0.20) + (recency × 0.15)
```

### Step 3: Greedy Diversity Packing
```
WHILE remaining_budget > 0 AND candidates remain AND selected.length < max_sources:
  1. Re-score all unselected candidates (diversity changes with each selection)
  2. Pick candidate with highest FINAL score
  3. Estimate tokens for this candidate:
     content = title + TL;DR + relevant_section (not full note)
     tokens = estimate_tokens(content)
  4. IF tokens <= remaining_budget:
     a. Add to selected[]
     b. remaining_budget -= tokens
     c. Remove from candidates
     d. Update diversity penalties for remaining candidates
  5. ELSE:
     a. Skip this candidate (never truncate mid-content)
     b. Try next highest-scoring candidate
     c. IF 3 consecutive skips → stop (remaining budget too small)
```

### Step 4: Extract Relevant Sections
```
FOR each selected note:
  1. Use read_file on full note from vault
  2. Extract sections most relevant to search_query:
     a. TL;DR callout → always include
     b. Content sections: rank each H2/H3 section by keyword overlap with query
     c. Select top sections until note's token share is met
  3. Store: { uuid, title, extracted_content, section_refs[], tokens_used }
```

### Step 5: Assemble Context Package

**Elicitation checkpoint:**
```
⛏️ Context Package Preview

📊 {selected_count} notes selected from {total_candidates} candidates
💰 Token budget: {used}/{total} ({pct}% used)

Sources selected:
1. [[{title_1}]] — Score: {score}, Tokens: {tokens} — "{tldr_excerpt}"
2. [[{title_2}]] — Score: {score}, Tokens: {tokens} — "{tldr_excerpt}"
...

📋 Proceed with this context? [Y/n/add {note}/remove {#}]
```

### Step 6: Write Context Package
```
Write to: .aiox/refinery/context-packages/context-package-{brief-id}.md

---
id: "{uuid}"
tipo: "context-package"
mining_brief: "{brief-id}"
token_budget: {total}
tokens_used: {used}
sources_count: {count}
assembled_at: "{ISO-8601}"
---

# ⛏️ Context Package — {search_query}

> [!INFO] Assembled by Talos
> {sources_count} sources | {tokens_used} tokens | Budget: {pct}% used

## Source 1: {title_1}
**UUID:** {uuid} | **Score:** {score} | **Status:** {status}
**Contribuição:** {why this note is relevant to the query}

{extracted_content_1}

---

## Source 2: {title_2}
...

---

## 📊 Assembly Metadata
| Metric | Value |
|--------|-------|
| Candidates searched | {total} |
| Selected | {count} |
| Token budget | {total} |
| Tokens used | {used} |
| Avg relevance | {avg_score} |
| Diversity score | {diversity_metric} |
| Dominant area | {most_common_area} |
```

### Step 7: Update Mining Brief
```
Update brief:
  context_assembly:
    package_path: "context-package-{brief-id}.md"
    sources_selected: {count}
    tokens_used: {used}
    avg_relevance: {score}
    diversity_score: {metric}
    status: "assembled"
```

---

## Post-Conditions
- Context package written to `.aiox/refinery/context-packages/`.
- Mining brief updated with assembly metadata and status "assembled".
- Cadarn has reviewed and approved the source selection.

## Output Summary
```
⛏️ Context Assembly Complete
━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 Sources selected: {count}/{candidates}
💰 Token budget: {used}/{total} ({pct}%)
🎯 Avg relevance: {score}
🌈 Diversity score: {metric}
📄 Package: .aiox/refinery/context-packages/context-package-{brief-id}.md
➡️ Next: Synthesis (*mine continues)
```

---

## CLI-Agnostic Mandate

This task MUST operate without any shell commands (`bash`, `sh`, `cmd`, `powershell`). All operations use native Claude Code tools:

| Operation | Tool | NOT |
|-----------|------|-----|
| Read mining brief | `read_file` | `cat`, `head` |
| Read candidate notes | `read_file` | `cat` |
| Write context package | `write_file` | `echo >`, shell redirect |
| Update mining brief | `edit_file` | `sed`, `awk` |
| Find notes in vault | `glob` | `find`, `ls` |
| Search content sections | `grep_search` | `grep`, `rg` |

**12 Canonical Metadata Fields** (used in scoring dimensions):
`uuid`, `aliases`, `tags_funcionais`, `tipo`, `status`, `criado_em`, `atualizado_em`, `tema`, `curso`, `fonte_principal`, `asset_original`, `publish`

**Status mapping for MATURITY dimension:**
| `status` value | Score |
|----------------|-------|
| `pronto` | 1.0 |
| `em_andamento` | 0.7 |
| `processar` | 0.4 |
| `captura` | 0.2 |

**RECENCY coalesce:** `criado_em` -> `atualizado_em` -> `file_mtime` (always has a valid date)

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
*Task created by aiox-master (Orion) on 2026-03-12 for aiox-talos-miner.*
