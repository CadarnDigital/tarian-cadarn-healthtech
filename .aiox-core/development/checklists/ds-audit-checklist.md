# Design System Audit Checklist

```yaml
checklist:
  id: ds-audit-checklist
  version: 1.0.0
  created: 2026-03-26
  purpose: "Checklist profissional para auditoria de Design System frontend — todas as categorias"
  mode: advisory  # Guia a auditoria, não bloqueia publicação
  reference_task: ".aiox-core/development/tasks/audit-design-system.md"
  source: "Adaptado de Alan Lendário — Design System Audit Prompt 2 (seção 5)"
```

---

## A) Tailwind CSS — Estado da Arte

### A.1 Detecção de Versão (PRIMEIRO PASSO)

```yaml
tailwind_version:
  - id: tw-version-detect
    check: "Qual versão no package.json?"
    type: blocking
    evidence: "package.json → devDependencies.tailwindcss"

  - id: tw-config-type
    check: "Configuração: tailwind.config.* (v3) ou @theme em CSS (v4)?"
    type: blocking
    evidence: "Presença de tailwind.config.js/ts vs @theme em CSS"

  - id: tw-directives
    check: "Directives: @tailwind base/components/utilities (v3) ou @import 'tailwindcss' (v4)?"
    type: blocking
    evidence: "Entry point CSS (globals.css, app.css)"

  - id: tw-postcss
    check: "PostCSS: postcss-import? @tailwindcss/postcss?"
    type: recommended
    evidence: "postcss.config.*"
```

### A.2 Se v3 Detectado

```yaml
tailwind_v3:
  - id: tw3-migration-viability
    check: "Viabilidade de migração para v4 avaliada?"
    type: recommended

  - id: tw3-blockers
    check: "Bloqueadores identificados? (Sass/Less? Browsers antigos? Dependencies de config JS?)"
    type: recommended

  - id: tw3-improvements
    check: "Melhorias possíveis dentro do v3 documentadas?"
    type: recommended

  - id: tw3-migration-plan
    check: "Plano incremental de migração criado (se aplicável)?"
    type: recommended
```

### A.3 Se v4 Detectado

```yaml
tailwind_v4:
  - id: tw4-theme
    check: "@theme configurado corretamente?"
    type: blocking
    evidence: "CSS entry point → @theme { ... }"

  - id: tw4-config-migrated
    check: "Migração completa de tailwind.config.js?"
    type: recommended

  - id: tw4-oklch
    check: "OKLCH sendo usado para cores?"
    type: recommended

  - id: tw4-container-queries
    check: "Container Queries usadas onde aplicável?"
    type: recommended

  - id: tw4-renames
    check: "Renames aplicados? (shadow->shadow-sm, outline-none->outline-hidden)"
    type: blocking
    evidence: "Buscar por classes obsoletas no código"
```

### A.4 Organização de Classes

```yaml
tailwind_classes:
  - id: tw-long-strings
    check: "Strings de classes gigantes sem padrão? (>10 classes inline)"
    type: recommended
    evidence: "Grep por className com 10+ classes"

  - id: tw-conflicts
    check: "Conflitos de classes detectados? (p-2 p-4, text-sm text-lg)"
    type: blocking
    evidence: "Buscar padrões conflitantes"

  - id: tw-cn-merge
    check: "Uso de cn/clsx + tailwind-merge?"
    type: recommended
    evidence: "Buscar import de cn, clsx, twMerge"

  - id: tw-variants-system
    check: "Sistema de variants implementado? (cva? tailwind-variants? manual?)"
    type: recommended
    evidence: "Buscar import de cva, tv, ou patterns manuais"

  - id: tw-arbitrary-overuse
    check: "Arbitrary values em excesso? ([...] repetidos que deveriam ser tokens)"
    type: recommended
    evidence: "Grep por padrões [...] repetidos"
```

### A.5 @apply e @layer

