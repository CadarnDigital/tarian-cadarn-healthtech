# Task: Synthesize Material (with Source Attribution)

## Metadata
- **id:** synthesize-material
- **agent:** aiox-talos-miner
- **version:** 2.0
- **elicit:** false
- **description:** Generates synthesized content from the assembled context package. Every claim traces to source notes via [¹][²] attribution. Detects knowledge gaps. Respects Article IV (No Invention).

---

## Pre-Conditions
- Context package exists at `.aiox/refinery/context-packages/context-package-{brief-id}.md`.
- Mining brief with FOCO parameters (output_type, search_query).

## Inputs
- `brief_id`: ID of the mining brief.

---

## Execution Steps

### Step 1: Load Context & Brief
```
1. Use read_file on context-package-{brief-id}.md
2. Use read_file on mining-brief-{brief-id}.yaml
3. Extract: output_type, output_subtype, expected_length, search_query
4. Load all source contents from context package
5. Build source index: Map<source_number, { uuid, title, path, sections[] }>
```

### Step 1b: Detect Vesta Template Compatibility
```
Check if the output_type maps to one of Vesta's 4 real templates:

| Vesta Template | Matches output_type | Template Structure |
|----------------|--------------------|--------------------|
| Nota Rapida    | MIND MAP, quick notes | H1 + TL;DR callout + body (short) |
| Resumo Livro   | BRIEFING, ARTICLE (from books) | H1 + TL;DR + Conceitos Chave + Citacoes + Reflexao |
| Diario          | Personal reflections | H1 + date + free-form journaling |
| Processar       | Raw captures to process | H1 + TL;DR + raw content + action items |

IF output matches a Vesta template:
  1. Use read_file to load the matching template from vault templates folder
  2. Set vesta_template = matched template name
  3. Adapt synthesis structure to follow template format
  4. Report: "Vesta template detected: {template_name}"
ELSE:
  Continue with generic FOCO-based structure below
```

### Step 2: Structure Output by Type
```
Based on output_type from FOCO:

POST (social media):
  structure = "Hook → Core Insight → Supporting Points → CTA"
  max_length = type-specific (LinkedIn: 1300 chars, Twitter: 280, etc.)

COURSE MODULE:
  structure = "Learning Objective → Theory → Examples → Practice Exercise → Summary"
  max_length = 2000-5000 words

ARTICLE:
  structure = "Hook/Intro → Context → Main Arguments → Counterpoints → Conclusion"
  max_length = subtype-specific (500-3000 words)

BRIEFING:
  structure = "Executive Summary → Key Findings → Analysis → Recommendations"
  max_length = 500-1000 words

MIND MAP:
  structure = "Central Theme → Branch 1 (+ sub-branches) → Branch 2 → ..."
  format = hierarchical bullet points with links
```

### Step 3: Synthesize with Attribution
```
FOR each section of the output structure:
  1. Identify which source notes are relevant to this section
  2. Synthesize content by:
     a. Extracting key ideas from relevant sources
     b. Paraphrasing in Cadarn's context (not copy-paste)
     c. Adding [N] reference after each claim:
        - Single source: "Zettelkasten propõe conexões atômicas. [¹]"
        - Multiple sources: "A escrita atômica melhora a retenção. [²][³]"
        - Direct quote: "> 'A nota é a unidade fundamental.' [¹]"
     d. IF a statement cannot be attributed to any source:
        - Mark as: "Inferência baseada em múltiplas fontes. [?]"
        - Flag in metadata: unattributed_count++
  3. Track: which sources were actually cited vs. only included in context
```

### Step 4: Gap Detection
```
1. From search_query, derive expected subtopics:
   - Use LLM reasoning: "For a comprehensive treatment of '{query}', these subtopics are expected: ..."
   - Generate list of 5-10 expected subtopics
2. FOR each expected subtopic:
   a. Check: was it covered by any source in the context package?
   b. Check: does any source mention it even tangentially?
   c. IF not covered at all:
      Record gap: { subtopic, severity, suggestion }
      Severity:
        CRITICAL → Core to the query, output is incomplete without it
        MODERATE → Adds depth, output still viable
        MINOR → Nice-to-have, tangential
3. Store gaps for mining report
```

### Step 5: Generate Synthesis Output
```
Write to: .aiox/refinery/outputs/synthesis-{brief-id}.md

---
id: "{uuid}"
tipo: "synthesis"
mining_brief: "{brief-id}"
output_type: "{type}"
sources_cited: {count}
sources_available: {total in context}
unattributed: {count of [?] marks}
gaps_detected: {count}
synthesized_at: "{ISO-8601}"
---

# {Generated Title based on query + output_type}

{SYNTHESIZED CONTENT WITH [¹][²] ATTRIBUTION}

---

## 📎 Fontes
[¹] [[{title_1}]] — §{section}, ¶{paragraph}
[²] [[{title_2}]] — §{section}
[³] [[{title_3}]] — §TL;DR
...

## 🕳️ Gaps Detectados
| # | Subtópico Ausente | Severidade | Sugestão |
|---|-------------------|-----------|----------|
| 1 | {subtopic} | {CRITICAL/MODERATE/MINOR} | {suggestion} |

## 📊 Métricas de Síntese
| Métrica | Valor |
|---------|-------|
| Fontes no contexto | {total} |
| Fontes citadas | {cited} |
| Taxa de citação | {cited/total × 100}% |
| Afirmações atribuídas | {attributed} |
| Inferências [?] | {unattributed} |
| Taxa de atribuição | {attributed/(attributed+unattributed) × 100}% |
| Gaps detectados | {count} (CRITICAL: {c}, MODERATE: {m}, MINOR: {mi}) |
```

### Step 6: Update Mining Brief
```
Update brief:
  synthesis:
    output_path: "synthesis-{brief-id}.md"
    sources_cited: {count}
    unattributed: {count}
    gaps: [{gap list}]
    status: "synthesized"
```

---

## Post-Conditions
- Synthesis output in `.aiox/refinery/outputs/`.
- Every claim attributed to source notes or flagged as [?] inference.
- Knowledge gaps identified with severity and suggestions.
- Mining brief updated with synthesis metadata.

## Output Summary
```
⛏️ Synthesis Complete
━━━━━━━━━━━━━━━━━━━━
📄 Output: .aiox/refinery/outputs/synthesis-{brief-id}.md
📎 Sources cited: {cited}/{available}
⚠️ Inferences [?]: {count}
🕳️ Gaps: {count} (CRITICAL: {c})
➡️ Next: Style Alignment
```

---

## CLI-Agnostic Mandate

This task MUST operate without any shell commands (`bash`, `sh`, `cmd`, `powershell`). All operations use native Claude Code tools:

| Operation | Tool | NOT |
|-----------|------|-----|
| Read context package | `read_file` | `cat`, `head` |
| Read mining brief | `read_file` | `cat` |
| Read Vesta templates | `read_file` | `cat` |
| Write synthesis output | `write_file` | `echo >`, shell redirect |
| Update mining brief | `edit_file` | `sed`, `awk` |
| Search source content | `grep_search` | `grep`, `rg` |

**Vesta Template Awareness:**
When the output type maps to one of Vesta's 4 templates (Nota Rapida, Resumo Livro, Diario, Processar), the synthesis MUST follow that template's structure to ensure vault consistency.

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
*Task created by aiox-master (Orion) on 2026-03-12 for aiox-talos-miner.*
