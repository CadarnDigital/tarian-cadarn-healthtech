---

## Task Definition

```yaml
task: runOperationalDiagnostic()
responsavel: Scala (Líder Operacional)
responsavel_type: Agente
squad: cadarn-operacional
templates:
  - operational-diagnostic-tmpl.yaml
  - gametape-review-tmpl.yaml
tarian_portable: true

description: >
  Executa diagnóstico completo de saúde operacional: coleta KPIs dos 4 agentes
  da squad, avalia 5 áreas, identifica área mais fraca e gera plano de ação
  de 90 dias. Opcionalmente inclui primeira sessão de Gametape Review.

Entrada:
  - campo: contexto_operacional
    tipo: object
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: relatorio_diagnostico
    tipo: markdown
    destino: File system
    persistido: true

  - campo: plano_acao_90dias
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Health Check — Rápido (1-2 prompts)
- Coleta 7 KPIs + scoring rápido por área
- Sem diagnóstico profundo
- **Trigger:** `*health-check`

### 2. Diagnóstico Completo — Full (5-7 prompts) **[DEFAULT]**
- Elicita contexto, coleta dados de cada agente
- Diagnóstico por área com evidências
- Plano de ação de 90 dias
- **Trigger:** `*diagnostico`

### 3. Gametape Review — Sessão (2-3 prompts)
- Facilita uma sessão de revisão de interação
- **Trigger:** `*gametape {tipo}`

---

## Workflow — Diagnóstico Completo

### Fase 1 — Elicitação de Contexto

**Passo 1: Visão Geral**
```
elicit: true
prompt: |
  Vou fazer um diagnóstico completo da saúde operacional.
  Preciso de uma visão geral primeiro.

  1. Nome da empresa/operação?
  2. Quantas pessoas no time?
  3. Há quantos meses está operando?
  4. Qual a maior dor operacional HOJE? (em uma frase)
  5. Último diagnóstico operacional foi quando? (se já fez)
```

### Fase 2 — Coleta de KPIs (delegar para agentes)

```
task: |
  Coletar os 7 KPIs. Para cada um, verificar se o dado existe:

  Se dado EXISTE (sistema, planilha, dashboard):
    → Registrar valor atual

  Se dado NÃO EXISTE:
    → Registrar como "Não medido" (isso por si só é um achado do diagnóstico)
    → Estimar com base no contexto se possível

  Fontes por KPI:
  - KPI-1 (MRR): perguntar ao usuário ou Vault
  - KPI-2 (Churn): perguntar ao usuário ou Arc
  - KPI-3 (Prazo): perguntar ao usuário ou Kairos
  - KPI-4 (NPS): perguntar ao usuário ou Arc
  - KPI-5 (Horas/Entregável): perguntar ao usuário ou Kairos
  - KPI-6 (Happiness): perguntar ao usuário ou Nexus
  - KPI-7 (Profit Margin): perguntar ao usuário ou Vault
```

**Passo 2: KPIs**
```
elicit: true
prompt: |
  Agora os números. Para cada KPI, me diga o valor atual.
  Se não sabe, diga "não meço":

  1. MRR (Receita Recorrente Mensal): R$___
  2. Churn Rate (% clientes perdidos/mês): ___%
  3. % Projetos no Prazo: ___%
  4. NPS do Cliente (último medido): ___
  5. Horas médias por entregável: ___h
  6. Happiness Metric do time (1-5): ___
  7. Margem de lucro (%): ___%
```

### Fase 3 — Diagnóstico por Área

**Passo 3: Entrega/Operações**
```
elicit: true
prompt: |
  Área 1 — Entrega e Operações (domínio do Kairos):

  1. Processos-chave estão documentados (SOPs)?
  2. Usam ferramenta de gestão de projetos? Qual?
  3. Existem automações (Make, n8n, nativas)?
  4. Há retrabalho significativo? Em quais áreas?
  5. Time sabe o que fazer sem perguntar ao líder?
