# Cowork Bridge — Arquitetura de 3 Braços

## Contexto

O Tarian opera com **3 braços complementares** que trabalham em paralelo permanentemente:

```
Claude Code ◄──── ClickUp (centro) ────► Claude Cowork
(execução)         (ponte)                (geração)
     │                                        │
   Make / N8N (automações)
```

**ClickUp é o centro nervoso.** Code e Cowork leem e escrevem no mesmo workspace.

## Os 3 Braços

### Claude Code (este ambiente)
- **Papel:** Mãos — executa, edita, builda, deploya, testa
- **Forças:** Git, MCPs (Meta Ads, GSC, Supabase), execução de código, edição de repo
- **ClickUp:** Via MCP oficial (`clickup`)
- **Quando usar:** Tudo que envolve código, repo, git, MCPs, deploy

### Claude Cowork (claude.ai Projects)
- **Papel:** Mesa de trabalho — gera texto, pesquisa, conecta com SaaS, agenda
- **Forças:** Connectors nativos (ClickUp, Notion, Slack, Calendar), texto longo, artifacts, scheduled tasks
- **ClickUp:** Via connector nativo (OAuth)
- **Quando usar:** Geração de conteúdo em batch, propostas, contratos, relatórios, pesquisa, scheduling
- **2 Projects:**
  - **Tarian Produção** — Marketing + Comercial
  - **Tarian Backoffice** — Operacional + Jurídico

### ClickUp (centro nervoso)
- **Papel:** Ponte bidirecional + gestão de projetos/processos
- **Templates base:** Bravy (JP) — Comercial, Marketing, Gestão, Projetos, Gente&Cultura, Produtos
- **Guardião:** Brenno (@gestor-processos)
- **Automações:** Make + N8N (templates Bravy)

## Regras para Agentes do Code

### O que cada agente PODE fazer com ClickUp
- Ler tasks, status, docs, comentários
- Criar/atualizar tasks dentro do escopo da sua squad
- Escrever decisões e contexto em Docs do ClickUp (para o Cowork ler)

### O que cada agente NÃO PODE fazer
- Alterar estrutura do workspace (Spaces, Folders) — exclusivo @devops
- Deletar tasks de outras squads
- Modificar automações Make/N8N

### Quando sugerir uso do Cowork
Se a tarefa se encaixa melhor no Cowork, o agente deve informar Fabiano:
- Geração de 3+ peças de conteúdo (batch) → Cowork Produção
- Rascunho de contrato/parecer jurídico longo → Cowork Backoffice
- Relatório gerencial extenso → Cowork Backoffice
- Proposta comercial formatada → Cowork Produção
- Pesquisa de concorrentes/referências → Cowork (search nativo)
- Tarefa recorrente/agendada → Cowork (scheduled tasks)

**Formato da sugestão:**
```
💡 Esta tarefa seria mais eficiente no Cowork ({Produção|Backoffice}).
Motivo: {motivo}.
O contexto necessário está no ClickUp em: {space/list/doc}.
```

### Continuidade Code → Cowork
Se Fabiano precisar continuar uma tarefa no Cowork:
1. O agente atual escreve um **handoff padronizado** no ClickUp (Doc ou comentário na task)
2. Formato: `cowork/handoff-template.md` — campos: contexto, feito, decisões, próximo passo, arquivos
3. Fabiano abre o Cowork, que lê o mesmo ClickUp e tem contexto completo

### Continuidade Cowork → Code
Se o Cowork gerou conteúdo que precisa entrar no repo:
1. Cowork escreve handoff no ClickUp com o resultado e marca "Para Code"
2. Fabiano pede ao Code para ler a task/doc no ClickUp
3. Code puxa o conteúdo e commita/aplica no repo
4. Kairos atualiza o status da task no ClickUp

### Template de Handoff
Referência completa com formato e exemplos: `cowork/handoff-template.md`

## Mapeamento Squad ↔ ClickUp ↔ Cowork

| Squad | Space ClickUp | Project Cowork |
|-------|---------------|----------------|
| Marketing | Tarian {cliente} - Marketing | Tarian Produção |
| Comercial | Tarian {cliente} - Comercial | Tarian Produção |
| Operacional | Tarian {cliente} - Gestão | Tarian Backoffice |
| Jurídica | Tarian {cliente} - Jurídico | Tarian Backoffice |

## Quem Opera

**Clientes NÃO usam os agentes.** Quem opera é a equipe Cadarn. Os agentes são ferramentas internas da operação.

---

*Rule: cowork-bridge | Criada: 2026-03-25 | Aprovada em mesa redonda*
