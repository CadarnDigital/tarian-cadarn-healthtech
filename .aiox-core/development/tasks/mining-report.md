# Task: Mining Report (Final Deliverable)

## Metadata
- **id:** mining-report
- **agent:** aiox-talos-miner
- **version:** 2.0
- **elicit:** false
- **description:** Generates the final mining report consolidating the styled output, source list, gap analysis, pipeline metrics, and reproducibility data. This is the deliverable Cadarn receives.

---

## Pre-Conditions
- All previous pipeline phases complete (FOCO → Mining → Assembly → Synthesis → Style).
- Mining brief with all phase metadata.
- Styled output at `.aiox/refinery/outputs/styled-{brief-id}.md`.

## Inputs
- `brief_id`: ID of the mining brief.

---

## Execution Steps

### Step 1: Collect Pipeline Data
```
1. Use read_file on mining-brief-{brief-id}.yaml (all phases)
2. Use read_file on styled-{brief-id}.md (final output)
3. Use read_file on synthesis-{brief-id}.md (gaps, attribution metrics)
4. Use read_file on context-package-{brief-id}.md (assembly metadata)
5. Compile: full pipeline trace from FOCO to final output
```

### Step 2: Calculate Pipeline Metrics
```
metrics:
  pipeline:
    total_phases: 6
    phases_completed: {count}
    total_duration: "{sum of all phase durations}"
  search:
    embeddings_searched: {count}
    candidates_found: {count}
    candidates_after_filter: {count}
  assembly:
    sources_selected: {count}
    token_budget: {total}
    tokens_used: {used}
    budget_efficiency: "{used/total × 100}%"
    avg_relevance: {score}
    diversity_score: {metric}
  synthesis:
    sources_cited: {count}
    sources_available: {count}
    citation_rate: "{cited/available × 100}%"
    attributed_claims: {count}
    inferences: {count}
    attribution_rate: "{attr/(attr+inf) × 100}%"
  style:
    profile: "{name or neutral}"
    char_count: {count}
    format_compliance: "✅ or ❌"
  gaps:
    total: {count}
    critical: {count}
    moderate: {count}
    minor: {count}
  metadata_coverage:
    total_notes_scanned: {count}
    fields_analyzed: 12
    coverage_per_field:
      uuid: "{pct}%"
      aliases: "{pct}%"
      tags_funcionais: "{pct}%"
      tipo: "{pct}%"
      status: "{pct}%"
      criado_em: "{pct}%"
      atualizado_em: "{pct}%"
      tema: "{pct}%"
      curso: "{pct}%"
      fonte_principal: "{pct}%"
      asset_original: "{pct}%"
      publish: "{pct}%"
    fully_populated_notes: {count}  # notes with all 12 fields filled
    fully_populated_rate: "{pct}%"
    avg_fields_per_note: {avg}  # out of 12
```

