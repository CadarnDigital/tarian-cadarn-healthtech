# Task: Semantic Mining

## Metadata
- **id:** semantic-mining
- **agent:** aiox-talos-miner
- **version:** 2.0
- **elicit:** false
- **description:** Executes semantic search against the Shared Embedding Store using the mining brief from FOCO. Returns ranked candidate notes for context assembly. READ-ONLY on all data stores.

---

## Pre-Conditions
- Mining brief exists at `.aiox/refinery/mining-briefs/{brief-id}.yaml` with status "ready".
- Shared Embedding Store at `.aiox/refinery/embeddings/` (vectors.bin + id-map.json).
- UUID Registry at `.aiox/refinery/uuid-registry.yaml`.

## Inputs
- `brief_id`: ID of the mining brief (from FOCO elicitation).

---

## Execution Steps

### Step 1: Load Mining Brief
```
1. Use read_file to load mining-brief-{brief_id}.yaml
2. Extract: search_query, terms[], tag_filters[], scope, min_relevance, max_sources
3. Extract metadata filters (if set): curso, tema, fonte_principal
4. Use edit_file to update brief status: "ready" → "mining"
```

### Step 2: Generate Query Embedding
```
1. Compose search string:
   IF terms exist → join terms with spaces
   ELSE → use raw search_query
2. Compute embedding via @xenova/transformers (all-MiniLM-L6-v2)
   - Input: search string
   - Output: Float32Array (384 dims) — the "query vector"
```

### Step 2b: Metadata Pre-Filtering (12 Canonical Fields)
```
Before vector search, apply metadata pre-filtering to reduce search space:

12 Canonical Fields:
  uuid, aliases, tags_funcionais, tipo, status, criado_em, atualizado_em,
  tema, curso, fonte_principal, asset_original, publish

1. Use read_file to load uuid-registry.yaml
2. FOR each registered note:
   a. Use read_file to read the note's frontmatter
   b. Apply pre-filters from mining brief:
      - IF curso filter set → keep only notes where curso matches
      - IF tema filter set → keep only notes where tema matches
      - IF fonte_principal filter set → keep only notes where fonte_principal matches
      - IF scope = "area-N" → keep only notes in matching area path
   c. Build pre-filtered UUID set: eligible_uuids[]
3. Report: "Pre-filter: {eligible} of {total} notes match metadata criteria"

NOTE: Pre-filtering happens BEFORE vector search to avoid wasting
cosine computations on notes that will be excluded anyway.
```

### Step 3: Vector Search (READ-ONLY)
```
1. Use read_file to load vectors.bin into Float32Array (READ-ONLY, no modifications)
2. Use read_file to load id-map.json → Map<uuid, index>
3. FOR each entry in id-map (filtered to eligible_uuids if pre-filter active):
   a. Retrieve vector at index
   b. Compute cosine similarity with query vector:
      dot = sum(query[i] * vec[i])
      normQ = sqrt(sum(query[i]²))
      normV = sqrt(sum(vec[i]²))
      cosine = dot / (normQ * normV)
   c. IF cosine >= min_relevance:
      Add to candidates: { uuid, cosine }
4. Sort candidates by cosine DESC
5. Report: "Vector search complete: {count} candidates above threshold {min_relevance}"
```

### Step 4: Apply Scope Filters
```
1. Use read_file to load uuid-registry.yaml (READ-ONLY)
2. FOR each candidate:
   a. Resolve uuid → { path, asset_path } from registry
   b. IF scope = "area-N":
      Filter: keep only notes where path starts with "{N} "
   c. IF scope = "moc-{name}":
      Use read_file on note frontmatter, keep only if tags_funcionais contains "MOC/{name}"
   d. IF scope = "vault-wide":
      No filter (keep all)
3. Report: "After scope filter: {count} candidates"
```

### Step 5: Apply Tag Filters
```
IF tag_filters is not empty:
  FOR each candidate:
    1. Use read_file on note frontmatter (from resolved path)
    2. Check: any tag in tag_filters present in tags_funcionais?
    3. IF yes → boost score by 20% (relevance bonus for tag match)
    4. IF no → keep but don't boost
  Re-sort by adjusted score
```

### Step 6: Enrich Candidates
```
FOR each candidate (top max_sources × 2, to give assembly room):
  1. Use read_file on note from vault path
  2. Extract:
     - title: from H1 heading
     - tldr: from TL;DR callout (first 200 chars)
     - status: from frontmatter
     - tipo: from frontmatter
     - tags: from tags_funcionais
     - content_preview: first 500 chars of body
     - has_asset: boolean (asset_original != "")
     - word_count: approximate
  3. Estimate token count: word_count * 1.3
  4. Store enriched candidate
```

### Step 7: Generate Candidate Report
```
Update mining brief with results:

mining_brief:
  ...
  mining_results:
    total_searched: {embedding count}
    candidates_found: {above threshold}
    after_scope_filter: {count}
    top_candidates:
      - uuid: "{uuid}"
        title: "{title}"
        path: "{vault path}"
        cosine: 0.92
        boosted_score: 0.94
        status: "🌲 evergreen"
        tokens_est: 340
        tldr: "{excerpt}"
      - ...
    status: "mined"
```

---

## Post-Conditions
- Mining brief updated with `mining_results` and status "mined".
- All data stores untouched (READ-ONLY operations only).
- Enriched candidate list ready for context assembly.

## Output Summary
```
⛏️ Semantic Mining Complete
━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 Embeddings searched: {total}
🎯 Candidates found: {count} (cosine > {threshold})
📂 After scope filter: {count}
🏷️ Tag-boosted: {count}
📄 Top candidate: "{title}" (score: {max_score})
➡️ Next: Context Assembly (*assemble)
```

---

## CLI-Agnostic Mandate

This task MUST operate without any shell commands (`bash`, `sh`, `cmd`, `powershell`). All operations use native Claude Code tools:

| Operation | Tool | NOT |
|-----------|------|-----|
| Read mining brief | `read_file` | `cat`, `head` |
| Read uuid-registry | `read_file` | `cat` |
| Read note frontmatter | `read_file` | `head -n 20` |
| Read embedding files | `read_file` | `cat`, shell pipes |
| Find notes in vault | `glob` | `find`, `ls` |
| Search note content | `grep_search` | `grep`, `rg` |
| Update brief status | `edit_file` | `sed`, `awk` |

**12 Canonical Metadata Fields** (used in pre-filtering):
`uuid`, `aliases`, `tags_funcionais`, `tipo`, `status`, `criado_em`, `atualizado_em`, `tema`, `curso`, `fonte_principal`, `asset_original`, `publish`

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
*Task created by aiox-master (Orion) on 2026-03-12 for aiox-talos-miner.*
