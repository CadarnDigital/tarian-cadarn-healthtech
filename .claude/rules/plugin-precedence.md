# Plugin Precedence — Governança de Uso de Plugins no Processo Cadarn

## Regra Principal

**Plugin entra como insumo na ENTRADA do processo Cadarn, nunca sai como entrega na SAÍDA.**

Onde existe squad especializada com método próprio (MKT, Comercial, Jurídica, Ops), o método Cadarn é o único pipeline de produção. Um plugin de domínio é fonte de framework e protocolo — não substituto de squad, não pipeline paralelo, não shortcut de gate.

## O que esta regra governa

Os plugins instalados no framework Claude Code carregam skills de domínio genérico:

| Plugin | Skills | Domínio |
|---|---|---|
| `knowledge-work/marketing` | brand-review, content-creation, seo | Marketing genérico |
| `knowledge-work/sales` | account-research, call-prep, call-summary, pipeline-review | Vendas genérica |
| `knowledge-work/legal` | review-contract | Direito anglo-saxão |
| `knowledge-work/data` | sql-queries, data-analysis, statistical-analysis | Dados e analytics |
| `commit-commands` | commit, commit-push-pr, clean_gone | Operações de git |

## O que é permitido

### Uso ESTÁVEL → internalizar como fragment
Conteúdo atemporal, sem DNA de marca, sem jurisdição específica: fórmulas de headline, checklists, espectrums de voz, padrões analíticos SQL, esqueleto de método (tiers de severidade, redline disciplinado).

- Extrair → criar fragment atômico em git Cadarn (L4)
- Preservar atribuição ao plugin original (Apache 2.0)
- Fragment indexado na Biblioteca Cadarn com mecanismo `[componente:]`

### Uso VOLÁTIL → invocar sob demanda, nunca copiar
Conteúdo que muda com versão, dialeto, jurisdição: sintaxe SQL específica de warehouse, cláusulas jurídicas de direito estrangeiro.

- Invocar a skill do plugin quando necessário
- NUNCA copiar como arquivo estático no git
- NUNCA referenciar `~/.claude/plugins/cache/{plugin}/{versão}/` de dentro de rule/agente

## O que é proibido

### Proibição 1 — Pipeline paralelo
Usar skill de plugin como substituto de uma sessão de squad especializada.

**Errado:**
> Atlas invoca `/account-research` para pesquisar empresa de cliente e entrega direto a Fabiano como output finalizado.

**Correto:**
> Atlas usa o framework de `account-research` como estrutura de pesquisa, executa via WebSearch, e entrega resultado pela pipeline normal com gate transversal.

### Proibição 2 — Saída client-facing sem gate Cadarn
Qualquer output que vai ao cliente passa pelos gates transversais (Grafia, Dick, Coel). Nenhuma skill de plugin bypassa esse gate.

### Proibição 3 — Substância jurídica estrangeira crua
Skills de `legal` contêm direito anglo-saxão (GDPR, work-for-hire, common law). Copiar ou usar cláusulas como se fossem válidas no Brasil é violação de No Invention (Art. IV) — o direito aplicável é LGPD/CDC/CLT, reescrito pela Squad Jurídica brasileira.

### Proibição 4 — Conteúdo de marketing sem DNA de cliente
Skills de `marketing` são genéricas, sem persona, sem Pilares Editoriais, sem Trava de Feed. Usar output de `/brand-review` ou `/content-creation` diretamente como copy de cliente é violação de identidade de marca.

### Proibição 5 — Ativação de MCP embutida sem Gage
Os plugins incluem `.mcp.json` com conectores (Apollo, Close, Ahrefs, Klaviyo, DocuSign, Hex, etc.). Ativação de qualquer MCP embutido é decisão **exclusiva de @devops (Gage)**. Nenhum outro agente ativa MCP por reflexo ou conveniência.

## Hierarquia de precedência

```
1. Método Cadarn e DNA do cliente   (SEMPRE prevalece)
2. Gates transversais (Grafia/Dick/Coel)
3. Especialidade da squad dona
4. Framework extraído de plugin (insumo na entrada)
5. Skill de plugin invocada sob demanda (volátil)
```

## Relação com o Roadmap de Canibalização

Esta rule governa a execução do roadmap aprovado em 2026-06-22:

| Bloco | Ação | Status |
|---|---|---|
| 0 | Esta rule criada | CONCLUÍDO |
| 1 | `data` absorvido integral → Atlas/Métrica/Dara | Pendente |
| 2 | Componentes Tier 1 como fragments atômicos | Pendente |
| 3 | `sales` método absorvido → Squad Comercial | Pendente |
| 4 | `legal` esqueleto → Squad Jurídica reescreve | Pendente |
| 5 | `marketing` neutralizado | Pendente |

Documento de decisão completo: `docs/decisions/canibalizacao-plugins-knowledge-work.md`

## Severidade

**MUST** — Violação desta regra transforma um insumo de inteligência em vetor de diluição do DNA Cadarn. A diferença entre "plugin nos torna mais inteligentes" e "plugin nos substitui" é exatamente o que esta rule protege.

---

*Rule: plugin-precedence | Criada: 2026-06-22 | Origem: Mesa Aria+Morgan+Cosmo (decisão aprovada por Fabiano) | Autoridade: Fabiano | Severidade: MUST*
