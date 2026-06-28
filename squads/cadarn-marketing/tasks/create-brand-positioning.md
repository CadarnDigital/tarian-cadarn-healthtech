---

## Task Definition

```yaml
task: createBrandPositioning()
responsavel: Vinci (Branding Estratégico)
responsavel_type: Agente
squad: cadarn-marketing
templates:
  - brand-positioning-tmpl.yaml
tarian_portable: true
depends_on:
  - run-diagnostic (recomendado, não obrigatório)

description: >
  Posicionamento de marca completo seguindo Creator Brand System (Tay Dantas):
  DNA de marca, arquétipo, universo visual, tom de voz, narrativa core,
  hierarquia B/M/V e regras de aplicação. Alimenta todos os agentes de criação.

Entrada:
  - campo: contexto_marca
    tipo: object
    origem: Elicitação ou diagnóstico prévio
    obrigatório: true

Saída:
  - campo: brand_positioning
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. YOLO Mode — Fast (0-1 prompts)
- Marca já tem identidade definida, só precisa documentar
- **Best for:** Formalizar marca existente

### 2. Interactive Mode — Balanced (5-7 prompts) **[DEFAULT]**
- Construção guiada do posicionamento
- **Best for:** Marca nova ou reposicionamento

---

## Workflow — Modo Interactive

### STEP 1 — Contexto e Essência (elicit)

```yaml
elicit:
  prompt: |
    Vamos construir o DNA da marca. Preciso saber:
    1. Nome da marca e segmento
    2. Quem é o público ideal (não o público atual — o público DESEJADO)
    3. Qual transformação a marca entrega?
    4. O que a marca NUNCA faria? (identidade por contraste)
    5. Se a marca fosse uma pessoa, como ela se comportaria?
    6. Existe um fundador visível? (personal brand?)
```

### STEP 2 — DNA de Marca (8 Elementos CBS)

```yaml
action: generate
agent: Vinci
framework: Creator Brand System
elements:
  - proposito: "Por que a marca existe além do lucro?"
  - valores: "3-5 valores inegociáveis"
  - crencas: "O que a marca defende publicamente?"
  - cultura: "Como a marca se comporta internamente?"
  - arquetipo: "Qual arquétipo dominante? (Jung)"
  - tom_de_voz: "Como a marca fala? Formal? Irreverente? Técnica?"
  - universo_visual: "Cores, formas, texturas, mood"
  - narrativa_core: "A história em 1 parágrafo"
```

### STEP 3 — Hierarquia B/M/V

```yaml
action: generate
agent: Vinci
output: bmv_hierarchy
format: |
  BRAND (marca mãe): posicionamento, personalidade, promessa
  MARCA PESSOAL (se aplicável): fundador, voz, autoridade
  VERTICAL (submarcas/produtos): posicionamento específico de cada oferta
```

### STEP 4 — Diferenciação e Contraste

```yaml
action: generate
agent: Vinci
sections:
  - diferencial_percebido: "O que o público REALMENTE percebe como diferente?"
  - territorio_proprio: "Espaço mental que a marca ocupa"
  - inimigos: "O que a marca combate (Pagans — alinhado com Coel/Primal Code)"
  - frases_proibidas: "Expressões que a marca NUNCA usa"
  - frases_assinatura: "Expressões proprietárias (Sacred Words)"
```

### STEP 5 — Gerar Documento Final

```yaml
action: generate
agent: Vinci
template: brand-positioning-tmpl.yaml
output: brand_positioning
```

### STEP 6 — Auditoria Primal Code (opcional)

```yaml
action: audit
agent: Coel (Brand Guardian)
condition: "Se usuário solicitar ou se marca for para publicação"
check: "Os 7 elementos do Primal Code estão presentes no posicionamento?"
```

---

## Quality Gates

- [ ] 8 elementos CBS definidos
- [ ] Hierarquia B/M/V clara
- [ ] Diferencial é percebido (não apenas declarado)
- [ ] Identidade por contraste presente (inimigos/Pagans)
- [ ] Tom de voz documentado com exemplos
- [ ] Frases proibidas + Sacred Words listadas

---

## Cross-Squad Integration

| Squad | Quando acionar | O que fornecer |
|-------|---------------|----------------|
| **Jurídica** | Registro de marca, PI | Brand name + Sacred Words para @signum |
| **Operacional** | Company narrative | DNA de marca para company-narrative-tmpl |

---

*Squad Cadarn Marketing — Task: Brand Positioning*
*Agente: Vinci (Creator Brand System)*
