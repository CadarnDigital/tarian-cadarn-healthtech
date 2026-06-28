# Relatorio de Auditoria — Design System

> **Projeto:** {projeto}
> **Data:** {data}
> **Agente:** @design-system (Cosmo)
> **Comando:** `*audit-ds`
> **Versao do template:** 1.0.0

---

## 1. Resumo Executivo

<!-- Max 10 bullets. Estado geral + top issues + top quick wins + recomendacao -->

- **Estado geral:** {estado_geral}
- **Stack detectada:** {stack_detectada}
- **Tailwind version:** {tailwind_version}
- **DS_Score:** {ds_score}/100 ({classificacao})

**Top 3 Issues Criticos:**
1. {issue_critico_1}
2. {issue_critico_2}
3. {issue_critico_3}

**Top 3 Quick Wins:**
1. {quick_win_1}
2. {quick_win_2}
3. {quick_win_3}

**Recomendacao geral:** {migrar | refatorar | manter | construir do zero}

---

## 2. Mapa do Projeto (Descoberta)

### Stack Detectada

| Item | Valor |
|------|-------|
| Framework | {framework} |
| React version | {react_version} |
| TypeScript version | {ts_version} |
| TypeScript strictness | {ts_strictness} |
| Tailwind version | {tailwind_version} |
| shadcn/ui | {shadcn_status} |
| Package manager | {package_manager} |
| Monorepo | {monorepo_status} |

### Estrutura de Pastas

```
{estrutura_pastas}
```

### Arquivos de Configuracao Criticos

| Arquivo | Status | Notas |
|---------|--------|-------|
| tailwind.config.* | {status} | {notas} |
| postcss.config.* | {status} | {notas} |
| next.config.* | {status} | {notas} |
| tsconfig.json | {status} | {notas} |
| .eslintrc.* | {status} | {notas} |
| .prettierrc | {status} | {notas} |
| components.json (shadcn) | {status} | {notas} |

### Padroes Identificados

- Componentes: {padrao_componentes}
- Variants: {padrao_variants}
- Dark mode: {padrao_dark_mode}
- Tokens: {padrao_tokens}
- cn/clsx/tailwind-merge: {padrao_cn}

### Hotspots

| Hotspot | Tipo | Impacto |
|---------|------|---------|
| {hotspot_1} | {tipo} | {impacto} |
| {hotspot_2} | {tipo} | {impacto} |

---

## 3. Estado do Tailwind e Tema

| Item | Valor |
|------|-------|
| Versao detectada | {tailwind_version_detectada} |
| Configuracao | {config_location} |
| OKLCH | {oklch_status} |
| Dark mode | {dark_mode_impl} |
| Container Queries | {container_queries_status} |
| Flash prevention | {flash_prevention_status} |

### Sistema de Tokens Atual

| Camada | Status | Observacao |
|--------|--------|-----------|
| Layer 1 (Global/Primitive) | {l1_status} | {l1_obs} |
| Layer 2 (Semantic/Alias) | {l2_status} | {l2_obs} |
| Layer 3 (Component) | {l3_status} | {l3_obs} |

### Recomendacao de Migracao

{migracao_recomendacao}

---

## 4. Diagnostico por Categoria

### 4.1 Arquitetura / Componentizacao (React/Next)

**Estado Atual:** {estado_4_1}

**Issues Encontrados:**

| # | Issue | Severidade | Evidencia | Impacto |
|---|-------|------------|-----------|---------|
| 1 | {issue} | {Alta/Media/Baixa} | {arquivo:localizacao} | {impacto} |

**Recomendacoes:**

| # | Acao | Esforco | Risco | Arquivos |
|---|------|---------|-------|----------|
| 1 | {acao} | {Alto/Medio/Baixo} | {risco} | {arquivos} |

### 4.2 Tailwind CSS (padroes, conflitos, variants)

**Estado Atual:** {estado_4_2}

**Issues Encontrados:**

| # | Issue | Severidade | Evidencia | Impacto |
|---|-------|------------|-----------|---------|
| 1 | {issue} | {severidade} | {evidencia} | {impacto} |

**Recomendacoes:**

