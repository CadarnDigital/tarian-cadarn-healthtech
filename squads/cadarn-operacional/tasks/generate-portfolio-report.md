---

## Task Definition

```yaml
task: generatePortfolioReport()
responsavel: Argus (account-orchestrator)
responsavel_type: Agente
squad: cadarn-operacional
templates:
  - monthly-portfolio-report-tmpl.yaml
tarian_portable: true
frequencia_recomendada: mensal

description: >
  Gera dois tipos de relatório: (1) Relatório de Portfólio para Fabiano —
  visão consolidada de toda a carteira, e (2) Relatório Mensal Executivo
  para o cliente — narrativa de valor com resultados, métricas e próximos passos.

Entrada:
  - campo: tipo_relatorio
    tipo: enum
    valores: [portfolio, cliente]
    obrigatório: true

  - campo: cliente
    tipo: string
    obrigatório: apenas se tipo = cliente

Saída:
  - campo: relatorio
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Relatório de Portfólio — Visão Fabiano **[DEFAULT sem argumento]**
- Consolida todos os clientes: health scores, MRR, riscos, oportunidades
- Diagnóstico da saúde da carteira como um todo
- **Trigger:** `*relatorio-portfolio`

### 2. Relatório Mensal Executivo — Visão Cliente
- Documento client-facing com resultados do mês, métricas, próximos passos
- Entregável de valor para o cliente (demonstra ROI)
- **Trigger:** `*relatorio-mensal {cliente}`

---

## Workflow — Relatório de Portfólio (Fabiano)

### Fase 1 — Coleta de Dados

```
task: |
  Coletar dados dos agentes para consolidação:

  DE ARGUS (portfólio interno):
  - Lista de clientes ativos com health scores mais recentes
  - Alertas ativos no período

  DE VAULT:
  - MRR total e por cliente
  - Comparativo vs mês anterior
  - Clientes com fatura em atraso

  DE ARC:
  - Distribuição de fase Coleman por cliente
  - Clientes em risco de churn (AFFIRM/ACCLIMATE)
  - NPS médio da carteira

  DE KAIROS:
  - % entregáveis no prazo (mês corrente)
  - Clientes com entregas atrasadas
```

### Fase 2 — Geração do Relatório de Portfólio

```
task: |
  Gerar relatório mensal de portfólio para Fabiano.
  Usar template monthly-portfolio-report-tmpl.yaml (seção: portfolio_view).

  ESTRUTURA:
  1. Executive Summary (5 linhas máximo)
     - MRR total + variação vs mês anterior
     - Distribuição de saúde (N verde / N amarelo / N vermelho)
     - Principal risco do mês
     - Principal oportunidade do mês

  2. Carteira de Clientes
     Tabela: Cliente | Segmento | Ticket | Health | Fase Coleman | Renovação | Alerta

  3. Clientes em Risco (vermelho + amarelo com detalhe)
     Para cada um: score, causa do alerta, ação recomendada, responsável, prazo

  4. Oportunidades de Expansão
     Clientes verdes prontos para upsell ou indicação

  5. Finanças da Carteira
     MRR total | Receita em risco | Receita em expansão potencial | Churn do mês

  6. Entregas do Mês
     % projetos no prazo | Clientes com atraso | Feedback crítico recebido

  7. Próximas Ações Prioritárias
     Top 5 ações para o próximo mês (cliente + ação + responsável + prazo)

output: relatorio-portfolio-{YYYY-MM}.md
```

---

## Workflow — Relatório Mensal Executivo (Cliente)

### Fase 1 — Coleta de Dados do Cliente

```
task: |
  Para o cliente {nome}, coletar dados do mês:

  DE MÉTRICA (squad-marketing):
  - Resultados de campanha (alcance, leads, conversão, etc.)
  - Comparativo vs mês anterior
  - Melhores e piores performances
  - Benchmarks do segmento (se disponível)

  DE ARC:
  - Fase Coleman atual
  - Touchpoints realizados no mês
  - NPS (se coletado no mês)

  DE KAIROS:
  - Entregáveis do mês (o que foi feito)
  - Status de prazos
  - Próximas entregas planejadas

  DO CONTRATO (Argus):
  - Objetivos dos primeiros 90 dias
  - O que foi contratado vs o que foi entregue
  - Data de renovação
```

### Fase 2 — Geração do Relatório Cliente

```
task: |
  Gerar relatório mensal executivo para o cliente {nome}.
  Usar template monthly-portfolio-report-tmpl.yaml (seção: client_report).

  REGRAS DE NARRATIVA:
  - Tom: profissional, claro, orientado a resultados — não técnico
  - Sempre conectar métricas ao objetivo do cliente (não métricas soltas)
  - Quando resultado for abaixo do esperado: explicar causa + plano de ajuste
  - Nunca omitir problemas — transparência é parte do serviço
  - Sempre terminar com: o que vem a seguir (próximas ações)

  ESTRUTURA (usar template):
  1. Destaques do Mês (3 bullets — o que foi mais relevante)
  2. Resultados vs Metas (tabela: KPI | Meta | Realizado | Status)
  3. O que fizemos (entregas do mês com contexto)
  4. Análise (o que funcionou, o que ajustaremos)
  5. Próximos 30 dias (o que está planejado)
  6. Pergunta de Engajamento (1 pergunta para abrir diálogo)

  VALIDAÇÃO ANTES DE ENVIAR:
  - [ ] Todos os KPIs têm valor real (não estimado sem aviso)
  - [ ] Problemas e ajustes estão mencionados (não apenas positivos)
  - [ ] Próximas ações são específicas (não genéricas)
  - [ ] Tom está alinhado com perfil DISC do cliente (consultar handoff)
  - [ ] Coel (brand-guardian) validou se conteúdo tem brand touchpoints corretos

output: relatorio-mensal-{cliente}-{YYYY-MM}.md
```

---

## Integração com Outros Agentes

- **Argus:** Orquestra a coleta e compila o relatório de portfólio
- **Métrica (squad-marketing):** Fornece dados de performance de campanha
- **Arc:** Fornece fase Coleman, NPS, touchpoints do cliente
- **Kairos:** Fornece lista de entregáveis e status de prazos
- **Vault:** Fornece MRR e status financeiro por cliente
- **Coel (brand-guardian):** Valida brand touchpoints antes de enviar ao cliente

---

*Squad Cadarn Operacional — Task v1.0*
*David Maister: "The deliverable is not the service — the relationship is."*