```yaml
tailwind_apply:
  - id: tw-apply-justified
    check: "@apply usado apenas para padrões reutilizáveis (3+ ocorrências)?"
    type: recommended

  - id: tw-layer-components
    check: "@layer components usado para Design System?"
    type: recommended

  - id: tw-layer-utilities
    check: "@layer utilities usado para utilities customizadas?"
    type: recommended

  - id: tw-apply-anti-pattern
    check: "NÃO está usando @apply para 'limpar código' (anti-pattern)?"
    type: blocking
```

### A.6 Responsividade

```yaml
tailwind_responsive:
  - id: tw-mobile-first
    check: "Mobile-first? (classes base para mobile, breakpoints para desktop)"
    type: blocking

  - id: tw-breakpoints-consistent
    check: "Breakpoints consistentes? (sm, md, lg, xl, 2xl)"
    type: recommended

  - id: tw-container-queries
    check: "Container queries onde componente precisa responder ao container?"
    type: recommended
```

### A.7 Estados Interativos

```yaml
tailwind_states:
  - id: tw-states-consistent
    check: "hover/focus/active/disabled consistentes?"
    type: blocking

  - id: tw-focus-visible
    check: "focus-visible para keyboard-only focus?"
    type: blocking

  - id: tw-motion-safe
    check: "motion-safe/motion-reduce para animações?"
    type: recommended

  - id: tw-state-contrast
    check: "Contraste suficiente em todos os estados?"
    type: blocking
```

---

## B) Design Tokens — Arquitetura 3 Camadas

### B.1 Mapeamento de Estado Atual

```yaml
tokens_current:
  - id: tok-source
    check: "Onde vivem os tokens? (CSS vars? theme config? JSON? inline?)"
    type: blocking
    evidence: "Localizar fonte de verdade de tokens"

  - id: tok-hierarchy
    check: "Existe hierarquia ou tudo é flat?"
    type: blocking

  - id: tok-dark-mode-impl
    check: "Dark mode: como é implementado? (class? media? data-attribute?)"
    type: blocking

  - id: tok-semantic-vs-presentational
    check: "Cores são semânticas ou presentacionais? (bg-blue-500 vs bg-primary)"
    type: blocking
```

### B.2 Hierarquia 3 Camadas

```yaml
tokens_layers:
  layer_1_primitive:
    - id: tok-l1-colors
      check: "Cores brutas definidas? (blue-500, gray-900)"
      type: recommended

    - id: tok-l1-spacing
      check: "Spacing scale definida?"
      type: recommended

    - id: tok-l1-typography
      check: "Typography scale definida?"
      type: recommended

    - id: tok-l1-theme-invariant
      check: "Não mudam entre temas?"
      type: blocking

  layer_2_semantic:
    - id: tok-l2-semantic-colors
      check: "Cores semânticas definidas? (primary, secondary, background, foreground)"
      type: blocking

    - id: tok-l2-theme-switching
      check: "Mudam entre light/dark?"
      type: blocking

    - id: tok-l2-aliases
      check: "São aliases para primitives?"
      type: recommended

  layer_3_component:
    - id: tok-l3-exists
      check: "Tokens específicos de componente existem?"
      type: recommended

    - id: tok-l3-inherits
      check: "Herdam do semantic?"
      type: recommended

    - id: tok-l3-examples
      check: "Ex: button-primary-bg, card-border, input-focus-ring?"
      type: recommended
```

### B.3 OKLCH

```yaml
tokens_oklch:
  - id: tok-oklch-status
    check: "Projeto usa OKLCH ou RGB/HSL?"
    type: blocking

  - id: tok-oklch-migration
    check: "Se HSL/RGB: plano de migração gradual existe?"
    type: recommended

  - id: tok-oklch-contrast
    check: "Contraste validado em OKLCH?"
    type: recommended
```

### B.4 Dark Mode

```yaml
tokens_dark_mode:
  - id: tok-dm-implementation
    check: "Implementação: class='dark'? data-theme='dark'? @media?"
    type: blocking

  - id: tok-dm-tokens
    check: "Tokens semânticos mudam corretamente?"
    type: blocking

  - id: tok-dm-contrast
    check: "Contraste validado em dark mode?"
    type: blocking

  - id: tok-dm-flash
    check: "Flash prevention? (script no <head>?)"
    type: recommended

  - id: tok-dm-system-pref
    check: "System preference detection?"
    type: recommended
```

