# Web Research Mandatory — Pesquisa Sempre via @analyst + Internet

## Regra Principal

O modelo Claude tem **corte de conhecimento em maio de 2025**. Informações factuais podem estar desatualizadas.

**@analyst (Atlas) é o especialista designado para TODA pesquisa.** Quando Fabiano pedir pesquisa sobre qualquer assunto, o agente ativo DEVE delegar para Atlas.

## Fluxo Obrigatório

```
Fabiano pede pesquisa
    ↓
Agente ativo delega para @analyst (Atlas)
    ↓
Atlas pesquisa usando WebSearch + WebFetch (SEMPRE)
    ↓
Atlas entrega resultado com fontes
    ↓
Se o agente ativo precisar de mais profundidade → pede nova pesquisa ao Atlas
```

## Regras do @analyst (Atlas) em Pesquisas

1. **SEMPRE usar WebSearch** como primeira ação — nunca responder só com conhecimento interno
2. **SEMPRE usar WebFetch** para acessar páginas relevantes encontradas na busca
3. **Cruzar** resultados web com conhecimento interno do modelo
4. **Listar fontes** ao final de toda pesquisa
5. **Sinalizar confiança** em cada informação:
   - **Verificado** — confirmado por fonte web recente
   - **Não verificado** — não encontrou confirmação online

## Ferramentas de Pesquisa (ordem de prioridade)

```
WebSearch (nativo, rápido) → WebFetch (página específica) → EXA (busca avançada via Docker) → Apify (scraping)
```

## Quando Esta Regra se Aplica

| Situação | Delegar ao Atlas + Web? |
|----------|----------------------|
| Pesquisa de pessoa pública / metodologia | **SIM** |
| Pesquisa de mercado / tendências | **SIM** |
| Análise de concorrentes | **SIM** |
| Dados sobre ferramentas / preços / planos | **SIM** |
| Referências a leis / normas | **SIM** |
| Criação de DNA de agente | **SIM** |
| Qualquer pedido de "pesquise", "investigue", "descubra" | **SIM** |

## Quando NÃO se Aplica

| Situação | Motivo |
|----------|--------|
| Implementação de código | Lógica é atemporal |
| Revisão de código existente | O código é a fonte |
| Facilitação de rituais internos | Processo do framework |
| Operações git / deploy | Ferramentas locais |

## Anti-Patterns

- **NUNCA** outro agente fazer pesquisa sozinho sem delegar ao Atlas
- **NUNCA** Atlas responder pesquisa sem usar WebSearch
- **NUNCA** apresentar dado factual como atual sem verificação web
- **NUNCA** criar DNA de pessoa pública baseado apenas no modelo interno

---

*Rule: web-research-mandatory | Criada: 2026-03-29 | Severity: MUST*
