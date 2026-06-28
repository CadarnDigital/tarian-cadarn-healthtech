---

## Task Definition

```yaml
task: createContentBatch()
responsavel: Logos (Copy) + Magnética (Roteiro) + Iris (Dir. Criativa) + Pixel (Design)
responsavel_type: Agente
squad: cadarn-marketing
templates:
  - briefing-conteudo-tmpl.yaml
tarian_portable: true
depends_on:
  - create-content-strategy (obrigatório — precisa do calendário)

description: >
  Produção de conteúdo em lote a partir do calendário editorial.
  Para cada slot do calendário, gera: copy, roteiro (se vídeo),
  direção criativa e briefing de design. Pipeline multi-agente
  sequencial com handoff entre camadas.

Entrada:
  - campo: calendario_editorial
    tipo: yaml
    origem: Task create-content-strategy
    obrigatório: true

  - campo: quantidade_slots
    tipo: number
    origem: Elicitação
    default: 7 (1 semana)

Saída:
  - campo: batch_conteudo
    tipo: markdown[]
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. YOLO Mode — Fast (0-1 prompts)
- Calendário existe, brand positioning definido
- Gera batch completo direto
- **Best for:** Produção semanal recorrente

### 2. Interactive Mode — Balanced (2-3 prompts) **[DEFAULT]**
- Confirma slots a produzir, valida tom/referências
- **Best for:** Primeiro batch, cliente novo

---

## Workflow — Pipeline Multi-Agente

### STEP 1 — Selecionar Slots (elicit)

```yaml
elicit:
  prompt: |
    Do calendário editorial, quantos slots quer produzir agora?
    1. Próximos 7 dias (1 semana)
    2. Próximos 14 dias (2 semanas)
    3. Slots específicos (informar quais)
```

### STEP 2 — Copy (Logos)

```yaml
action: generate
agent: Logos (Copywriter)
for_each: slot selecionado
output_per_slot:
  - headline: "Gancho principal (Hormozi pattern)"
  - body: "Corpo do texto (Ícaro storytelling)"
  - cta: "Call to action (regra: 1 CTA por peça)"
  - hashtags: "Se Instagram (máx 5)"
  - caption_alt: "Versão alternativa para teste A/B (se solicitado)"

rules:
  - "NUNCA copy genérica — sempre com Sacred Words do cliente"
  - "NUNCA múltiplos CTAs — 1 por peça"
  - "Carrossel: 1 gancho + 1 ideia por slide + CTA final"
  - "Reel: gancho nos primeiros 3 segundos"
```

### STEP 3 — Roteiro (Magnética) — SE vídeo

```yaml
condition: "slot.formato in [Reel, Video, Live, YouTube]"
action: generate
agent: Magnética (Roteirista)
for_each: slot de vídeo
output_per_slot:
  - gancho: "Primeiros 3 segundos (7 tipos de gancho Becker)"
  - desenvolvimento: "Corpo do roteiro com timestamps"
  - cta_falado: "CTA no roteiro"
  - duracao_estimada: "Em segundos"
  - notas_producao: "Cenário, iluminação, props"
```

### STEP 4 — Direção Criativa (Iris)

```yaml
action: generate
agent: Iris (Diretora Criativa)
for_each: slot selecionado
output_per_slot:
  - conceito_visual: "Direção visual da peça"
  - referencias: "Moodboard descritivo (cores, texturas, mood)"
  - layout: "Estrutura visual (grid, hierarquia)"
  - tipografia: "Uso de tipos conforme brand guidelines"
  - notas_pixel: "Instruções específicas para o designer"
```

### STEP 5 — Briefing de Design (consolidado)

```yaml
action: generate
template: briefing-conteudo-tmpl.yaml
for_each: slot selecionado
consolidate:
  - copy (de Logos)
  - roteiro (de Magnética, se vídeo)
  - direcao_criativa (de Iris)
  - brand_guidelines (do cliente)
output: briefing pronto para Pixel executar
```

### STEP 6 — Design (Pixel) — OPCIONAL nesta task

```yaml
condition: "Se Canva MCP estiver ativo e autenticado"
action: generate
agent: Pixel (Designer)
for_each: slot selecionado
output_per_slot:
  - design_url: "Link do Canva ou arquivo exportado"
  - formatos: "Feed (1080x1080), Stories (1080x1920), etc."
note: "Se Canva MCP não disponível, briefing é entregue para execução manual"
```

---

## Quality Gates

- [ ] Cada slot tem copy completa (headline + body + CTA)
- [ ] Slots de vídeo têm roteiro com gancho nos primeiros 3s
- [ ] Direção criativa presente para todos os slots
- [ ] Briefing consolidado por slot
- [ ] Sacred Words do cliente presentes em todas as copies
- [ ] Nenhuma copy genérica ou sem contraste

---

## Cross-Squad Integration

| Squad | Quando acionar | O que fornecer |
|-------|---------------|----------------|
| **Jurídica** | Copy de oferta/promoção | @aequitas valida CDC/CONAR |
| **Jurídica** | Uso de imagem de pessoa | @signum valida direitos |

---

*Squad Cadarn Marketing — Task: Content Batch Production*
*Agentes: Logos + Magnética + Iris + Pixel (pipeline sequencial)*
