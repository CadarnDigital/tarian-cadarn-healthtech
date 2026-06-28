# Dev Agent Memory (Dex)

## Active Patterns
<!-- Current, verified patterns used by this agent -->

### Key Patterns
- CommonJS (`require`/`module.exports`), NOT ES Modules
- ES2022, Node.js 18+, 2-space indent, single quotes
- Absolute imports always (never relative `../`)
- kebab-case for files, PascalCase for components
- Jest 30.2.0 for testing, `npm test` to run

### Project Structure
- `.aiox-core/core/` — Core modules (synapse, session, code-intel, orchestration)
- `.aiox-core/development/` — Agents, tasks, templates, scripts
- `.aiox-core/infrastructure/` — CI/CD, git detection, project-status
- `tests/` — Test suites (mirrors source structure)
- `docs/stories/` — Story files (active development)

### Git Rules
- NEVER push — delegate to @devops
- Conventional commits: `feat:`, `fix:`, `docs:`, `test:`, `chore:`, `refactor:`
- Reference story: `feat: implement feature [Story NOG-18]`

### Common Gotchas
- Windows paths: use forward slashes in code, bash shell not cmd
- `fs.existsSync` for sync checks, `fs.promises` for async
- atomicWriteSync from `.aiox-core/core/synapse/utils/atomic-write` for safe file writes
- CodeRabbit runs in WSL, not Windows directly

### Story Workflow
- Read task → Implement → Write tests → Validate → Mark checkbox [x]
- ONLY update: checkboxes, Debug Log, Completion Notes, Change Log, File List
- NEVER modify: Status, Story, AC, Dev Notes, Testing sections

## Promotion Candidates
<!-- Patterns seen across 3+ agents — candidates for CLAUDE.md or .claude/rules/ -->
<!-- Format: - **{pattern}** | Source: {agent} | Detected: {YYYY-MM-DD} -->
- **NEVER push — delegate to @devops** | Source: dev, analyst, sm, data-engineer, ux, qa (6 agents) | Detected: 2026-02-22 | Status: Already elevated to `.claude/rules/agent-authority.md`
- **CommonJS module system (require/module.exports)** | Source: dev, analyst, sm, data-engineer, ux, architect (6 agents) | Detected: 2026-02-22 | Status: Already in CLAUDE.md (Padroes de Codigo)
- **Conventional commits format** | Source: dev, devops, analyst, sm, data-engineer, ux (6 agents) | Detected: 2026-02-22 | Status: Already in CLAUDE.md (Convencoes Git)
- **kebab-case for files** | Source: dev, analyst, sm, data-engineer, ux (5 agents) | Detected: 2026-02-22 | Status: Already in CLAUDE.md (Padroes de Codigo)

## Claude Design — Handoff para Astro/React (adicionado 2026-05-03)

Claude Design (Anthropic, lançado 17/04/2026) gera HTML/CSS/JS interativo. Dex é o responsável por receber o handoff e implementar no Astro/React.

**O que chega no handoff:**
- HTML standalone (melhor para revisar animações)
- ZIP com design files + chat + README ("Claude Code Handoff bundle")
- "Handoff to Claude Code" — Claude Code lê o bundle e implementa

**O que NÃO vem no handoff:**
- Arquivos `.astro` ou componentes `.tsx` nativos — conversão é feita pelo Claude Code no terminal
- CSS variables exportadas oficialmente — implementar tokens a partir do bundle
- Componentes React prontos — HTML precisa ser convertido

**Para animações e mídia:**
- Animações CSS/WebGL do Claude Design entram como HTML — integrar diretamente no `.astro`
- GIF: pode vir como asset do Claude Design (aceita upload de GIF)
- Vídeo MP4/WebM em loop: NÃO é exportado pelo Claude Design — implementar com:
  ```html
  <video autoplay loop muted playsinline src="https://cdn.exemplo.com/loop.mp4" />
  ```
  Hospedar o vídeo num CDN externo e referenciar por URL

**Fluxo padrão Pixel → Dex:**
1. Pixel cria no Claude Design, exporta como Handoff to Claude Code
2. Dex recebe o bundle, converte HTML → `.astro` / `.tsx`
3. Injeta tokens de identidade como CSS variables no Tailwind/CSS Modules existentes
4. Implementa vídeo loopado via `<video>` com CDN URL

**Princípio operacional:**
Quando surgir dúvida sobre se o Claude Design suporta algum recurso que afeta o handoff, **pesquisar primeiro via Atlas + YouTube + help center oficial** (support.claude.com) antes de testar. Pesquisa é mais barata que consumir usage da ferramenta.

## Protocolo Superpowers — Squad Forja (adicionado 2026-06-22)

Fonte canônica: `.claude/rules/forja-superpowers-default.md` (auto-load em `packages/**` e `squads/**`).

**Iron Laws (inegociáveis):**
1. Entrevista de clareza antes de codar — `superpowers:brainstorming` (dispensa: Fabiano diz "vai direto")
2. Causa-raiz confirmada antes de qualquer fix — `superpowers:systematic-debugging` (sem dispensa)
3. Rodar e observar antes de declarar pronto — `superpowers:verification-before-completion` (sem dispensa)

**TDD calibrado:**
- OBRIGATÓRIO: lógica de negócio, validações, endpoints, transformações de dados
- DISPENSADO: UI/CSS, config, migration SQL, spike/exploração

**Proibições explícitas:**
- `superpowers:finishing-a-development-branch` — faz `git push -u origin`. Operação EXCLUSIVA de @devops (Gage). Nunca invocar.
- `superpowers:using-git-worktrees` — apenas sob demanda explícita de Fabiano.

## Archived
<!-- Patterns no longer relevant — kept for history -->
<!-- Format: - ~~{pattern}~~ | Archived: {YYYY-MM-DD} | Reason: {reason} -->
