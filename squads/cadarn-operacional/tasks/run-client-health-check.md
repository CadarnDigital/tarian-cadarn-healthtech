---

## Task Definition

```yaml
task: runClientHealthCheck()
responsavel: Argus (account-orchestrator)
responsavel_type: Agente
squad: cadarn-operacional
templates: []
tarian_portable: true
frequencia_recomendada: semanal

description: >
  Verifica proativamente o estado de saúde de todos os clientes ativos
  do portfólio. Coleta dados dos agentes especializados (Arc, Kairos, Vault),
  calcula health score por cliente, identifica alertas e gera lista de ações.

Entrada:
  - campo: lista_clientes_ativos
    tipo: list
    origem: Portfólio (Argus) ou elicitação
    obrigatório: true

Saída:
  - campo: relatorio_health_check
    tipo: markdown
    destino: File system
    persistido: true

  - campo: alertas_ativos
    tipo: list
    destino: Argus + Fabiano (se vermelho)
    persistido: true
```

---

## Execution Modes

### 1. Full Check — Todos os clientes **[DEFAULT]**
- Percorre cada cliente, coleta 5 dimensões, gera score composto
- Produz tabela consolidada com semáforos + lista de ações
- **Trigger:** `*health-check` ou `*health-check-portfolio`

### 2. Spot Check — Cliente específico
- Diagnóstico rápido de um cliente para resposta imediata
- **Trigger:** `*health-score {cliente}`

---

## Workflow — Full Check (todos os clientes)

### Fase 1 — Levantamento de Clientes Ativos

```
task: |
  Levantar lista de clientes ativos. Fontes:
  1. Portfólio interno de Argus (se já cadastrado)
  2. Elicitação com Fabiano (se portfólio não existe ainda)

  Para cada cliente, confirmar:
  - Nome / empresa
  - Data de início do contrato
  - Ticket mensal
  - Gestor de conta responsável
```

### Fase 2 — Coleta de Dados por Dimensão

```
task: |
  Para CADA cliente ativo, coletar os dados das 5 dimensões.
  Consultar agente responsável por cada dimensão:

  DIMENSÃO 1 — RESULTADO (30 pts) → Métrica (squad-marketing)
  Perguntas:
  - As métricas contratadas estão sendo atingidas? (sim/parcial/não)
  - Qual o resultado mais recente mensurável?
  - O cliente tem acesso a esses dados (dashboard/relatório)?
  Score: 30 = atingindo | 15 = parcialmente | 5 = não atingindo | 0 = sem dados

  DIMENSÃO 2 — RELACIONAMENTO (25 pts) → Arc (client-success)
  Perguntas:
  - Em qual fase Coleman o cliente está atualmente?
  - Qual foi o último touchpoint? (data + tipo)
  - Qual o NPS mais recente? (se medido)
  - Houve algum sinal de insatisfação nas últimas 2 semanas?
  Score:
    Fase Coleman: ADVOCATE/ADOPT=25 | ACCOMPLISH=20 | ACCLIMATE=12 | ACTIVATE=8 | AFFIRM=5
    Ajuste negativo: NPS < 7 → -5 pts | touchpoint > 14 dias → -5 pts

  DIMENSÃO 3 — ENTREGA (20 pts) → Kairos (gestor-processos)
  Perguntas:
  - Todos os entregáveis do mês foram entregues no prazo?
  - Há entregável em atraso hoje? (quantos dias)
  - Houve retrabalho significativo no último ciclo?
  Score: 20 = tudo no prazo | 10 = até 5 dias de atraso | 5 = >5 dias | 0 = >10 dias

  DIMENSÃO 4 — FINANCEIRO (15 pts) → Vault (financeiro)
  Perguntas:
  - Fatura do mês atual está paga?
  - Há fatura em atraso?
  Score: 15 = em dia | 8 = até 10 dias atraso | 3 = 10-20 dias | 0 = >20 dias

  DIMENSÃO 5 — EXPANSÃO (10 pts) → Arc + Caio
  Perguntas:
  - Cliente está na fase ADOPT ou ADVOCATE?
  - Cliente fez upsell ou indicou alguém nos últimos 90 dias?
  Score: 10 = indicou + upsell | 7 = um dos dois | 3 = ADOPT sem expansão | 0 = abaixo de ADOPT
```

### Fase 3 — Cálculo do Health Score

```
task: |
  Para cada cliente:

  1. Somar pontos das 5 dimensões
  2. Atribuir semáforo:
     Verde  (70-100): cliente saudável
     Amarelo (40-69): atenção necessária
     Vermelho (0-39): risco de churn — ESCALONAR

  3. Verificar THRESHOLDS DE ALERTA IMEDIATO:
     (independente do score composto — alertas absolutos)

     VERMELHO IMEDIATO:
     - NPS < 5
     - Sem touchpoint há > 21 dias
     - Entregável atrasado > 10 dias
     - Fatura atrasada > 20 dias
     - Preso em ACCLIMATE há > 45 dias

     AMARELO:
     - NPS entre 5-7
     - Sem touchpoint entre 14-21 dias
     - Entregável atrasado 5-10 dias
     - Fatura atrasada 10-20 dias
     - Sem aprovação de peça há > 10 dias

     OPORTUNIDADE (positivo):
     - NPS ≥ 9 por 2 ciclos → acionar Caio (upsell)
     - Na fase ADOPT há > 30 dias → acionar para indicação
     - Renovação em < 30 dias → preparar proposta de expansão
```

### Fase 4 — Geração do Output

```
task: |
  Gerar relatório semanal de health check:

  FORMATO DO RELATÓRIO:
  ─────────────────────────────────────────────
  HEALTH CHECK — {data}
  Portfólio: {N} clientes ativos | MRR: R$ {total}

  RESUMO:
  🟢 Verde: {N} clientes ({%} do MRR)
  🟡 Amarelo: {N} clientes ({%} do MRR)
  🔴 Vermelho: {N} clientes ({%} do MRR)

  ─── ALERTAS URGENTES (ação em <24h) ───
  [cliente vermelho com o threshold que disparou + ação recomendada]

  ─── TABELA COMPLETA ───
  | Cliente | Score | 🎯 Resultado | 💬 Rel. | 📦 Entrega | 💰 Fin. | 📈 Exp. | Alerta |
  (uma linha por cliente)

  ─── PRÓXIMAS AÇÕES ───
  [lista priorizada: cliente + ação + responsável + prazo]

  ─── OPORTUNIDADES ───
  [clientes verdes prontos para upsell ou indicação]
  ─────────────────────────────────────────────

  ESCALAMENTO AUTOMÁTICO:
  Se QUALQUER cliente estiver vermelho → gerar alert separado para Fabiano
  com: cliente, score, threshold que disparou, ação recomendada imediata.

output: health-check-{YYYY-MM-DD}.md
```

---

## Integração com Outros Agentes

- **Arc:** Fonte de fase Coleman, NPS, touchpoints — dimensão Relacionamento
- **Kairos:** Fonte de status de entregáveis — dimensão Entrega
- **Vault:** Fonte de status financeiro — dimensão Financeiro
- **Métrica (squad-marketing):** Fonte de resultados de campanha — dimensão Resultado
- **Caio:** Fonte de expansão/indicações — dimensão Expansão
- **Fabiano:** Recebe escalamentos de clientes vermelhos em <24h

---

*Squad Cadarn Operacional — Task v1.0*
*Framework: Lincoln Murphy — Customer Success at Scale + David Maister*
