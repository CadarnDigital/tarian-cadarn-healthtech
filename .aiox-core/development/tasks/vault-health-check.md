# Task: Vault Health Check

## Metadata
- **id:** vault-health-check
- **agent:** aiox-vesta-custodian
- **version:** 2.0
- **elicit:** false
- **description:** Comprehensive integrity validation of the Obsidian vault — checks broken links, orphan UUIDs, checksum mismatches, missing assets, and Modelo Spira compliance.

---

## Pre-Conditions
- Vault exists at `{vault_path}`.
- UUID registry exists at `.aiox/refinery/uuid-registry.yaml`.

## Inputs
- `vault_path`: Root of the Obsidian vault.

## CLI-Agnostic Mandate

> **NON-NEGOTIABLE:** This task MUST execute using only native Claude Code tools.
> - Use `Glob("**/*.md")` to discover all vault notes — NEVER shell commands (`find`, `ls`, `dir`).
> - Use `Read` (read_file) to inspect frontmatter and content — NEVER `cat`, `head`, or `grep` in Bash.
> - Use `Glob` for asset existence checks — NEVER `test -f` or `[[ -e ]]`.
> - All integrity checks are performed by parsing read_file output in-memory.
> This ensures cross-platform compatibility (Windows, macOS, Linux) without shell dependencies.

---

## Execution Steps

### Step 1: UUID Integrity
```
1. Load uuid-registry.yaml
2. FOR each entry in registry:
   a. CHECK: File exists at entry.path → OK / ORPHAN_UUID (registry points to missing file)
   b. CHECK: File at path has matching id in frontmatter → OK / UUID_MISMATCH
   c. CHECK: No duplicate UUIDs in registry → OK / DUPLICATE_UUID
3. FOR each .md file in vault:
   a. CHECK: File has id in frontmatter → OK / NO_UUID
   b. CHECK: id exists in registry → OK / UNREGISTERED_NOTE
```

### Step 2: Checksum Integrity
```
FOR each note with checksum in frontmatter:
  1. Calculate SHA-256 of current content body
  2. Compare with stored checksum
  3. IF mismatch → flag CHECKSUM_DRIFT (note was edited since promotion)
  NOTE: Checksum drift is INFORMATIONAL, not an error — it means the user refined the note.
```

### Step 3: Asset Integrity (CADARN-6)
```
FOR each note with asset_original in frontmatter:
  1. Parse asset path from embed: ![[_assets/file.pdf]] or [[_assets/file.pdf]]
  2. CHECK: Asset file exists at expected path → OK / MISSING_ASSET
  3. CHECK: Asset file size matches expected (if logged) → OK / SIZE_MISMATCH
  4. FOR each file in _assets/ folders:
     a. CHECK: File is referenced by at least one note → OK / ORPHAN_ASSET
```

### Step 4: Link Integrity
```
FOR each note:
  1. Extract all wikilinks: [[target]]
  2. FOR each link:
     a. CHECK: Target note exists in vault → OK / BROKEN_LINK
     b. CHECK: If link uses UUID-based alias, UUID resolves → OK / BROKEN_UUID_LINK
```

### Step 5: Modelo Spira Compliance
```
1. CHECK: All 8 areas exist as top-level folders → OK / MISSING_AREA
2. CHECK: Each area has .00 Inbox/ → OK / MISSING_INBOX
3. CHECK: Each area has .99 Arquivo/ → OK / MISSING_ARCHIVE
4. CHECK: JD subcategory naming follows pattern {n}.{dezena} → OK / BAD_JD_NAMING
5. CHECK: _assets/ exists in each subcategory with notes → OK / MISSING_ASSETS_FOLDER
6. CHECK: No notes exist at vault root (all should be in areas) → OK / ROOT_NOTES
```

### Step 6: 12-Field Metadata Completeness
```
12 canonical fields: id, title, tipo, status, tags_funcionais, criado_em,
                     atualizado_em, area, origin, asset_original, checksum, aliases

FOR each note (using Read/read_file to parse frontmatter):
  1. Count how many of the 12 fields are present and non-empty
  2. Classify:
     - COMPLETE: All 12 fields present (conditional fields counted as present if N/A)
     - PARTIAL: 8-11 fields present
     - INCOMPLETE: < 8 fields present
  3. Track which fields are most commonly missing

Report:
  12-Field Completeness:
    COMPLETE:   {count} ({pct}%)
    PARTIAL:    {count} ({pct}%)
    INCOMPLETE: {count} ({pct}%)
    Most missing: {field} ({count} notes)
```

### Step 7: Embedding Store Integrity
```
1. Load id-map.json
2. CHECK: All UUIDs in id-map exist in uuid-registry → OK / ORPHAN_EMBEDDING
3. CHECK: vectors.bin size = entries_count × 384 × 4 bytes → OK / SIZE_MISMATCH
4. CHECK: All registered notes have an embedding → OK / MISSING_EMBEDDING
```

### Step 8: Generate Health Report
```
🏠 Vault Health Report
━━━━━━━━━━━━━━━━━━━━━
📅 Date: {YYYY-MM-DD HH:mm}
📁 Vault: {vault_path}

✅ PASSED                          ❌ ISSUES
━━━━━━━━                          ━━━━━━━━
UUID Integrity: {pass/fail}        Orphan UUIDs: {count}
Checksum: {pass/info}              Checksum Drift: {count} (informational)
Assets: {pass/fail}                Missing Assets: {count}
                                   Orphan Assets: {count}
Links: {pass/fail}                 Broken Links: {count}
Spira Structure: {pass/fail}       Structure Issues: {count}
Metadata: {pass/fail}               Incomplete Notes: {count}
Embeddings: {pass/fail}            Missing Embeddings: {count}

📊 12-Field Completeness:
  COMPLETE:   {count} ({pct}%)
  PARTIAL:    {count} ({pct}%)
  INCOMPLETE: {count} ({pct}%)

📊 Vault Stats:
  Total notes: {count}
  Total assets: {count}
  Registry entries: {count}
  Embeddings: {count}

🔧 Recommended Actions:
  - {action 1 based on issues found}
  - {action 2}
```

---

## Post-Conditions
- Health report generated (displayed to user).
- No files modified (this task is read-only diagnostic).
- Issues logged to `.aiox/refinery/health-report-{date}.yaml` for tracking.

## Severity Levels
| Level | Issues | Action |
|-------|--------|--------|
| **CRITICAL** | DUPLICATE_UUID, UUID_MISMATCH | Must fix before next promotion |
| **WARNING** | MISSING_ASSET, BROKEN_LINK, ORPHAN_UUID | Should fix soon |
| **WARNING** | INCOMPLETE_METADATA (< 8 fields) | Should fix soon |
| **INFO** | CHECKSUM_DRIFT, ORPHAN_ASSET, MISSING_EMBEDDING, PARTIAL_METADATA | Optional cleanup |

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level) — Updated 2026-03-12*