---

## C) shadcn/ui + Radix UI

### C.1 Detecção

```yaml
shadcn_detection:
  - id: shd-components-json
    check: "components.json existe?"
    type: blocking
    evidence: "root/components.json"

  - id: shd-ui-folder
    check: "Pasta components/ui/ existe?"
    type: blocking

  - id: shd-components-list
    check: "Quais componentes instalados? (listar)"
    type: blocking

  - id: shd-versions
    check: "Versões das dependências (Radix, cmdk, cva)?"
    type: recommended
```

### C.2 Auditoria de Componentes

```yaml
shadcn_audit:
  - id: shd-forward-ref
    check: "forwardRef implementado corretamente?"
    type: blocking

  - id: shd-data-state
    check: "data-state atributos do Radix preservados?"
    type: blocking

  - id: shd-composition
    check: "Composição com primitives (Dialog.Root, Dialog.Trigger, etc.)?"
    type: blocking

  - id: shd-typescript
    check: "TypeScript props bem tipadas?"
    type: blocking

  - id: shd-variants
    check: "Variants usando cva ou equivalente?"
    type: recommended
```

### C.3 Acessibilidade Radix

```yaml
shadcn_a11y:
  - id: shd-keyboard
    check: "Keyboard navigation funcionando?"
    type: blocking

  - id: shd-focus-mgmt
    check: "Focus management em modals/dropdowns?"
    type: blocking

  - id: shd-aria
    check: "ARIA attributes presentes?"
    type: blocking

  - id: shd-screen-reader
    check: "Screen reader announcements?"
    type: recommended
```

### C.4 Manutenção

```yaml
shadcn_maintenance:
  - id: shd-update-convention
    check: "Convenção de update definida?"
    type: recommended

  - id: shd-customizations-doc
    check: "Customizações documentadas?"
    type: recommended

  - id: shd-divergence-risk
    check: "Risco de divergência mapeado?"
    type: recommended

  - id: shd-changelog
    check: "Changelog de modificações?"
    type: recommended
```

### C.5 Consistência

```yaml
shadcn_consistency:
  - id: shd-css-vars
    check: "CSS variables do tema integradas?"
    type: blocking

  - id: shd-variants-consistent
    check: "Variants consistentes entre componentes?"
    type: blocking

  - id: shd-sizes-consistent
    check: "Sizes consistentes (sm, md, lg)?"
    type: recommended

  - id: shd-states-consistent
    check: "Estados consistentes (default, hover, focus, disabled)?"
    type: blocking
```

---

## D) React/Next.js — Arquitetura Moderna

### D.1 Detecção de Stack

```yaml
react_stack:
  - id: react-nextjs-version
    check: "Next.js version?"
    type: blocking
    evidence: "package.json → dependencies.next"

  - id: react-router
    check: "App Router ou Pages Router?"
    type: blocking

  - id: react-version
    check: "React version (18.x, 19.x)?"
    type: blocking

  - id: react-ts-strictness
    check: "TypeScript strictness level?"
    type: recommended
    evidence: "tsconfig.json → strict"
```

### D.2 Server Components (se App Router)

```yaml
react_rsc:
  - id: rsc-minimize-client
    check: "Minimizando 'use client'?"
    type: blocking

  - id: rsc-server-default
    check: "Server Components onde possível?"
    type: blocking

  - id: rsc-client-justified
    check: "Client Components apenas quando necessário (interatividade, hooks)?"
    type: blocking

  - id: rsc-suspense
    check: "Suspense boundaries para loading states?"
    type: recommended
```

### D.3 Performance Arquitetural

```yaml
react_performance:
  - id: react-unnecessary-effects
    check: "useEffect desnecessários? (estado derivado?)"
    type: blocking

  - id: react-derived-state
    check: "State que poderia ser derivado?"
    type: recommended

  - id: react-prop-drilling
    check: "Prop drilling excessivo?"
    type: recommended

  - id: react-context-overuse
    check: "Context overuse?"
    type: recommended

  - id: react-memoization
    check: "Memoization correta (useMemo, useCallback, memo)?"
    type: recommended
```

