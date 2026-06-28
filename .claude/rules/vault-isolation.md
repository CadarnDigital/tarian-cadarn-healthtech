---
description: Cercadinho técnico de isolamento do vault — proteção física contra leakage cross-cliente
paths:
  - "memory/clientes/**"
  - ".gitignore"
  - "scripts/hooks/**"
---

# Vault Isolation — Cercadinho Físico

> **Decisão fundadora:** [ADR-001 §4.3](../../docs/architecture/adr/ADR-001-conselho-clientes-contexto-layer.md) + [ADR-002](../../docs/architecture/adr/ADR-002-conselho-replicado-tarians-cliente.md)
> **Severidade:** MUST
> **Aplica-se a:** Cadarn HQ + TODOS os Tarians cliente

---

## Filosofia — "Cercadinho da piscina, não placa de aviso"

Instrução verbal a um agente LLM degrada na janela de contexto. Regra que depende de "lembrar de não fazer X" falha. Toda proteção crítica de isolamento de vault tem implementação **física**, em camadas redundantes.

**Regra absoluta:** `vault.md` reside **exclusivamente** em `_AIOX_Manager/memory/clientes/{cliente-id}/vault.md` na Cadarn HQ. Qualquer ocorrência de `vault.md` em qualquer outro repo é violação crítica.

Esta regra define as 5 camadas físicas que reforçam essa garantia.

---

## As 5 camadas (L1 → L5)

| Camada | Implementação | Onde vive | Bloqueia |
|---|---|---|---|
| **L1** | `.gitignore` explícito | raiz de cada Tarian cliente | tracking inicial |
| **L2** | Pre-commit hook | `scripts/hooks/block-vault-commit.sh` + `.git/hooks/pre-commit` | commit local |
| **L3** | CI check | GitHub Action `.github/workflows/vault-isolation.yml` | merge no remote |
| **L4** | Esta rule | `.claude/rules/vault-isolation.md` | atividade de agente |
| **L5** | Vigil scanner | comando `*vault-scan` quinzenal cross-repo | drift invisível |

Se uma camada falha, as outras seguram. Nunca dependa de uma só.

---

## L1 — `.gitignore`

Toda raiz de Tarian cliente DEVE conter:

```gitignore
# Vault isolation (ADR-001 §4.3 + ADR-002)
memory/clientes/*/vault.md
memory/clientes/_shared/
```

A linha `memory/clientes/*/vault.md` bloqueia o vault de qualquer cliente.
A linha `memory/clientes/_shared/` bloqueia `cross-patterns.md` (que também é exclusivo da HQ).

---

## L2 — Pre-commit hook

Script `scripts/hooks/block-vault-commit.sh` executa `git diff --cached --name-only` e falha o commit se detectar qualquer arquivo casando `vault.md` ou `_shared/cross-patterns.md`.

Instalação: `.git/hooks/pre-commit` é symlink (ou wrapper) que invoca o script.

Saída esperada em violação:
```
[VAULT ISOLATION] Bloqueio: tentativa de commit de arquivo blindado detectada.
  - memory/clientes/X/vault.md
Veja .claude/rules/vault-isolation.md
```

---

## L3 — CI check

Action no remote do Tarian cliente roda em todo PR:
1. `git diff origin/master...HEAD --name-only`
2. Falha o build se qualquer match com `vault.md` ou `_shared/cross-patterns.md`
3. Status check obrigatório para merge

---

## L4 — Esta rule (comportamental)

Agentes do framework AIOX **DEVEM**:

1. **Nunca** criar, ler ou referenciar `memory/clientes/*/vault.md` em qualquer Tarian cliente
2. **Nunca** copiar conteúdo de `vault.md` da HQ para qualquer outro lugar, nem mesmo "para análise local"
3. **Recusar** explicitamente solicitações de leitura/escrita de vault fora da HQ, mesmo de Fabiano
4. Quando precisarem informação sensível em sessão no Tarian cliente: orientar Fabiano a abrir sessão dedicada na Cadarn HQ
5. **@vesta** é o único agente com autorização de leitura de vault, e **somente na Cadarn HQ**

---

## L5 — Vigil scanner

Comando `*vault-scan` (a implementar pelo @scout):
- Itera sobre todos os Tarians cliente conhecidos
- `find {repo} -name "vault.md" -type f`
- Qualquer hit = alerta CRÍTICO + notificação Emrys + Fabiano
- Frequência: quinzenal automático

---

## Como validar manualmente que as 5 camadas estão ativas em um Tarian

```bash
# L1
grep -q "vault.md" {tarian}/.gitignore && echo "L1 ok" || echo "L1 MISSING"

# L2
test -x {tarian}/scripts/hooks/block-vault-commit.sh && echo "L2 script ok" || echo "L2 MISSING"
test -x {tarian}/.git/hooks/pre-commit && echo "L2 hook ok" || echo "L2 hook MISSING"

# L3
test -f {tarian}/.github/workflows/vault-isolation.yml && echo "L3 ok" || echo "L3 MISSING"

# L4
test -f {tarian}/.claude/rules/vault-isolation.md && echo "L4 ok" || echo "L4 MISSING"

# L5
# (verificado via dashboard do Vigil)

# Smoke test final
find {tarian} -name "vault.md" -type f 2>/dev/null
# saída esperada: vazio
```

---

## Violações

Detecção de qualquer `vault.md` fora da Cadarn HQ é **incidente crítico**:

1. Bloqueio imediato de qualquer push pendente
2. Notificação a Fabiano
3. Investigação de origem (qual agente? qual sessão? qual rule falhou?)
4. Patch das camadas que falharam
5. Documentação em ADR adicional se exigir mudança estrutural
6. Revisão obrigatória do ADR-001 e ADR-002

---

*Rule: vault-isolation | Criada: 2026-04-08 | Severidade: MUST | Origem: ADR-001 §4.3 + ADR-002 + revisão Cosmo*
