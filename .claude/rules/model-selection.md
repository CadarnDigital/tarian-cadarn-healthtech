# Model Selection — Padrão Planner-Executor para o AIOX

## Regra Principal

O AIOX adota um padrão **planner-executor** explícito entre modelos Claude:

- **Opus 4.6** para decisões de julgamento, design de sistema, síntese cross-domain pesada
- **Sonnet 4.6** para execução de template, implementação de código, aplicação de rule já definida
- **Haiku 4.5** para tarefas mecânicas triviais

O ponto de transição entre modelos **coincide com handoffs formais** já previstos em outras rules do framework (ex: `orion-delegation.md`, `specialist-handoff-mandatory.md`). Não existe ponto de corte novo a inventar: a troca de modelo acompanha a troca de papel.

## Por que esta regra existe

1. **Custo real não-trivial.** Opus é ~5x mais caro que Sonnet em input e ~5x em output. Rodar aplicação de template em Opus é desperdício direto.
2. **Qualidade do Opus não se aplica a todo trabalho.** A vantagem do Opus está em julgamento, analogia, síntese cruzada, diagnóstico contrafactual. Em execução mecânica (escrever arquivo a partir de template, editar linha, aplicar rule), Sonnet entrega qualidade indistinguível.
3. **Ponto de transição natural já existe.** Os protocolos do AIOX (Távolas Nomeadas, Story Development, Orion Delegation) já separam "quem decide" de "quem executa". Basta alinhar a escolha de modelo ao papel.
4. **Replicável em Tarian de clientes.** Uma rule de model selection bem formalizada vira economia cruzada em todos os projetos do framework.

## Matriz de decisão por natureza do trabalho

### 🔴 Use Opus 4.6 quando

| Categoria | Exemplos |
|---|---|
| **Design de sistema novo** | Criar um método, framework, arquitetura conceitual inédita (ex: criar o Método CADARN, escrever esta rule pela primeira vez) |
| **Síntese cross-domain pesada** | Comparar 6+ conceitos e destilar distinção não-óbvia que vira decisão permanente (ex: Logos vs Verbo vs Mozi) |
| **Decisões irreversíveis de alto impacto** | Rebrandings, pivots, ADRs constitucionais, escolha de stack, alterações no Código CADARN |
| **Diagnóstico de falha estratégica** | "Por que isto não está funcionando?" com raciocínio contrafactual, identificação de causa raiz não-óbvia |
| **Copy client-facing de alta visibilidade** | Manifestos, hero sections, headlines das Bandeiras, peças que definem marca por anos |
| **Convocação de Távola Magna** | Decisões que exigem as 6 squads simultâneas |
| **Fases de julgamento de Távola Nomeada** | Fases 1-3 (briefing, composição, protocolo) |
| **Mesa redonda estratégica** | Deliberação de trade-offs entre squads |
| **Primeira versão de uma skill/rule/template** | Quando não há padrão anterior a aplicar |

### 🟢 Use Sonnet 4.6 quando

| Categoria | Exemplos |
|---|---|
| **Aplicação de template existente** | Criar nova Távola Nomeada seguindo padrão já formalizado, criar novo agente seguindo template |
| **Execução de task já definida** | Implementar story, rodar checklist, aplicar rule conhecida, fechar gate de QA |
| **Fase 4 de Távola Nomeada** | Craft executando criação técnica (skill + CLAUDE.md + memória) |
| **Consolidação e resumo** | Checkpoints, memórias, changelogs, sumários de sessão, atas |
| **Edição e refatoração** | Ajustar arquivo existente, atualizar CLAUDE.md, indexar MEMORY.md |
| **Criação de código rotineira** | Implementação de feature com escopo claro, testes, fix de bug, refatoração guiada |
| **Conversas operacionais** | Status, perguntas factuais sobre o framework, navegação de arquivos |
| **Copy rotineira** | Posts, legendas, headlines que seguem padrão já validado em bandeira existente |
| **Squad Forja em modo execução** | 90% do trabalho de @dev, @qa, @devops após a story estar bem definida |
| **Peças de conteúdo dentro de bandeira já fechada** | O pensamento estratégico foi feito; a execução da peça pode ser Sonnet |

### 🟡 Use Haiku 4.5 quando

| Categoria | Exemplos |
|---|---|
| **Tarefas ultra-mecânicas** | Renomear arquivo, find/replace, formatar lista, reorganizar frontmatter |
| **Comandos simples** | `*status`, `*help`, listagem, contagem |
| **Triagem inicial** | Classificar pedido antes de escalar para Sonnet/Opus |
| **Responder pergunta factual objetiva** | "Qual o caminho do arquivo X?", "Quantos agentes a Squad MKT tem?" |

