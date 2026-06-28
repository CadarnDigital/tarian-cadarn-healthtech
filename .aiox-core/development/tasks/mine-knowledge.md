# Task: Mine Knowledge from M2M Files

**Task ID:** mine-knowledge
**Version:** 1.0
**Purpose:** Ler material M2M já processado pelo Echo e extrair inteligência acionável consolidada (DNA-EXTRACT.md) para alimentar agentes-clone
**Orchestrator:** @knowledge-miner (Athena)
**Mode:** Autonomous with elicitation for ambiguity
**Quality Standard:** 7 dimensões de extração completas, zero invenção

---

## Overview

```text
INPUT: Pasta de arquivos M2M (ex: .aiox-core/knowledge/cursos/engaje-mais-venda/)
    ↓
[STEP 1: SCAN] — Inventariar todos os .md na pasta
    ↓
[STEP 2: EXTRACT PER FILE] — Para cada arquivo, extrair as 7 dimensões
    ↓
[STEP 3: CONSOLIDATE] — Fundir extrações por módulo, deduplicar
    ↓
[STEP 4: GENERATE DNA-EXTRACT] — Produzir arquivo final usando template
    ↓
[STEP 5: VALIDATE] — Quality gate (completude, rastreabilidade, zero invenção)
    ↓
OUTPUT: DNA-EXTRACT.md pronto para injeção no agente-clone
```

---

## Inputs

| Parameter | Type | Required | Description | Example |
|-----------|------|----------|-------------|---------|
| `source_path` | string | Yes | Pasta raiz dos arquivos M2M | `.aiox-core/knowledge/cursos/engaje-mais-venda/` |
| `specialist_name` | string | Yes | Nome do especialista | `"Rafael Kiso"` |
| `domain` | string | Yes | Área de expertise | `"Instagram marketing"` |
| `output_path` | string | No | Onde salvar o DNA-EXTRACT (default: `{source_path}/DNA-EXTRACT.md`) | — |
| `focus_filter` | string | No | Filtrar módulos específicos (glob) | `"03-*"` |

---

## Preconditions

- [ ] Pasta `source_path` existe e contém arquivos `.md`
- [ ] Arquivos foram processados pelo Echo (têm frontmatter com `agent_id: aiox-m2m-etl`)
- [ ] Template `dna-extract-tmpl.md` disponível em `.aiox-core/development/templates/`

---

## STEP 1: SCAN — Inventário de Fontes

**Duration:** < 1 minute
**Mode:** Automatic

### Actions

1. Listar recursivamente todos os `.md` em `source_path`
2. Para cada arquivo:
   - Ler frontmatter (source_file, module, course, extraction_quality)
   - Classificar: **aula** (arquivo individual) vs **resumo** (_resumo-modulo-*.md)
   - Contar linhas de conteúdo (excluindo frontmatter)
3. Agrupar por módulo/subpasta
4. Priorizar resumos como fonte primária (têm visão consolidada do módulo)

### Output

```yaml
scan_result:
  total_files: N
  total_lines: N
  modules:
    - name: "01-entendendo-o-instagram"
      files: N
      has_summary: true/false
    - name: "02-setup"
      files: N
      has_summary: true/false
  quality_issues: [] # Arquivos sem frontmatter, vazios, etc.
```

### Veto Conditions

- **VETO:** Pasta vazia ou sem arquivos `.md` → "Nenhum material M2M encontrado em {source_path}"
- **VETO:** Menos de 3 arquivos → "Material insuficiente para extração significativa"

---

## STEP 2: EXTRACT PER FILE — Extração das 7 Dimensões

**Duration:** 2-5 min por módulo
**Mode:** Autonomous

### Actions

Para cada arquivo (priorizando resumos primeiro, depois aulas individuais):

1. Ler o conteúdo completo
2. Extrair as **7 dimensões** abaixo:

#### Dimensão 1: Conceitos-Chave
- Identificar termos definidos explicitamente pelo especialista
- Capturar: **termo**, **definição no contexto**, **quando usar**
- Incluir: jargão técnico, neologismos, redefinições de termos comuns

#### Dimensão 2: Frameworks e Modelos
- Identificar estruturas com etapas sequenciais ou componentes nomeados
- Capturar: **nome**, **propósito**, **etapas**, **quando aplicar**
- Incluir: fórmulas, templates, processos, checklists

#### Dimensão 3: Regras e Princípios
- Identificar afirmações com tom de verdade inegociável
- Marcadores linguísticos: "sempre", "nunca", "obrigatório", "fundamental", "é preciso"
- Capturar: **regra**, **justificativa**, **fonte (módulo/aula)**

#### Dimensão 4: Anti-Patterns
- Identificar o que o especialista condena
- Marcadores: "erro", "nunca faça", "armadilha", "cuidado", "evite"
- Capturar: **erro**, **consequência**, **alternativa correta**

