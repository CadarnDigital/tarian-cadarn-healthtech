---

## Task Definition

```yaml
task: runPerformanceAnalysis()
responsavel: Métrica (Analytics de Conteúdo)
responsavel_type: Agente
squad: cadarn-marketing
templates:
  - relatorio-campanha-tmpl.yaml
tarian_portable: true

description: >
  Análise de performance integrada seguindo Pirâmide de Dados (Kiso):
  métricas de conteúdo orgânico + pago, diagnóstico de causa raiz,
  detecção de corrupção de audiência, análise de Reels, frequência
  como saturação e recomendações acionáveis.

Entrada:
  - campo: dados_performance
    tipo: object
    origem: Elicitação ou GA4/Meta Ads
    obrigatório: true

Saída:
  - campo: relatorio_performance
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Quick Mode — Snapshot (1-2 prompts)
- Dados já fornecidos (print ou CSV)
- Gera análise rápida com diagnóstico
- **Best for:** Check semanal

### 2. Full Mode — Relatório completo (3-5 prompts) **[DEFAULT]**
- Coleta dados de múltiplos canais
- Análise cruzada orgânico + pago
- **Best for:** Relatório mensal, apresentação para cliente

---

## Workflow — Modo Full

### STEP 1 — Coleta de Dados (elicit)

```yaml
elicit:
  prompt: |
    Para a análise de performance, preciso dos dados:
    1. Período de análise (últimos 7, 14, 30 dias?)
    2. Instagram Insights: alcance, impressões, engajamento, seguidores
    3. Top 3 posts (métricas de cada)
    4. Meta Ads (se ativo): spend, impressões, cliques, leads/vendas
    5. Site (se ativo): sessões, bounce rate, conversões
    6. WhatsApp (se ativo): mensagens recebidas, respondidas
```

### STEP 2 — Pirâmide de Dados (Kiso)

```yaml
action: analyze
agent: Métrica
framework: Pirâmide de Dados
layers:
  base: "Métricas de vaidade (alcance, impressões, seguidores)"
  meio: "Métricas de engajamento (saves, shares, comments, DMs)"
  topo: "Métricas de negócio (leads, vendas, ROAS, LTV)"

output: |
  DIAGNÓSTICO POR CAMADA:
  Base → O conteúdo está sendo VISTO? (alcance)
  Meio → O conteúdo está RESSONANDO? (engajamento)
  Topo → O conteúdo está CONVERTENDO? (negócio)

  Se base alta + meio baixo → conteúdo genérico, não ressoa
  Se meio alto + topo baixo → falta CTA ou oferta fraca
  Se tudo baixo → problema de distribuição ou público errado
```

### STEP 3 — Diagnósticos Especializados

```yaml
action: analyze
agent: Métrica
diagnostics:

  audience_corruption:
    check: "Seguidores crescem mas engajamento cai?"
    cause: "Audiência corrompida — seguidores fora do ICP"
    action: "Parar sorteio/viral vazio, focar em conteúdo de nicho"

  reel_diagnostic:
    check: "Reel com alcance alto mas saves/shares baixo?"
    cause: "Entretenimento puro sem valor — não gera lembrança"
    action: "Adicionar gancho de valor nos primeiros 3s"

  frequency_saturation:
    check: "CTR caindo com frequência alta?"
    cause: "Saturação de criativo — mesmo público vendo muitas vezes"
    action: "Renovar criativos ou expandir público"

  organic_decay:
    check: "Alcance orgânico caindo mês a mês?"
    cause_options:
      - "Algoritmo penalizando (frequência irregular)"
      - "Conteúdo perdeu relevância"
      - "Formato desatualizado"
    action: "Testar novos formatos, verificar Golden Hour"
```

### STEP 4 — Integração Orgânico + Pago

```yaml
action: analyze
agent: Métrica
cross_analysis:
  - "Alcance alto + conversão baixa → público errado ou criativo fraco"
  - "CTR alta + conversão baixa → landing page inadequada"
  - "Post com baixo engajamento orgânico → NÃO usar como anúncio"
  - "Post com alto save/share orgânico → promover com verba"
```

### STEP 5 — Relatório Final

```yaml
action: generate
template: relatorio-campanha-tmpl.yaml
output: relatorio_performance
sections:
  - resumo_executivo: "3 bullets: o que funcionou, o que não funcionou, próximo passo"
  - metricas_periodo: "Tabela comparativa (período atual vs anterior)"
  - piramide_dados: "Diagnóstico por camada"
  - top_conteudos: "Top 3 + análise de por que funcionaram"
  - diagnosticos: "Problemas detectados + causa raiz"
  - recomendacoes: "Ações concretas para o próximo período"
  - kpis_estrelas_guia: "3 KPIs para acompanhar"
```

---

## Quality Gates

- [ ] Diagnóstico por camada da pirâmide presente
- [ ] Comparativo período atual vs anterior
- [ ] Causa raiz identificada (não só sintoma)
- [ ] Top 3 conteúdos analisados
- [ ] Recomendações acionáveis (não genéricas)
- [ ] Máximo 3 KPIs estrelas-guia definidos

---

*Squad Cadarn Marketing — Task: Performance Analysis*
*Agente: Métrica (Pirâmide de Dados — Kiso)*
