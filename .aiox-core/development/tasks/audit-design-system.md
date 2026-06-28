# Audit Design System Task

## Purpose

Executar auditoria profunda de Design System em projetos frontend (React/Next.js), combinando análise compacta (quick) e abrangente (full) com evidências rastreáveis no código. Tudo baseado em boas práticas 2025: Tailwind CSS v3/v4, shadcn/ui, WCAG 2.2, APCA, W3C Design Tokens DTCG, OKLCH e Core Web Vitals.

---

## Execution Modes

**Escolha o modo de execução:**

### 1. Quick Mode (`--quick`) - Auditoria Compacta (1 output)
- Descoberta + auditoria em passagem única
- Output condensado: Resumo Executivo + Diagnóstico + Quick Wins
- **Melhor para:** Avaliação rápida, projetos pequenos, check periódico

### 2. Full Mode (default) - Auditoria Profunda (5 fases)
- Processo completo em 5 fases com documentação detalhada
- Output estruturado em 9 seções com DS_Score calculado
- **Melhor para:** Projetos novos, antes de refactors grandes, auditorias formais

**Usage:**
```
*audit-ds                    # Full mode (default)
*audit-ds --quick            # Quick mode
*audit-ds --quick {package}  # Quick mode em package específico
*audit-ds {package}          # Full mode em package específico
```

---

## Task Definition (AIOX Task Format V1.0)

```yaml
task: auditDesignSystem()
responsável: Cosmo (Design System Architect)
responsavel_type: Agente
atomic_layer: Organism

**Entrada:**
- campo: mode
  tipo: string
  origem: User Input
  obrigatório: false
  validação: quick|full
  default: full

- campo: package
  tipo: string
  origem: User Input
  obrigatório: false
  validação: Valid package path in packages/
  default: auto-detect

- campo: brand_guidelines
  tipo: file_path
  origem: Context / Brand Guardian
  obrigatório: false
  validação: Path to brand guidelines (Primal Code)
  default: null

**Saída:**
- campo: audit_report
  tipo: markdown
  destino: docs/audits/ds-audit-{package}-{date}.md
  persistido: true

- campo: ds_score
  tipo: object
  destino: Inline no report
  persistido: true

- campo: action_plan
  tipo: markdown
  destino: Inline no report
  persistido: true
```

---

## Constitutional Gates

### Gate: No Invention (Article IV)

```yaml
constitutional_gate:
  article: IV
  name: No Invention — Evidence-Based Audit
  severity: BLOCK

  validation:
    - Toda afirmação DEVE apontar evidência no código (arquivo + símbolo + localização)
    - NUNCA inventar arquivos, rotas, APIs, dependências ou versões
    - Se não encontrar algo, dizer explicitamente "não encontrado no repo"
    - Marcar claramente: "encontrado" vs "inferido" vs "recomendado"

  on_violation:
    action: BLOCK
    message: |
      CONSTITUTIONAL VIOLATION: Article IV - No Invention
      Auditoria deve ser 100% baseada em evidências do código real.
      Nenhuma afirmação sem rastreabilidade ao repositório.
```

---

## Pre-Conditions

```yaml
pre-conditions:
  - [ ] Acesso ao repositório confirmado (pode ler arquivos do projeto)
    tipo: pre-condition
    blocker: true
    validação: |
      Verificar que Read/Grep/Glob funcionam no diretório do projeto
    error_message: "Não tenho acesso ao código. Informe o path do projeto."

  - [ ] Package identificado (auto-detect ou informado pelo usuário)
    tipo: pre-condition
    blocker: true
    validação: |
      package.json existe no path fornecido ou detectado
    error_message: "Package não encontrado. Informe o path: *audit-ds {path}"
```

---

## Regras Anti-Alucinação (OBRIGATÓRIO)

> **Severidade: BLOCK** — Violação destas regras invalida toda a auditoria.

### Regras Absolutas

1. **Trabalhe SOMENTE com o que encontrar no repositório**
2. **Nunca invente** arquivos, rotas, APIs, dependências, versões ou padrões
3. **Toda afirmação** deve apontar "onde está no código":
   - Caminho do arquivo
   - Nome do símbolo (componente/função/variável)
   - Localização aproximada ("perto do topo", "na exportação", "linha ~X")
4. **Se não encontrar**, diga explicitamente: "não encontrado no repo"
5. **Marque claramente**: `[ENCONTRADO]` vs `[INFERIDO]` vs `[RECOMENDADO]`

### Criação de Novos Artefatos

Ao sugerir criar algo novo (componente/hook/util/token), SEMPRE explique:
- **(a) Por que é necessário** — qual problema resolve
- **(b) Verificação de duplicação** — como confirmou que não existe
- **(c) Impacto** — o que muda, o que depende disso
- **(d) Risco** — o que pode quebrar, edge cases

