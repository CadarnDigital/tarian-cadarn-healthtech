---

## Task Definition

```yaml
task: analyzeLaborRisk()
responsavel: Ergon (Especialista Trabalhista)
responsavel_type: Agente
squad: cadarn-juridica
templates:
  - contrato-pj-antiprecarizacao-tmpl.yaml
tarian_portable: true

description: >
  Análise de risco trabalhista: diagnóstico de vínculo empregatício,
  geração de contratos PJ anti-pejotização, cálculo de verbas
  rescisórias, checklists de RH e avaliação de assédio.

Entrada:
  - campo: tipo_analise
    tipo: enum [vinculo, rescisao, contrato-pj, checklist-rh, assedio]
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: parecer_trabalhista
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Diagnóstico de Vínculo (2-3 prompts)
- 4 requisitos CLT + Matriz de Subordinação
- **Trigger:** `*vinculo {descrição da relação}`

### 2. Cálculo de Rescisão (2-3 prompts)
- Verbas rescisórias por modalidade
- **Trigger:** `*rescisao {modalidade, tempo, salário}`

### 3. Contrato PJ Anti-Pejotização (3-4 prompts) **[DEFAULT]**
- Gerar minuta com cláusulas protetoras
- **Trigger:** `*contrato-pj {descrição da contratação}`

### 4. Checklist de RH (1-2 prompts)
- Por processo: admissão, demissão, compliance, corretor
- **Trigger:** `*checklist-rh {tipo}`

### 5. Avaliação de Assédio (2-3 prompts)
- Classificação moral/sexual/digital + risco + recomendações
- **Trigger:** `*assedio {descrição da situação}`

---

## Workflow — Diagnóstico de Vínculo

### Fase 1 — Elicitação

**Passo 1: Contexto da relação**
```
elicit: true
prompt: |
  ⚖️ Diagnóstico de Vínculo Empregatício — Ergon

  Preciso entender a relação de trabalho:

  1. Quem é a pessoa? (designer, gestor de tráfego, redator, corretor, etc.)
  2. Como é contratada? (PJ, MEI, autônomo, CLT, sem contrato)
  3. Trabalha exclusivamente para você? (sim/não/parcial)
  4. Tem horário fixo ou entregas por demanda?
  5. Quem define COMO o trabalho é feito? (contratante ou contratado)
  6. Há quanto tempo trabalha assim?
```

### Fase 2 — Diagnóstico 4 Requisitos

```
task: |
  Analisar os 4 requisitos do art. 3º CLT:

  REQUISITO 1 — PESSOALIDADE
  - Só essa pessoa pode fazer o trabalho?
  - Pode enviar prepostos/substitutos?
  - 🟢 Baixo risco: pode enviar substitutos
  - 🔴 Alto risco: só essa pessoa executa

  REQUISITO 2 — ONEROSIDADE
  - Recebe pagamento regular?
  - Emite NF?
  - 🟢 Sempre presente (não é diferenciador)

  REQUISITO 3 — HABITUALIDADE
  - Trabalha com que frequência?
  - 🟢 Baixo risco: por projeto/demanda
  - 🔴 Alto risco: diário, há meses

  REQUISITO 4 — SUBORDINAÇÃO
  - Aplicar Matriz de Subordinação (5 indicadores):
    a) Define horário? (contratante = subordinação)
    b) Define método? (contratante = subordinação)
    c) Controla ferramentas? (contratante = subordinação)
    d) Aplica punições? (contratante = subordinação)
    e) Integra organização? (sim = subordinação)

  RISCO FINAL:
  - 0-1 requisitos presentes: BAIXO
  - 2 requisitos presentes: MÉDIO (ajustar contrato)
  - 3-4 requisitos presentes: ALTO (reconfigurar relação)

output: diagnostico-vinculo-{pessoa}-{data}.md
```

### Fase 3 — Recomendações

```
task: |
  Se risco MÉDIO ou ALTO:

  1. Ações imediatas para reduzir risco
  2. Cláusulas contratuais necessárias (usar template anti-pejotização)
  3. Mudanças operacionais (autonomia, prepostos, pluralidade)
  4. Timeline de implementação
  5. Disclaimer: escalar para advogado se > R$ 20.000 ou litígio

output: plano-adequacao-{pessoa}-{data}.md
```

---

## Output

```
{output_dir}/
├── diagnostico-vinculo-{pessoa}-{data}.md    # Diagnóstico completo
├── contrato-pj-{pessoa}-{data}.md            # Minuta anti-pejotização
├── calculo-rescisao-{data}.md                # Verbas rescisórias
├── checklist-rh-{processo}-{data}.md         # Checklist por processo
└── avaliacao-assedio-{data}.md               # Avaliação de assédio
```

**Output dir padrão:** `docs/juridico/trabalhista/`

---

## Integração Cross-Squad

- **Operacional (Nexus/RH):** Ergon é acionado para toda questão trabalhista de RH
- **Themis:** Ergon é acionado quando contratos PJ precisam de revisão anti-pejotização
- **Escalação:** Valor > R$ 20.000 ou litígio → advogado humano obrigatório

---

*Squad Cadarn Jurídica — Task v1.0*
*Framework: CLT Art. 3 + Matriz de Subordinação + Anti-Pejotização*
