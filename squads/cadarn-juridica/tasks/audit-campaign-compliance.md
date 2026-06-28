---

## Task Definition

```yaml
task: auditCampaignCompliance()
responsavel: Aequitas (Especialista Consumidor & Publicidade)
responsavel_type: Agente
squad: cadarn-juridica
templates:
  - campanha-compliance-tmpl.yaml
tarian_portable: true

description: >
  Auditoria de compliance publicitário para campanhas de marketing digital.
  Verifica CDC, CONAR, regulamentação setorial, influencer marketing,
  promoções e dark patterns. Cross-squad com Marketing.

Entrada:
  - campo: campanha_ou_peca
    tipo: string
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: parecer_compliance
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Auditoria de Peça (2-3 prompts)
- Analisa peça específica (post, anúncio, vídeo, landing page)
- **Trigger:** `*auditar-campanha {peça ou descrição}`

### 2. Checklist de Oferta (1-2 prompts)
- Checklist universal 20 itens para ofertas e promoções
- **Trigger:** `*checklist-oferta {tipo}`

### 3. Compliance de Influencer (2-3 prompts)
- Contrato e disclosure para influencer marketing
- **Trigger:** `*influencer {campanha ou contrato}`

### 4. Promoção / Sorteio (2-3 prompts)
- Árvore de decisão SPA, regulamento, autorização
- **Trigger:** `*promocao {ação promocional}`

### 5. Compliance Setorial (2-3 prompts)
- Regras específicas por setor regulado
- **Trigger:** `*setorial {setor: saude | imobiliario | advocacia | financeiro}`

---

## Workflow — Auditoria de Peça

### Fase 1 — Recepção

**Passo 1: Material**
```
elicit: true
prompt: |
  ⚖️ Auditoria de Compliance Publicitário — Aequitas

  1. Descreva a peça/campanha (ou cole o texto/link)
  2. Canal: Instagram, Facebook, Google Ads, TikTok, WhatsApp, site?
  3. Setor do cliente: imobiliário, saúde, advocacia, educação, geral?
  4. Contém claims de resultado? (ex: "perca 10kg", "ganhe R$ 5.000")
  5. Envolve influencer ou depoimentos de clientes?
```

### Fase 2 — Pipeline de 8 Etapas

```
task: |
  Executar pipeline de auditoria publicitária:

  ETAPA 1 — IDENTIFICAÇÃO PUBLICITÁRIA
  - Conteúdo é claramente identificado como publicidade?
  - CONAR Art. 28: identificação clara e ostensiva
  - Se influencer: #publi ou #ad obrigatório (CONAR Anexo P)

  ETAPA 2 — VERACIDADE (Art. 37 CDC)
  - Claims são comprováveis?
  - Dados estatísticos têm fonte?
  - Depoimentos são reais e documentados?

  ETAPA 3 — PUBLICIDADE ABUSIVA (Art. 37 §2 CDC)
  - Explora medo, superstição ou deficiência de julgamento?
  - Discriminatória? Incita violência?
  - Explora público vulnerável (crianças, idosos)?

  ETAPA 4 — REGULAMENTAÇÃO SETORIAL
  - Saúde: CFM 2.336/2023, ANVISA, CRO, CRP
  - Imobiliário: CRECI, COFECI, Lei 4.591/64
  - Advocacia: CFOAB 205/2021
  - Financeiro: BACEN, CVM, SUSEP

  ETAPA 5 — PROMOÇÕES E SORTEIOS
  - Se promoção: Lei 5.768/71, SECAP/SEAE
  - Se sorteio: autorização prévia obrigatória + GRU
  - Se concurso cultural: precisa de regulamento

  ETAPA 6 — DARK PATTERNS
  - Urgência artificial ("últimas vagas")?
  - Scarcity falsa ("só hoje")?
  - Confirmshaming?
  - Hidden costs?

  ETAPA 7 — COMPARATIVA (Art. 32 CONAR)
  - Compara com concorrente? Objetiva e comprovável?
  - Usa marca de terceiro? (risco STJ jul/2024)

  ETAPA 8 — DISCLAIMER E DISCLOSURE
  - IA: disclosure de uso obrigatório
  - Resultados: "resultados podem variar"
  - Saúde: disclaimer profissional obrigatório

  Para cada etapa: CONFORME / NÃO CONFORME / N/A
  Gerar parecer usando template campanha-compliance-tmpl.yaml

output: auditoria-campanha-{tipo}-{data}.md
```

---

## Output

```
{output_dir}/
├── auditoria-campanha-{tipo}-{data}.md    # Parecer completo
├── checklist-oferta-{data}.md             # Checklist universal
└── disclaimer-{setor}-{data}.md           # Disclaimer gerado
```

**Output dir padrão:** `docs/juridico/campanhas/`

---

## Integração Cross-Squad (Marketing → Jurídica)

| Agente Marketing | Quando aciona Aequitas |
|-----------------|----------------------|
| Pixel (Designer) | Peça para setor regulado |
| Pulso (Social Media) | Sorteio/promoção no calendário |
| Mídia (Tráfego) | Campanha paga em setor regulado |
| Logos (Copywriter) | Claims de resultado ou comparativa |
| Coel (Brand Guardian) | Auditoria identificou risco jurídico |

---

*Squad Cadarn Jurídica — Task v1.0*
*Framework: CDC + CONAR + Regulamentação Setorial*
