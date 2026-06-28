---

## Task Definition

```yaml
task: applyWorkingGenius()
responsavel: Nexus (RH e Gestão de Pessoas)
responsavel_type: Agente
squad: cadarn-operacional
template: working-genius-tmpl.yaml
tarian_portable: true

description: >
  Conduz o mapeamento completo de Working Genius do time: assessment individual,
  sessão de revelação em grupo, team map com análise de cobertura/gaps e plano de ação.

Entrada:
  - campo: contexto_time
    tipo: object
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: team_map
    tipo: markdown
    destino: File system
    persistido: true

  - campo: plano_realocacao
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. YOLO Mode — Fast (0-1 prompts)
- Time já fez assessment oficial (workinggenius.com)
- Usuário fornece resultados direto
- Gera team map e análise imediatamente
- **Best for:** Resultados já em mãos

### 2. Interactive Mode — Balanced (3-5 prompts) **[DEFAULT]**
- Elicita contexto do time
- Guia mapeamento qualitativo (se não fez oficial)
- Monta team map progressivamente
- **Best for:** Primeiro mapeamento do time

---

## Workflow de Execução

### Fase 1 — Elicitação de Contexto

**Passo 1: O Time**
```
elicit: true
prompt: |
  Vamos mapear os Working Genius do time.

  1. Quantas pessoas no time?
  2. Liste os nomes (ex: {MEMBRO_1}, {MEMBRO_2}, {MEMBRO_3})
  3. Já fizeram o assessment oficial em workinggenius.com?
     - Se SIM: me passe os resultados de cada pessoa
     - Se NÃO: vou guiar um mapeamento qualitativo
  4. Qual o desafio atual do time? (ex: execução travada, muitas ideias sem implementação)
```

**Passo 2: Assessment (se não fez oficial)**
```
elicit: true
prompt: |
  Para cada pessoa do time, vou fazer 6 perguntas.
  Responda G (Gênio), C (Competência) ou F (Frustração).

  Começando por {{membro_1}}:

  1. WONDER (Ponderar) — {{membro_1}} se energiza questionando como as coisas são feitas?
  2. INVENTION (Inventar) — Se energiza criando soluções novas?
  3. DISCERNMENT (Discernir) — Se energiza avaliando ideias e dando feedback?
  4. GALVANIZING (Mobilizar) — Se energiza convencendo pessoas a agir?
  5. ENABLEMENT (Habilitar) — Se energiza ajudando outros a terem sucesso?
  6. TENACITY (Tenacidade) — Se energiza completando tarefas e fechando projetos?

  Responda G/C/F para cada.
```
Repetir para cada membro do time.

### Fase 2 — Montar Team Map

```
task: |
  Com os resultados de todos os membros, gerar:

  1. TEAM MAP (tabela):
     | Membro | W | I | D | G | E | T |
     |--------|---|---|---|---|---|---|
     (preenchido com G/C/F)

  2. COBERTURA por tipo:
     - Quantos Gênios em cada tipo
     - Tipos com 0 Gênios = GAP CRÍTICO
     - Tipos com 2+ Gênios = SOBREPOSIÇÃO

  3. FLUXO DE TRABALHO:
     Ideação (W→I) → Ativação (D→G) → Implementação (E→T)
     Marcar onde o time é FORTE e onde é FRACO

output: team_map.md
```

### Fase 3 — Análise de Gaps

```
task: |
  Para cada GAP identificado (tipo sem Gênio no time):

  1. Impacto: como isso afeta o trabalho hoje?
  2. Evidência: "Esse problema já aconteceu? Ex: ideias que nunca saem do papel (falta T)"
  3. Opções de compensação:
     a) Realocar de Competência para cobrir (funciona, mas drena)
     b) Criar processo/ferramenta (ex: checklist para compensar falta de T)
     c) Automatizar (informar Kairos)
     d) Contratar com foco no gap (informar Scala)

  Recomendar a melhor opção para cada gap.

output: analise_gaps.md
```

### Fase 4 — Plano de Realocação

```
task: |
  Com base no team map e gaps, gerar plano de ação:

  Para cada membro:
  - MANTER: tarefas que alinham com seus Gênios (maximizar)
  - REDUZIR: tarefas que são Frustrações (minimizar ou eliminar)
  - AJUSTAR: tarefas que são Competências (usar com moderação)

  Para o time:
  - Quem lidera o quê baseado em Gênios
  - Processos para cobrir gaps
  - Próximo assessment: daqui a 6 meses
  - Quando reavaliar: se alguém sair/entrar no time

output: plano_realocacao.md
```

### Fase 5 — Validação

```
checklist:
  - [ ] Todos os membros do time foram mapeados?
  - [ ] Team map está completo (6 tipos x N membros)?
  - [ ] Gaps identificados com opção de compensação?
  - [ ] Plano de realocação é realista (não depende só de boa vontade)?
  - [ ] Próximo assessment agendado?
  - [ ] Resultados compartilhados com TODO o time (não só líder)?
```

---

## Output — Arquivos Gerados

```
{output_dir}/
├── working-genius-team-map.md        # Team map + cobertura
├── working-genius-gaps.md            # Análise de gaps + compensações
└── working-genius-realocacao.md      # Plano de ação por membro
```

**Output dir padrão:** `docs/operacional/pessoas/` (ou equivalente no projeto do cliente)

---

## Integração com Outros Agentes

- **Scala (Líder):** Recebe plano de realocação para implementar mudanças
- **Arc (Client Success):** Atualiza onboarding de funcionário com Working Genius no Dia 8-10
- **Kairos (Processos):** Cria processos/automações para compensar gaps
- **Coel (Brand Guardian):** `brand_touchpoints` no template para auditoria

---

*Squad Cadarn Operacional — Task v1.0*
*Framework: Patrick Lencioni — The 6 Types of Working Genius*
