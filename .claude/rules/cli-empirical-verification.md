---
name: cli-empirical-verification
description: Agentes da Forja verificam empiricamente soluções de CLI/infra antes de
             recomendar — especialmente em ambientes com peculiaridades conhecidas (WSL,
             containers, proxy). Auth-critical nunca recomendado sem verificação.
paths:
  - packages/**
  - docs/stories/**
---

# CLI Empirical Verification — Verificação Antes de Recomendar

## Regra Principal

**Antes de recomendar qualquer solução de CLI ou infra com comportamento dependente de
ambiente ou versão, o agente DEVE verificar empiricamente ou qualificar de forma explícita.**

Conhecimento de treinamento descreve o que a ferramenta deveria fazer em condições genéricas.
Não descreve o que ela faz no ambiente real do usuário.

## Gatilho

Esta rule dispara quando o agente está prestes a recomendar:

1. Flag ou subcomando específico de CLI externa (supabase, gh, vercel, docker, npm, etc.)
2. Solução de autenticação, credenciais ou troca de contexto de conta
3. Configuração de infra com comportamento dependente de SO ou versão
4. Workaround para comportamento de versão específica de ferramenta

**Não dispara** para comandos universais sem variação por ambiente: `git status`,
`npm install`, `ls`, e similares de stdlib madura.

## Duas Categorias de Risco

### Categoria A — auth-critical (risco de silent failure)

Qualquer recomendação que:
- Altera credenciais ativas
- Troca contexto de conta ou projeto
- Executa operação destrutiva irreversível (push, migration, deploy)

**Protocolo:**
1. Verificar empiricamente via Bash antes de recomendar
2. Se verificação não for possível no ambiente: **não recomendar** — devolver ao usuário:
   > "Não consigo verificar este comando no seu ambiente antes de recomendar.
   > Teste você primeiro: `{comando de diagnóstico seguro}` e me diga o resultado."

O risco de silent failure nesta categoria invalida qualquer qualificação passiva.
Uma flag que aceita argumento sem reportar erro e falha silenciosamente é mais
perigosa do que uma flag que falha com mensagem clara.

### Categoria B — CLI com variável de ambiente

Soluções de CLI não-destrutivas cujo comportamento pode variar por SO, versão ou config.

**Protocolo:**
1. Identificar: este comando pode ser executado sem efeito colateral destrutivo?
   - SIM → executar via Bash e verificar o resultado antes de recomendar
   - NÃO → qualificar com formato explícito (ver abaixo)

2. Formato de qualificação obrigatório quando não verificado:

```
⚠️ Não verificado no seu ambiente ({ambiente conhecido / versão})
Recomendo: `{comando}`
Antes de executar: `{comando de diagnóstico seguro}`
Variável de risco: {o que pode fazer isso não funcionar aqui}
```

## Ambientes com Peculiaridades Conhecidas

Sempre mapear ao avaliar uma recomendação de CLI:

| Ambiente | Peculiaridade |
|---|---|
| **WSL** | Keyring do sistema bloqueado — CLIs que dependem de libsecret falham silenciosamente |
| **Dev Containers / Codespaces** | Credenciais do host não passam para o container por padrão |
| **Docker-in-Docker** | Sockets e permissões de rede diferem do host |
| **Proxy corporativo** | Autenticação OAuth de CLIs (GitHub, Vercel, Supabase) pode falhar sem configuração explícita de proxy |
| **macOS Keychain vs Linux Keyring** | Comportamento divergente em CLIs que usam libsecret |

## Agentes Cobertos

Dex (@dev), Aria (@architect), Gage (@devops).

Aegis (@aegis) é consultado sempre que a recomendação envolve Categoria A.

## Anti-Patterns

```
❌  ERRADO — afirmar como solução sem verificar:
    "Use supabase login --profile cadarn-martech para separar contas."

❌  ERRADO — qualificar auth-critical com aviso passivo:
    "⚠️ Não testado, mas tente: supabase login --profile cadarn-martech"

✅  CORRETO — Categoria B com qualificação explícita:
    "⚠️ Não verificado no seu ambiente (WSL)
     Recomendo: `supabase login --profile cadarn-martech`
     Antes de executar: `supabase status 2>&1` — observe se há erro de keyring
     Variável de risco: WSL bloqueia keyring do sistema; a flag pode aceitar o
     argumento sem fazer nada"

✅  CORRETO — Categoria A sem verificação possível:
    "Não consigo verificar este comando no seu ambiente antes de recomendar.
     Teste você primeiro: `supabase projects list` para confirmar qual conta
     está ativa, e me diga o resultado."
```

## Origem desta rule

Incidente projeto MAPA (2026-06-15): Dex recomendou `supabase login --profile cadarn-martech`
baseado em documentação da CLI. A flag existe e aceita o argumento, mas o keyring é
explicitamente bloqueado no source code (credentials/store.go) em ambientes WSL.
O silent failure levou o usuário a acreditar que a autenticação estava isolada quando não estava.

Deliberação: Emrys + Dex + Gage + Aegis (2026-06-15).

## Severidade

**MUST** — Recomendações de CLI não verificadas em Categoria A podem resultar em operações
destrutivas executadas no contexto errado (conta, projeto, ambiente).

---

*Rule: cli-empirical-verification | Criada: 2026-06-15 | Origem: Incidente MAPA --profile WSL |
Deliberação: Emrys + Dex + Gage + Aegis | Autoridade: Fabiano | Severidade: MUST*
