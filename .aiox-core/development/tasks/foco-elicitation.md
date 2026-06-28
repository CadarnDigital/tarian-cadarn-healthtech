# Task: FOCO Elicitation Protocol

## Metadata
- **id:** foco-elicitation
- **agent:** aiox-talos-miner
- **version:** 2.0
- **elicit:** true
- **description:** Executes the FOCO Protocol (Finalidade, Objeto, Contexto) — 3 structured questions that ensure Talos understands exactly what Cadarn wants before mining begins. Produces a mining-brief.yaml.

---

## Pre-Conditions
- User has a mining objective in mind.
- Vault exists with promoted Cover Notes (for Q3 autocomplete).
- Style Vault at `.aiox/refinery/styles/` (for Q3 style selection).

## Inputs
- None required — this task IS the input gathering phase.

---

## Execution Steps

### Step 1: Q1 — Finalidade (Output Type)
```
⛏️ PROTOCOLO FOCO — Fase 1/3

🎯 Q1: Qual é o RESULTADO FINAL que você quer?

1. 📱 Post para rede social
   └─ a) LinkedIn  b) Instagram  c) Twitter/X  d) Genérico
2. 📚 Material de curso
   └─ a) Módulo completo  b) Aula única  c) Exercícios  d) Slide deck
3. 📝 Artigo / Blog post
   └─ a) Curto (500-800 palavras)  b) Longo (1500-3000 palavras)  c) Newsletter
4. 📋 Briefing executivo
   └─ a) Resumo de tema  b) Comparativo  c) Análise de decisão
5. 🧠 Mapa mental / Resumo de estudo
6. 🎯 Outro: (descreva)

Select [1-6] + sub-option (e.g., "1a" for LinkedIn post):
```

**Capture:** `output_type`, `output_subtype`, `expected_length`

### Step 2: Q2 — Objeto (Search Query)
```
⛏️ PROTOCOLO FOCO — Fase 2/3

🔍 Q2: Sobre O QUÊ exatamente?

Descreva o tema, conceito ou pergunta que você quer minerar.
Pode usar palavras-chave ou uma frase completa.

> Exemplos:
> - "Zettelkasten e seus benefícios para criadores de conteúdo"
> - "Comparação entre PARA e Johnny Decimal"
> - "Como usar Progressive Summarization"

Seu tema:
```

**Capture:** `search_query` (free text)

**Post-processing:**
```
1. Extract key terms from search_query
2. If vault has existing tags matching key terms, suggest:
   "🏷️ Tags relacionadas encontradas no vault: #zettelkasten, #produtividade, #notas-atômicas"
   "Incluir notas com essas tags na busca? [Y/n]"
3. Store: search_terms[], tag_filters[]
```

### Step 3: Q3 — Contexto (Scope & Style)
```
⛏️ PROTOCOLO FOCO — Fase 3/3

📚 Q3: ONDE procurar e com qual VOZ?

Escopo de busca:
1. 🌐 Todo o vault (busca ampla)
2. 📂 Área específica:
   └─ 1.Projetos  2.Biblioteca  3.Pessoal  4.Profissional
      5.Finanças   6.Saúde      7.Criatividade  8.Sistema
3. 🗺️ MOC específico: {lista de MOCs existentes}
4. 🤖 Deixe o Talos decidir (busca inteligente)

Filtros de metadados (opcional — baseados nos 12 campos canônicos):
5. 📖 Filtrar por curso: {lista de valores únicos do campo `curso`}
6. 🎯 Filtrar por tema: {lista de valores únicos do campo `tema`}
7. 📚 Filtrar por fonte_principal: {lista de valores únicos do campo `fonte_principal`}

Estilo de voz:
A. {lista de perfis do Style Vault}
B. 🎤 Tom neutro (sem perfil)

Select scope [1-4], optional filters [5-7], and style [A-B or profile name]:
```

**Capture:** `source_scope`, `area_filter`, `moc_filter`, `curso_filter`, `tema_filter`, `fonte_principal_filter`, `style_profile`

**Metadata filter discovery (via native tools):**
```
1. Use read_file to load uuid-registry.yaml
2. Use glob to list all Cover Notes in vault
3. For each Cover Note, read frontmatter and extract unique values for:
   - curso, tema, fonte_principal
4. Present unique values as selectable options in Q3
5. Store selected filters in mining brief
```

### Step 4: Confirm & Generate Brief
```
⛏️ PROTOCOLO FOCO — Confirmação

📋 Mining Brief:
━━━━━━━━━━━━━━━
🎯 Finalidade: {output_type} — {output_subtype}
🔍 Objeto: "{search_query}"
🏷️ Tags: {tag_filters or "auto-detect"}
📚 Escopo: {scope_description}
🎤 Estilo: {style_profile or "neutro"}
💰 Token budget: {default 8000}
📊 Max sources: {default 20}

Confirmar e iniciar mineração? [Y/n/edit]
```

### Step 5: Save Mining Brief
```
Write to: .aiox/refinery/mining-briefs/mining-brief-{timestamp}.yaml

mining_brief:
  id: "{uuid}"
  timestamp: "{ISO-8601}"
  foco:
    finalidade:
      type: "{output_type}"
      subtype: "{output_subtype}"
      expected_length: "{chars or words}"
    objeto:
      query: "{search_query}"
      terms: [{extracted terms}]
      tag_filters: [{tag list}]
    contexto:
      scope: "{vault-wide|area-N|moc-name}"
      area: {N or null}
      moc: "{moc-name or null}"
      curso: "{curso filter or null}"
      tema: "{tema filter or null}"
      fonte_principal: "{fonte_principal filter or null}"
      style: "{profile-id or neutral}"
  config:
    token_budget: 8000
    max_sources: 20
    min_relevance: 0.6
  status: "ready"
```

---

## Post-Conditions
- `mining-brief-{timestamp}.yaml` saved to `.aiox/refinery/mining-briefs/`.
- Brief status is "ready" — can be consumed by `semantic-mining` task.
- User has confirmed all 3 FOCO dimensions.

## Output Summary
```
⛏️ FOCO Complete
━━━━━━━━━━━━━━━
📄 Brief: .aiox/refinery/mining-briefs/mining-brief-{timestamp}.yaml
🎯 Type: {output_type}
🔍 Query: "{search_query}"
📚 Scope: {scope}
🎤 Style: {style}
➡️ Next: Run *mine to continue pipeline, or *assemble to skip to context assembly
```

---

## CLI-Agnostic Mandate

This task MUST operate without any shell commands (`bash`, `sh`, `cmd`, `powershell`). All operations use native Claude Code tools:

| Operation | Tool | NOT |
|-----------|------|-----|
| Read mining briefs | `read_file` | `cat`, `head` |
| Find vault notes | `glob` | `find`, `ls` |
| Search note content | `grep_search` | `grep`, `rg` |
| Write mining brief | `write_file` / `edit_file` | `echo >`, `sed` |
| List style profiles | `glob` on `.aiox/refinery/styles/` | `ls` |
| Extract metadata filter values | `read_file` + parse frontmatter | shell pipes |

**12 Canonical Metadata Fields** (referenced in Q3 filters):
`uuid`, `aliases`, `tags_funcionais`, `tipo`, `status`, `criado_em`, `atualizado_em`, `tema`, `curso`, `fonte_principal`, `asset_original`, `publish`

---
*v2.0: CLI-Agnostic + 12-Field Metadata (Black Level)*
*Task created by aiox-master (Orion) on 2026-03-12 for aiox-talos-miner.*
