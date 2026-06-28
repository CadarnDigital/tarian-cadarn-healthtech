---

## Task Definition

```yaml
task: runDiagnostic()
responsavel: Clarissa (Consultora Sênior)
responsavel_type: Agente
squad: cadarn-marketing
templates:
  - diagnostico-multicanal-tmpl.yaml
tarian_portable: true

description: >
  Diagnóstico multicanal completo seguindo Metodologia CR+ (Etapa 1):
  fotografia da presença digital, público, concorrência, SWOT digital,
  análise de canais e recomendações iniciais. Entrada obrigatória para
  qualquer plano de marketing.

Entrada:
  - campo: contexto_cliente
    tipo: object
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: diagnostico_completo
    tipo: markdown
    destino: File system
    persistido: true

  - campo: swot_digital
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. YOLO Mode — Fast (0-1 prompts)
- Cliente já descrito com dados de presença digital
- Gera diagnóstico direto a partir dos dados fornecidos
- **Best for:** Renovação de diagnóstico, cliente já mapeado

### 2. Interactive Mode — Balanced (6-8 prompts) **[DEFAULT]**
- Elicita dados do cliente passo a passo
- Valida cada componente com o usuário
- **Best for:** Primeiro diagnóstico, cliente novo

### 3. Pre-Flight Mode — Deep (10-12 prompts)
- Pesquisa ativa nas redes do cliente
- Benchmarking com concorrentes reais
- **Best for:** Proposta de alto valor, imersão completa

---

## Workflow — Modo Interactive

### STEP 1 — Briefing e Contexto (elicit)

```yaml
elicit:
  prompt: |
    Para um diagnóstico completo, preciso entender:
    1. Nome do negócio e segmento
    2. Público-alvo atual (quem compra hoje?)
    3. Canais digitais ativos (Instagram, site, Google, WhatsApp, etc.)
    4. Objetivo principal (mais leads? Mais vendas? Posicionamento?)
    5. Orçamento atual com marketing (se houver)
    6. Maior dor hoje

  validate:
    required: [nome_negocio, segmento, canais_ativos, objetivo]
```

### STEP 2 — Análise de Mercado e Concorrência

```yaml
action: analyze
agent: Clarissa
steps:
  - Identificar 3-5 concorrentes diretos
  - Benchmark de presença digital (seguidores, frequência, formatos)
  - Identificar gaps de mercado (o que ninguém faz bem)
  - Mapear referências/inspirações do segmento
```

### STEP 3 — Auditoria de Canais

```yaml
action: audit
agent: Clarissa
channels:
  - instagram: bio, frequência, formatos, engajamento, estética
  - site: SEO básico, velocidade, mobile, CTA, conversão
  - google: GMB, reviews, posicionamento orgânico
  - whatsapp: uso comercial, catálogo, automações
  - email: lista, frequência, taxa de abertura
  - outros: TikTok, YouTube, LinkedIn (se aplicável)
```

### STEP 4 — SWOT Digital

```yaml
action: generate
agent: Clarissa
output: swot_digital
format: |
  FORÇAS (internas, positivas)
  FRAQUEZAS (internas, negativas)
  OPORTUNIDADES (externas, positivas)
  AMEAÇAS (externas, negativas)

  + Cruzamento TOWS: FO, FA, DO, DA → ações derivadas
```

### STEP 5 — Diagnóstico Consolidado

```yaml
action: generate
agent: Clarissa
template: diagnostico-multicanal-tmpl.yaml
output: diagnostico_completo
sections:
  - resumo_executivo
  - perfil_do_negocio
  - analise_de_mercado
  - auditoria_de_canais
  - swot_digital
  - posicionamento_atual (6 pilares)
  - kpis_estrelas_guia (máximo 3)
  - recomendacoes_iniciais
  - proximo_passo
```

### STEP 6 — Validação (elicit)

```yaml
elicit:
  prompt: |
    📋 Diagnóstico pronto. Revise e me diga:
    1. Algum dado incorreto?
    2. Faltou algum canal relevante?
    3. As recomendações fazem sentido para a realidade do negócio?
```

---

## Quality Gates

- [ ] Todos os 7 componentes do diagnóstico presentes
- [ ] SWOT com cruzamento TOWS (não só lista)
- [ ] Máximo 3 KPIs estrelas-guia definidos
- [ ] Recomendações acionáveis (não genéricas)
- [ ] Posicionamento avaliado nos 6 pilares
- [ ] Próximo passo claro e concreto

---

## Cross-Squad Integration

| Squad | Quando acionar | O que fornecer |
|-------|---------------|----------------|
| **Jurídica** | Se diagnóstico revelar LGPD gaps | Dados coletados para @shield |
| **Operacional** | Se dor for processual (não marketing) | Encaminhar para @scala |
| **Comercial** | Se pipeline de vendas for o gargalo | Dados para lead qualification |

---

*Squad Cadarn Marketing — Task: Diagnóstico Multicanal*
*Agente: Clarissa (Metodologia CR+)*
