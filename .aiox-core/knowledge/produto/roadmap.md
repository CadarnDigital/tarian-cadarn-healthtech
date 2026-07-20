# Roadmap — Cadarn Healtech

> Fonte: Design Brief Llif v1.0, Cap 6 do Corpus IA
> **Cap 6 = HIPÓTESE Cadarn — a validar. Não é plano consolidado.**

## Fase atual: Validação (piloto)

**Objetivo:** Validar a jogada BPO Tech com 1-2 clientes-piloto antes de escalar.

**Capacidades ativas — Llif:**

| Capacidade | Status | Comando |
|---|---|---|
| Diagnóstico de corretora | ativo | `*diagnostico-corretora` |
| Diagnóstico de clínica | ativo | `*diagnostico-clinica` |
| Planilha de ROI | ativo | `*planilha-roi` |
| Roteiro de venda consultiva | ativo | `*roteiro-venda-consultiva` |
| E-mail de convite | ativo | `*email-convite` |
| Apresentação comercial | ativo | `*apresentacao-comercial` |
| Roadmap de validação | ativo | `*roadmap-validacao` |
| Crossover (corretora↔clínica) | ativo | `*crossover` |

**Ponto de entrada PENDENTE:** martelo de Fabiano
- Opção A: Delma / corretora → `*diagnostico-corretora`
- Opção B: Alexandre / faturamento → `*diagnostico-clinica`

---

## Próximo ciclo: Operação [HIPÓTESE CADARN — a validar]

**Trigger:** piloto validado + ROI real confirmado

**O que muda:**
- 2º agente nasce por cisão (comercial/SDR) — herda caps 3-4-5 de Llif
- Llif foca em estratégia + entregáveis de alto valor
- SDR assume prospecção e qualificação

**Comando de cisão:** `*extend-squad cadarn-healthtech --add agent`

---

## Decisões de não-fazer

- **Produto SaaS antes de validar BPO** — Motivo: aprendizado de campo define o produto
- **Integração técnica complexa na venda** — Motivo: anti-pattern do corpus (exige integração = trava)
- **Liderar com IA na abordagem** — Motivo: IA entra no passo 3, nunca abre
