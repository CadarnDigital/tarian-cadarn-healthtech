---
paths:
  - "packages/**"
  - "squads/**"
---

# Forja Superpowers Default — Protocolo de Qualidade da Squad Forja

## Regra Principal

Ao trabalhar em `packages/**` ou `squads/**`, Dex (@dev) segue este protocolo de qualidade como default. As Iron Laws são inegociáveis. As demais regras têm dispensa explícita de Fabiano como único escape hatch.

---

## Iron Laws (sempre ligadas)

### 1. Entrevista de clareza antes de codar (Ponto de Partida)

**Skill:** `superpowers:brainstorming`

Antes de iniciar trabalho substantivo em qualquer story ou tarefa técnica, Dex faz uma rodada de clareza: qual o objetivo, qual o scope, qual a restrição mais crítica. Isso não é burocracia — é o que separa implementação certa de retrabalho.

**Dispensa:** Fabiano diz "é rápido, vai direto" ou equivalente → Dex pula a entrevista e vai à implementação imediatamente.

### 2. Causa-raiz obrigatória antes de corrigir

**Skill:** `superpowers:systematic-debugging`

Ao encontrar qualquer bug ou comportamento inesperado: diagnosticar a causa real antes de propor ou executar qualquer fix. Nunca partir para solução baseada em sintoma sem confirmar a causa. Se a causa for incerta, sinalizar como `[diagnóstico pendente de confirmação]` antes de agir.

**Sem dispensa.** Esta Iron Law não tem escape hatch — diagnóstico sem causa confirmada é Art. V violado (Quality First).

### 3. Rodar e observar antes de declarar pronto

**Skill:** `superpowers:verification-before-completion`

Nenhuma task é declarada "pronto" sem evidência de que o código rodou e a saída foi observada. A evidência é o que o terminal mostrou — não o fato de o código "parecer certo". Se o ambiente bloquear a execução, reportar o bloqueio (ver `anti-impersonation-fail-loud.md` Regra 3) em vez de presumir sucesso.

**Sem dispensa.** Esta Iron Law não tem escape hatch.

---

## TDD Calibrado por Tipo de Tarefa

| Tipo de tarefa | TDD obrigatório? |
|---|---|
| Lógica de negócio (cálculos, validações, transformações) | OBRIGATÓRIO |
| Endpoints de API (Helm, Nexo, MAPA) | OBRIGATÓRIO |
| Regras de dados (parsing, conversão, ranking) | OBRIGATÓRIO |
| UI/CSS, componentes visuais sem lógica | DISPENSADO |
| Configuração (env, yaml, toml, JSON) | DISPENSADO |
| Migration SQL, DDL | DISPENSADO |
| Spike ou exploração técnica | DISPENSADO |

**Skill aplicável quando TDD é obrigatório:** `superpowers:test-driven-development`

Quando TDD é obrigatório e Fabiano não dispensou explicitamente, escrever o teste antes da implementação. O teste falhar primeiro é o sinal de que o teste está correto.

---

## Proibições e Blindagem

### finishing-a-development-branch — PROIBIDO como default

`superpowers:finishing-a-development-branch` faz `git push -u origin` e abre PR. Esta operação é **exclusiva de @devops (Gage)**. Dex nunca invoca esta skill por conta própria — não como default, não como atalho, não "só desta vez".

Ao concluir uma story: commit local (`git add`, `git commit`) → sinalizar a Gage que está pronto para push/PR. Nunca o push diretamente.

### /commit-push-pr — PROIBIDO (mesma categoria)

`commit-commands:/commit-push-pr` (plugin `commit-commands`) faz commit + push + abre PR em sequência. Push e criação de PR são **exclusivos de @devops (Gage)**. Invocar `/commit-push-pr` viola Art. II (Agent Authority) da mesma forma que `finishing-a-development-branch`.

Usar apenas `/commit` do mesmo plugin quando necessário — e somente para o commit local, nunca para push.

### using-git-worktrees — apenas sob demanda explícita

`superpowers:using-git-worktrees` é ferramenta de casos específicos (trabalho paralelo em múltiplas branches, exploração isolada). Não é default de nenhum fluxo de desenvolvimento. Usar somente quando Fabiano pedir explicitamente ou quando a situação for genuinamente paralela e não resolver de outra forma.

### brainstorming e writing-plans — scope restrito

`superpowers:brainstorming` e `superpowers:writing-plans` são ativados somente quando há ambiguidade técnica real não coberta por decisões upstream (PM/Architect). Se o escopo da story está bem definido e não há gap técnico a resolver, Dex vai direto à execução com `superpowers:executing-plans`.

---

## Mapa Skill → Comportamento

| Situação | Skill superpowers | Comportamento |
|---|---|---|
| Início de trabalho substantivo | `brainstorming` | Entrevista de clareza — 2 a 4 perguntas focadas no scope e restrições |
| Bug reportado ou comportamento inesperado | `systematic-debugging` | Sequência: reproduzir → isolar → confirmar causa → propor fix |
| Declarar task como completa | `verification-before-completion` | Rodar o código, ler saída, confirmar evidência antes do "pronto" |
| Task com lógica/validação/endpoint | `test-driven-development` | Escrever teste primeiro, ver falhar, implementar, ver passar |
| Plano de ataque para task complexa | `writing-plans` + `executing-plans` | Escrever plano → aguardar aprovação → executar sem desvio |

---

## Escape Hatch — Como Dispensar

### Dispensar a entrevista de clareza
Fabiano diz qualquer variante de: "vai direto", "é rápido", "não precisa perguntar", "pode começar". Dex registra no chat e vai à implementação.

### Dispensar TDD
Fabiano declara explicitamente que a task é spike, exploração, ou que testes virão em story separada. Dex registra no Change Log da story e implementa sem teste prévio.

### Sobre o hook completion-guard
Este protocolo inclui um hook de harness que bloqueia declarações de "pronto" sem evidência de execução. A spec completa do hook está em `.claude/hooks/completion-guard-spec.md`. A inserção em `.claude/settings.json` é responsabilidade de Gage (@devops). Quando o hook estiver ativo, a mensagem de bloqueio indicará o que está faltando — Dex deve apresentar a evidência (saída do terminal) antes de repetir a declaração de conclusão.

---

## Severidade

**MUST** — Iron Laws são inegociáveis. Violação das Iron Laws é Art. V Constitution (Quality First). As proibições (finishing-a-development-branch, using-git-worktrees) são Art. II (Agent Authority).

---

*Rule: forja-superpowers-default | Criada: 2026-06-22 | Origem: Mesa Morgan (PM) + Dex (Dev), consolidada por Emrys, aprovada por Fabiano | Autoridade: Fabiano | Severidade: MUST | Paths: packages/\*\*, squads/\*\**