---

## Fase 1: Descoberta (NÃO PULAR)

### Passo 1 — Mapeamento de Estrutura

```yaml
discovery_structure:
  - [ ] Identificar root do projeto (package.json, tsconfig.json)
  - [ ] Mapear estrutura de pastas (src/, app/, pages/, components/, lib/, utils/)
  - [ ] Localizar configs críticos:
      - tailwind.config.* (JS/TS/CSS)
      - postcss.config.*
      - next.config.*
      - tsconfig.json
      - .eslintrc.* / eslint.config.*
      - .prettierrc / prettier.config.*
      - components.json (shadcn)
  - [ ] Identificar entry points de CSS (@import, globals.css, app.css)
  - [ ] Verificar CLAUDE.md e design-system-prompt.md (config IA do AIOX)
```

### Passo 2 — Detecção de Stack

```yaml
discovery_stack:
  - [ ] Framework: Next.js (App Router vs Pages Router) / Vite / outro
  - [ ] React version (18.x, 19.x)
  - [ ] TypeScript version e strictness level
  - [ ] Tailwind version (v3.x vs v4.x) — CRÍTICO determinar primeiro
  - [ ] Estado do shadcn/ui (instalado? parcial? ausente?)
  - [ ] Gerenciador de pacotes (npm/yarn/pnpm/bun)
  - [ ] Monorepo? (Turborepo/Nx/pnpm workspaces)
```

### Passo 3 — Inventário de Padrões Existentes

```yaml
discovery_patterns:
  - [ ] Como componentes são criados (convenções de naming, exports)
  - [ ] Onde vivem os componentes UI base (components/ui? lib/components?)
  - [ ] Existe util cn/clsx/tailwind-merge?
  - [ ] Existe sistema de variants (cva? tailwind-variants? manual?)
  - [ ] Como dark mode é implementado (class? media? data-attribute?)
  - [ ] Tokens existentes (CSS variables? theme config? JSON?)
  - [ ] Padrões de acessibilidade já implementados
  - [ ] Atomic Design adotado? (atoms/molecules/organisms/templates/pages)
  - [ ] spec.json do Design System existe?
```

### Passo 4 — Identificação de Hotspots

```yaml
discovery_hotspots:
  - [ ] Componentes mais utilizados (imports frequentes)
  - [ ] Arquivos com mais linhas de CSS/classes
  - [ ] Componentes com lógica complexa (forms, tables, modals)
  - [ ] Páginas/rotas principais
  - [ ] Áreas com código duplicado aparente
```

**Elicitation Point (se necessário):**
> Se o projeto for multi-package ou tiver ambiguidade sobre qual frontend auditar, perguntar ao usuário ANTES de prosseguir.

---

## Fase 2: Planejamento

Após a descoberta, criar plano de auditoria específico:

```yaml
audit_plan:
  - [ ] Prioridades baseadas no estado real (o que é mais crítico para ESTE projeto)
  - [ ] Ordem de análise (categorias prioritárias baseado nas dependências)
  - [ ] Riscos identificados (o que pode quebrar, o que precisa cuidado)
  - [ ] Quick wins óbvios (melhorias de baixo esforço/alto impacto já visíveis)
  - [ ] Brand guidelines disponíveis? (Primal Code do cliente via @brand-guardian)
```

**No modo `--quick`:** Fases 1 e 2 são compactadas em uma única passagem silenciosa (não geram output separado).

---

## Fase 3: Auditoria Profunda

Executar checklist completo por categoria. Referência: `.aiox-core/development/checklists/ds-audit-checklist.md`

### Categorias de Auditoria

| Categoria | Seção no Checklist | Peso no DS_Score |
|-----------|-------------------|------------------|
| A) Tailwind CSS | 5.A | — |
| B) Design Tokens | 5.B | — |
| C) shadcn/ui + Radix | 5.C | — |
| D) React/Next.js | 5.D | — |
| E) Acessibilidade | 5.E | 25% |
| F) Tooling/DX/CI | 5.F | — |
| G) Performance | 5.G | 15% |
| H) Configuração IA | 5.H | — |
| I) Brand Compliance | 5.I | 20% |
| J) Atomic Design | 5.J | — |

### DS_Score Calculation