### D.4 Composição de Componentes

```yaml
react_composition:
  - id: react-separation
    check: "Separação container/presentational?"
    type: recommended

  - id: react-hooks-extracted
    check: "Hooks extraídos para lógica reutilizável?"
    type: recommended

  - id: react-props-api
    check: "API de props consistente?"
    type: blocking

  - id: react-compound
    check: "Compound components onde apropriado?"
    type: recommended
```

### D.5 Padronização

```yaml
react_standards:
  - id: react-naming
    check: "Naming conventions consistentes?"
    type: blocking

  - id: react-folders
    check: "Estrutura de pastas padronizada?"
    type: recommended

  - id: react-exports
    check: "Exports consistentes (named vs default)?"
    type: recommended

  - id: react-kebab-dirs
    check: "kebab-case para diretórios?"
    type: recommended

  - id: react-pascal-components
    check: "PascalCase para componentes?"
    type: blocking
```

---

## E) Acessibilidade — WCAG 2.2 + APCA

### E.1 Focus Management

```yaml
a11y_focus:
  - id: a11y-focus-never-removed
    check: "Nunca removendo focus sem substituir?"
    type: blocking

  - id: a11y-focus-visible
    check: "focus-visible para keyboard-only?"
    type: blocking

  - id: a11y-focus-ring-contrast
    check: "Focus ring com contraste 3:1?"
    type: blocking

  - id: a11y-focus-trap
    check: "Focus trap em modals?"
    type: blocking

  - id: a11y-skip-links
    check: "Skip links para navegação?"
    type: recommended
```

### E.2 Screen Readers

```yaml
a11y_screen_reader:
  - id: a11y-sr-only-icons
    check: "sr-only em botões com ícone?"
    type: blocking

  - id: a11y-labels
    check: "Labels em form inputs?"
    type: blocking

  - id: a11y-aria-labels
    check: "aria-label/aria-labelledby onde necessário?"
    type: blocking

  - id: a11y-aria-live
    check: "aria-live para conteúdo dinâmico?"
    type: recommended

  - id: a11y-headings
    check: "Headings hierárquicos (h1->h2->h3)?"
    type: blocking
```

### E.3 Componentes Interativos

```yaml
a11y_interactive:
  - id: a11y-keyboard-nav
    check: "Navegação por teclado funcionando?"
    type: blocking

  - id: a11y-enter-space
    check: "Enter/Space para ativar?"
    type: blocking

  - id: a11y-escape-close
    check: "Escape para fechar?"
    type: blocking

  - id: a11y-arrow-keys
    check: "Arrow keys para navegação em listas?"
    type: recommended

  - id: a11y-disabled-clear
    check: "Estados disabled claramente indicados?"
    type: blocking
```

### E.4 Contraste

```yaml
a11y_contrast:
  - id: a11y-text-normal
    check: "Texto normal: 4.5:1?"
    type: blocking

  - id: a11y-text-large
    check: "Texto grande (18px+ ou 14px+ bold): 3:1?"
    type: blocking

  - id: a11y-ui-components
    check: "UI components: 3:1?"
    type: blocking

  - id: a11y-state-changes
    check: "State changes (hover/focus): 3:1?"
    type: blocking

  - id: a11y-light-dark-validated
    check: "Validado em light E dark mode?"
    type: blocking
```

### E.5 Motion

```yaml
a11y_motion:
  - id: a11y-motion-reduce
    check: "motion-reduce respeitado?"
    type: blocking

  - id: a11y-animations-pausable
    check: "Animações pausáveis?"
    type: recommended

  - id: a11y-no-flashing
    check: "Sem conteúdo piscando >3x/segundo?"
    type: blocking
```

### E.6 UX States

