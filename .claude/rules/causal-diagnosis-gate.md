---
name: causal-diagnosis-gate
description: Antes de recomendar ação difícil de desfazer, o agente confirma a causa
             real — nunca afirma diagnóstico baseado em sintoma como se fosse certeza.
paths:
  - packages/**
  - docs/stories/**
---

# Causal Diagnosis Gate

> **"Entendi o sintoma. Provei a causa?"**

## Regra

Antes de recomendar qualquer ação difícil de desfazer, confirme a causa real — não
suponha. O fato de uma explicação fazer sentido não significa que ela é verdadeira.
Hipótese não é diagnóstico.

## Quando Esta Rule Entra em Ação

Dispara quando a ação recomendada envolve:

- Apagar, mover ou migrar algo permanentemente (deleção, DROP, transferência de recurso)
- Mudar quem controla um recurso (criação de organização, troca de ownership, troca de provedor)
- Qualquer coisa cara de reverter — ações que, se o diagnóstico estiver errado,
  exigem horas ou dias para desfazer

**E** o diagnóstico veio de comportamento observado, não de verificação direta.

> **Diferença:** Evidência direta = você rodou um comando e o output confirmou a causa.
> Comportamento observado = você viu um erro ou output e inferiu a causa.

## Protocolo

Antes de apresentar a recomendação, o agente verifica:

1. A causa foi confirmada — não apenas inferida de um sintoma?
2. A explicação mais simples foi testada antes da mais cara?
3. A ação proposta é proporcional à causa confirmada?

Se qualquer resposta for não: verificar primeiro, ou declarar incerteza antes de recomendar.

**Formato de declaração de incerteza:**

```
Hipótese: {o que o sintoma sugere}
Não verificado: {por que não consigo confirmar agora}
Antes de executar: {o que o usuário deve testar primeiro}
Só se confirmado: {a ação recomendada}
```

## Agentes Cobertos

Dex (@dev), Aria (@architect), Gage (@devops) — e qualquer agente que, no curso de
uma tarefa, diagnostique a causa de um erro e proponha ação para resolvê-la.

## Relação com `cli-empirical-verification`

As duas rules cobrem o mesmo padrão raiz por vetores diferentes:

- `cli-empirical-verification` — comportamento de CLI dependente de ambiente
- `causal-diagnosis-gate` — diagnóstico causal que leva a ação irreversível

Um agente pode violar as duas ao mesmo tempo. Elas são complementares.

## Origem

Incidente projeto MAPA (2026-06-15): Dex diagnosticou "Supabase não suporta contas
pessoais GitHub" com base em `gh api user` retornar tipo "User". Propôs criar
organização GitHub e transferir o repositório. Atlas verificou em 80 segundos:
diagnóstico errado. Supabase suporta contas pessoais. Problema real: sessão OAuth
desatualizada. Reconectar o GitHub resolveu.

Causa raiz nomeada por Dex: "o agente trata plausibilidade como evidência."
Deliberação: Emrys + Dex + Aria + Quinn + Morgan + Aegis + Cosmo + Pax (2026-06-15).

## Severidade

**MUST** — Diagnóstico errado afirmado com confiança transfere certeza falsa ao usuário,
que executa ação irreversível sob premissa incorreta.

---

*Rule: causal-diagnosis-gate | Criada: 2026-06-15 | Origem: Incidente MAPA OAuth GitHub |
Autoridade: Fabiano | Severidade: MUST*