| # | Acao | Esforco | Risco | Arquivos |
|---|------|---------|-------|----------|
| 1 | {acao} | {esforco} | {risco} | {arquivos} |

<!-- Ref: anti-patterns em .aiox-core/development/data/tailwind-anti-patterns.md -->

### 4.3 Tokenizacao / Design Tokens (3 camadas, OKLCH)

**Estado Atual:** {estado_4_3}

**Issues Encontrados:**

| # | Issue | Severidade | Evidencia | Impacto |
|---|-------|------------|-----------|---------|
| 1 | {issue} | {severidade} | {evidencia} | {impacto} |

**Recomendacoes:**

| # | Acao | Esforco | Risco | Arquivos |
|---|------|---------|-------|----------|
| 1 | {acao} | {esforco} | {risco} | {arquivos} |

<!-- Ref: spec em .aiox-core/development/data/design-tokens-w3c-dtcg.md -->

### 4.4 shadcn/ui + Radix (padroes, a11y)

**Estado Atual:** {estado_4_4}

**Issues Encontrados:**

| # | Issue | Severidade | Evidencia | Impacto |
|---|-------|------------|-----------|---------|
| 1 | {issue} | {severidade} | {evidencia} | {impacto} |

**Recomendacoes:**

| # | Acao | Esforco | Risco | Arquivos |
|---|------|---------|-------|----------|
| 1 | {acao} | {esforco} | {risco} | {arquivos} |

### 4.5 Performance (render, bundle, vitals)

**Estado Atual:** {estado_4_5}

**Issues Encontrados:**

| # | Issue | Severidade | Evidencia | Impacto |
|---|-------|------------|-----------|---------|
| 1 | {issue} | {severidade} | {evidencia} | {impacto} |

**Recomendacoes:**

| # | Acao | Esforco | Risco | Arquivos |
|---|------|---------|-------|----------|
| 1 | {acao} | {esforco} | {risco} | {arquivos} |

<!-- Ref: benchmarks em .aiox-core/development/data/frontend-benchmarks-2025.md -->

### 4.6 Acessibilidade e UX (WCAG 2.2, APCA)

**Estado Atual:** {estado_4_6}

**Issues Encontrados:**

| # | Issue | Severidade | Evidencia | Impacto |
|---|-------|------------|-----------|---------|
| 1 | {issue} | {severidade} | {evidencia} | {impacto} |

**Recomendacoes:**

| # | Acao | Esforco | Risco | Arquivos |
|---|------|---------|-------|----------|
| 1 | {acao} | {esforco} | {risco} | {arquivos} |

### 4.7 Tooling / DX / CI (Prettier, ESLint, hooks)

**Estado Atual:** {estado_4_7}

**Issues Encontrados:**

| # | Issue | Severidade | Evidencia | Impacto |
|---|-------|------------|-----------|---------|
| 1 | {issue} | {severidade} | {evidencia} | {impacto} |

**Recomendacoes:**

| # | Acao | Esforco | Risco | Arquivos |
|---|------|---------|-------|----------|
| 1 | {acao} | {esforco} | {risco} | {arquivos} |

### 4.8 Configuracao IA (.cursorrules)

**Estado Atual:** {estado_4_8}

**Issues Encontrados:**

| # | Issue | Severidade | Evidencia | Impacto |
|---|-------|------------|-----------|---------|
| 1 | {issue} | {severidade} | {evidencia} | {impacto} |

**Recomendacoes:**

| # | Acao | Esforco | Risco | Arquivos |
|---|------|---------|-------|----------|
| 1 | {acao} | {esforco} | {risco} | {arquivos} |

---

## 5. DS_Score

### 5 Eixos do Radar

| Eixo | Score (0-100) | Peso | Ponderado |
|------|---------------|------|-----------|
| Accessibility | {acc_score} | 0.30 | {acc_pond} |
| Performance | {perf_score} | 0.20 | {perf_pond} |
| Consistency | {cons_score} | 0.25 | {cons_pond} |
| Coverage | {cov_score} | 0.25 | {cov_pond} |
| **DS_Score** | | **1.00** | **{ds_score_total}** |

### Classificacao

