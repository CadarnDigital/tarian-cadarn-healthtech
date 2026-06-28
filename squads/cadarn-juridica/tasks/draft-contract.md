---

## Task Definition

```yaml
task: draftContract()
responsavel: Themis (Líder Jurídico)
responsavel_type: Agente
squad: cadarn-juridica
templates:
  - contrato-agencia-12clausulas-tmpl.yaml
  - contrato-pj-antiprecarizacao-tmpl.yaml
  - checklist-ia-compliance-tmpl.yaml
tarian_portable: true

description: >
  Gera ou audita contratos de prestação de serviços para agências Martech.
  Modo auditor: recebe contrato existente e identifica riscos.
  Modo gerador: cria minuta com 12 cláusulas protegendo a agência.

Entrada:
  - campo: tipo_contrato
    tipo: enum [agencia, pj-freelancer, intermediacao, nda, aditivo]
    origem: Elicitação
    obrigatório: true

  - campo: contrato_existente
    tipo: string
    origem: Elicitação
    obrigatório: false
    nota: "Se modo auditor, colar contrato aqui"

Saída:
  - campo: contrato_ou_parecer
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Auditar Contrato Existente (3-5 prompts)
- Recebe contrato, identifica gaps usando 12 cláusulas como checklist
- **Trigger:** `*contrato {colar contrato ou descrever}`

### 2. Gerar Minuta Nova (4-6 prompts) **[DEFAULT]**
- Elicita contexto e gera minuta completa
- **Trigger:** `*contrato novo {tipo}`

### 3. Gerar Contrato PJ (3-4 prompts)
- Específico para contratação de freelancers/PJ
- Anti-pejotização como foco
- **Trigger:** `*contrato pj {descrição}`

---

## Workflow — Gerar Minuta Nova

### Fase 1 — Elicitação

**Passo 1: Tipo e partes**
```
elicit: true
prompt: |
  📝 Geração de Contrato — Themis

  1. Tipo: agência↔cliente, PJ/freelancer, NDA, intermediação, aditivo?
  2. Quem são as partes? (nomes, CNPJs se tiver)
  3. Serviços a prestar (listar todos)?
  4. Valor mensal (ou setup + mensal)?
  5. Prazo pretendido?
```

**Passo 2: Detalhes críticos**
```
elicit: true
prompt: |
  Detalhes que protegem o contrato:

  1. Usa IA generativa na entrega? (sim/não)
  2. Terá exclusividade de praça? (sim/não)
  3. Quem cria as contas de plataforma? (agência ou cliente)
  4. Haverá verba de mídia separada? (sim/não, valor)
  5. Setor regulado? (saúde, imobiliário, advocacia, financeiro, nenhum)
```

### Fase 2 — Geração

```
task: |
  Gerar minuta usando template contrato-agencia-12clausulas-tmpl.yaml:

  12 Cláusulas obrigatórias:
  1. Preâmbulo e Qualificação
  2. Objeto — escopo exaustivo com exclusões
  3. Entregáveis, SLA e Prazos
  4. KPIs e Métricas — natureza REFERENCIAL (obrigação de MEIO)
  5. Remuneração — Setup Fee + MRR, verba separada
  6. Propriedade Intelectual — cessão expressa, cláusula IA
  7. Confidencialidade (NDA) — 2 anos pós-término
  8. Limitação de Responsabilidade — cap 12 meses
  9. Proteção de Dados (LGPD) — controlador/operador
  10. Rescisão — aviso 30 dias, multa 20%, portabilidade 15 dias
  11. Exclusividade (se aplicável) — acréscimo 20-30%
  12. Reajuste — IPCA anual + cláusula de equilíbrio

  Se usa IA: adicionar checklist-ia-compliance-tmpl.yaml como anexo
  Se PJ: usar contrato-pj-antiprecarizacao-tmpl.yaml em vez da estrutura de 12

  SEMPRE incluir:
  - 2 testemunhas (título executivo extrajudicial)
  - Resolução escalonada (negociação → mediação → arbitragem/foro)
  - Disclaimer de revisão por advogado

output: contrato-{tipo}-{partes}-{data}.md
```

### Fase 3 — Revisão Cruzada

```
task: |
  Verificar automaticamente:

  - Se imobiliário → Praedium revisa cláusulas específicas do setor
  - Se LGPD relevante → Shield revisa cláusula 9
  - Se envolve contratação PJ → Ergon revisa anti-pejotização
  - Se envolve conteúdo/marca → Signum revisa cláusula 6 (PI)

  Consolidar ajustes no documento final.
```

---

## Workflow — Auditar Contrato Existente

### Passo 1
```
elicit: true
prompt: |
  🔍 Auditoria de Contrato — Themis

  Cole o contrato ou descreva as cláusulas principais.
  Vou verificar contra as 12 cláusulas essenciais.
```

### Passo 2 — Análise
```
task: |
  Verificar cada uma das 12 cláusulas:

  Para cada cláusula:
  - ✅ PRESENTE e adequada
  - ⚠️ PRESENTE mas com gaps (detalhar)
  - ❌ AUSENTE (risco)

  Gerar relatório com:
  - Score: X/12 cláusulas adequadas
  - Riscos identificados (ordenados por gravidade)
  - Recomendações específicas de ajuste
  - Cláusulas sugeridas para inclusão

output: auditoria-contrato-{data}.md
```

---

## Output

```
{output_dir}/
├── contrato-{tipo}-{partes}-{data}.md    # Minuta gerada
├── auditoria-contrato-{data}.md          # Relatório de auditoria
└── checklist-ia-{data}.md                # Anexo IA (se aplicável)
```

**Output dir padrão:** `docs/juridico/contratos/`

---

*Squad Cadarn Jurídica — Task v1.0*
*Framework: 12 Cláusulas Themis + Anti-Pejotização Ergon*
