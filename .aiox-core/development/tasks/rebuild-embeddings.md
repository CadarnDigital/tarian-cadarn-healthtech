# Task: Rebuild Shared Embedding Store

## Metadata
- **id:** rebuild-embeddings
- **agent:** aiox-vesta-custodian
- **version:** 2.0
- **elicit:** true
- **description:** Full rebuild of the Shared Embedding Store from all notes in the vault. Expensive operation — use only when the store is corrupted, the model is upgraded, or a major vault restructure occurred.

---

## Pre-Conditions
- Vault exists at `{vault_path}` with notes containing frontmatter (id field).
- `.aiox/refinery/embeddings/` directory exists.
- `@xenova/transformers` is available (or will be installed).

## Inputs
- `vault_path`: Root of the Obsidian vault.

## CLI-Agnostic Mandate

> **NON-NEGOTIABLE:** This task MUST execute using only native Claude Code tools.
> - Use `Glob("**/*.md")` to discover all vault notes — NEVER shell commands (`find`, `ls`, `dir`).
> - Use `Read` (read_file) to extract note content for embedding input — NEVER `cat`, `head`, or shell pipes.
> - Content extraction (frontmatter parsing, body text extraction) is done by parsing read_file output in-memory.
> - File operations (backup, write) use `Read`/`Write`/`Edit` — NEVER `cp`, `mv`, or shell redirects.
> This ensures cross-platform compatibility (Windows, macOS, Linux) without shell dependencies.

## Elicitation (elicit: true)

### E1: Confirm Rebuild
```
⚠️ REBUILD EMBEDDINGS — Expensive Operation
This will recalculate ALL embeddings from scratch.

Current store:
  - Vectors: {current_count}
  - Model: {current_model}
  - File size: {vectors_bin_size}

Estimated time: ~{count × 50}ms ({count} notes × ~50ms/embedding)

Reason for rebuild:
1. Store corrupted (size mismatch, missing entries)
2. Model upgrade (switching to new embedding model)
3. Major vault restructure (many notes changed)
4. First-time build (no store exists)

Select reason [1-4]:
Proceed? [Y/n]
```

---

## Execution Steps

### Step 1: Backup Current Store
```
IF .aiox/refinery/embeddings/vectors.bin exists:
  1. Copy vectors.bin → vectors.bin.bak
  2. Copy id-map.json → id-map.json.bak
  3. Log: "Backup created at {timestamp}"
```

### Step 2: Collect All Notes
```
1. Use Glob("**/*.md") to discover all .md files in vault
2. FOR each file found:
   a. Use Read (read_file) to load full file content
   b. Parse frontmatter YAML to extract id (UUID)
   c. Extract: { uuid, title, content_body (strip frontmatter, first 512 chars) }
   d. Skip files without valid id in frontmatter
   e. Store in processing queue
3. Report: "Found {count} notes to embed"
```

### Step 3: Initialize New Store
```
1. Acquire lock: .aiox/refinery/embeddings/vectors.lock
2. Create new empty vectors.bin
3. Create new id-map.json: {}
4. Update model-info.json:
   {
     "model": "all-MiniLM-L6-v2",
     "dims": 384,
     "version": "1.0",
     "rebuilt_at": "{ISO 8601}",
     "rebuild_reason": "{selected reason}",
     "total_vectors": 0
   }
```

### Step 4: Batch Compute Embeddings
```
FOR each note in queue (with progress reporting):
  1. Prepare input: title + " " + content_preview
  2. Compute embedding via @xenova/transformers pipeline('feature-extraction', 'Xenova/all-MiniLM-L6-v2')
  3. Normalize to Float32Array (384 dims)
  4. Append to vectors.bin
  5. Add to id-map.json: { uuid: current_index }
  6. Update model-info.json: total_vectors++

  Progress: [{bar}] {current}/{total} ({pct}%) — ETA: {remaining}ms
```

### Step 5: Verify Store Integrity
```
1. CHECK: vectors.bin size = total_vectors × 384 × 4 bytes
2. CHECK: id-map.json has total_vectors entries
3. CHECK: All UUIDs in id-map exist in uuid-registry
4. IF all checks pass → delete .bak files
5. IF any check fails → restore from .bak, report error
6. Release lock: vectors.lock
```

---

## Post-Conditions
- Shared Embedding Store fully rebuilt with all vault notes.
- `model-info.json` updated with rebuild metadata.
- Backup files removed on success (or restored on failure).
- Lock released.

## Output Summary
```
🏠 Embedding Rebuild Complete
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
✅ Vectors computed: {total}
📐 Dimensions: 384
🧠 Model: all-MiniLM-L6-v2
📦 Store size: {size_mb} MB
⏱️ Time elapsed: {duration}
🔒 Integrity: VERIFIED
```

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level) — Updated 2026-03-12*
