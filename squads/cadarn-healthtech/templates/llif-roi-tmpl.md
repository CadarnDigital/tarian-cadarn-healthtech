---
template: Planilha de ROI Cadarn Healthtech
versao: 1.0
criado_em: 2026-06-28
uso: Output de *planilha-roi
tier_de_fonte: 🜂 (Cap. 6 — projeção Cadarn) + dado real do cliente (obrigatório)
alerta: ROI 211,7% entra APENAS como referência marcada. Número entregue = calculado com dados reais.
---

# PLANILHA DE ROI — CADARN HEALTHTECH
**Data:** ___________  
**Cliente:** ___________  
**Ponto de entrada:** ___________  
**Dados fornecidos em:** ___________

---

## SEÇÃO 1 — SITUAÇÃO ATUAL (BASELINE DO CLIENTE)

> Preencher com dados reais coletados em *diagnostico. Estimativas sinalizadas explicitamente.

| Métrica | Valor | Fonte |
|---|---|---|
| Volume mensal de operações (guias / cadastros) | | [ ] Cliente  [ ] Estimativa |
| Custo mensal da operação (equipe + overhead) | R$ | [ ] Cliente  [ ] Estimativa |
| Taxa de problema atual (glosa / retrabalho) | % | [ ] Cliente  [ ] Estimativa |
| Valor médio por operação | R$ | [ ] Cliente  [ ] Estimativa |
| Operações com problema / mês | | calculado: volume × taxa |
| Custo do problema / mês | R$ | calculado |
| Gap de caixa médio | dias | [ ] Cliente  [ ] Estimativa |

**Estimativas não fornecidas pelo cliente:**  
```
[listar aqui o que é [INFERÊNCIA — não verificada] e a base usada]
```

---

## SEÇÃO 2 — SITUAÇÃO COM CADARN HEALTHTECH `[HIPÓTESE CADARN — a validar]`

> Projeções baseadas no ponto de entrada identificado. Precisam ser validadas no piloto.

| Hipótese | Premissa | Valor estimado |
|---|---|---|
| Redução de retrabalho | % do problema atual eliminado | ____% `[HIPÓTESE]` |
| Redução de glosa administrativa | % das glosas admin eliminadas | ____% `[HIPÓTESE]` |
| Redução no ciclo de caixa | dias economizados | ____ dias `[HIPÓTESE]` |
| Capacidade com a mesma equipe | % a mais processável | ____% `[HIPÓTESE]` |

**Base das hipóteses:**  
```
[descrever de onde vieram as premissas — não inventar sem sinalização]
```

---

## SEÇÃO 3 — CÁLCULO DE ROI (3 CENÁRIOS)

> ROI calculado com os dados reais do cliente. Sinalizar toda premissa não confirmada.

### Parâmetros de entrada

| Parâmetro | Valor |
|---|---|
| Economia mensal estimada (base) `[HIPÓTESE]` | R$ |
| Investimento mensal Cadarn Healthtech | R$ (a definir na proposta) |

### Tabela de Cenários

| Cenário | Premissa | Economia / mês | Investimento / mês | ROI mensal | ROI anual | Payback |
|---|---|---|---|---|---|---|
| **Conservador** (−30% sobre base) | Resultado abaixo do esperado | R$ | R$ | % | % | meses |
| **Base** (premissas confirmadas) | Resultado conforme modelo | R$ | R$ | % | % | meses |
| **Otimista** (+20% sobre base) | Resultado acima do esperado | R$ | R$ | % | % | meses |

**Fórmula:**  
`ROI = (Economia − Investimento) / Investimento × 100`  
`Payback = Investimento acumulado / Economia mensal`

---

## SEÇÃO 4 — REFERÊNCIA INTERNA `[HIPÓTESE CADARN — a validar]`

> Esta seção é para contexto interno. NÃO apresentar ao cliente como benchmark ou resultado esperado.

```
ROI Cadarn Healthtech — Cap. 6 (projeção interna): 211,7%

CONTEXTO OBRIGATÓRIO:
Este número é uma projeção modelada internamente pela Cadarn Healthtech,
baseada em cenário hipotético do Cap. 6 do Corpus IA.

NÃO É:
- Benchmark de mercado
- Resultado esperado para o cliente
- Promessa de retorno

É:
- Referência interna de potencial do modelo operacional
- Teto hipotético para orientar a modelagem de cenários

O número que vai para o cliente é o ROI calculado na Seção 3,
com os dados reais fornecidos por ele.
```

---

## SEÇÃO 5 — PREMISSAS E LIMITAÇÕES

```
PREMISSAS (o que precisa ser verdade para os cálculos se sustentarem):
1. [premissa 1]
2. [premissa 2]
3. [premissa 3]

DADOS DO CLIENTE (confirmados):
- [dado 1]: R$ / % / unidade
- [dado 2]: R$ / % / unidade

ESTIMATIVAS (não confirmadas):
- [estimativa 1]: [INFERÊNCIA — não verificada] — base: [explicar]
- [estimativa 2]: [INFERÊNCIA — não verificada] — base: [explicar]

LIMITAÇÕES:
- Todo este cálculo é pré-piloto. Os números reais aparecem DURANTE a operação.
- Investimento mensal ainda a ser definido na proposta comercial.
- ROI real pode variar conforme a complexidade da operação do cliente.
```

---

## GATE NO INVENTION (verificar antes de entregar)

- [ ] Dados do cliente estão separados de estimativas?
- [ ] Estimativas estão marcadas como `[INFERÊNCIA — não verificada]`?
- [ ] ROI 211,7% aparece APENAS na Seção 4 como referência interna marcada `[HIPÓTESE]`?
- [ ] ROI entregue ao cliente é o da Seção 3 (calculado com dados reais)?
- [ ] Nenhuma promessa de resultado sem condicional explícita?
- [ ] Investimento mensal: indicado como "a definir" se não foi proposto?

---

*Template v1.0 — Llif / Cadarn Healthtech | Preencher a partir de *planilha-roi | ROI 211,7% = referência interna, nunca benchmark*