```yaml
a11y_ux_states:
  - id: a11y-loading
    check: "Loading states claros?"
    type: blocking

  - id: a11y-empty
    check: "Empty states informativos?"
    type: recommended

  - id: a11y-error
    check: "Error states com mensagens úteis?"
    type: blocking

  - id: a11y-success
    check: "Success feedback presente?"
    type: recommended

  - id: a11y-microcopy
    check: "Microcopy consistente?"
    type: recommended
```

---

## F) Tooling, DX e CI

### F.1 Prettier

```yaml
tooling_prettier:
  - id: tool-prettier-tailwind
    check: "prettier-plugin-tailwindcss instalado?"
    type: blocking
    evidence: "package.json → devDependencies"

  - id: tool-prettier-config
    check: ".prettierrc presente e configurado?"
    type: blocking

  - id: tool-prettier-editor
    check: "Integrado no editor/CI?"
    type: recommended
```

### F.2 ESLint

```yaml
tooling_eslint:
  - id: tool-eslint-tailwind
    check: "eslint-plugin-tailwindcss instalado?"
    type: recommended

  - id: tool-eslint-rules
    check: "Rules ativas: no-contradicting-classname, enforces-shorthand?"
    type: recommended

  - id: tool-eslint-a11y
    check: "eslint-plugin-jsx-a11y para acessibilidade?"
    type: blocking

  - id: tool-eslint-consistent
    check: "Configuração consistente?"
    type: recommended
```

### F.3 Git Hooks

```yaml
tooling_hooks:
  - id: tool-husky
    check: "Husky instalado?"
    type: recommended

  - id: tool-lint-staged
    check: "lint-staged configurado?"
    type: recommended

  - id: tool-pre-commit
    check: "Pre-commit rodando lint/format?"
    type: recommended

  - id: tool-pre-push
    check: "Pre-push rodando testes?"
    type: recommended
```

### F.4 CI Pipeline

```yaml
tooling_ci:
  - id: tool-ci-lint
    check: "Lint check no CI?"
    type: recommended

  - id: tool-ci-typecheck
    check: "Type check no CI?"
    type: recommended

  - id: tool-ci-tests
    check: "Testes no CI?"
    type: blocking

  - id: tool-ci-visual-regression
    check: "Visual regression? (Lost Pixel, Chromatic)"
    type: recommended

  - id: tool-ci-bundle-size
    check: "Bundle size check?"
    type: recommended
```

### F.5 Documentação

```yaml
tooling_docs:
  - id: tool-storybook
    check: "Storybook presente?"
    type: recommended

  - id: tool-components-documented
    check: "Componentes documentados?"
    type: recommended

  - id: tool-props-documented
    check: "Props documentadas?"
    type: recommended

  - id: tool-usage-examples
    check: "Exemplos de uso?"
    type: recommended
```

---

## G) Performance — Dados e Métricas

### G.1 Render Performance

```yaml
perf_render:
  - id: perf-re-renders
    check: "Re-renders evitáveis identificados?"
    type: blocking

  - id: perf-keys-stable
    check: "Keys estáveis em listas?"
    type: blocking

  - id: perf-memoization
    check: "Memoization aplicada corretamente?"
    type: recommended

  - id: perf-effect-deps
    check: "useEffect com deps corretas?"
    type: blocking

  - id: perf-suspense
    check: "Suspense para code splitting?"
    type: recommended
```

### G.2 Bundle

```yaml
perf_bundle:
  - id: perf-dynamic-imports
    check: "Dynamic imports para não-críticos?"
    type: recommended

  - id: perf-tree-shaking
    check: "Tree shaking funcionando?"
    type: recommended

  - id: perf-css-purge
    check: "CSS purge configurado corretamente?"
    type: blocking

  - id: perf-bundle-analysis
    check: "Análise de bundle disponível?"
    type: recommended
```

### G.3 Assets

```yaml
perf_assets:
  - id: perf-next-image
    check: "Next Image para imagens?"
    type: blocking

  - id: perf-modern-formats
    check: "Formatos modernos (WebP, AVIF)?"
    type: recommended

  - id: perf-lazy-loading
    check: "Lazy loading?"
    type: recommended

  - id: perf-sizes-srcset
    check: "Sizes/srcset definidos?"
    type: recommended

  - id: perf-fonts
    check: "Fonts otimizadas (display swap, preload)?"
    type: recommended
```

