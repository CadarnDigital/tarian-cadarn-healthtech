---

## Task Definition

```yaml
task: auditRealEstateAd()
responsavel: Praedium (Especialista Imobiliário)
responsavel_type: Agente
squad: cadarn-juridica
templates:
  - anuncio-imobiliario-compliance-tmpl.yaml
tarian_portable: true

description: >
  Auditoria de compliance para publicidade imobiliária digital.
  Verifica CRECI, COFECI, plataformas, Lei 4.591/64, CDC setorial,
  distrato e gera checklist por canal (Meta, Google, ZAP, OLX, etc.).

Entrada:
  - campo: anuncio_ou_campanha
    tipo: string
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: parecer_imobiliario
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Auditar Anúncio (2-3 prompts) **[DEFAULT]**
- Checklist 10 pontos para peça específica
- **Trigger:** `*auditar-anuncio {anúncio ou descrição}`

### 2. Checklist por Canal (1-2 prompts)
- Regras específicas por plataforma
- **Trigger:** `*checklist-compliance {canal}`

### 3. Compliance por Plataforma (1-2 prompts)
- Guia completo de regras da plataforma
- **Trigger:** `*plataforma {Meta | Google | ZAP | OLX | VivaReal | WhatsApp | TikTok}`

### 4. Contrato de Intermediação (2-3 prompts)
- Análise de contrato corretor↔cliente
- **Trigger:** `*contrato-intermediacao {contrato ou cláusula}`

---

## Workflow — Auditar Anúncio

### Fase 1 — Recepção

**Passo 1: Material**
```
elicit: true
prompt: |
  🏛️ Auditoria de Anúncio Imobiliário — Praedium

  1. Descreva o anúncio (ou cole texto/link)
  2. Canal: Meta Ads, Google Ads, ZAP Imóveis, OLX, VivaReal, site, WhatsApp?
  3. Tipo de imóvel: venda, locação, lançamento, loteamento?
  4. Valor anunciado?
  5. CRECI do corretor/imobiliária está visível no anúncio?
```

### Fase 2 — Checklist 10 Pontos

```
task: |
  Verificar os 10 pontos do Checklist de Compliance Imobiliário:

  1. CRECI VISÍVEL — Número do CRECI do responsável está no anúncio?
     (Obrigatório: Lei 6.530/78 + Resolução COFECI 1.065/2007)

  2. INFORMAÇÕES OBRIGATÓRIAS — Endereço, área, preço, condições?
     (CDC Art. 31: informação clara, precisa e ostensiva)

  3. FOTOS REAIS — Imagens correspondem ao imóvel real?
     (Fotos de banco = publicidade enganosa, Art. 37 CDC)

  4. PROMESSAS DE VALORIZAÇÃO — Promete retorno financeiro?
     (PROIBIDO sem fundamento técnico comprovável)

  5. METRAGEM — Informada corretamente? Útil vs construída?
     (Erro de metragem = vício do produto, Art. 18 CDC)

  6. META HOUSING ADS — Se Meta: categoria "Habitação" configurada?
     (Meta exige categoria especial, limita segmentação)

  7. GOOGLE ADS — Se Google: sem marca concorrente como keyword?
     (STJ jul/2024 condenou por concorrência desleal)

  8. PORTAIS (ZAP/OLX/VivaReal) — Regras da plataforma atendidas?
     (Cada portal tem TOS próprios para anúncios)

  9. DISTRATO — Se lançamento/na planta: informações do distrato?
     (Lei 13.786/2018: regras de distrato obrigatórias)

  10. DISCLAIMERS — Avisos legais necessários presentes?
      (Condições de financiamento, sujeito a disponibilidade, etc.)

  Para cada ponto: ✅ CONFORME / ⚠️ ATENÇÃO / ❌ NÃO CONFORME

  Gerar usando template anuncio-imobiliario-compliance-tmpl.yaml

output: auditoria-anuncio-imobiliario-{data}.md
```

---

## Output

```
{output_dir}/
├── auditoria-anuncio-imobiliario-{data}.md   # Parecer completo
├── checklist-{canal}-{data}.md                # Checklist por canal
└── guia-plataforma-{nome}-{data}.md           # Guia por plataforma
```

**Output dir padrão:** `docs/juridico/imobiliario/`

---

## Integração

- **Marketing (Pixel/Mídia):** Praedium é acionado quando peça é de setor imobiliário
- **Themis:** Praedium é acionado para cláusulas imobiliárias em contratos
- **Cliente Zero:** `{CLIENTE_IMOBILIARIO}` — preencher no setup do Tarian

---

*Squad Cadarn Jurídica — Task v1.0*
*Framework: CRECI/COFECI + CDC Setorial + Meta Housing + Lei 13.786/2018*