```yaml
ds_score:
  axes:
    - name: accessibility
      weight: 0.25
      source: "Categoria E — WCAG 2.2 + APCA compliance"
      scoring: "0-10 baseado no checklist E"

    - name: performance
      weight: 0.15
      source: "Categoria G — Core Web Vitals + bundle"
      scoring: "0-10 baseado em métricas reais"

    - name: consistency
      weight: 0.20
      source: "Categorias A+B+C — tokens, variants, padrões"
      scoring: "0-10 baseado em uniformidade de padrões"

    - name: coverage
      weight: 0.20
      source: "Categorias D+F+J — componentes, tooling, Atomic Design"
      scoring: "0-10 baseado em cobertura do sistema"

    - name: brand
      weight: 0.20
      source: "Categoria I — rastreabilidade de tokens ao brand"
      scoring: "0-10 baseado em aderência ao Primal Code"

  formula: |
    DS_Score = (a11y * 0.25) + (perf * 0.15) + (consistency * 0.20)
            + (coverage * 0.20) + (brand * 0.20)

  classification:
    '0.0-3.9': 'CRITICAL — Design System precisa de refatoração fundamental'
    '4.0-5.9': 'NEEDS WORK — Gaps significativos, plano de ação necessário'
    '6.0-7.9': 'GOOD — Base sólida com melhorias pontuais'
    '8.0-9.9': 'EXCELLENT — Padrão profissional, manutenção evolutiva'
```

### Multi-Client Drift Detection (AIOX-specific)

```yaml
drift_detection:
  purpose: "Comparar tokens entre clientes para detectar divergência"
  when: "Projeto atende múltiplos clientes com Design Systems separados"

  checks:
    - [ ] Tokens primitivos (Layer 1) são compartilhados?
    - [ ] Tokens semânticos (Layer 2) divergem entre clientes?
    - [ ] Componentes base são reutilizados ou duplicados?
    - [ ] Brand tokens são isolados por cliente?
    - [ ] Há contaminação entre clientes (tokens de um em outro)?

  output: "Tabela comparativa de tokens por cliente + recomendação de consolidação"
```

---

## Fase 4: Recomendações

Para cada issue encontrado, documentar:

```yaml
recommendation_format:
  issue: "Descrição do problema"
  severity: "CRITICAL | HIGH | MEDIUM | LOW"
  evidence: "arquivo:localização — o que foi encontrado"
  impact: "O que está sendo afetado"
  solution: "Ação recomendada + snippet quando aplicável"
  effort: "Alto | Médio | Baixo"
  risk: "O que pode quebrar"
  files_affected: ["lista de arquivos"]
```

### Matriz de Priorização

Ordenar por: **Impacto Alto + Esforço Baixo** primeiro (quick wins no topo).

---

## Fase 5: Plano de Ação

```yaml
action_plan:
  quick_wins: "Esta semana — implementar imediatamente"
  short_term: "1-2 sprints"
  medium_term: "1-2 meses"
  long_term: "Roadmap (inclui migração Tailwind v4 se aplicável)"
```

Se Tailwind v4 for objetivo, incluir estratégia de migração com passos pequenos e validações (visual regression).

---

## Formato de Saída (9 Seções)

### Modo Full — USE EXATAMENTE ESTES TÍTULOS

```markdown
## 1. Resumo Executivo
- Máximo 10 bullets
- Estado geral do projeto
- Top 3 issues críticos
- Top 3 quick wins
- DS_Score geral
- Recomendação geral (migrar? refatorar? manter?)

## 2. Mapa do Projeto (Descoberta)
- Stack detectada (framework, versions, configs)
- Estrutura de pastas
- Arquivos de configuração críticos
- Padrões identificados
- Hotspots mapeados

## 3. Estado do Tailwind e Tema
- Versão detectada (v3 ou v4)
- Localização da configuração
- Sistema de tokens atual
- Dark mode implementation
- OKLCH status
- Recomendação de migração (se aplicável)

## 4. Diagnóstico por Categoria
Para CADA categoria (4.1-4.10), usar formato:
  #### 4.X [Nome]
  **Estado Atual:** [1-2 frases]
  **Issues:**
  | # | Issue | Severidade | Evidência | Impacto |
  **Recomendações:**
  | # | Ação | Esforço | Risco | Arquivos |
  **Snippet de Solução (se aplicável)**

  Categorias:
  4.1 Arquitetura/Componentização (React/Next)
  4.2 Tailwind CSS (padrões, conflitos, variants)
  4.3 Tokenização/Design Tokens (3 camadas, OKLCH)
  4.4 shadcn/ui + Radix (padrões, a11y)
  4.5 Performance (render, bundle, vitals)
  4.6 Acessibilidade e UX (WCAG 2.2, APCA)
  4.7 Tooling/DX/CI (Prettier, ESLint, hooks)
  4.8 Configuração IA (CLAUDE.md + design-system-prompt.md)
  4.9 Brand Compliance (Primal Code, multi-client)
  4.10 Atomic Design Validation

## 5. DS_Score
- Radar chart (representação textual) com 5 eixos
- Score individual por eixo
- Score geral ponderado
- Classificação (CRITICAL / NEEDS WORK / GOOD / EXCELLENT)

## 6. Matriz de Priorização
| # | Item | Impacto | Esforço | Risco | Categoria | Arquivos |
Ordenar: Impacto Alto + Esforço Baixo primeiro

## 7. Plano de Ação Incremental
- Quick Wins (Esta Semana)
- Short Term (1-2 Sprints)
- Medium Term (1-2 Meses)
- Long Term (Roadmap)

## 8. Convenções Propostas + Config IA
- Padrões recomendados para CLAUDE.md / design-system-prompt.md
- Anti-patterns específicos do projeto
- Regras para spec.json do Design System

## 9. Checklist de Qualidade para PRs
- Referência: .aiox-core/development/checklists/ds-quality-pr-checklist.md
- Copiar inline para uso imediato
```