## Pontos de transição formais no AIOX

Estes são os handoffs onde a troca de modelo é **natural e recomendada**:

### Távolas Nomeadas (rule `tavolas-nomeadas.md`)
```
Fase 1 — Briefing        ┐
Fase 2 — Composição      ├─→  OPUS (julgamento)
Fase 3 — Protocolo       ┘
       ↓ [HANDOFF: Emrys → Craft]
Fase 4 — Execução        →  SONNET (aplicação de template)
```

### Story Development Cycle (rule `story-lifecycle.md`)
```
@pm *create-epic         ┐
@sm *draft               ├─→  OPUS (design de requisitos)
@po *validate            ┘
       ↓ [HANDOFF: River/Pax → Dex]
@dev *develop            ┐
@qa *review              ├─→  SONNET (execução + validação)
@devops *push            ┘
```

### Orion Delegation (rule `orion-delegation.md`)
```
Emrys identifica especialista    →  OPUS (diagnóstico da complexidade)
       ↓ [HANDOFF: Emrys → Especialista]
Especialista executa              →  SONNET (execução dentro do domínio)
```

### Criação de Agente (rule `specialist-handoff-mandatory.md`)
```
Emrys + Fabiano definem persona, escopo, comandos  →  OPUS (design)
       ↓ [HANDOFF: Emrys → Craft]
Craft escreve o YAML do agente                       →  SONNET (scaffolding)
```

### Mesa Redonda Estratégica
```
Deliberação e decisão           →  OPUS
       ↓ [HANDOFF: decisão → consolidação]
Consolidação em memória/ata     →  SONNET
```

## Regra de Consulta Obrigatória — Troca de Modelo em Spawn (MUST)

**Antes de invocar a tool Agent com um `model` explícito (override do default — por exemplo `model: "opus"` num spawn de subagente), o agente condutor DEVE perguntar a Fabiano e aguardar confirmação. Nunca decidir sozinho e informar depois.**

### Por que esta regra existe

O restante desta rule orienta QUANDO Opus é tecnicamente mais adequado que Sonnet — mas orientação de adequação técnica não é autorização de gasto. Em 2026-07-20, uma Távola Express de 6 agentes foi rodada inteira em Opus sem consulta prévia. Fabiano gostou de a ferramenta permitir essa escolha, mas foi claro: quer ser consultado ANTES de cada troca de modelo em spawn, não informado depois do fato.

### Regra prática

Antes de qualquer `Agent(model: "opus"|"sonnet"|"haiku"|"fable")` que seja um override explícito do default:

1. Identificar que o spawn vai usar model explícito
2. PERGUNTAR a Fabiano antes de disparar: *"Vou rodar {tarefa} em {modelo}, porque {razão}. Confirma?"*
3. AGUARDAR confirmação explícita antes de chamar a tool Agent

**Exceção:** se Fabiano já autorizou o modelo para aquela sessão/tarefa específica (ex: "roda tudo em Opus hoje", "pode usar Opus pra Távola inteira"), não é preciso perguntar de novo dentro da mesma sessão para a mesma tarefa recorrente.

### Severidade

**MUST** — específico para o ATO de escolher/trocar o modelo de um spawn. Isso substitui, só neste ponto, o caráter "SHOULD, nunca bloqueia" do resto da rule. A orientação de QUANDO Opus é tecnicamente melhor continua SHOULD; a consulta antes de AGIR sobre essa escolha é MUST.

---

## Regra de exceção: Sonnet escala de volta

Se durante a execução em Sonnet aparecer uma **ambiguidade não resolvida** nas fases anteriores de julgamento, Sonnet deve **parar e devolver a decisão ao Opus** em vez de inventar. Exemplos:

- Template faz referência a campo que não foi definido no briefing
- Fase de execução descobre um trade-off não mapeado
- Aplicação de rule conflita com outra rule não citada no planejamento
- Surge novo requisito mid-task que altera premissas

**Regra de ouro:** Sonnet executa, **não inventa**. Se faltou decisão, escala de volta.

## Como operacionalizar a troca

Há 3 caminhos práticos:

### Caminho A — Troca inline via comando do CLI
Se o Claude Code da sessão atual suporta `/model sonnet` no meio da conversa, basta trocar quando o protocolo chegar ao ponto de handoff. **Mais fluido, menos setup.** Verificar disponibilidade no plano e versão do CLI.

### Caminho B — Parking + Resume entre modelos
1. Finalizar fase de julgamento em Opus
2. Rodar `/park {namespace}` salvando checkpoint com fase anterior aprovada
3. Abrir nova sessão em Sonnet
4. Rodar `/resume {namespace}`
5. Primeira instrução vira "executar a próxima fase"

