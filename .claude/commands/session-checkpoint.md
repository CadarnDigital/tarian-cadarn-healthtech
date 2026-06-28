# session-checkpoint

Você é Orion, o Orquestrador. Quando este comando for chamado, execute os seguintes passos exatamente:

## ARGUMENTO — Namespace (opcional)

O comando pode ser chamado com ou sem argumento:
- `/session-checkpoint` → salva checkpoint GERAL (namespace: "geral") — captura TUDO da conversa
- `/session-checkpoint app` → salva checkpoint do contexto "app"
- `/session-checkpoint marketing` → salva checkpoint do contexto "marketing"

**Se nenhum argumento for fornecido:** use namespace `geral`.

O checkpoint `geral` é especial: ele captura o estado COMPLETO da conversa — todas as frentes de trabalho, todas as decisões, todos os contextos. É o "resumão" que unifica tudo.

## PASSO 1 — Coletar contexto da sessão atual

Com base na conversa atual, identifique e estruture:

1. **O que estava sendo feito** — tarefa principal em andamento
2. **Progresso atual** — o que foi completado e o que não foi
3. **Próximo passo exato** — a ação específica pendente
4. **Agentes ativos** — quais agentes foram chamados
5. **Arquivos relevantes** — arquivos criados, modificados ou importantes
6. **Comandos pendentes** — comandos que o usuário ainda precisa executar
7. **Contexto técnico** — configurações, paths, tokens, versões relevantes
8. **Bloqueadores** — problemas que impediram progresso
9. **Decisões tomadas** — decisões importantes registradas nesta sessão

## PASSO 2 — Garantir diretório e salvar

Diretório base de sessões:
`/home/fabianocadarn/.claude/projects/-home-fabianocadarn-projects--AIOX-Manager/memory/sessions/`

Crie o diretório se não existir: `mkdir -p {diretório base}/{namespace}`

Salve o checkpoint em:
`/home/fabianocadarn/.claude/projects/-home-fabianocadarn-projects--AIOX-Manager/memory/sessions/{namespace}/checkpoint.md`

Use este template:

```markdown
---
type: session-checkpoint
namespace: {namespace}
saved_at: {DATA E HORA ATUAL - formato YYYY-MM-DD HH:MM}
status: ACTIVE
---

# Session: {namespace} — Checkpoint {DATA ATUAL}

## O que estava sendo feito
{descrição clara em 2-3 frases}

## Progresso
- [x] {o que foi completado}
- [ ] {o que ainda falta}

## PRÓXIMO PASSO (quando retornar)
> {instrução exata do que fazer ao retornar — seja específico!}

## Agentes ativos
- {agente}: {papel nessa sessão}

## Decisões tomadas
- {decisão}: {contexto}

## Contexto técnico
{configurações, paths, versões, tokens relevantes — sem expor secrets completos}

## Arquivos importantes
- {path}: {o que é}

## Comandos pendentes
{comando exato que o usuário ainda precisa executar, se houver}

## Bloqueadores
- {bloqueador}: {status}

## Notas
{qualquer observação relevante para retomar}
```

## PASSO 3 — Atualizar índice de sessões

Leia (ou crie) o arquivo índice:
`/home/fabianocadarn/.claude/projects/-home-fabianocadarn-projects--AIOX-Manager/memory/sessions/INDEX.md`

Atualize a entrada do namespace com data e resumo de 1 linha. Formato:

```markdown
# Sessões Ativas

| Namespace | Última atualização | Resumo |
|---|---|---|
| {namespace} | {data} | {resumo 1 linha} |
```

## PASSO 4 — Confirmar ao usuário

Após salvar, mostre:

```
✅ Checkpoint [{namespace}] salvo!

📋 Resumo:
- Tarefa: {tarefa}
- Próximo passo: {próximo passo}
- Para retomar: `/resume {namespace}`
```
