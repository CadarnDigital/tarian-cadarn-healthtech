# Task: Update MOCs (Sync New Notes)

## Metadata
- **id:** update-mocs
- **agent:** aiox-argos-indexer
- **version:** 2.0
- **elicit:** false
- **description:** Synchronizes all existing MOC Dashboards with newly promoted notes from Vesta. Detects unassociated notes and proposes MOC assignments or new MOC creation.

---

## CLI-Agnostic Mandate

This task MUST be executed using **native Claude Code tools only** — no shell commands:

| Operation | Use | NOT |
|-----------|-----|-----|
| Read files | `read_file` | `cat`, `head`, `tail` |
| Find files | `glob` | `find`, `ls -R` |
| Search content | `grep_search` | `grep`, `rg`, `awk` |
| Batch field extraction | `grep_search("^(status|tipo|area|tema|tags_funcionais|created_at):")` | `grep`, `awk` |
| Write files | `write_file` / `edit_file` | `echo >`, `sed` |

All metadata operations use the **12 canonical frontmatter fields**:
`status`, `tipo`, `area`, `tema`, `palavras_chave`, `fonte_principal`, `curso`, `modulo`, `aula`, `created_at`, `title`, `tags_funcionais`

---

## Pre-Conditions
- Vault exists at `{vault_path}` with MOCs in `8 Sistema/8.10 MOCs/`.
- Cover Notes promoted by Vesta with `created_at` timestamps.

## Inputs
- `vault_path`: Root of the Obsidian vault.

---

## Execution Steps

### Step 1: Discover MOCs & New Notes
```
1. Use glob("8 Sistema/8.10 MOCs/**/*.md") for existing MOC files
2. Use read_file to extract frontmatter; filter where tipo = "map-of-content"
3. Extract MOC topics from tags: "MOC/{topic}" from each MOC's tags_funcionais
4. Build: Map<topic, moc_file_path>
5. Use grep_search("tags_funcionais:") across vault for batch field extraction
6. Identify notes NOT tagged with any MOC topic:
   - Filter: notes where tags_funcionais contains NO "MOC/{anything}"
   - Sort by created_at DESC (newest first)
7. Report: "Found {moc_count} MOCs and {unassociated_count} unassociated notes"
```

### Step 2: Auto-Match Notes to MOCs
```
FOR each unassociated note:
  1. Score against each existing MOC topic:
     a. Title match: note title contains MOC topic → +3
     b. Tag overlap: shared tags between note and MOC's associated notes → +2 per shared tag
     c. Area proximity: same Spira area as majority of MOC's notes → +1
  2. Best match = MOC with highest score
  3. Categorize:
     - score >= 4 → "Auto-assign" (high confidence)
     - score 2-3 → "Suggest" (medium confidence)
     - score < 2 → "Orphan" (no good match)
```

### Step 3: Present Proposals
```
🗺️ MOC Sync Report
━━━━━━━━━━━━━━━━━━

📋 Auto-assignments (high confidence):
  1. [[2.10.05-New-Note]] → MOC/Frameworks (score: 5)
  2. [[7.20.03-Another-Note]] → MOC/Criatividade (score: 4)

📋 Suggestions (review needed):
  3. [[3.10.02-Reflection]] → MOC/Mindset? (score: 3)
  4. [[4.10.01-Career-Plan]] → MOC/Profissional? (score: 2)

📋 Orphans (no matching MOC):
  5. [[5.10.01-Budget-Template]] — No matching MOC found
  6. [[6.10.01-Workout-Plan]] — No matching MOC found

💡 Suggested new MOCs for orphan clusters:
  - "Finanças Pessoais" would cover 3 orphan notes
  - "Saúde & Fitness" would cover 2 orphan notes
```

### Step 4: Apply Auto-Assignments
```
FOR each auto-assigned note:
  1. Read note frontmatter
  2. Add "MOC/{topic}" to tags_funcionais[]
  3. Write updated frontmatter (preserve body)
  4. Log: "{note} → MOC/{topic} (auto, score: {score})"
```

### Step 5: Refresh MOC Queries
```
FOR each MOC that received new notes:
  1. Read MOC file
  2. Update "Tópicos Quentes" section if applicable:
     - Add newly promoted notes that need attention (#refinar, #resumir)
  3. Update "Insights" section if new insights-report exists:
     - Pull relevant connection suggestions for this MOC's topic
  4. Write updated MOC
```

### Step 6: Log Sync
```
Append to .aiox/refinery/moc-sync-log.yaml:
  - timestamp: {ISO-8601}
    mocs_updated: {count}
    notes_assigned: {count_auto}
    notes_suggested: {count_suggest}
    notes_orphaned: {count_orphan}
    new_mocs_suggested: [{topic_list}]
```

---

## Post-Conditions
- Auto-assigned notes tagged with appropriate `MOC/{topic}`.
- Existing MOCs refreshed with new content references.
- Orphan notes identified with suggestions for new MOCs.
- Sync log updated.

## Output Summary
```
🗺️ MOC Sync Complete
━━━━━━━━━━━━━━━━━━━
📊 MOCs scanned: {moc_count}
✅ Auto-assigned: {count_auto} notes
❓ Suggestions: {count_suggest} notes (review needed)
🏝️ Orphans: {count_orphan} notes
💡 New MOCs suggested: {count_new_mocs}
📄 Sync log: .aiox/refinery/moc-sync-log.yaml
```

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
