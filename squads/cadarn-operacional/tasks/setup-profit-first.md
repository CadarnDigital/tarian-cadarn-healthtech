---

## Task Definition

```yaml
task: setupProfitFirst()
responsavel: Vault (Gestor Financeiro)
responsavel_type: Agente
squad: cadarn-operacional
templates:
  - profit-first-setup-tmpl.yaml
  - fix-this-next-diagnostic-tmpl.yaml
tarian_portable: true

description: >
  Implementa o sistema Profit First completo: diagnóstico Fix This Next,
  setup de 5 contas, definição de CAPs/TAPs, configuração de ritmo bi-mensal
  e primeira alocação. Inclui diagnóstico financeiro para priorização.

Entrada:
  - campo: contexto_financeiro
    tipo: object
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: plano_profit_first
    tipo: markdown
    destino: File system
    persistido: true

  - campo: diagnostico_bhn
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. YOLO Mode — Fast (0-1 prompts)
- Dados financeiros já conhecidos
- Gera plano com defaults para o setor
- **Best for:** Empresa já mapeada pelo Vault

### 2. Interactive Mode — Balanced (4-6 prompts) **[DEFAULT]**
- Elicita contexto financeiro completo
- Diagnóstico Fix This Next antes do setup
- **Best for:** Primeira implementação

---

## Workflow de Execução

### Fase 0 — Fix This Next (pré-requisito)

```
task: |
  ANTES de implementar Profit First, verificar se a empresa está no nível
  certo da pirâmide. Se SALES está quebrado, Profit First sozinho não resolve.

  Aplicar template fix-this-next-diagnostic-tmpl.yaml:
  - Percorrer SALES → PROFIT → ORDER
  - Se SALES tem needs não atendidas: AVISAR que o foco deve ser vendas primeiro
  - Se SALES OK mas PROFIT quebrado: Profit First é a solução CERTA
  - Se ambos OK: Profit First otimiza o que já funciona
```

### Fase 1 — Elicitação de Contexto

**Passo 1: Situação Atual**
```
elicit: true
prompt: |
  Vamos implementar Profit First. Preciso entender a situação financeira atual.

  1. Receita mensal média (últimos 3 meses)?
  2. Tipo de receita: recorrente (retainers), projetos pontuais, ou misto?
  3. Despesas fixas mensais (aluguel, salários, ferramentas, etc.)?
  4. Quantos sócios? Cada um tira pró-labore?
  5. Já separa lucro de alguma forma?
  6. Tem dívidas da empresa?
  7. Tem reserva de emergência? Se sim, quantos meses cobre?
```

**Passo 2: Banco e Operação**
```
elicit: true
prompt: |
  Sobre a operação bancária:

  1. Qual o banco principal da empresa?
  2. Consegue abrir contas adicionais (sub-contas, poupanças)?
  3. Quem controla as finanças no dia a dia? (sócio, contador, financeiro)
  4. Usa algum sistema de gestão financeira? (planilha, Conta Azul, etc.)
```

### Fase 2 — Diagnóstico Fix This Next

```
task: |
  Com os dados financeiros, aplicar o diagnóstico Fix This Next:

  1. Avaliar SALES (5 needs): Lifestyle Congruence, Prospect Attraction,
     Client Conversion, Delivering, Collecting
  2. Se SALES OK → avaliar PROFIT (5 needs)
  3. Identificar nível e Vital Need

  Output:
  - Nível atual na pirâmide
  - Vital Need identificada
  - Recomendação: "Profit First é o próximo passo" ou "Antes, resolver X"

output: diagnostico-bhn-{empresa}.md
```

### Fase 3 — Setup Profit First

**Step 3.1 — Definir CAPs Iniciais**
```
task: |
  Com base na receita e despesas informadas:

  1. Calcular CAPs realistas (não ideais):
     - PROFIT: começar com X% (mínimo 1%)
     - OWNER: X% (atual pró-labore convertido em %)
     - OPEX: X% (despesas atuais convertidas em %)
     - TAX: X% (estimativa de impostos)

  2. Definir TAPs alvo (onde queremos chegar em 12 meses):
     Usar tabela de referência do template por faixa de receita

  3. Plano de migração trimestral:
     Q1: CAPs iniciais
     Q2: +1-3% em PROFIT, ajustar OPEX
     Q3: +1-3% em PROFIT, ajustar OPEX
     Q4: Avaliar se TAPs foram atingidos

output: caps_taps_definidos
```

**Step 3.2 — Setup Bancário**
```
task: |
  Gerar instruções personalizadas de setup bancário:

  1. Quais contas abrir e onde
  2. Conta de PROFIT em banco DIFERENTE (dificultar acesso)
  3. Como configurar transferências automáticas (se banco permite)
  4. Planilha de controle (formato simples)

output: setup_bancario
```

**Step 3.3 — Configurar Ritmo**
```
task: |
  Gerar calendário de alocação:

  1. Dia 10: rotina de alocação (5 passos)
  2. Dia 25: rotina de alocação + revisão OPEX
  3. Trimestral: distribuição de lucro + ajuste CAPs
  4. Alertas e lembretes sugeridos

output: calendario_alocacao
```

### Fase 4 — Primeira Alocação (Simulação)

```
task: |
  Simular a primeira alocação com dados reais:

  Receita do mês atual: R${{receita}}

  | Conta | CAP | Valor | Destino |
  |-------|-----|-------|---------|
  | PROFIT | X% | R$XX | Banco Y (poupança) |
  | OWNER | X% | R$XX | Conta Z |
  | OPEX | X% | R$XX | Conta W |
  | TAX | X% | R$XX | Poupança impostos |
  | **TOTAL** | 100% | R${{receita}} | |

  "Se esse número de OPEX não cobre suas despesas, o problema é DESPESA.
  Lista de cortes sugeridos: (analisar despesas informadas)"

output: primeira_alocacao_simulada
```

### Fase 5 — Entrega e Validação

```
checklist:
  - [ ] Diagnóstico Fix This Next concluído?
  - [ ] CAPs realistas definidos (não utópicos)?
  - [ ] TAPs alvo definidos com prazo (12 meses)?
  - [ ] Setup bancário instruído (contas a abrir)?
  - [ ] Conta de PROFIT em banco separado?
  - [ ] Calendário de alocação (10 e 25) configurado?
  - [ ] Primeira alocação simulada com números reais?
  - [ ] Plano trimestral de ajuste CAPs→TAPs?
  - [ ] Se OPEX não fecha: lista de cortes recomendados?
```

---

## Output — Arquivos Gerados

```
{output_dir}/
├── diagnostico-bhn-{empresa}.md          # Fix This Next: nível + Vital Need
├── plano-profit-first-{empresa}.md       # CAPs, TAPs, setup, calendário
├── simulacao-alocacao-{empresa}.md       # Primeira alocação com números reais
└── planilha-alocacao-{empresa}.md        # Template mensal de controle
```

**Output dir padrão:** `docs/operacional/financeiro/`

---

## Integração com Outros Agentes

- **Scala (Líder):** KPI-7 (Profit Margin) alimenta diagnóstico operacional
- **Kairos (Processos):** Automatizar lembretes de alocação via ClickUp/Make
- **Arc (Client Success):** Churn impacta MRR → alerta cruzado
- **Nexus (RH):** Pay Increase Framework usa dados do Profit First

---

*Squad Cadarn Operacional — Task v1.0*
*Framework: Mike Michalowicz — Profit First + Fix This Next*
