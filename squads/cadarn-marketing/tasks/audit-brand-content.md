---

## Task Definition

```yaml
task: auditBrandContent()
responsavel: Coel (Brand Guardian)
responsavel_type: Agente
squad: cadarn-marketing
templates:
  - auditoria-primal-code-tmpl.yaml
tarian_portable: true
cross_squad: true

description: >
  Auditoria de conteúdo pelo Primal Code® de Patrick Hanlon.
  Pipeline completo de 5 etapas: Scanner de Identidade, Teste de Coerência,
  Teste do Inimigo, Força do Belief System e Veredito Final.
  Opera em Modo Guardião (conteúdo público) ou Modo Conselheiro (mesa redonda).

Entrada:
  - campo: peca_ou_lote
    tipo: string | string[]
    origem: Elicitação ou output de create-content-batch
    obrigatório: true

Saída:
  - campo: auditoria
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Single Mode — 1 peça
- Audita uma peça específica
- **Best for:** Validação pontual antes de publicar

### 2. Batch Mode — Lote completo **[DEFAULT]**
- Audita todas as peças de um batch de conteúdo
- Gera relatório consolidado com score por peça
- **Best for:** QA do batch semanal

### 3. Conselheiro Mode — Mesa redonda
- Parecer leve sobre artefato de qualquer squad
- **Trigger:** `*parecer {artefato}`

---

## Workflow — Modo Batch

### STEP 1 — Receber Lote

```yaml
action: load
input: batch de conteúdo (output de create-content-batch)
parse: "Separar cada peça individual para auditoria sequencial"
```

### STEP 2 — Para Cada Peça: Pipeline 5 Etapas

```yaml
for_each: peca in lote

etapa_1_scanner:
  action: "Mapear 7 elementos: PRESENTE (2pts), PARCIAL (1pt), AUSENTE (0pts)"
  output: score_identidade (máx 14pts)
  limiares:
    reel_autoridade: 8
    carrossel_educativo: 6
    stories_bastidores: 5
    post_oferta: 7

etapa_2_coerencia:
  action: "Testar coerência com DNA da marca"
  checks:
    - "Coerência com Creation Story e Creed"
    - "Tom de voz do Leader"
    - "Sacred Words presentes?"

etapa_3_inimigo:
  action: "Classificar contraste"
  levels: [DECLARA, IMPLICA, POSICIONA, NEUTRA]
  alert: "Post de oferta sem Pagans = CRÍTICO"

etapa_4_belief:
  action: "A peça contribui para o sistema de crença?"
  levels: [REFORÇA, NEUTRA, ENFRAQUECE]

etapa_5_veredito:
  action: "Veredito final"
  options:
    - APROVADO
    - APROVADO_COM_RESSALVAS
    - REVISAO_NECESSARIA
    - PAUSADO_ESCALAR_FABIANO
```

### STEP 3 — Relatório Consolidado

```yaml
action: generate
template: auditoria-primal-code-tmpl.yaml
output: auditoria
sections:
  - resumo_executivo: "X aprovadas, Y com ressalvas, Z para revisão"
  - tabela_por_peca: "Peça | Score /14 | Veredito | Ação"
  - padroes_detectados: "Gaps recorrentes no lote"
  - recomendacoes: "Ações corretivas específicas"
```

### STEP 4 — Escalação (se necessário)

```yaml
condition: "Se alguma peça = PAUSADO_ESCALAR_FABIANO"
action: alert
format: "⚠️ PAUSA — Escalar para Fabiano: [motivo]. Aguardando decisão."
```

---

## Quality Gates

- [ ] Todas as peças passaram pelas 5 etapas
- [ ] Score /14 calculado para cada peça
- [ ] Veredito claro por peça
- [ ] Padrões recorrentes identificados
- [ ] Escalações feitas quando necessário

---

*Squad Cadarn Marketing — Task: Brand Content Audit*
*Agente: Coel (Primal Code® — Patrick Hanlon)*