#### Dimensão 5: Táticas Acionáveis
- Identificar instruções DO/DON'T com contexto
- Capturar: **tática**, **tipo (DO/DON'T)**, **quando aplicar**, **detalhe**
- Agrupar por categoria temática

#### Dimensão 6: Métricas e Benchmarks
- Identificar números, porcentagens, ranges, SLAs
- Capturar: **métrica**, **valor**, **contexto**, **fonte**
- REGRA: Só incluir se o especialista cita o número. Nunca inventar.

#### Dimensão 7: Vocabulário Signature
- Termos recorrentes em múltiplos arquivos
- Expressões que definem a voz do especialista
- Termos que o especialista evita ou condena
- Metáforas e analogias frequentes

### Output por módulo

```yaml
module_extraction:
  module: "05-publicacao-de-conteudo"
  files_processed: N
  concepts: [...]
  frameworks: [...]
  rules: [...]
  anti_patterns: [...]
  tactics: [...]
  metrics: [...]
  vocabulary: [...]
```

### Veto Conditions

- **VETO:** Extrair informação não presente no texto fonte → "Artigo IV (No Invention): toda afirmação deve ter rastreabilidade"
- **WARNING:** Módulo com menos de 2 conceitos extraídos → "Módulo pode ter sido processado com qualidade baixa"

---

## STEP 3: CONSOLIDATE — Fusão e Deduplicação

**Duration:** 2-3 minutes
**Mode:** Autonomous

### Actions

1. **Merge:** Combinar extrações de todos os módulos em listas únicas por dimensão
2. **Dedup:** Remover entradas duplicadas ou quase-duplicadas:
   - Conceitos com mesmo nome → manter a definição mais completa
   - Regras semanticamente idênticas → fundir, manter ambas as fontes
   - Táticas redundantes → consolidar em uma entrada
3. **Cross-reference:** Identificar conceitos que aparecem em múltiplos módulos (alta importância)
4. **Rank:** Ordenar por frequência de aparição (mais recorrente = mais importante para o especialista)
5. **Categorize:** Agrupar táticas por categoria temática

### Output

```yaml
consolidated:
  concepts: N (após dedup)
  frameworks: N
  rules: N
  anti_patterns: N
  tactics: N
  metrics: N
  vocabulary_terms: N
  dedup_removals: N
  cross_references: N
```

### Veto Conditions

- **VETO:** Menos de 5 conceitos consolidados → "Extração insuficiente. Revisar material fonte."
- **VETO:** Zero frameworks extraídos → "Especialista sem frameworks identificáveis. Verificar profundidade do material M2M."

---

## STEP 4: GENERATE DNA-EXTRACT — Produzir Output Final

**Duration:** 2-5 minutes
**Mode:** Autonomous

### Actions

1. Carregar template: `.aiox-core/development/templates/dna-extract-tmpl.md`
2. Preencher todas as 7 seções com dados consolidados
3. Preencher metadados de extração (stats)
4. Calcular confidence_score:
   - Base: (dimensões com >= 3 itens) / 7 * 100
   - Bonus: +5% por cross-reference encontrada (max +15%)
   - Penalty: -10% por dimensão vazia
5. Salvar em `output_path` (default: `{source_path}/DNA-EXTRACT.md`)

### Output

```yaml
dna_extract:
  file: "{output_path}/DNA-EXTRACT.md"
  lines: N
  confidence_score: "N%"
  sections_complete: "N/7"
```

### Veto Conditions

- **VETO:** confidence_score < 50% → "Extração com confiança baixa. Revisar material fonte antes de usar para criar agente."

---

## STEP 5: VALIDATE — Quality Gate

**Duration:** 1-2 minutes
**Mode:** Autonomous

### Checks

| # | Check | Critério | Blocking |
|---|-------|----------|----------|
| 1 | Completude | Todas as 7 seções preenchidas | YES |
| 2 | Rastreabilidade | Cada regra/framework tem campo "Fonte" | YES |
| 3 | Zero invenção | Nenhum dado sem correspondência no material | YES |
| 4 | Volume mínimo | >= 5 conceitos, >= 2 frameworks, >= 5 regras | YES |
| 5 | Vocabulário | >= 5 termos signature identificados | NO (warning) |
| 6 | Métricas | >= 1 benchmark citado | NO (warning) |
| 7 | Formato | Segue template dna-extract-tmpl.md | YES |

### Decision

```text
IF all blocking pass:
    → PASS — DNA-EXTRACT pronto para uso
ELSE:
    → FAIL — Listar gaps e sugerir ações
    → Opções: (1) Corrigir agora, (2) Salvar como draft, (3) Abortar
```

### Final Presentation

```yaml
summary:
  specialist: "{specialist_name}"
  domain: "{domain}"
  source: "{source_path}"
  output: "{output_path}/DNA-EXTRACT.md"
  stats:
    files_processed: N
    concepts: N
    frameworks: N
    rules: N
    anti_patterns: N
    tactics: N
    metrics: N
    vocabulary_terms: N
  confidence: "N%"
  verdict: "PASS | FAIL"
  next_steps:
    - "Usar DNA-EXTRACT como input para Squad Creator (*create-squad)"
    - "Ou injetar diretamente em agente-clone existente"
```

---

## Error Handling

```yaml
error_handling:
  empty_folder:
    action: "Informar e sugerir rodar Echo (M2M-ETL) primeiro"

  no_frontmatter:
    action: "WARNING — processar mesmo assim, mas marcar confidence como lower"

  file_too_large:
    threshold: 5000 lines
    action: "Processar em chunks de 2000 linhas, consolidar depois"

  ambiguous_extraction:
    action: "Elicitar usuário — apresentar trecho e perguntar classificação"
```

---

## Integration with AIOX Pipeline

```text
Fonte Bruta (PDF, DOCX, vídeo)
    ↓
Echo (M2M-ETL) — *convert
    ↓
Arquivos M2M (.md com frontmatter)
    ↓
Athena (Knowledge Miner) — *mine    ← ESTA TASK
    ↓
DNA-EXTRACT.md
    ↓
Squad Creator — *create-squad / *create agent
    ↓
Agente-Clone operacional
```

---

_Task Version: 1.0_
_Created: 2026-03-20_
_Philosophy: "Não inventar — minerar. O especialista já disse tudo; nosso trabalho é organizar."_
