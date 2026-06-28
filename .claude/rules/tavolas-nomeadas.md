---
paths:
  - ".claude/skills/tavola-*/**"
  - "squads/cadarn-marketing/**"
  - "docs/pipeline/**"
---

# Távolas Nomeadas — Padrão de Convocação Persistente por Tarefa

## Regra Principal

Uma **Távola Nomeada** é uma skill persistente em `.claude/skills/tavola-{nome}/SKILL.md` que convoca uma composição **fixa e pré-definida** de agentes para uma tarefa recorrente específica. Serve como atalho memorizado: em vez de decidir caso a caso "quem convoco pra isso", a Távola Nomeada já tem a resposta guardada.

Exemplos conceituais: Távola Pipeline, Távola Onboarding, Távola Kickoff-Cliente, Távola Crise, Távola Revisão-Trimestral. Cada uma com seu próprio conjunto de agentes e protocolo.

## Por que esta regra existe

Trabalho real raramente convoca uma squad inteira. Para escrever um carrossel você chama Logos + Coel + Magnética + Pixel — não os 11 da Squad MKT. Para revisar um pipeline comercial você chama Cadarn + Camy + Morgan + Coel — não os 11 da Forja. Composições específicas se repetem e têm protocolos estáveis.

Táblas Nomeadas capturam essas composições como ativos reutilizáveis, com 4 benefícios diretos:

1. **Velocidade** — `/tavola-pipeline` ativa o subset certo imediatamente, sem decisão repetida
2. **Consistência** — sempre os mesmos agentes discutem o mesmo tema, construindo memória coletiva do assunto
3. **Descoberta** — skills listadas viram documentação viva dos fluxos de trabalho recorrentes da Cadarn
4. **Protocolo dedicado** — cada Távola pode ter suas próprias fases, perguntas-padrão, output esperado

## Hierarquia de Távolas (contexto completo)

```
Távola Express            (foco, efêmera, 1-3 agentes, sem skill, conversacional)
       ↓
TÁVOLA NOMEADA            ← esta rule
  /tavola-{nome}          (persistente, composição fixa, protocolo próprio)
       ↓
Távola de Domínio         (uma squad inteira — @squad-mkt:*, /forja, etc)
       ↓
Távola Cruzada            (2-3 squads, efêmera, conversacional)
       ↓
TÁVOLA MAGNA              (todas as 6 squads, sob Regência de Emrys)
  /tavola-magna
```

A Távola Nomeada ocupa um nicho único: **composição menor que uma squad inteira, mas persistente e reutilizável** — o contrário da Távola Express que é efêmera.

## Critério para criar uma Távola Nomeada

**Criar APENAS se pelo menos 2 das condições abaixo forem verdadeiras:**

1. A composição de agentes se repete de forma estável em 3+ ocasiões por trimestre
2. A tarefa tem protocolo próprio (ordem de fala, perguntas padrão, output esperado) que vale formalizar
3. Salvar a composição economiza decisão repetida ("quem convoco pra isso?")
4. A Távola constrói memória coletiva útil para futuras sessões (contexto acumulado)

**Não criar se:**

- A composição muda caso a caso (use Távola Express conversacional)
- É trabalho de squad inteira (use skill da squad diretamente)
- É decisão única que não se repete (use Távola Express)
- É para "experimentar um nome legal" (não é critério)

## Governança de criação

- **Só Fabiano (com apoio de Emrys) cria Távolas Nomeadas.** Outros agentes podem propor via mesa redonda, mas criação é restrita para manter higiene do catálogo.
- **Craft (@squad-creator) executa** a criação técnica (escreve o arquivo da skill) sob briefing de Emrys
- **Emrys governa** o catálogo — pode sugerir depreciação de Távolas inativas

## Protocolo de criação (4 fases)

Quando Fabiano disser "cria Távola X" ou "vamos criar uma Távola para Y", Emrys segue este protocolo:

### Fase 1 — Briefing (Fabiano responde)

Emrys pergunta:
1. **Nome** proposto (ex: "Pipeline")
2. **Propósito** — qual tarefa recorrente convoca esta Távola?
3. **Frequência esperada** — 3+ sessões por trimestre? Se não, vira Távola Express
4. **Output típico** — o que sai de cada sessão?