### G.4 Core Web Vitals

```yaml
perf_vitals:
  - id: perf-lcp
    check: "LCP < 2.5s?"
    type: blocking

  - id: perf-inp
    check: "INP < 200ms?"
    type: blocking

  - id: perf-cls
    check: "CLS < 0.1?"
    type: blocking

  - id: perf-fcp
    check: "FCP < 1.8s?"
    type: recommended

  - id: perf-instrumentation
    check: "Instrumentação presente? (Analytics, Vercel)"
    type: recommended
```

### G.5 Benchmarks de Referência

```yaml
perf_benchmarks:
  css_production:
    excellent: "<15KB"
    good: "15-50KB"
    average: "50-100KB"
    poor: ">100KB"
  css_gzipped:
    excellent: "<5KB"
    good: "5-15KB"
    average: "15-30KB"
    poor: ">30KB"
  js_total:
    excellent: "<100KB"
    good: "100-200KB"
    average: "200-500KB"
    poor: ">500KB"
```

---

## H) Configuração IA (AIOX-specific)

> Adaptado de .cursorrules para o contexto AIOX: usamos CLAUDE.md + design-system-prompt.md + spec.json

### H.1 CLAUDE.md do Projeto

```yaml
ia_claude_md:
  - id: ia-claude-exists
    check: "CLAUDE.md existe no repo do projeto?"
    type: blocking

  - id: ia-claude-stack
    check: "Documenta stack utilizada?"
    type: blocking

  - id: ia-claude-components
    check: "Lista componentes disponíveis?"
    type: recommended

  - id: ia-claude-patterns
    check: "Define padrões de código?"
    type: blocking

  - id: ia-claude-tailwind-version
    check: "Atualizado para versão atual do Tailwind?"
    type: recommended
```

### H.2 design-system-prompt.md

```yaml
ia_ds_prompt:
  - id: ia-ds-prompt-exists
    check: "design-system-prompt.md existe?"
    type: recommended

  - id: ia-ds-prompt-tokens
    check: "Documenta tokens disponíveis?"
    type: recommended

  - id: ia-ds-prompt-components
    check: "Lista componentes UI com API?"
    type: recommended

  - id: ia-ds-prompt-anti-patterns
    check: "Lista anti-patterns específicos do projeto?"
    type: recommended

  - id: ia-ds-prompt-order
    check: "Define ordem de classes (LDPETCE ou similar)?"
    type: recommended
```

### H.3 spec.json

```yaml
ia_spec_json:
  - id: ia-spec-exists
    check: "spec.json do Design System existe?"
    type: recommended

  - id: ia-spec-tokens
    check: "Tokens definidos no spec?"
    type: recommended

  - id: ia-spec-components
    check: "Componentes catalogados no spec?"
    type: recommended

  - id: ia-spec-atomic
    check: "Classificação Atomic Design presente?"
    type: recommended
```

---

## I) Brand Compliance (AIOX-specific)

> Golden Rule de Coel (@brand-guardian): todo token deve rastrear ao brand guideline.

### I.1 Token Traceability

```yaml
brand_traceability:
  - id: brand-tokens-traceable
    check: "Cada token de cor/tipografia rastreia a um guideline de marca?"
    type: blocking
    veto_if_fail: "Token sem rastreabilidade = risco de drift visual"

  - id: brand-no-hardcode
    check: "Nenhuma cor hardcoded fora do sistema de tokens?"
    type: blocking

  - id: brand-typography-system
    check: "Tipografia segue o sistema definido no brand?"
    type: blocking

  - id: brand-spacing-system
    check: "Spacing segue a escala definida?"
    type: recommended
```

### I.2 Multi-Client Isolation

