---
paths:
  - ".claude/skills/**"
  - ".aiox-core/**"
---
# Skill Incorporation Policy — Governança de Plugins Externos no AIOX

## Propósito

Governar a incorporação de skills/plugins externos no framework AIOX, garantindo que nenhuma skill de origem externa ganhe permissões perigosas sem revisão explícita, registro de auditoria e período de quarentena.

Esta rule é pré-requisito constitucional para a Wave 5 (Plugins Externos + Sigstore). Conforme o PRD V1.1 §3.7, a rule deve estar ativa há 30+ dias com auditoria contínua antes de qualquer skill externa ser aceita.

## Escopo

**Todo plugin/skill** que vier de fora dos diretórios controlados por Fabiano:

| Diretório | Status |
|---|---|
| `.claude/skills/` — skills internas Cadarn | INTERNO — fora do escopo desta rule |
| `.aiox-core/development/agents/` — agentes do framework | INTERNO — fora do escopo desta rule |
| Qualquer outro path | EXTERNO — coberto por esta rule |

Skills externas são identificadas pelo registro em `.aiox-core/security/external-skills-paths.yaml`.

## Princípios

### 1. Zero-Trust por Default

Toda skill externa é tratada como não confiável até aprovação explícita. Ausência de registro em `external-skills-paths.yaml` significa não-autorizada. Linter rejeita skills não registradas.

### 2. Allowlist Explícita

Nenhuma permissão é concedida implicitamente. Cada tool declarada no frontmatter de uma skill externa é verificada contra o ruleset canônico (`.aiox-core/security/skill-incorporation-ruleset.yaml`). Padrão BLOCK_ALWAYS é bloqueio imediato.

### 3. Sandbox Obrigatório (Wave 1.5)

Toda skill externa em produção deve rodar em sandbox isolado via bwrap wrapper (Story 1.5 — implementação futura). Esta rule cria a política; a Story 1.5 cria o mecanismo técnico. Até Story 1.5 estar ativa, skills externas não devem ser aceitas em modo enforce.

### 4. Auditoria Contínua

Todo evento de incorporação (BLOCK, REQUIRE_AUDIT, WARN_REVIEW) é registrado em `.aiox/audit/skill-incorporation-events.jsonl`. O audit log é imutável — append-only. Não deletar entradas.

## Processo de Incorporação

### Passo 1 — PR com skill externa

Abrir PR com a skill externa. Notificar **@aegis** (owner desta rule) e **@cosmo** (consistência com framework) como revisores obrigatórios. Sem aprovação de ambos, o PR não é mergeado.

### Passo 2 — Registro em external-skills-paths.yaml

Adicionar o path da skill em `.aiox-core/security/external-skills-paths.yaml` com comentário descrevendo a origem e o propósito.

### Passo 3 — Execução do linter

```bash
node .aiox-core/security/skill-permissions-linter.js [path-da-skill]
```

O linter aplica o ruleset canônico sobre as permissões declaradas no frontmatter da skill. Ver procedimento completo em `docs/security/skill-incorporation-procedure.md`.

### Passo 4 — Quarentena (7 dias mínimo)

Skills aprovadas pelo linter (sem BLOCK_ALWAYS) entram em quarentena obrigatória:

```yaml
# No frontmatter da skill:
quarantine: true
quarantine_started_at: YYYY-MM-DD
```

Em quarentena: padrões BLOCK_ALWAYS viram WARNING (não bloqueiam). A skill opera em modo warn-only por 7 dias. Monitorar audit log durante o período.

### Passo 5 — Ativação

Após 7 dias em quarentena sem anomalias:
1. Abrir PR removendo flags `quarantine` e `quarantine_started_at`
2. @aegis revisa o audit log do período
3. Merge libera enforcement ativo

## Ruleset Canônico

`.aiox-core/security/skill-incorporation-ruleset.yaml` — 3 categorias:

| Categoria | Ação do Linter | Exemplo |
|---|---|---|
| `BLOCK_ALWAYS` | exit 1, mensagem clara | `Bash(curl *)`, `Bash(eval *)`, `Bash(sudo *)` |
| `REQUIRE_AUDIT` | exit 0 + warning + audit log | `Bash(npm *)`, `Bash(docker *)` |
| `WARN_REVIEW` | exit 0 + warning visível | `Bash(git push *)`, `mcp__.*__write.*` |

**Nota de segurança (Marco 3.5, auditoria Aegis HIGH):** O padrão `Bash(*)` sozinho não fecha todos os vetores de bypass. Plugins hostis podem declarar `Bash(bash <cmd>)` ou `Bash(/bin/sh <cmd>)` para escapar. O ruleset inclui explicitamente os bypass patterns de shell alternativo.

## Linter

`.aiox-core/security/skill-permissions-linter.js`

```bash
# Verificar skill externa:
node .aiox-core/security/skill-permissions-linter.js path/da/skill.md

# Verificar com output verbose:
node .aiox-core/security/skill-permissions-linter.js path/da/skill.md --verbose
```

Comando Aegis: `*lint-skill {path}` invoca este linter.

## Relação com outras regras

| Rule | Relação |
|---|---|
| `agent-authority.md` | Delegation matrix — Aegis owns security review, Gage owns CI/CD execution |
| `security-review-mandatory.md` | Gate Aegis obrigatório — esta rule é o gate específico para skills externas |
| `anti-impersonation-fail-loud.md` | Fail-loud quando linter bloqueia — reportar, não improvizar alternativa |

## Ownership

- **Aegis (@aegis):** owner da rule, do ruleset e do linter — define a política
- **Cosmo (@design-system):** revisa consistência com framework
- **Gage (@devops):** executa CI/CD com o linter integrado (Wave 5)
- **Fabiano:** autoridade absoluta — único que pode dispensar gate

## Severidade

**MUST** — Violação compromete a integridade do framework AIOX. Uma skill hostil com `Bash(curl *)` pode exfiltrar credenciais, executar código remoto ou comprometer o ambiente de desenvolvimento.

---

*Rule: skill-incorporation-policy | Criada: 2026-05-01 | Origem: PRD V1.1 §3.7 + Story 0.6 Projeto Câmara | Owner: Aegis (@aegis) | Co-revisor: Cosmo (@design-system) | Autoridade: Fabiano | Severidade: MUST | Bloqueia: Wave 5 (Plugins Externos + Sigstore)*
