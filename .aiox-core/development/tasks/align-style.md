# Task: Align Style (Style Vault Application)

## Metadata
- **id:** align-style
- **agent:** aiox-talos-miner
- **version:** 2.0
- **elicit:** false
- **description:** Adapts synthesized content to a specific voice profile from the Style Vault. Applies tone, vocabulary, format constraints, and few-shot calibration. Fallback to neutral if no profile selected.

---

## Pre-Conditions
- Synthesis output exists at `.aiox/refinery/outputs/synthesis-{brief-id}.md`.
- Style Vault at `.aiox/refinery/styles/` (optional — fallback to neutral).
- Mining brief with `foco.contexto.style` field.

## Inputs
- `brief_id`: ID of the mining brief.

---

## Execution Steps

### Step 1: Load Style Profile
```
1. Use read_file on mining brief: foco.contexto.style
2. IF style = "neutral" OR style vault is empty:
   a. Set mode = "neutral"
   b. Skip style application, pass synthesis through unchanged
   c. Jump to Step 5
3. ELSE:
   a. Use read_file to load style-registry.yaml
   b. Find profile matching style ID
   c. Use read_file on profile file: .aiox/refinery/styles/{profile-id}.md
   d. Extract: tom, audiencia, formato, max_chars, vocabulary, rules, examples
   e. Set mode = "styled"
```

### Step 2: Load Few-Shot Examples
```
IF profile has examples section:
  1. Parse ![[_examples/{file}]] references
  2. Use read_file on each example file
  3. Store as few_shot_examples[] (ordered by relevance to current output_type)
  4. Report: "Loaded {count} few-shot examples for calibration"
IF no examples:
  Continue without few-shot (rule-based only)
```

### Step 3: Apply Style Rules
```
Use read_file on synthesis content and apply transformations:

1. FORMAT CONSTRAINTS:
   - IF max_chars defined → ensure output fits within limit
   - IF formato defined → restructure to match (e.g., "Hook → Insight → CTA")
   - IF output_type = "post" AND format = "LinkedIn":
     Apply: short paragraphs, line breaks for respiro, emoji sparingly

2. VOCABULARY ALIGNMENT:
   - Replace words in "Evitar" list with equivalents from "Usar" list
   - Preserve technical terms unchanged (never translate jargon)
   - Match tone: commanding → shorter sentences; analytical → longer with qualifiers

3. AUDIENCE CALIBRATION:
   - IF audiencia = "técnico" → keep depth, add specifics
   - IF audiencia = "executivo" → summarize, focus on actions/outcomes
   - IF audiencia = "estudante" → add explanations, simpler vocabulary

4. FEW-SHOT CALIBRATION:
   - Use loaded examples as style reference
   - Match: sentence length, paragraph structure, opening pattern, closing pattern
   - DO NOT copy example content — only emulate style patterns
```

### Step 4: Validate Style Compliance
```
Post-application checks:

1. LENGTH CHECK:
   IF max_chars and content exceeds → trim from lowest-priority section
   IF word limit and content exceeds → condense (never drop source attributions)

2. ATTRIBUTION PRESERVATION:
   CRITICAL: All [¹][²] references MUST survive style transformation
   Check: every [N] in synthesis exists in styled output
   IF any missing → restore from synthesis (attribution is non-negotiable)

3. TONE CHECK:
   Verify opening matches expected pattern (hook for posts, summary for briefings)
   Verify closing matches expected pattern (CTA for posts, recommendations for briefings)
```

### Step 5: Generate Styled Output
```
Write to: .aiox/refinery/outputs/styled-{brief-id}.md

---
id: "{uuid}"
tipo: "styled-output"
mining_brief: "{brief-id}"
style_profile: "{profile-id or neutral}"
output_type: "{type}"
char_count: {count}
word_count: {count}
styled_at: "{ISO-8601}"
---

# {Title — styled for audience}

{STYLED CONTENT WITH PRESERVED [¹][²] ATTRIBUTION}

---

## 📎 Fontes
(preserved from synthesis — identical)

## 🎨 Style Metadata
| Aspect | Applied |
|--------|---------|
| Profile | {profile name or "Neutral"} |
| Tom | {tone} |
| Audiência | {audience} |
| Formato | {format} |
| Char limit | {max_chars or "none"} |
| Char count | {actual} |
| Few-shot examples | {count or 0} |
| Vocabulary swaps | {count} |
```

### Step 6: Update Mining Brief
```
Update brief:
  style_alignment:
    output_path: "styled-{brief-id}.md"
    profile_used: "{id or neutral}"
    char_count: {count}
    attribution_preserved: true
    status: "styled"
```

---

## Post-Conditions
- Styled output in `.aiox/refinery/outputs/`.
- All source attributions preserved through style transformation.
- Format and length constraints respected.
- Mining brief updated with style metadata.

## Output Summary
```
⛏️ Style Alignment Complete
━━━━━━━━━━━━━━━━━━━━━━━━━━
📄 Output: .aiox/refinery/outputs/styled-{brief-id}.md
🎨 Profile: {name or "Neutral"}
📏 Characters: {count}/{max or "unlimited"}
📎 Attribution: ✅ Preserved ({count} references)
➡️ Next: Mining Report (final)
```

---

## CLI-Agnostic Mandate

This task MUST operate without any shell commands (`bash`, `sh`, `cmd`, `powershell`). All operations use native Claude Code tools:

| Operation | Tool | NOT |
|-----------|------|-----|
| Read mining brief | `read_file` | `cat`, `head` |
| Read style registry | `read_file` | `cat` |
| Read style profiles | `read_file` on `.aiox/refinery/styles/{id}.md` | `cat`, shell pipes |
| Read few-shot examples | `read_file` | `cat` |
| Read synthesis output | `read_file` | `cat` |
| Write styled output | `write_file` | `echo >`, shell redirect |
| Update mining brief | `edit_file` | `sed`, `awk` |
| List available profiles | `glob` on `.aiox/refinery/styles/*.md` | `ls`, `find` |

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
*Task created by aiox-master (Orion) on 2026-03-12 for aiox-talos-miner.*
