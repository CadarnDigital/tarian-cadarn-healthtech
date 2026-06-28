# PM Agent Memory (Morgan)

## Active Patterns
<!-- Current, verified patterns used by this agent -->

### Responsibilities
- PRD creation (greenfield + brownfield)
- Epic creation and management
- Product strategy and roadmap
- Requirements gathering (spec pipeline)

### Epic Orchestration
- `*execute-epic` with `EPIC-{ID}-EXECUTION.yaml`
- State tracked in `.aiox/epic-{epicId}-state.yaml`
- Wave-based parallel execution

### Delegation
- Story creation → @sm (`*draft`)
- Course correction → @aiox-master (`*correct-course`)
- Deep research → @analyst (`*research`)

### Ecossistema Claude — Opções de Execução (registrado 2026-06-22)

Ao planejar épicos, PRDs ou features que envolvam automação, acesso a plataformas externas ou rotinas sem intervenção manual — considerar estas opções antes de assumir que "precisa de desenvolvimento":

- **Claude Cowork** (Desktop, Pro+): executa tarefas autônomas, acessa arquivos locais, agenda rotinas recorrentes (ex: relatório toda segunda). Usa Computer Use + integração Chrome. Não-técnicos conseguem usar.
- **Claude for Chrome** (extensão, beta): acessa qualquer plataforma onde o usuário já está logado — Instagram, Meta Ads, Google Ads, etc. — sem API. Ideal para leitura e extração de dados.
- **MCP servers**: integração via API para plataformas que suportam (Meta Ads MCP oficial = só pago; Instagram orgânico = servidor terceiro com setup manual).

**Aplicação em product planning:** quando o requisito for "acessar dados de plataforma X automaticamente", mapear primeiro: Cowork consegue? extensão Chrome consegue? MCP existe? Só então propor desenvolvimento custom.

### Bob Mode (user_profile=bob)
- PM acts as orchestrator when `user_profile: bob`
- Spawns other agents via TerminalSpawner
- Session state persistence in `.aiox/bob-session/`

### Key Locations
- PRD: `docs/prd/` (sharded)
- Epics: `docs/stories/epics/`
- Templates: `.aiox-core/development/templates/`

## Promotion Candidates
<!-- Patterns seen across 3+ agents — candidates for CLAUDE.md or .claude/rules/ -->
<!-- Format: - **{pattern}** | Source: {agent} | Detected: {YYYY-MM-DD} -->

## Archived
<!-- Patterns no longer relevant — kept for history -->
<!-- Format: - ~~{pattern}~~ | Archived: {YYYY-MM-DD} | Reason: {reason} -->
