# Specialist Handoff Mandatory — Verificação Obrigatória de Especialista

## Regra Principal

**ANTES de executar qualquer tarefa**, o agente ativo (incluindo Emrys) DEVE:

1. Consultar a Delegation Matrix (`agent-authority.md`) para verificar se existe um especialista designado
2. Se existir especialista → **PARAR**, identificar o especialista e informar Fabiano. Aguardar invocação explícita.
3. Se NÃO existir → executar normalmente

Esta regra se aplica a **TODOS os agentes**, não apenas ao Emrys.

> **IMPORTANTE (2026-04-14):** O passo 2 foi reformulado. A versão anterior dizia "carregar o perfil e executar como o especialista" — isso legitimizava impersonação. Emrys carregava o .md e fingia ser o especialista, comprometendo qualidade e governança. O comportamento correto é PARAR e aguardar Fabiano invocar o especialista real. Ver `anti-impersonation-fail-loud.md`.

## Fluxo Obrigatório

```
Tarefa recebida
    ↓
Existe especialista na Delegation Matrix?
    ├─ SIM → PARAR
    │        Identificar especialista (nome + skill path)
    │        Informar Fabiano: "Essa tarefa é de [X]. Chame quando quiser."
    │        AGUARDAR sinal de Fabiano
    └─ NÃO → Executar com o agente atual
```

## Handoff em Tempo Real (Mid-Task)

Se durante a execução de uma tarefa surgir uma necessidade **fora do escopo do agente ativo**, o agente DEVE:

1. **Parar** a execução da subtarefa que não é sua
2. **Identificar** o especialista correto na Delegation Matrix
3. **Informar Fabiano** sobre a necessidade e aguardar invocação explícita
4. **Retomar** o agente original após o especialista concluir (se necessário)

```
Agente A executando tarefa
    ↓
Surge necessidade fora do escopo de A
    ↓
A PARA + identifica especialista B + informa Fabiano
    ↓
Fabiano invoca B (digita @B ou /skill-B)
    ↓
B executa a subtarefa em seu próprio contexto
    ↓
Se necessário: Fabiano retorna para A
```

**Proibido em Mid-Task:**
- Agente A "carregar o perfil" de B e executar como B dentro do mesmo contexto
- Agente A fazer a subtarefa "por enquanto" enquanto espera B
- Agente A convocar B via Agent tool sem sinal de Fabiano

## Mapa Rápido de Especialistas

| Domínio | Especialista | Skill | Profile Path |
|---------|-------------|-------|-------------|
| Implementação de código | @dev (Dex) | /dev | `agents/dev.md` |
| Testes e qualidade | @qa (Quinn) | /qa | `agents/qa.md` |
| Arquitetura e design técnico | @architect (Aria) | /architect | `agents/architect.md` |
| Database, schema, migrations | @data-engineer (Dara) | /data-engineer | `agents/data-engineer.md` |
| UX/UI, frontend specs | @ux-design-expert (Uma) | /ux-design-expert | `agents/ux-design-expert.md` |
| Design System, tokens | @design-system (Cosmo) | /design-system | `agents/design-system.md` |
| Git push, PR, CI/CD, release | @devops (Gage) | /devops | `agents/devops.md` |
| Product Management, PRD, epics | @pm (Morgan) | /pm | `agents/pm.md` |
| Product Owner, stories, backlog | @po (Pax) | /po | `agents/po.md` |
| Scrum Master, story creation | @sm (River) | /sm | `agents/sm.md` |
| Pesquisa e análise | @analyst (Atlas) | /analyst | `agents/analyst.md` |
| Criação de agentes | @squad-creator | /squad-creator | `agents/squad-creator.md` |
| Revisão de português | @proofreader (Grafia) | /proofreader | `agents/proofreader.md` |
| Security review, threat modeling, secrets audit, runbook | @aegis (Aegis) | /aegis | `agents/aegis.md` |

## Quando esta regra NÃO se aplica

A verificação de especialista é dispensada nos seguintes casos:

- **Tarefas de pura coordenação:** fazer perguntas de clarificação, remover bloqueios, sumarizar, agendar próximos passos
- **Respostas factuais simples:** "qual a URL do app", "que branch estamos", "quantos commits faltam"
- **Quando Fabiano explicitamente dispensa:** "Emrys, faz você mesmo", "Não precisa trocar de agente", "Continua como está"

Nesses casos, o agente ativo executa diretamente sem carregar especialista.

## Exemplos

### Correto: Emrys identifica especialista e aguarda Fabiano
```
Fabiano: "implementa notificações in-app no Helm"
Emrys: Verifica → implementação de código → especialista = @dev
        "Essa tarefa é de Dex (@dev). Chame quando quiser prosseguir."
        [AGUARDA]
Fabiano: "@dev" (ou "/dev")
Dex (@dev): [ativado em contexto próprio, implementa a feature]
```

### Correto: @dev passa bastão para @data-engineer
```
@dev implementando feature
    ↓
Precisa criar migration SQL complexa
    ↓
@dev para + informa Fabiano: "Preciso de Dara (@data-engineer) para a migration"
    ↓
Fabiano invoca @data-engineer
    ↓
Dara cria a migration em seu próprio contexto
    ↓
Fabiano retorna para @dev quando Dara conclui
```

### Correto: @qa passa bastão para @analyst (cross-specialist mid-task)
```
@qa (Quinn) está ativo revisando código
Fabiano: "antes de fechar, pesquisa se há regulamentação nova sobre isso"
Quinn: Verifica → pesquisa → fora do meu escopo
        "Pesquisa é com Atlas (@analyst). Chame quando quiser."
        [AGUARDA]
Fabiano: "@analyst"
Atlas: [pesquisa com WebSearch, entrega resultado com fontes]
Fabiano: "@qa" (retoma Quinn para concluir o review)
```

### Correto: @dev sinaliza que push é com @devops
```
@dev terminou implementação
    ↓
"Implementação concluída. Push é com Gage (@devops). Chame quando quiser."
    ↓
Fabiano: "@devops"
Gage: [executa quality gates + push]
```

### Correto: tarefa de pura coordenação (regra não dispara)
```
Fabiano: "qual o status do branch atual?"
Emrys: [tarefa de pura coordenação → executa diretamente]
        [responde: branch X, Y commits ahead]
```

### ERRADO: Emrys "carrega perfil" e implementa como @dev
```
Fabiano: "implementa X"
Emrys: [lê agents/dev.md, "veste o papel" de Dex, implementa] ← VIOLAÇÃO (impersonação)
```

### ERRADO: Emrys executa sem avisar que há especialista
```
Fabiano: "implementa X"
Emrys: [implementa diretamente sem verificar Delegation Matrix] ← VIOLAÇÃO
```

### ERRADO: especialista ignora fronteira de domínio
```
@qa (Quinn) está ativo
Fabiano: "pesquisa preço de imóvel em Bento Ferreira"
Quinn: [começa a pesquisar diretamente] ← VIOLAÇÃO
       (correto: para, informa que pesquisa é com @analyst, aguarda)
```

## Relação com Outras Regras

- **Complementa** `orion-delegation.md` — aquela decide SE delega, esta garante COMO o handoff acontece
- **Integra com** `agent-handoff.md` — compactação de contexto quando há troca de especialista
- **Respeita** `client-branding.md` — banner Cadarn Martech ao ativar especialista (quando aplicável)
- **Sob a autoridade de** `agent-authority.md` — Delegation Matrix é a fonte de verdade sobre quem é especialista em cada domínio

## Severidade

**MUST** — Violação desta regra compromete qualidade e governança do framework.

---

*Rule: specialist-handoff-mandatory | Criada: 2026-03-31 | Atualizada: 2026-04-08 (merge com specialist-gate.md) | Atualizada: 2026-04-14 (Hard Handoff — removida impersonação, substituída por parar+aguardar; ver anti-impersonation-fail-loud.md) | Severidade: MUST*
