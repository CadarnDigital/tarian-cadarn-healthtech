# Session Management — Protocolo de Economia e Continuidade

## Regra Principal

Sessões longas no AIOX seguem três gatilhos obrigatórios: **compactação proativa durante a sessão**, **checkpoint antes de encerrar**, e **retomada estruturada na próxima sessão**. `/clear` sem checkpoint é descarte — proibido quando há trabalho em andamento.

## Por que esta regra existe

Sessões extensas acumulam histórico verboso que não agrega contexto — apenas consome tokens. A compactação proativa (antes que o Claude force) produz resumo de qualidade superior. Sem checkpoint, trabalho em andamento se perde ao encerrar. A rotina abaixo elimina ambos os problemas.

## Os 3 Gatilhos

### Gatilho 1 — Compactação proativa (durante a sessão)

**Quando usar:** ao perceber que a sessão está ficando pesada — muitas trocas de agente, muitos arquivos lidos, contexto acumulado sem /compact anterior.

**Comando:**
```
/compact
```

O Claude Code resume toda a conversa em ~2-3k tokens e descarta o histórico bruto. O contexto permanece funcional — só a verbosidade é eliminada.

**Regra:** usar ANTES do Claude forçar compactação automática. Quando Claude força, a qualidade do resumo é inferior porque o contexto já está saturado.

**Frequência recomendada:** a cada 50-80 turnos de troca substantiva, ou sempre que mudar de tema/agente dentro da mesma sessão.

### Gatilho 2 — Checkpoint antes de encerrar (pré-/clear ou pré-encerramento)

**Quando usar:** sempre que a sessão contiver trabalho em andamento — decisões tomadas, artefatos criados, contexto que precisará ser retomado.

**Comando:**
```
/park {namespace}
```

Cria commit de checkpoint + salva estado da sessão. Permite retomada exata na próxima sessão.

**Regra:** NUNCA rodar `/clear` em sessão com trabalho em andamento sem ter rodado `/park` antes. O hook de auto-checkpoint já bloqueia encerramento sem salvamento — mas o `/park` é mais completo.

**Para decisões críticas mid-session:** salvar em memória no momento em que acontecem, não esperar o checkpoint final.

### Gatilho 3 — Retomada estruturada (início da próxima sessão)

**Quando usar:** ao iniciar sessão que dá continuidade a trabalho anterior.

**Comando:**
```
/resume {namespace}
```

Retoma com contexto completo do checkpoint anterior. Elimina necessidade de re-explicar contexto — que custaria mais tokens do que a sessão anterior teria custado compactar.

## Regra específica: /clear puro

`/clear` sem `/park` prévio é permitido APENAS quando:
- A sessão foi puramente exploratória (perguntas, nenhum artefato, nenhuma decisão)
- Nenhum trabalho em andamento será retomado

Em qualquer outro caso: `/park` antes do `/clear`.

## Protocolo para Távolas

Sessões de Távola têm perfil diferente: o modelo Conductor-Hub spawna subagentes isolados, o que mantém o contexto principal mais leve por design. Ainda assim:

- Aplicar `/compact` entre fases do protocolo (ex: entre fase de briefing e fase de execução)
- Salvar atas de turno em `docs/projeto-camara/atas/` (ou equivalente) conforme protocolo da Távola
- `/park` ao encerrar sessão de Távola com protocolo incompleto

## Anti-patterns

- ❌ `/clear` direto sem `/park` quando há trabalho em andamento
- ❌ Esperar Claude forçar `/compact` — fazer proativamente
- ❌ Salvar decisões críticas só no final da sessão (salvar no momento)
- ❌ Iniciar nova sessão de continuidade sem `/resume` — re-explicar contexto custa mais tokens

## Relação com outras regras

| Rule/Skill | Relação |
|---|---|
| `agent-handoff.md` | Compactação em troca de agente complementa a compactação de sessão |
| `/park` skill | Executor do Gatilho 2 |
| `/session-checkpoint` skill | Alternativa leve ao `/park` para checkpoints sem commit |
| `feedback_auto_checkpoint.md` | Hook que bloqueia encerramento sem salvamento — primeira linha de defesa |

## Severidade

**SHOULD** — é otimização operacional, não constitucional. Violações não comprometem governança, mas aumentam custo e risco de perda de trabalho.

Emrys pode (e deve) lembrar Fabiano do `/compact` quando identificar que a sessão está pesando, e do `/park` antes de encerrar.

---

*Rule: session-management | Criada: 2026-05-01 | Proposta por: Morgan (PM) | Autoridade: Fabiano | Severidade: SHOULD*
