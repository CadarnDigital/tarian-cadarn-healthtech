# MEMORY — Emrys (@aiox-master)

> Memória persistente do agente Emrys (AIOX Master / Regência). Criado em 2026-05-02 — Story 2.2 (Projeto Câmara Wave 2).

## Contexto do Agente

- **Persona:** Emrys
- **Papel:** Regência do AIOX, orquestrador master, autoridade transversal
- **Hierarquia:** Autoridade superior ao Squad Forja; subordinado apenas a Fabiano

## Decisões e Padrões Registrados

### Ecossistema Claude — Opções de Execução (registrado 2026-06-22)

Quando surgir qualquer problema de automação, acesso a plataformas, rotinas autônomas ou execução sem humano presente — verificar primeiro qual produto do ecossistema Claude resolve antes de concluir que "não é possível":

| Produto | Canal | Quando usar |
|---|---|---|
| **Claude Chat** | Web + Desktop + Mobile | Conversas pontuais, sem automação |
| **Claude Code** | Terminal + Desktop + IDEs | Desenvolvimento, git, arquivos locais, CLI |
| **Claude Cowork** | Desktop nativo (Pro+) | Rotinas autônomas, acesso a arquivos, tarefas recorrentes, não-técnicos |
| **Claude for Chrome** | Extensão Chrome (beta, Pro+) | Acesso a qualquer app/plataforma onde o usuário já está logado, sem API |

**Cowork** (lançado jan/2026, Windows fev/2026): agente autônomo que executa tarefas sem o usuário presente — acessa arquivos locais, navega com Computer Use, agenda rotinas, integra com Chrome. Não é o Cowork antigo descontinuado — é produto oficial dentro do Claude Desktop.

**Claude for Chrome**: extensão oficial Anthropic (dez/2025, beta). Lê e interage com qualquer página aberta. Integra com Claude Code via `/chrome`. Limitação atual: plano Pro usa apenas Haiku 4.5.

**Regra de bolso:** antes de dizer "não tem como fazer X automaticamente", perguntar se o Cowork ou a extensão Chrome resolve.

## Histórico de Sessões

<!-- Registrar sessões relevantes do projeto aqui após onboarding -->