```

**Passo 4: Finanças + Pessoas + Clientes + Sistemas**
```
elicit: true
prompt: |
  Agora as outras 4 áreas de uma vez (respostas curtas):

  Financeiro (Vault):
  - Profit First implementado? (sim/não/parcial)
  - Tem reserva de caixa? (quantos meses)
  - Precificação é por valor ou por hora?

  Pessoas (Nexus):
  - Working Genius do time mapeado? (sim/não)
  - Reuniões são estruturadas? (4 tipos ou ad hoc)
  - Expectativas estão escritas ou são verbais?

  Clientes (Arc):
  - Tem processo de onboarding do cliente? (sim/não/informal)
  - Contata o cliente em <24h após fechamento?
  - Clientes indicam espontaneamente?

  Sistemas/Escala (Scala):
  - Negócio funciona se você tirar 1 semana de férias?
  - Decision trees existem para decisões recorrentes?
  - Faz Gametape Review ou algo similar?
```

### Fase 4 — Análise e Scoring

```
task: |
  Com todos os dados coletados:

  1. SCORING POR ÁREA (verde/amarelo/vermelho):
     - Entrega/Operações: ___
     - Financeiro: ___
     - Pessoas/Cultura: ___
     - Clientes/Retenção: ___
     - Sistemas/Escala: ___

  2. KPIs com SEMÁFORO:
     - Verde: dentro da meta
     - Amarelo: próximo da meta
     - Vermelho: longe da meta
     - Cinza: não medido (gap de medição)

  3. ÁREA FOCO: a mais fraca (vermelho > amarelo > cinza)

  4. TOP 3 ACHADOS (insights mais relevantes):
     Achados não óbvios que conectam áreas

  5. PLANO DE AÇÃO (máx 5 ações em 90 dias):
     Focado na área mais fraca
     Cada ação com: responsável (agente), prazo, KPI impactado

output: relatorio-diagnostico-{empresa}.md
```

### Fase 5 — Entrega

```
task: |
  Gerar 2 documentos:

  1. Relatório de Diagnóstico (completo):
     - Resumo executivo (1 parágrafo)
     - Score geral + por área
     - 7 KPIs com semáforo
     - Análise por área com evidências
     - Top 3 achados

  2. Plano de Ação 90 Dias (executável):
     | # | Ação | Agente | Prazo | KPI | Prioridade |
     (máximo 5 ações, ordenadas por impacto)

  3. Agendar próximo diagnóstico: daqui a 90 dias

output:
  - relatorio-diagnostico-{empresa}.md
  - plano-acao-90d-{empresa}.md
```

---

## Workflow — Gametape Review (sessão)

### Passo 1
```
elicit: true
prompt: |
  Vamos fazer uma sessão de Gametape Review.

  1. Tipo: vendas, atendimento, reunião ou entrega?
  2. Quem participou da interação?
  3. Tem gravação/registro? (link, prints, descrição)
  4. Quem vai participar da revisão hoje?
```

### Passo 2 — Facilitar os 7 passos

```
task: |
  Facilitar a sessão seguindo os 7 passos do template:

  1. GRAVAR: confirmar que temos o registro
  2. SELECIONAR: já selecionado na elicitação
  3. ASSISTIR: guiar o grupo para revisar sem interrupção
  4. ANOTAR: usar formato | Momento | Funcionou | Não funcionou | Faria diferente |
  5. DISCUTIR: começar pelo positivo, foco em comportamento
  6. IDENTIFICAR PADRÃO: recorrente ou pontual?
  7. AÇÃO: definir pelo menos 1 ação concreta

  Gerar ata da sessão usando template do gametape-review-tmpl.yaml

output: gametape-{data}-{tipo}.md
```

---

## Output — Arquivos Gerados

### Diagnóstico
```
{output_dir}/
├── relatorio-diagnostico-{empresa}.md    # Diagnóstico completo
└── plano-acao-90d-{empresa}.md           # Plano executável
```

### Gametape
```
{output_dir}/
└── gametape-{data}-{tipo}.md             # Ata da sessão
```

**Output dir padrão:** `docs/operacional/diagnosticos/`

---

## Integração com Outros Agentes

- **Vault:** Fornece KPI-1 (MRR) e KPI-7 (Margem) + diagnóstico Fix This Next
- **Kairos:** Fornece KPI-3 (Prazo) e KPI-5 (Horas/Entregável) + auditoria de processos
- **Nexus:** Fornece KPI-6 (Happiness) + diagnóstico Five Dysfunctions
- **Arc:** Fornece KPI-2 (Churn) e KPI-4 (NPS) + diagnóstico de jornada

Scala ORQUESTRA — cada agente fornece dados do seu domínio.

---

*Squad Cadarn Operacional — Task v1.0*
*Framework: Leila Hormozi — Scaling Systems + Gametape Review*
