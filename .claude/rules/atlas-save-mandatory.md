# Atlas Save Mandatory — Toda Pesquisa Persiste em _inbox

## Regra Principal

**Todo resultado de pesquisa gerado pelo @analyst (Atlas) DEVE ser salvo como arquivo `.md` em `_inbox/` antes de encerrar o turno.** Nenhuma pesquisa fica apenas no chat.

Esta rule se aplica a qualquer agente que realize pesquisa via WebSearch ou WebFetch durante uma sessão.

## Por que esta regra existe

Pesquisas solicitadas no chat desaparecem quando a sessão encerra ou o contexto é compactado. O custo de repetir uma pesquisa é alto (tempo + tokens). A `_inbox/` resolve isso com uma ação simples de salvar antes de entregar.

## Caminho de destino

Repositório git (relativo à raiz do projeto):
```
docs/biblioteca/pesquisas/_inbox/
```

## Nomenclatura obrigatória

```
YYYY-MM-DD_{tema-slug}.md
```

- Data no formato ISO: `2026-04-26`
- Tema em minúsculas, sem acentos, palavras separadas por hífen
- Máximo 60 caracteres no slug

**Exemplos válidos:**
- `2026-04-26_icp-imobiliario-comportamento-corretor.md`
- `2026-04-26_hormozi-oferta-unica-framework.md`
- `2026-04-26_lgpd-agencia-marketing-compliance.md`

## Estrutura obrigatória do arquivo salvo

```markdown
---
tema: {título descritivo da pesquisa}
data: {YYYY-MM-DD}
agente: Atlas
solicitado_por: Fabiano
natureza: {externo | interno}     # OBRIGATÓRIO — validação dura (bib.a.2)
fontes: {lista das principais fontes consultadas}
status: inbox
---

# {Título da Pesquisa}

{conteúdo integral da pesquisa}
```

## Protocolo de execução

### Ao concluir qualquer pesquisa:

1. **Compor o arquivo** — frontmatter + conteúdo integral
2. **Definir o slug** — extrair tema central da pesquisa, converter para kebab-case sem acentos
3. **Salvar** usando a tool `Write` no caminho `_inbox/YYYY-MM-DD_{slug}.md`
4. **Confirmar para Fabiano:**
   > `"Pesquisa salva em _inbox/2026-04-26_{slug}.md"`

### O que salvar

- **Salvar:** toda pesquisa com WebSearch + WebFetch, dossiês, benchmarks, análises de mercado, análises de concorrentes, pesquisas de ICP, dados de legislação
- **Não salvar:** respostas factuais rápidas de 1-2 linhas, buscas internas de código, navegação de arquivos do projeto

### Fronteira de dúvida

Se a pesquisa retornou mais de 3 fontes ou gerou mais de 200 palavras de conteúdo relevante → **salvar**. Abaixo disso → julgamento do agente.

## Notificação ao Fabiano

Sempre ao final da entrega, informar em uma linha:

> `📥 Salvo: _inbox/{nome-do-arquivo}.md`

Nunca omitir essa confirmação — ela é o sinal de que o ciclo de pesquisa foi concluído com persistência.

## Relação com o INDEX.md

O `docs/biblioteca/INDEX.md` é gerado em batch (não item a item). Pesquisas novas ficam na `_inbox/` até Fabiano organizar. Quando quiser regenerar o índice, pedir ao Emrys: *"regenera o INDEX da biblioteca"*.

## Relação com outras regras

- **Complementa `web-research-mandatory.md`** — aquela obriga pesquisa via WebSearch; esta garante que o resultado persiste
- **Complementa `squad-mkt-insights.md`** — insights MKT descobertos em pesquisas candidatos ao caderno devem ser sinalizados a Fabiano, mas o arquivo já estará salvo na inbox

## Severidade

**MUST** — Violação desperdiça pesquisa paga (tempo + tokens). Toda pesquisa perdida é retrabalho garantido.

---

*Rule: atlas-save-mandatory | Criada: 2026-04-26 | Proposta por: Emrys | Autoridade: Fabiano | Severidade: MUST*
