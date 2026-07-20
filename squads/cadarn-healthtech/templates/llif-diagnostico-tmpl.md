---
template: Diagnóstico Cadarn Healtech
versao: 1.0
criado_em: 2026-06-28
uso: Output de *diagnostico-corretora | *diagnostico-clinica
tier_de_fonte: FATO (Caps 1-5 para dados de mercado) + dado real do cliente
---

# DIAGNÓSTICO CADARN HEALTECH
**Data:** ___________  
**Analista:** Llif / Cadarn Healtech  
**Tipo de operação:** [ ] Corretora  [ ] Clínica / Hospital  [ ] Faturamento hospitalar

---

## BLOCO 1 — CONTEXTO DA OPERAÇÃO

| Campo | Dado coletado |
|---|---|
| Empresa / nome do cliente | |
| Porte estimado | [ ] Pequeno  [ ] Médio  [ ] Grande |
| Operadoras principais com que trabalha | |
| Volume mensal (guias ou cadastros) | |
| Tamanho da equipe operacional | |
| Ponto de contato | |

---

## BLOCO 2 — ONDE A DEMORA APARECE

> Mapeamento do gargalo principal. Dado coletado em conversa com o cliente.

**Descrição do gargalo (com as palavras do cliente):**

```
[transcrição ou paráfrase do cliente]
```

**Tipificação da Demora:**

| Tipo | Presente? | Estimativa de impacto |
|---|---|---|
| Cadastro travado (guia retida antes de emissão) | [ ] Sim  [ ] Não | |
| Glosa administrativa (campo, código, prazo) `[fonte: cap-03]` | [ ] Sim  [ ] Não | |
| Glosa clínica (procedimento, CID, elegibilidade) `[fonte: cap-03]` | [ ] Sim  [ ] Não | |
| Retrabalho de equipe (mesmo processo feito 2x+) | [ ] Sim  [ ] Não | |
| Atraso no ciclo de caixa (gap médio ≥ 30 dias) `[fonte: cap-03]` | [ ] Sim  [ ] Não | |

**Ponto de entrada identificado:**  
`[ ] Cadastro  [ ] Glosa administrativa  [ ] Contestação  [ ] Conciliação  [ ] Outro: ___`

---

## BLOCO 3 — CUSTO ESTIMADO DA DEMORA

> Calculado com os dados do cliente. Estimativas sinalizadas como [INFERÊNCIA — não verificada].

| Métrica | Valor (dado do cliente) | Valor (estimativa) |
|---|---|---|
| Horas/semana em retrabalho | | [INFERÊNCIA — não verificada] |
| Custo mensal de equipe no gargalo (R$) | | [INFERÊNCIA — não verificada] |
| Percentual de glosa atual | | [INFERÊNCIA — não verificada] |
| Valor médio represado mensalmente (R$) | | [INFERÊNCIA — não verificada] |
| Gap de caixa médio (dias) | | `[fonte: cap-03]` referência: 32 dias |

**Custo total estimado da Demora (mensal):**  
`R$ _________ — [ ] dado real  [ ] estimativa [INFERÊNCIA — não verificada]`

---

## BLOCO 4 — O QUE É RESOLVÍVEL (ESCOPO POSSÍVEL)

> Apenas o que a Cadarn Healtech pode atacar no ponto de entrada identificado.

**Ponto de entrada confirmado para piloto:**

```
[descrever o gargalo específico que seria abordado no piloto]
```

**O que não está no escopo:**
- [ ] Integração com sistema legado do cliente
- [ ] Assessoria jurídica / contestação clínica
- [ ] Atendimento ao paciente
- [ ] Outro: ___________

**Hipótese de impacto no ponto de entrada** `[HIPÓTESE CADARN — a validar]`:

```
[descrever o que poderia mudar — sinalizado como hipótese]
```

---

## BLOCO 5 — PRÓXIMOS PASSOS

| Passo | Responsável | Prazo sugerido |
|---|---|---|
| Compartilhar amostra de dados (XML / planilha de glosa / relatório de cadastro) | Cliente | |
| Proposta de piloto (escopo + prazo + investimento) | Cadarn Healtech | |
| Reunião de alinhamento de piloto | Ambos | |

**Proposta de formato de piloto:**  
`[ ] Wizard of Oz (2 semanas)  [ ] Design Partner (6 semanas)  [ ] A definir`

---

## GATE NO INVENTION (verificar antes de entregar)

- [ ] Todos os dados de mercado citam `[fonte: cap-0X]`?
- [ ] Estimativas não fornecidas pelo cliente estão como `[INFERÊNCIA — não verificada]`?
- [ ] Hipóteses de impacto estão marcadas como `[HIPÓTESE CADARN — a validar]`?
- [ ] Nenhuma promessa de resultado antes de validação no piloto?

---

*Template v1.0 — Llif / Cadarn Healtech | Preencher a partir de *diagnostico-corretora ou *diagnostico-clinica*