### Modo Quick — Output Condensado

```markdown
## Resumo Executivo (10 bullets max)
## DS_Score (5 eixos + classificação)
## Top Issues (tabela: issue | severidade | evidência | ação)
## Quick Wins (checklist acionável)
```

---

## Anti-Patterns a Detectar

### Tailwind Anti-Patterns
- Classes dinâmicas quebradas: `text-${color}-500` (Tailwind não gera)
- `@apply` excessivo (perde benefícios utility-first)
- Arbitrary values repetidos que deveriam ser tokens
- Classes conflitantes (`p-2 p-4`)
- Remoção de focus sem substituir: `focus:outline-none` sem `focus-visible:ring-*`

### React Anti-Patterns
- `useEffect` para derivar estado (deve ser cálculo direto)
- Keys instáveis em listas (`key={index}`)
- Prop drilling excessivo
- `"use client"` desnecessário em componentes sem interatividade

### Acessibilidade Anti-Patterns
- Botão sem texto acessível (ícone sem `sr-only`)
- Div clicável em vez de `<button>`
- Input sem label
- Imagem sem alt

### Brand Anti-Patterns (AIOX-specific)
- Token sem rastreabilidade ao brand guideline
- Cor hardcoded que deveria ser token semântico
- Tipografia fora do sistema do cliente
- Componente com estilo de um cliente contaminando outro

---

## Post-Conditions

```yaml
post-conditions:
  - [ ] Relatório gerado com todas as seções obrigatórias
    tipo: post-condition
    blocker: true

  - [ ] DS_Score calculado com 5 eixos
    tipo: post-condition
    blocker: true

  - [ ] Nenhuma afirmação sem evidência no código
    tipo: post-condition
    blocker: true

  - [ ] Plano de ação com pelo menos 3 quick wins
    tipo: post-condition
    blocker: false
```

---

## Error Handling

**Strategy:** warn-and-continue (auditoria é diagnóstico, não execução)

1. **Error:** Acesso ao repo indisponível
   - **Resolution:** Informar "Não tenho acesso ao código aqui." e listar o que precisaria ser habilitado
   - **Recovery:** Parar imediatamente, não inventar nada

2. **Error:** Package ambíguo (múltiplos frontends)
   - **Resolution:** Listar packages encontrados e perguntar qual auditar
   - **Recovery:** Elicitation point — aguardar input do usuário

3. **Error:** Brand guidelines não disponíveis
   - **Resolution:** Prosseguir sem a categoria I (Brand Compliance)
   - **Recovery:** DS_Score calculado com 4 eixos, marcar Brand como "N/A"

---

## Handoff

```yaml
next_agent: @dev
next_command: "*develop {story-id}"
condition: "Auditoria concluída, action plan com stories criadas"
alternatives:
  - agent: @architect
    command: "*review-architecture"
    condition: "Issues arquiteturais graves detectados"
  - agent: @brand-guardian
    command: "*audit-primal-code"
    condition: "Drift de brand detectado entre clientes"
  - agent: @po
    command: "*create-story"
    condition: "Quick wins identificados para virar stories"
```

---

## Referências

- **Checklist completo:** `.aiox-core/development/checklists/ds-audit-checklist.md`
- **Checklist de PR:** `.aiox-core/development/checklists/ds-quality-pr-checklist.md`
- **Prompt base (compacto):** Adaptado de Alan Lendário — Design System Audit Prompt 1
- **Prompt base (completo):** Adaptado de Alan Lendário — Design System Audit Prompt 2
- **Referência técnica:** Tailwind v4, OKLCH, W3C DTCG v2025.10, WCAG 2.2, APCA

---

## Metadata

```yaml
version: 1.0.0
created: 2026-03-26
dependencies:
  - .aiox-core/development/checklists/ds-audit-checklist.md
  - .aiox-core/development/checklists/ds-quality-pr-checklist.md
tags:
  - design-system
  - audit
  - frontend
  - quality
```
