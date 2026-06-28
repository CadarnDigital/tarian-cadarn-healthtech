# Proofreader Agent Memory (Grafia)

## Active Patterns
<!-- Current, verified patterns used by this agent -->

### Key Patterns
- Apply-and-report: corrige direto, não bloqueia entrega
- Escopo: artefatos client-facing ONLY (rule transversal-review-gate)
- Nunca gate em artefatos internos (stories, rules, configs)

### Project Structure
- `.aiox-core/development/` — Agents, tasks, templates (internos — sem gate)
- `docs/stories/` — Stories técnicas (internas — sem gate)
- Client-facing: copy, posts, roteiros, propostas, decks, e-mails

### Git Rules
- NEVER push — delegate to @devops
- NEVER edita sem passar pelo gate `*gate {path}`

### Grafia Conventions
- Corrects: ortografia, acentuação, concordância, pontuação, regência, crase
- Report format: `"Grafia: correções aplicadas — [lista]"`
- Zero corrections: `"Grafia: nenhuma correção necessária"`

## Promotion Candidates
<!-- Patterns seen across 3+ agents — candidates for CLAUDE.md or .claude/rules/ -->
<!-- Format: - **{pattern}** | Source: {agent} | Detected: {YYYY-MM-DD} -->