| Faixa | Classificacao |
|-------|---------------|
| 90-100 | Excelente |
| 75-89 | Bom |
| 60-74 | Precisa Atencao |
| < 60 | Critico |

**Resultado:** {ds_score_total} — **{classificacao_final}**

### Detalhamento por Sub-metrica

**Accessibility ({acc_score}):**
- WCAG 2.2 conformance: {wcag_conf}
- Contraste: {contraste}
- Keyboard navigation: {keyboard}
- Screen reader: {sr}

**Performance ({perf_score}):**
- LCP: {lcp}
- INP: {inp}
- CLS: {cls}
- Bundle size: {bundle}

**Consistency ({cons_score}):**
- DS adherence: {adherence}%
- Token coverage: {token_cov}%
- Component reuse rate: {reuse}%

**Coverage ({cov_score}):**
- Documentation coverage: {doc_cov}%
- spec.json coverage: {spec_cov}%
- Test coverage: {test_cov}%

---

## 6. Matriz de Priorizacao

| # | Item | Impacto | Esforco | Risco | Categoria | Arquivos Afetados |
|---|------|---------|---------|-------|-----------|-------------------|
| 1 | {item} | {Alto/Medio/Baixo} | {esforco} | {risco} | {cat} | {arquivos} |

<!-- Ordenar por: Impacto Alto + Esforco Baixo primeiro (quick wins no topo) -->

---

## 7. Plano de Acao Incremental

### Quick Wins (Esta Semana)

- [ ] {quick_win_1}
- [ ] {quick_win_2}
- [ ] {quick_win_3}

### Short Term (1-2 Sprints)

- [ ] {short_1}
- [ ] {short_2}

### Medium Term (1-2 Meses)

- [ ] {medium_1}
- [ ] {medium_2}

### Long Term (Roadmap)

- [ ] {long_1}
- [ ] {long_2}

---

## 8. Convencoes Propostas

### Componentes

- {conv_componentes}

### Tailwind

- {conv_tailwind}

### Tokens

- {conv_tokens}

### Acessibilidade

- {conv_a11y}

### Naming

- {conv_naming}

---

## 9. Checklist de Qualidade para Novas Features

### Componentes

- [ ] API consistente (variants/sizes/states)
- [ ] TypeScript props tipadas (interface, nunca `any`)
- [ ] Sem duplicacao (verificado via IDS: REUSE > ADAPT > CREATE)
- [ ] spec.json criado e atualizado
- [ ] Hierarquia Atomic respeitada

### Tokens

- [ ] Sem hardcode de cor/spacing/typo
- [ ] Usando tokens semanticos (Layer 2), nunca globais direto
- [ ] Tokens novos registrados no arquivo DTCG

### Tailwind

- [ ] Classes ordenadas (Prettier plugin)
- [ ] Sem conflitos (eslint-plugin-tailwindcss)
- [ ] Usando cn/cva para composicao
- [ ] Sem @apply desnecessario
- [ ] Sem arbitrary values repetidos

### Acessibilidade

- [ ] `focus-visible` presente em todos interativos
- [ ] Labels em todos os inputs
- [ ] `sr-only` em botoes com icone
- [ ] Keyboard navigation testada
- [ ] Contraste validado (4.5:1 texto, 3:1 UI)
- [ ] `motion-reduce` respeitado

### UX States

- [ ] Loading state
- [ ] Empty state
- [ ] Error state
- [ ] Success feedback

### Performance

- [ ] Keys estaveis em listas
- [ ] Memoization correta (sem over-memoization)
- [ ] Sem useEffect desnecessario
- [ ] Dynamic imports para componentes pesados

### Evidencia

- [ ] Testado em light/dark mode
- [ ] Testado mobile
- [ ] Visual regression passou (se configurado)
- [ ] Testado com screen reader (componentes interativos)

---

## Cross-references

- Benchmarks: `.aiox-core/development/data/frontend-benchmarks-2025.md`
- Anti-patterns: `.aiox-core/development/data/tailwind-anti-patterns.md`
- Design tokens spec: `.aiox-core/development/data/design-tokens-w3c-dtcg.md`