### Fase 2 — Composição (Emrys propõe, Fabiano decide)

Emrys sugere uma composição baseada no propósito, separando:
- **Mandatório** — participa de toda sessão (core da Távola)
- **Sob demanda** — participa quando trigger específico ocorre

Fabiano ajusta: adiciona, remove, promove/rebaixa. Define o **lead operacional** (quem coordena).

### Fase 3 — Protocolo (opcional, pode deixar livre)

Se fizer sentido formalizar:
1. Ordem de fala / rodadas
2. Perguntas padrão por agente
3. Output format esperado
4. Critérios de sucesso

Se não fizer sentido (cada sessão é diferente), pular esta fase.

### Fase 4 — Criação (Craft executa)

Emrys delega ao Craft (@squad-creator):
1. Craft cria `.claude/skills/tavola-{nome}/SKILL.md` seguindo o template abaixo
2. Emrys atualiza CLAUDE.md se relevante
3. Cria memória `memory/tavola_{nome}.md` com contexto

## Modelo de Execução: Conductor-Hub

Todas as Távolas Nomeadas operam sob o modelo **Conductor-Hub** com subagentes reais:

### Como funciona

1. **Condutor** (lead operacional da Távola, ou Emrys) opera no contexto principal
2. Para cada turno: condutor **spawna 1 subagente real** via Agent tool
3. Cada subagente recebe: **persona compactada (~800 tokens) + MEMORY.md integral + contexto da sessão + instrução específica**
4. Subagente opera em contexto **isolado** e retorna contribuição
5. Condutor apresenta a Fabiano. **Pausa** (turn-by-turn, rule `tavola-turn-by-turn.md`)
6. Fabiano reage. Condutor decide: re-spawn mesmo agente ou próximo
7. Subagentes **NÃO compartilham contexto** por default (opt-in se Fabiano pedir)
8. No fim: condutor consolida decisões + propõe entradas de MEMORY.md

### Injeção de memória nos spawns (obrigatório)

O mecanismo de auto-load (STEP 2.5 das activation-instructions) NÃO funciona para spawns via Agent tool. O condutor é responsável por injetar a memória manualmente no briefing de cada spawn.

**Protocolo do condutor:**
1. Na abertura da sessão, ler os MEMORY.md de todos os agentes mandatórios
2. Para cada spawn, incluir no prompt: persona compactada + MEMORY.md integral + contexto + instrução
3. Se o agente não tem MEMORY.md, spawnar apenas com persona compactada + contexto

### Template de briefing para spawn

```
Você é {nome} ({papel na Távola}).

## Sua persona (compactada):
{~800 tokens do .md completo: DNA, estilo, framework de decisão, regras}

## Sua memória persistente (MEMORY.md):
{conteúdo integral do MEMORY.md}

## Contexto desta sessão:
- Tema: {tema}
- Decisões até agora: {lista}
- Última fala + reação de Fabiano: {resumo}

## Sua tarefa neste turno:
{instrução específica + pergunta-âncora se aplicável}

## Rules:
- Acrônimo CADARN: C-Clareza, A-Arquitetura, D-Dados, A-Ação, R-Rastreio, N-Norma
- {outras rules relevantes para o agente}
```

## Template de Távola Nomeada

Novas Távolas devem seguir este esqueleto YAML, preenchendo os campos marcados com `{...}`:

```yaml
---
name: tavola-{nome}
description: Activate Távola {Nome} Cadarn — {propósito breve em inglês}
user-invocable: true
allowed-tools: Read, Glob, Grep
argument-hint: "[command] (ex: *help, *roster, *mesa-redonda {topic}, *exit)"
---

agent:
  name: Távola {Nome}
  id: tavola-{nome}
  title: {Título descritivo}
  icon: '{emoji}'
  scope: named-collective
  whenToUse: |
    {Quando convocar esta Távola — critérios concretos}

    NOT for:
    - {Quando NÃO convocar}

convocation_purpose: "{propósito declarado}"
frequency: "{recorrente / mensal / trimestral / sob demanda}"
created_by: Fabiano + Emrys
created_at: "{YYYY-MM-DD}"
execution_model: subagent   # Conductor-Hub: condutor spawna subagentes reais via Agent tool

members:
  mandatory:
    - skill: {skill-path}           # ex: @squad-mkt:estrategista
      id: {agent-id}                 # ex: estrategista
      name: {agent-name}             # ex: Cadarn
      role: {papel nesta Távola}     # ex: estratégia e Método CADARN
      memory_path: {path}            # ex: squads/cadarn-marketing/memory/estrategista.md

  on_demand:
    - skill: {skill-path}
      id: {agent-id}
      name: {agent-name}
      role: {papel}
      trigger: "{quando acionar}"    # ex: "quando precisa de dados"

  transversal:
    - skill: /proofreader
      name: Grafia
      note: "sob rule transversal-review-gate (apenas client-facing)"
    - skill: /feynman
      name: Dick
      note: "sob demanda"

lead:
  skill: {skill-path}
  name: {agent-name}
  role: "{como lidera — coordena, arbitra, etc}"

protocol:   # opcional — pode ser null se cada sessão é livre
  phases:
    - phase: 1
      name: {nome da fase}
      owner: {agent-id}
      actions:
        - "{ação}"
    # ... mais fases se precisar

  output_format: "{o que sai de cada sessão}"
  success_criteria:
    - "{como saber que a sessão deu certo}"

motto: "{lema curto e memorável}"

signature_closing: "— Távola {Nome}, {lema} {emoji}"

relationships:
  hierarchy: "{como se encaixa na hierarquia: Express ← Nomeada → Domínio → Cruzada → Magna}"
  vs_similar: "{distinção de outras Távolas Nomeadas relacionadas}"
```

O arquivo também deve ter, ao final, uma seção em markdown com:
- Quick Reference dos comandos
- Quando usar (critérios)
- Relação com outras skills
- Rodapé com versão e autor

## Manutenção do catálogo

### Quando um agente é renomeado ou muda de squad

- Táblas Nomeadas referenciam agentes por **id** (estável) e **skill path** (estável), não por nome humano
- Quando um agente muda de nome: atualizar apenas o campo `name` nas Távolas que referenciam
- Quando um agente muda de skill path: atualizar o campo `skill` + eventualmente o `id`
- Ao renomear/mover agente, Emrys roda busca por todas as Távolas Nomeadas que referenciam e atualiza em lote

### Depreciação

Uma Távola Nomeada deve ser depreciada quando:
- Não é usada há 6+ meses
- A tarefa recorrente mudou e a composição não reflete mais o trabalho real
- Foi substituída por uma Távola Nomeada mais específica ou mais ampla

Processo: Emrys sinaliza em revisão trimestral → Fabiano decide → Craft arquiva (move arquivo para `.claude/skills/tavolas-deprecadas/` ou deleta)

### Limite soft

Manter no máximo ~12 Távolas Nomeadas ativas simultaneamente. Passou disso, Emrys sinaliza "catálogo proliferando" e sugere consolidação.

## Localização dos arquivos

| Tipo | Path |
|---|---|
| Skill ativa | `.claude/skills/tavola-{nome}/SKILL.md` |
| Memória de contexto | `memory/tavola_{nome}.md` (opcional, se houver contexto histórico valioso) |
| Skill depreciada | `.claude/skills/tavolas-deprecadas/tavola-{nome}/` (se aplicável no futuro) |

## Relação com outras regras

- **Complementa** `agent-authority.md` — Távolas Nomeadas respeitam a delegation matrix (ex: git push continua exclusivo do @devops mesmo dentro de uma Távola)
- **Complementa** `specialist-handoff-mandatory.md` — dentro de uma Távola, quando surge tarefa fora do escopo dos membros presentes, handoff para especialista ainda é mandatório
- **Complementa** `transversal-review-gate.md` — artefatos gerados por Távolas Nomeadas client-facing passam pelo gate
- **Sob autoridade de** Emrys (Regência) — Emrys governa o catálogo

## Severidade

**SHOULD** — Távolas Nomeadas são um padrão recomendado, não obrigatório. Decisões podem ser tomadas sem criar Távola Nomeada formal (via Távola Express conversacional). Porém, quando uma composição se repete frequentemente, criar a Távola Nomeada é o caminho correto.

---

*Rule: tavolas-nomeadas | Criada: 2026-04-11 | Atualizada: 2026-04-12 (Conductor-Hub + memory_path + spawn template) | Mantenedor: Emrys (Regência) | Severidade: SHOULD*
