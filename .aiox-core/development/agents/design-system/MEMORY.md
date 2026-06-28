# MEMORY — Cosmo (@design-system)

> Memória persistente do agente Cosmo (Design System). Criado em 2026-05-02 — Story 2.2 (Projeto Câmara Wave 2).

## Contexto do Agente

- **Persona:** Cosmo
- **Squad:** Forja Cadarn
- **Papel:** Design System, tokens, componentização atômica

## Decisões e Padrões Registrados

### Claude Design — ferramenta relevante para DS (adicionado 2026-05-03)

Claude Design (Anthropic, lançado 17/04/2026) é uma ferramenta de design visual baseada em Opus 4.7 que gera HTML/CSS/JS interativo a partir de prompts. É relevante para Cosmo porque permite configurar e persistir um Design System da organização.

**Como o DS funciona no Claude Design:**
- Configurado uma vez por organização: upload de assets reais (PNG, JPEG, PDF de brand guide, código com tokens CSS)
- Claude extrai automaticamente: paleta (hex), tipografia, componentes, padrões de layout
- Após publicado, novos projetos da organização herdam o DS automaticamente
- Atualização: via "Remix" conversacional nas configurações da org — não há editor manual de tokens

**Pro/Max (Fabiano usa este plano):**
- DS persiste para o usuário dentro dos seus próprios projetos
- Não é compartilhado com outros membros de uma organização
- Para uso solo, é suficiente — criando um projeto por cliente, a identidade fica salva naquele projeto

**Limitações conhecidas (maio 2026):**
- Não existe editor textual de tokens CSS — a configuração é por extração de assets
- Fontes proprietárias sem CDN público (Google Fonts, Fontshare) não renderizam no canvas — usa fallback silencioso
- Textura de papel como overlay não tem mecanismo nativo — implementar via CSS pseudo-elemento no handoff
- Monorepos grandes causam lag — linkar só subdiretório específico

**Princípio operacional:**
Quando surgir dúvida sobre se o Claude Design suporta algum recurso de DS, **pesquisar primeiro via Atlas + YouTube + help center oficial** (support.claude.com) antes de testar. Pesquisa é mais barata que consumir usage do Claude Design. A ferramenta está em research preview e evolui rapidamente — limitações de hoje podem não existir amanhã.

## Histórico de Sessões

- **2026-05-03:** Sessão de análise de ferramentas para site Cadarn. Leitura de 3 vídeos + 5 pesquisas sobre Claude Design. Memória atualizada por Morgan (PM).
