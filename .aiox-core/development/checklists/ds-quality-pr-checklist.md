# Design System — PR Quality Checklist

```yaml
checklist:
  id: ds-quality-pr-checklist
  version: 1.0.0
  created: 2026-03-26
  purpose: "Checklist de qualidade para PRs que tocam componentes UI — usado por @dev e @qa"
  mode: blocking  # PR não deve ser aprovado se items blocking falharem
  usage: "Copiar para descrição do PR ou usar como guia de review"
  reference_task: ".aiox-core/development/tasks/audit-design-system.md"
  source: "Adaptado de Alan Lendário — Design System Audit Prompt 2, seção 9 + extensões AIOX"
```

---

## Como Usar

1. **@dev:** Antes de abrir o PR, percorra este checklist e marque os items
2. **@qa:** Durante o review, valide os items marcados e verifique os não marcados
3. **Copiar para PR:** Cole a seção "Checklist para PR" na descrição do PR

---

## Checklist para PR

> Copie o bloco abaixo para a descrição do PR quando ele tocar componentes UI.

```markdown
## UI Quality Checklist

### Componentes
- [ ] API consistente (variants/sizes/states)
- [ ] TypeScript props tipadas (interface, sem `any`)
- [ ] Sem duplicação de componente existente
- [ ] forwardRef implementado (se componente base)
- [ ] Compound components quando apropriado

### Design Tokens
- [ ] Sem hardcode de cor/spacing/tipografia fora do sistema de tokens
- [ ] Usando tokens semânticos (Layer 2), não primitivos (Layer 1)
- [ ] Tokens novos adicionados nas 3 camadas (primitive -> semantic -> component)
- [ ] Dark mode funciona com os novos tokens

### Tailwind CSS
- [ ] Classes ordenadas (Prettier plugin)
- [ ] Sem conflitos de classes (p-2 p-4, text-sm text-lg)
- [ ] Usando cn/cva para composição
- [ ] Sem arbitrary values repetidos (criar token se 3+ usos)
- [ ] Sem @apply desnecessário
- [ ] Mobile-first (classes base = mobile, breakpoints = desktop)

### Acessibilidade
- [ ] focus-visible presente em elementos interativos
- [ ] Labels em todos os inputs (label, aria-label, aria-labelledby)
- [ ] sr-only em botões com ícone sem texto
- [ ] Keyboard navigation testada (Tab, Enter, Space, Escape)
- [ ] Contraste 4.5:1 (texto) e 3:1 (UI/estados) validado
- [ ] motion-reduce respeitado em animações
- [ ] aria-live em conteúdo dinâmico

### UX States
- [ ] Loading state implementado
- [ ] Empty state informativo
- [ ] Error state com mensagem útil
- [ ] Success feedback presente
- [ ] Disabled state claramente indicado

### Performance
- [ ] Keys estáveis em listas (nunca index como key)
- [ ] Memoization correta (sem useMemo/useCallback desnecessário)
- [ ] Sem useEffect derivando estado (usar cálculo direto)
- [ ] Dynamic import para componentes pesados
- [ ] Next Image para imagens (se Next.js)

### Brand Compliance (AIOX)
- [ ] Tokens novos rastreiam ao brand guideline do cliente
- [ ] Sem contaminação entre clientes (tokens isolados)
- [ ] Cores/tipografia dentro do sistema aprovado

### spec.json (AIOX)
- [ ] Componente novo adicionado ao spec.json
- [ ] Variants documentadas no spec
- [ ] Classificação Atomic Design correta (atom/molecule/organism)
- [ ] Sem pulo de hierarquia (atom nao importa organism)

### DS_Score Impact
- [ ] Mudança não degrada nenhum eixo do DS_Score
- [ ] Se a11y score era < 8, mudança melhora ou mantém
- [ ] Se performance score era < 8, mudança melhora ou mantém

### Evidência
- [ ] Testado em light mode
- [ ] Testado em dark mode
- [ ] Testado em mobile (responsive)
- [ ] Testado com keyboard-only
- [ ] Visual regression passou (se configurado)
```

---

## Guia de Review por Severidade

### Items Blocking (PR NÃO deve ser aprovado)

| # | Item | Categoria | Justificativa |
|---|------|-----------|---------------|
| 1 | TypeScript props tipadas | Componentes | `any` proibido — padrão do projeto |
| 2 | Sem hardcode de cor/spacing | Tokens | Hardcode = drift futuro garantido |
| 3 | focus-visible presente | A11y | WCAG 2.2 1.4.11 — obrigatório |
| 4 | Labels em inputs | A11y | WCAG 2.2 1.3.1 — obrigatório |
| 5 | Contraste validado | A11y | WCAG 2.2 1.4.3 — obrigatório |
| 6 | Keys estáveis | Performance | Keys instáveis = re-render cascade |
| 7 | Sem contaminação entre clientes | Brand | Isolamento de marca = crítico |
| 8 | Classificação Atomic correta | spec.json | Hierarquia = composabilidade |
| 9 | Error state com mensagem | UX | Falha silenciosa = UX hostil |
| 10 | Sem conflitos de classes | Tailwind | Classes conflitantes = bug visual |

### Items Recommended (Melhorias desejáveis)

| # | Item | Categoria | Quando exigir |
|---|------|-----------|---------------|
| 1 | Compound components | Componentes | Componentes com 3+ sub-parts |
| 2 | motion-reduce | A11y | Qualquer animação CSS/JS |
| 3 | Visual regression | Evidência | Se CI tem Lost Pixel/Chromatic |
| 4 | Dynamic import | Performance | Componente > 50KB |
| 5 | Tokens nas 3 camadas | Tokens | Token novo (não reutilizando existente) |

---

## Integração com Workflows AIOX

### No Story Development Cycle (SDC)

```
@dev implementa → Percorre este checklist → Abre PR
@qa review → Valida checklist na descrição do PR → Gate decision
```

### No QA Loop

```
@qa encontra violação deste checklist → REJECT com item específico
@dev corrige → Re-submete → @qa re-valida
```

### Com CodeRabbit

CodeRabbit detecta automaticamente alguns items deste checklist:
- Conflitos de classes Tailwind
- `any` em TypeScript
- Missing labels em inputs
- Keys instáveis

Items NÃO cobertos por CodeRabbit (review manual necessário):
- Brand compliance
- spec.json coverage
- DS_Score impact
- UX states (loading/empty/error/success)
- Dark mode validation

---

## Template Compacto (para PRs pequenos)

> Use este template para PRs menores que tocam UI mas não criam componentes novos.

```markdown
## UI Quick Check
- [ ] Tokens (sem hardcode)
- [ ] A11y (focus-visible, labels, contraste)
- [ ] Tailwind (sem conflitos, mobile-first)
- [ ] UX states (loading/error)
- [ ] Light + dark mode testado
- [ ] Brand OK (sem contaminação)
```

---

**Version:** 1.0.0
**Created:** 2026-03-26
**Source:** Adaptado de Alan Lendário — Design System Audit Prompt 2, seção 9 + extensões AIOX
**Used by:** @dev (pre-PR), @qa (review), @design-system (audit)
