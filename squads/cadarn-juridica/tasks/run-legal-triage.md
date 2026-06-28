---

## Task Definition

```yaml
task: runLegalTriage()
responsavel: Themis (Líder Jurídico)
responsavel_type: Agente
squad: cadarn-juridica
templates:
  - parecer-juridico-tmpl.yaml
tarian_portable: true

description: >
  Triagem jurídica: recebe questão, classifica área, encaminha para
  especialista correto e coordena parecer consolidado. Porta de entrada
  para toda demanda jurídica da squad.

Entrada:
  - campo: questao_juridica
    tipo: string
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: parecer_consolidado
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Triagem Rápida (1-2 prompts)
- Classifica área + encaminha para especialista
- Sem parecer consolidado
- **Trigger:** `*triagem {questão}`

### 2. Parecer Completo (3-5 prompts) **[DEFAULT]**
- Triagem + análise especializada + consolidação
- **Trigger:** `*parecer {questão}`

### 3. Coordenação Multi-Área (4-6 prompts)
- Questão cruza 2+ áreas jurídicas
- **Trigger:** `*coordenar {tema}`

---

## Workflow — Triagem + Parecer Completo

### Fase 1 — Recepção e Classificação

**Passo 1: Entender a questão**
```
elicit: true
prompt: |
  ⚖️ Triagem Jurídica — Themis

  Preciso entender a questão para encaminhar corretamente.

  1. Descreva a situação ou dúvida jurídica
  2. Qual o contexto? (contrato, campanha, contratação, compliance, etc.)
  3. Há urgência? (notificação recebida, prazo correndo, liminar?)
  4. Valor envolvido (aproximado)?
```

### Fase 2 — Classificação e Roteamento

```
task: |
  Árvore de Triagem (executar mentalmente):

  1. LGPD, privacidade, dados pessoais, cookies, ANPD → Shield
  2. Imobiliário, CRECI, incorporação, locação, plataformas imóveis → Praedium
  3. CDC, publicidade, CONAR, promoções, influencer, setorial → Aequitas
  4. Trabalhista, vínculo, PJ, rescisão, assédio, eSocial → Ergon
  5. PI, marcas, direito autoral, imagem, IA/autoria, ECAD → Signum
  6. Contratos, tributário, empresarial, IA compliance → Themis (retém)
  7. Multi-área (2+ especialistas) → Themis coordena

  Verificar triggers de ESCALAÇÃO HUMANA:
  - Valor > R$ 20.000 → ESCALAR
  - Liminar/notificação judicial → ESCALAR
  - Violação de PI por terceiro → ESCALAR
  - Dano por output de IA → ESCALAR
  - Relação com consumidor (CDC aplicável) → ALERTAR

  Informar ao usuário:
  - Área classificada
  - Especialista designado
  - Se multi-área: quais especialistas serão coordenados
  - Se escalação necessária: informar com disclaimer
```

### Fase 3 — Análise Especializada

```
task: |
  O especialista designado analisa a questão usando seus frameworks:

  Shield: Pipeline LGPD (7 etapas)
  Praedium: Checklist Compliance Imobiliário (10 pontos)
  Aequitas: Pipeline Auditoria Publicitária (8 etapas)
  Ergon: Diagnóstico 4 Requisitos + Matriz de Subordinação
  Signum: Pipeline de Auditoria PI (6 etapas)
  Themis: 25 Regras + 6 Frameworks Operacionais

  Output: parecer técnico do especialista com fundamentação legal
```

### Fase 4 — Consolidação (Themis)

```
task: |
  Themis consolida o parecer:

  1. Resumo executivo (1 parágrafo, leigo pode entender)
  2. Fundamentação legal (artigos, leis, jurisprudência)
  3. Análise de risco (ALTO / MÉDIO / BAIXO)
  4. Recomendações práticas (ações concretas)
  5. Disclaimer obrigatório

  Se multi-área:
  - Consolidar pareceres de todos especialistas
  - Resolver conflitos entre áreas
  - Priorizar recomendações por risco

  Gerar usando template: parecer-juridico-tmpl.yaml

output: parecer-juridico-{tema}-{data}.md
```

---

## Output — Arquivos Gerados

```
{output_dir}/
├── parecer-juridico-{tema}-{data}.md    # Parecer consolidado
└── triagem-{data}.md                     # Log de triagem (se multi-área)
```

**Output dir padrão:** `docs/juridico/pareceres/`

---

## Integração Cross-Squad

- **Marketing → Jurídica:** Coel, Pixel, Pulso, Mídia, Logos, Magnética podem acionar *triagem
- **Jurídica → Marketing:** Themis notifica Coel se risco de marca identificado
- **Operacional → Jurídica:** Nexus pode acionar Ergon para questões trabalhistas
- **Comercial → Jurídica:** Caio pode acionar Themis para contratos de venda

---

*Squad Cadarn Jurídica — Task v1.0*
*Pipeline: Triagem → Análise → Consolidação → Validação*