```yaml
brand_multi_client:
  - id: brand-client-isolation
    check: "Tokens de marca isolados por cliente?"
    type: blocking
    veto_if_fail: "Contaminação entre clientes = violação grave de brand"

  - id: brand-no-contamination
    check: "Nenhum token de cliente A aparece em cliente B?"
    type: blocking

  - id: brand-shared-primitives
    check: "Primitives (Layer 1) são compartilhados corretamente?"
    type: recommended

  - id: brand-semantic-per-client
    check: "Semantics (Layer 2) são específicos por cliente?"
    type: blocking
```

### I.3 Primal Code Alignment

```yaml
brand_primal_code:
  - id: brand-primal-exists
    check: "Primal Code do cliente está documentado?"
    type: recommended

  - id: brand-primal-colors
    check: "Cores do DS alinham com o Primal Code?"
    type: blocking

  - id: brand-primal-voice
    check: "Tom de voz refletido em microcopy/UX writing?"
    type: recommended

  - id: brand-primal-visual
    check: "Identidade visual (grid, espaçamento, formas) consistente?"
    type: recommended
```

---

## J) Atomic Design Validation (AIOX-specific)

### J.1 Hierarquia

```yaml
atomic_hierarchy:
  - id: atomic-levels-defined
    check: "Níveis Atomic Design definidos? (atoms/molecules/organisms/templates/pages)"
    type: recommended

  - id: atomic-no-skip
    check: "Sem pulo de nível? (átomo NÃO importa organismo)"
    type: blocking
    veto_if_fail: "Violação de hierarquia Atomic Design compromete composabilidade"

  - id: atomic-atoms-pure
    check: "Atoms são puros? (sem lógica de negócio, sem fetch)"
    type: blocking

  - id: atomic-molecules-compose
    check: "Molecules compõem atoms corretamente?"
    type: recommended

  - id: atomic-organisms-self-contained
    check: "Organisms são self-contained com lógica própria?"
    type: recommended
```

### J.2 spec.json Coverage

```yaml
atomic_spec:
  - id: atomic-spec-covers-atoms
    check: "Todos os atoms estão no spec.json?"
    type: recommended

  - id: atomic-spec-covers-molecules
    check: "Todas as molecules estão no spec.json?"
    type: recommended

  - id: atomic-spec-variants
    check: "Variants de cada componente documentadas no spec?"
    type: recommended

  - id: atomic-spec-props
    check: "Props/API de cada componente documentadas no spec?"
    type: recommended
```

### J.3 Classificação

```yaml
atomic_classification:
  - id: atomic-folder-structure
    check: "Estrutura de pastas reflete classificação Atomic?"
    type: recommended

  - id: atomic-naming-convention
    check: "Naming convention indica o nível? (ex: prefix, folder)"
    type: recommended

  - id: atomic-imports-direction
    check: "Imports seguem direção correta? (atoms <- molecules <- organisms)"
    type: blocking
```

---

## Validation Execution

### Uso no Audit Task

Este checklist é referenciado por `.aiox-core/development/tasks/audit-design-system.md` na Fase 3 (Auditoria Profunda). O agente @design-system (Cosmo) percorre cada categoria e documenta evidências.

### Contagem de Items

| Categoria | Blocking | Recommended | Total |
|-----------|----------|-------------|-------|
| A) Tailwind CSS | 9 | 16 | 25 |
| B) Design Tokens | 8 | 10 | 18 |
| C) shadcn/ui + Radix | 12 | 9 | 21 |
| D) React/Next.js | 10 | 11 | 21 |
| E) Acessibilidade | 17 | 7 | 24 |
| F) Tooling/DX/CI | 3 | 15 | 18 |
| G) Performance | 6 | 11 | 17 |
| H) Configuração IA | 2 | 10 | 12 |
| I) Brand Compliance | 6 | 4 | 10 |
| J) Atomic Design | 3 | 7 | 10 |
| **Total** | **76** | **100** | **176** |

---

**Version:** 1.0.0
**Created:** 2026-03-26
**Source:** Adaptado de Alan Lendário — Design System Audit Prompt 2, seção 5 (A-H) + extensões AIOX (I-J)
**Reference Task:** `.aiox-core/development/tasks/audit-design-system.md`
