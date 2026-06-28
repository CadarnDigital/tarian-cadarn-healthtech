# Task: Deduplicate Vault (3-Layer Analysis)

## Metadata
- **id:** deduplicate-vault
- **agent:** aiox-argos-indexer
- **version:** 2.0
- **elicit:** true
- **description:** Progressive 3-layer deduplication analysis of the vault. Generates a candidate report for human decision — never auto-deletes or auto-merges.

---

## CLI-Agnostic Mandate

This task MUST be executed using **native Claude Code tools only** — no shell commands (`cat`, `grep`, `find`, `ls`, etc.):

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
- Vault exists at `{vault_path}` with Cover Notes containing frontmatter (id, checksum).
- UUID registry at `.aiox/refinery/uuid-registry.yaml` (for L1).
- Shared Embedding Store at `.aiox/refinery/embeddings/` (for L3).

## Inputs
- `vault_path`: Root of the Obsidian vault.
- `layer`: `L1` | `L2` | `L3` | `all` (default: `all`).
- `threshold`: Cosine similarity threshold for L3 (default: `0.85`).

## Elicitation (elicit: true)

### E1: Scope
```
🔍 Dedup Scope:
1. Full vault — All notes across all areas
2. Single area — Notes in one Spira area
3. Recent only — Notes promoted in the last {N} days

Select [1-3] (default: 1):
```

### E2: Layer Selection
```
🔍 Dedup Layers:
1. L1 only — Exact duplicates (SHA-256) — instant
2. L2 only — Fuzzy duplicates (SimHash) — seconds
3. L3 only — Semantic duplicates (Embeddings) — minutes
4. All layers (progressive) — recommended

Select [1-4] (default: 4):
```

---

## Execution Steps

### Step 1: Load Data Sources
```
1. Use read_file to load uuid-registry.yaml → Map<uuid, { path, checksum, asset_path }>
2. Use glob("**/*.md") to discover all notes in scope, then count
3. IF layer includes L3:
   a. Load vectors.bin into Float32Array (READ-ONLY)
   b. Load id-map.json → Map<uuid, vector_index>
   c. Report: "Loaded {count} embeddings ({size}MB)"
```

### Step 2: L1 — Exact Duplicate Detection (SHA-256)
```
1. Build inverted index: Map<checksum, [uuids with that checksum]>
2. FOR each checksum with 2+ UUIDs:
   a. These are EXACT duplicates
   b. Record candidate pair: { noteA, noteB, checksum, layer: "L1", confidence: 1.0 }
3. Report: "L1 complete: {count} exact duplicate pairs found"

Performance: O(n) single pass over registry.
```

### Step 3: L2 — Fuzzy Duplicate Detection (SimHash)
```
1. FOR each note in scope:
   a. Use read_file to extract title + first paragraph (first 200 chars of content)
   b. Compute 128-bit SimHash fingerprint:
      - Tokenize text into words
      - Hash each word (64-bit)
      - Accumulate weighted bit vectors
      - Reduce to 128-bit fingerprint
   c. Store: Map<uuid, simhash_fingerprint>

2. FOR each pair (i, j) where i < j:
   a. Compute Hamming distance between fingerprints
   b. IF distance <= 3 bits:
      Record candidate: { noteA, noteB, hamming: distance, layer: "L2", confidence: 1-(distance/128) }

3. Report: "L2 complete: {count} fuzzy duplicate pairs found"

Performance: O(n²) pairwise comparison.
Optimization: For large vaults (>5000), use locality-sensitive hashing (LSH) to reduce to O(n log n).
```

### Step 4: L3 — Semantic Duplicate Detection (Embedding Cosine)
```
1. FOR each pair of notes with embeddings in Shared Store:
   a. Retrieve vectors: vecA = vectors[id_map[uuidA]], vecB = vectors[id_map[uuidB]]
   b. Compute cosine similarity:
      dot = sum(vecA[i] * vecB[i]) for i in 0..383
      normA = sqrt(sum(vecA[i]²))
      normB = sqrt(sum(vecB[i]²))
      cosine = dot / (normA * normB)
   c. IF cosine >= threshold:
      Record candidate: { noteA, noteB, cosine, layer: "L3", confidence: cosine }

2. Report: "L3 complete: {count} semantic duplicate pairs found"

Performance: O(n²) pairwise. For 8000 notes = 32M comparisons × ~1µs each = ~32 seconds.
Optimization: Pre-filter with L2 results to reduce search space.
```

### Step 5: Deduplicate Across Layers
```
1. Merge candidates from L1, L2, L3
2. Remove duplicates (same pair detected by multiple layers → keep highest confidence)
3. Sort by confidence DESC
4. Assign priority:
   - L1 exact matches → "🔴 Definite Duplicate"
   - L2 hamming ≤ 1 → "🟠 Very Likely Duplicate"
   - L2 hamming 2-3 → "🟡 Possible Duplicate"
   - L3 cosine ≥ 0.90 → "🟠 Very Likely Duplicate"
   - L3 cosine 0.85-0.89 → "🟡 Possible Duplicate"
   - L3 cosine threshold-0.84 → "🔵 Worth Investigating"
```

### Step 6: Generate Candidate Report
```
Write to: {vault_path}/8 Sistema/.00 Inbox/dedup-candidates-report-{date}.md

---
id: "{{uuid}}"
tipo: "dedup-report"
status: "🗺️ active"
tags_funcionais: ["Argos", "Dedup", "Report"]
created_at: "{YYYY-MM-DD HH:mm}"
---

# 🔍 Dedup Candidates Report — {date}

> [!WARNING] Human Decision Required
> This report contains CANDIDATES only. Review each pair and mark [x] to confirm action.

## Summary
- Notes scanned: {total}
- L1 exact duplicates: {count_L1}
- L2 fuzzy duplicates: {count_L2}
- L3 semantic duplicates: {count_L3}
- Total unique pairs: {count_unique}

## 🔴 Definite Duplicates (L1 — SHA-256 Match)
| # | Note A | Note B | Checksum | Suggested Action |
|---|--------|--------|----------|-----------------|
| 1 | [[Note A]] | [[Note B]] | abc123... | Archive newer |

- [ ] Confirm: Archive [[Note B]] → .99 Arquivo/

## 🟠 Very Likely Duplicates (L2/L3 — High Confidence)
| # | Note A | Note B | Layer | Score | Suggested Action |
|---|--------|--------|-------|-------|-----------------|
| 1 | [[Note C]] | [[Note D]] | L3 | 0.93 | Merge content |

- [ ] Confirm: Merge [[Note D]] into [[Note C]]

## 🟡 Possible Duplicates (Review Needed)
...

## 🔵 Worth Investigating
...
```

---

## Post-Conditions
- Candidate report created in `8 Sistema/.00 Inbox/`.
- No notes deleted, merged, or modified (READ-ONLY analysis).
- Report is a checklist for Cadarn to review and approve actions.

## Output Summary
```
🗺️ Dedup Analysis Complete
━━━━━━━━━━━━━━━━━━━━━━━━━
📊 Notes scanned: {total}
🔴 Exact duplicates: {count_L1} pairs
🟠 High-confidence: {count_high} pairs
🟡 Possible: {count_possible} pairs
📄 Report: 8 Sistema/.00 Inbox/dedup-candidates-report-{date}.md
⏱️ Time elapsed: {duration}
```

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
