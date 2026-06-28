---
paths:
  - "docs/stories/**"
---
# Forja Wave-Close Gate — Auditoria Obrigatória Entre Waves

## Regra Principal

Nenhuma story da wave N+1 pode ser draftada por @sm sem que o Wave-Close Gate da wave N tenha sido concluído com veredicto registrado — incluindo obrigatoriamente uma recomendação sobre o PRD.

## Quando se aplica

Toda vez que uma wave (ou unidade equivalente de trabalho planejado) é marcada como concluída, antes de @sm draftar qualquer story nova.

O gate se aplica a:
- Waves do EXECUTION-PLAN (Wave A, Wave B, etc.)
- Fases completas (F0, F1, F2…) quando não há subdivisão em waves
- Marcos equivalentes: "sprint", "batch" ou qualquer agrupamento definido no EXECUTION-PLAN

## Participantes

| Agente | Papel no gate |
|--------|---------------|
| Morgan (PM) | Checklist de produto — ACs, dívidas, EXECUTION-PLAN |
| Cosmo (Design System) | Checklist de DS — consistência, catálogo de componentes |

Morgan conduz o gate. Cosmo participa quando a wave contiver entregas de interface, tokens, componentes ou qualquer coisa ligada ao DS. Se a wave for exclusivamente backend/infra, Cosmo responde com uma linha e encerra.

## Protocolo de execução

### PASSO 1 — Acionamento

O gate começa com sinal explícito de Fabiano ou Morgan. Formas válidas:

- Fabiano diz "fecha a Wave X", "audita a Wave X", "wave-close Wave X"
- Morgan identifica que a última story da wave foi marcada Done e propõe o gate a Fabiano

### PASSO 2 — Checklist Morgan (produto)

Morgan verifica cada item e marca ✅ ou ⚠️ com comentário quando necessário:

```
[ ] 1. Todas as ACs de todas as stories da wave foram cumpridas?
[ ] 2. Alguma story foi marcada Done com AC parcial ou desvio não documentado?
[ ] 3. A wave gerou dívida de produto (mudança de comportamento, edge case novo, decisão adiada)?
[ ] 4. O EXECUTION-PLAN está coerente com o que foi realmente entregue?
[ ] 5. Alguma decisão tomada durante a wave invalidou premissa do PRD?
```

### PASSO 3 — Checklist Cosmo (design system)

Cosmo verifica cada item e marca ✅ ou ⚠️:

```
[ ] 1. Alguma entrega da wave criou componente não catalogado no DS?
[ ] 2. Alguma entrega criou inconsistência com tokens existentes?
[ ] 3. Algum padrão novo emergiu que precisa virar spec antes da próxima wave?
[ ] 4. O sistema de tipos e variantes está coerente após as entregas?
```

Se a wave não tiver impacto em interface ou DS, Cosmo responde:
> `"Sem impacto DS — checklist não aplicável para esta wave."`

### PASSO 4 — Veredicto (obrigatório)

Morgan emite o veredicto com dois elementos. Nenhum gate encerra sem os dois.

**Elemento 1 — Status do gate:**

| Status | Significado |
|--------|-------------|
| ✅ PASS | Sem pendências. Próxima wave pode ser iniciada. |
| ⚠️ PASS COM RESSALVAS | Pode iniciar próxima wave, mas há itens a monitorar registrados. |
| 🔴 BLOCKED | Há dívida crítica ou invalidação de premissa. Próxima wave aguarda resolução. |

**Elemento 2 — Recomendação PRD (obrigatório em todo veredicto):**

Morgan emite uma das três opções abaixo, sempre com justificativa:

- `PRD não requer atualização` — a wave entregou exatamente o planejado; o PRD segue válido.
- `PRD requer atualização — seções: {lista}` — especificar quais seções e o que mudou.
- `PRD requer revisão completa` — decisões da wave invalidaram premissas estruturais.

### PASSO 5 — Registro

Morgan registra o veredicto em `docs/{projeto}/wave-close/{wave-id}.md`.

Formato mínimo do arquivo de gate:

```markdown
# Wave-Close: {wave-id}
**Data:** {YYYY-MM-DD}
**Status:** {PASS | PASS COM RESSALVAS | BLOCKED}

## Checklist Morgan
{itens com status}

## Checklist Cosmo
{itens com status ou "não aplicável"}

## Veredicto
{texto}

## Recomendação PRD
{uma das três opções + justificativa}
```

## Bloqueio da próxima wave

Enquanto o gate não tiver veredicto registrado, @sm **não pode draftar** stories da próxima wave.

Se @sm for convocado antes do gate:
1. Verificar se existe arquivo de gate para a wave anterior em `docs/{projeto}/wave-close/`
2. Se não existir: sinalizar `"Wave-Close Gate pendente para {wave-id} — acione Morgan antes de draftar"`
3. Aguardar Fabiano resolver

## Quando NÃO se aplica

- Hotfixes e patches urgentes fora de wave planejada (não bloqueiam o gate, mas são registrados como dívida no próximo gate)
- Stories isoladas que nunca pertenceram a uma wave definida no EXECUTION-PLAN

## Relação com outras regras

- **`story-lifecycle.md`** — o gate é um pré-requisito para a transição de status que abre a próxima wave
- **`agent-authority.md`** — @sm é bloqueado por esta regra; Morgan conduz, Cosmo participa
- **`specialist-handoff-mandatory.md`** — se o gate revelar necessidade de outro especialista, handoff mandatório antes de prosseguir

## Severidade

**MUST** para Squad Forja — toda transição entre waves formalizadas no EXECUTION-PLAN.

---

*Rule: forja-wave-close-gate | Criada: 2026-04-26 | Proposta por: Morgan (PM) | Autoridade: Fabiano | Severidade: MUST*