### Step 3: Generate Final Report
```
Write to: .aiox/refinery/reports/mining-report-{brief-id}.md

---
id: "{uuid}"
tipo: "mining-report"
mining_brief: "{brief-id}"
output_type: "{type}"
total_sources: {count}
gaps_detected: {count}
delivered_at: "{ISO-8601}"
tags_funcionais: ["Talos", "Report", "Mining"]
---

# ⛏️ Mining Report — {query_title}

> [!SUCCESS] Entrega do Talos
> Output tipo: **{output_type}** | Fontes: **{cited}** | Gaps: **{gap_count}**

---

## 📝 Output Final

{FULL STYLED CONTENT — ready to use}

---

## 📎 Fontes Consultadas

### Citadas Diretamente
| # | Nota | Área | Status | Relevância |
|---|------|------|--------|-----------|
| [¹] | [[{title}]] | {area} | {status} | {score} |
| [²] | [[{title}]] | {area} | {status} | {score} |

### No Contexto (não citadas)
| Nota | Razão da não-citação |
|------|---------------------|
| [[{title}]] | Conteúdo redundante com [¹] |

---

## 🕳️ Gaps de Conhecimento

| # | Subtópico Ausente | Severidade | Impacto no Output | Próximo Passo |
|---|-------------------|-----------|-------------------|---------------|
| 1 | {subtopic} | 🔴 CRITICAL | {impact} | {suggestion} |
| 2 | {subtopic} | 🟡 MODERATE | {impact} | {suggestion} |
| 3 | {subtopic} | 🔵 MINOR | {impact} | {suggestion} |

---

## 📊 Métricas do Pipeline

### Busca & Seleção
| Métrica | Valor |
|---------|-------|
| Embeddings pesquisados | {count} |
| Candidatos encontrados | {count} |
| Token budget | {used}/{total} ({pct}%) |
| Relevância média | {score} |
| Diversidade | {metric} |

### Qualidade da Síntese
| Métrica | Valor |
|---------|-------|
| Fontes citadas / disponíveis | {cited}/{available} ({rate}%) |
| Afirmações atribuídas | {count} |
| Inferências [?] | {count} |
| Taxa de atribuição | {rate}% |
| Compliance Article IV | {✅ if inf=0, ⚠️ if inf>0} |

### Estilo
| Métrica | Valor |
|---------|-------|
| Perfil de voz | {name or Neutro} |
| Caracteres | {count}/{max or "∞"} |
| Formato | {compliance ✅/❌} |

### Cobertura de Metadados (12 Campos Canônicos)
| Campo | Preenchido | Cobertura |
|-------|-----------|-----------|
| uuid | {count}/{total} | {pct}% |
| aliases | {count}/{total} | {pct}% |
| tags_funcionais | {count}/{total} | {pct}% |
| tipo | {count}/{total} | {pct}% |
| status | {count}/{total} | {pct}% |
| criado_em | {count}/{total} | {pct}% |
| atualizado_em | {count}/{total} | {pct}% |
| tema | {count}/{total} | {pct}% |
| curso | {count}/{total} | {pct}% |
| fonte_principal | {count}/{total} | {pct}% |
| asset_original | {count}/{total} | {pct}% |
| publish | {count}/{total} | {pct}% |

| Resumo | Valor |
|--------|-------|
| Notas com 12/12 campos | {count} ({pct}%) |
| Media de campos por nota | {avg}/12 |

---

## 🔄 Reprodutibilidade

Para reproduzir este mining:
```
*mine "{query}" --style {profile} --budget {tokens}
```

Artefatos do pipeline:
- Brief: `.aiox/refinery/mining-briefs/mining-brief-{id}.yaml`
- Context: `.aiox/refinery/context-packages/context-package-{id}.md`
- Synthesis: `.aiox/refinery/outputs/synthesis-{id}.md`
- Styled: `.aiox/refinery/outputs/styled-{id}.md`
- Report: `.aiox/refinery/reports/mining-report-{id}.md`

---
*Relatório gerado por Talos (aiox-talos-miner) em {date}.*
```

### Step 4: Log Mining Session
```
Append to .aiox/refinery/mining-log.yaml:
  - session_id: "{brief-id}"
    timestamp: "{ISO-8601}"
    query: "{search_query}"
    output_type: "{type}"
    style: "{profile or neutral}"
    sources_cited: {count}
    gaps_detected: {count}
    attribution_rate: "{rate}%"
    report_path: "reports/mining-report-{brief-id}.md"
```

### Step 5: Present to Cadarn
```
⛏️ Mining Complete — Entrega para Cadarn
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📄 Relatório: .aiox/refinery/reports/mining-report-{brief-id}.md

📝 Output: {output_type} sobre "{query}"
📎 Fontes: {cited} notas citadas
🕳️ Gaps: {count} ({critical} críticos)
📊 Atribuição: {rate}%
🎨 Estilo: {profile or "Neutro"}

O output final está pronto para uso no relatório acima.
Deseja refinar algo? [*mine refinement / *gaps / done]
```

---

## Post-Conditions
- Final mining report in `.aiox/refinery/reports/`.
- Session logged to mining-log.yaml for history and reproducibility.
- All pipeline artifacts preserved for audit trail.
- Cadarn has actionable output ready to use.

---

## CLI-Agnostic Mandate

This task MUST operate without any shell commands (`bash`, `sh`, `cmd`, `powershell`). All operations use native Claude Code tools:

| Operation | Tool | NOT |
|-----------|------|-----|
| Read mining brief | `read_file` | `cat`, `head` |
| Read pipeline outputs | `read_file` | `cat` |
| Read vault notes (for metadata coverage) | `read_file` | `cat`, `head` |
| Find all vault notes | `glob` | `find`, `ls` |
| Write final report | `write_file` | `echo >`, shell redirect |
| Append to mining log | `edit_file` | `echo >>`, shell append |
| Count metadata fields | `read_file` + parse frontmatter | `grep -c`, `wc` |

**12 Canonical Metadata Fields** (coverage stats):
`uuid`, `aliases`, `tags_funcionais`, `tipo`, `status`, `criado_em`, `atualizado_em`, `tema`, `curso`, `fonte_principal`, `asset_original`, `publish`

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
*Task created by aiox-master (Orion) on 2026-03-12 for aiox-talos-miner.*