Mais rigoroso na separação, mais chato operacionalmente. Útil quando as fases estão separadas por mais de 5 minutos (cache TTL).

### Caminho C — Duas sessões paralelas
Manter uma sessão Opus aberta para decisão e uma sessão Sonnet aberta para execução. Trocar conforme o papel em jogo. Exige disciplina mas é o mais flexível para trabalho longo.

**Recomendação padrão:** Caminho A quando disponível, Caminho B como fallback formal.

## Aplicabilidade por squad

| Squad / Contexto | Tendência dominante |
|---|---|
| **Squad MKT** — brief estratégico, definição de bandeira, manifesto | Opus |
| **Squad MKT** — execução de peça dentro de bandeira já fechada | Sonnet |
| **Squad Comercial** — diagnóstico de pipeline, redesenho de funil | Opus |
| **Squad Comercial** — execução de triagem, MEDDIC, pós-venda | Sonnet |
| **Squad Ops** — design de processo novo | Opus |
| **Squad Ops** — execução de processo existente | Sonnet |
| **Squad Jurídica** — análise de risco, parecer complexo, novo contrato | Opus |
| **Squad Jurídica** — revisão de cláusula padrão, compliance rotineiro | Sonnet |
| **Squad Forja** — arquitetura, decisão de stack, design de sistema | Opus |
| **Squad Forja** — implementação, teste, deploy, git operations | Sonnet |
| **Conselho de Mentoria** — mentoria estratégica, provocação, diagnóstico | Opus |
| **Távola Magna** | Opus (inegociável) |
| **Távolas Nomeadas Fase 1-3** | Opus |
| **Távolas Nomeadas Fase 4** | Sonnet |

## Economia esperada

Estimativa grosseira baseada em volume típico de sessões AIOX:

| Cenário | Custo relativo |
|---|---|
| Tudo em Opus | 100% (baseline atual) |
| Opus só nas fases de julgamento + Sonnet na execução | **~30-40%** |
| Tudo em Sonnet | ~20% |

O ponto ótimo (~30-40%) preserva 90-95% da qualidade do all-Opus, economizando 60-70% do custo.

## Anti-patterns

- ❌ **Trocar de modelo no meio de um raciocínio em andamento** (quebra cache desnecessariamente). Trocar só em handoff formal.
- ❌ **Usar Opus para redigir checkpoint/memória/changelog** (é consolidação, não julgamento)
- ❌ **Usar Sonnet para primeira versão de rule/framework/método** (é design, não aplicação)
- ❌ **Usar Haiku para qualquer trabalho que envolva Cadarn Martech específico** (falta de contexto de domínio)
- ❌ **Trocar modelo sem compactar contexto** — sempre gerar handoff artifact antes da troca (rule `agent-handoff.md`)

## Governança desta rule

- **Autoridade:** Fabiano + Emrys (Regência)
- **Enforcement:** Opcional — é otimização, não constitucional. Emrys sugere a troca quando detecta handoff formal, mas não bloqueia.
- **Revisão:** Trimestral ou quando Anthropic mudar pricing/modelos significativamente

## Relação com outras rules

- **`tavolas-nomeadas.md`** — as fases 1-3 são Opus, fase 4 é Sonnet
- **`orion-delegation.md`** — Emrys é Opus, especialistas executando são Sonnet
- **`specialist-handoff-mandatory.md`** — o handoff de persona pode vir junto com handoff de modelo
- **`agent-handoff.md`** — compactação de contexto é pré-requisito de toda troca de modelo
- **`story-lifecycle.md`** — fases de design (SM/PO/Architect) tendem a Opus, execução (Dev/QA/DevOps) tende a Sonnet
- **`transversal-review-gate.md`** — Grafia e Dick rodam em Sonnet na maioria dos casos

## Severidade

**SHOULD** — esta rule é **recomendação fortemente otimizada**, não constitucional. A qualidade final não degrada significativamente se você rodar tudo em Opus. O que muda é custo. Violações (rodar Opus onde Sonnet bastava) não comprometem governança, só economia.

Como a rule visa otimização econômica, Emrys deve **sinalizar** oportunidades de troca de modelo nos pontos de handoff formal, mas **nunca bloquear** uma decisão de usar Opus quando Fabiano optar conscientemente.

---

*Rule: model-selection | Criada: 2026-04-11 | Atualizada: 2026-07-20 (Regra de Consulta Obrigatória — MUST perguntar antes de trocar modelo em spawn) | Autor: Fabiano + Emrys | Padrão: Planner-Executor | Severidade: SHOULD (orientação) / MUST (consulta antes de trocar) | Revisão: trimestral*
