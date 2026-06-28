---

## Task Definition

```yaml
task: planPaidMedia()
responsavel: Mídia (Gestor de Tráfego Pago)
responsavel_type: Agente
squad: cadarn-marketing
templates:
  - plano-midia-paga-tmpl.yaml
tarian_portable: true
depends_on:
  - run-diagnostic (recomendado)
  - create-content-strategy (recomendado)

description: >
  Planejamento de mídia paga seguindo Metodologia Sobral:
  estrutura de campanhas (Perpétua/Lançamento/Diária), segmentação
  hierárquica (quente→morno→frio), nomenclatura padrão, testes
  Ninja/Boladão, métrica principal por campanha e engenharia de verba.

Entrada:
  - campo: contexto_midia
    tipo: object
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: plano_midia
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. YOLO Mode — Fast (0-1 prompts)
- Verba e objetivo já definidos
- **Best for:** Renovação de plano mensal

### 2. Interactive Mode — Balanced (4-6 prompts) **[DEFAULT]**
- Elicita verba, objetivo, público e histórico
- **Best for:** Primeiro plano de mídia

---

## Workflow — Modo Interactive

### STEP 1 — Briefing de Mídia (elicit)

```yaml
elicit:
  prompt: |
    Para montar o plano de mídia paga:
    1. Verba mensal disponível (R$)
    2. Plataforma principal: Meta Ads? Google Ads? Ambos?
    3. Objetivo: Leads? Vendas? Reconhecimento? Tráfego?
    4. Já rodou anúncios antes? (Se sim, resultados recentes)
    5. Tem pixel/tag instalado?
    6. Negócio local ou nacional?
```

### STEP 2 — Estrutura de Campanhas (Sobral)

```yaml
action: generate
agent: Mídia
framework: Metodologia Sobral
output: estrutura_campanhas
format: |
  3 TIPOS DE CAMPANHA:

  PERPÉTUA [CONTINUA] — Always-on, otimização contínua
  - Objetivo: conversão/leads recorrentes
  - Segmentação: público quente (remarketing, lookalike)
  - Verba: 60-70% do total

  LANÇAMENTO [TESTE] — Início em teste, escala se validar
  - Objetivo: testar nova oferta/criativo/público
  - Segmentação: morno → frio
  - Verba: 20-30% do total

  DIÁRIA — Oferta do dia, evento, urgência
  - Objetivo: conversão imediata
  - Segmentação: quente (base existente)
  - Verba: 5-10% do total
```

### STEP 3 — Segmentação Hierárquica

```yaml
action: generate
agent: Mídia
output: segmentacao
format: |
  QUENTE (prioridade máxima):
  - Visitou site (pixel)
  - Engajou Instagram (últimos 30/60/90d)
  - Lista de clientes/leads (upload)
  - Lookalike 1% dos clientes

  MORNO:
  - Lookalike 2-3% dos clientes
  - Interesses específicos + localização
  - Seguidores de concorrentes (se disponível)

  FRIO:
  - Interesses amplos + demográfico
  - Lookalike 5-10%
  - Broad (sem segmentação — deixar algoritmo)
```

### STEP 4 — Engenharia de Verba

```yaml
action: generate
agent: Mídia
output: distribuicao_verba
format: |
  VERBA TOTAL: R$ {{verba_mensal}}

  | Tipo | % | R$ | Campanhas |
  |------|---|----|-----------|
  | Perpétua | 65% | R$ X | [lista] |
  | Lançamento | 25% | R$ X | [lista] |
  | Diária | 10% | R$ X | [lista] |

  REGRAS SOBRAL:
  - Se negócio local: mínimo R$20/dia por campanha
  - Teste Ninja: R$10/dia por 3 dias → mata ou escala
  - Teste Boladão: R$50/dia → dados rápidos para decisão
  - Andrômeda: R$100+/dia → escala agressiva pós-validação
```

### STEP 5 — Nomenclatura e Métricas

```yaml
action: generate
agent: Mídia
output: nomenclatura_metricas
format: |
  NOMENCLATURA PADRÃO:
  [TIPO] | [OBJETIVO] | [PÚBLICO] | [CRIATIVO] | [DATA]
  Ex: [CONTINUA] | LEADS | LOOKALIKE-1% | CARROSSEL-V2 | 2026-04

  MÉTRICA PRINCIPAL (1 por campanha — NUNCA misturar):
  - Campanha de leads → CPL (Custo por Lead)
  - Campanha de vendas → ROAS ou CPA
  - Campanha de alcance → CPM
  - Campanha de tráfego → CPC

  REGRA: Se não sabe a métrica, NÃO rode a campanha.
```

### STEP 6 — Plano Final

```yaml
action: generate
template: plano-midia-paga-tmpl.yaml
output: plano_midia
```

---

## Quality Gates

- [ ] 3 tipos de campanha estruturados
- [ ] Segmentação hierárquica (quente→morno→frio)
- [ ] Verba distribuída com percentuais claros
- [ ] Nomenclatura padrão definida
- [ ] 1 métrica principal por campanha
- [ ] Pixel/tag verificado
- [ ] Regras de teste (Ninja/Boladão) aplicadas

---

## Cross-Squad Integration

| Squad | Quando acionar | O que fornecer |
|-------|---------------|----------------|
| **Jurídica** | Anúncio de oferta | @aequitas valida CDC + CONAR |
| **Jurídica** | Anúncio imobiliário | @praedium valida CRECI |
| **Operacional** | Budget approval | @vault valida verba no Profit First |

---

*Squad Cadarn Marketing — Task: Paid Media Planning*
*Agente: Mídia (Metodologia Sobral)*
