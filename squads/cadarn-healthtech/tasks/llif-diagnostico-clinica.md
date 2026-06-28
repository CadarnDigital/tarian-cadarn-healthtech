---
task: Diagnóstico de Clínica/Hospital — Raio-X de Glosas 30-60 dias
responsavel: Llif
responsavel_type: agent
versao: 1.0
criado_em: 2026-06-28
tier_de_fonte: FATO (Caps 1-2-3 + Glossário) + porta 🜂 sinalizada
Entrada: |
  - periodo: 30 ou 60 dias
  - volume_guias: número aproximado de guias no período
  - operadoras_problema: operadora(s) com maior índice de glosa
  - valor_medio_guia: valor médio por guia (opcional)
  - taxa_glosa_percebida: percentual estimado pelo cliente (opcional)
Saida: |
  - raio_x_glosas: diagnóstico estruturado em 5 blocos
  - classificacao_natureza: administrativa vs clínica (com base em dados)
  - perda_estimada: em R$ ou % sobre faturamento
  - proximo_passo: sugestão de trilha
Checklist:
  - "[ ] Coletar inputs mínimos (período, volume, operadoras)"
  - "[ ] Classificar glosas por natureza (administrativa vs clínica)"
  - "[ ] Estimar perda financeira com dados do cliente"
  - "[ ] Aplicar tier epistêmico: FATO cita [fonte: cap-0X]; hipótese sinaliza 🜂"
  - "[ ] Estruturar raio-X em 5 blocos"
  - "[ ] Verificar gate No Invention antes de entregar"
---

# *diagnostico-clinica — Raio-X de Glosas 30-60 dias

Produz um raio-X das glosas do período, classificando por natureza, identificando padrões TISS e estimando perda financeira. Usa o template `llif-diagnostico-tmpl.md`.

## Protocolo de Elicitação

Se os inputs não foram fornecidos, perguntar UMA por vez:

```
1. "Vamos olhar os últimos 30 ou 60 dias?"
2. "Quantas guias foram enviadas nesse período, aproximadamente?"
3. "Qual operadora voltou mais glosa?"
```

## Workflow

### Passo 1 — Caracterizar o Universo de Glosas

Com os dados do cliente, montar o quadro:

| Métrica | Valor fornecido | Referência de mercado (FATO) |
|---|---|---|
| Volume de guias | [dado do cliente] | — |
| Taxa de glosa estimada | [dado do cliente] | 7–18% `[fonte: cap-03]` |
| Origem principal | [dado do cliente] | 68% administrativa `[fonte: cap-03]` |
| Gap de caixa estimado | [calcular] | 32 dias médio `[fonte: cap-03]` |

**Sinalizar:** se o dado do cliente não foi fornecido, usar referência de mercado com `[fonte: cap-0X]` e indicar que é referência, não dado real.

### Passo 2 — Classificar Glosas por Natureza

Distinguir com base nos relatos do cliente:

**Glosa Administrativa (≈68% do universo) `[fonte: cap-03]`:**
- Campo obrigatório do TISS ausente ou incorreto (CBO, CID, código do prestador)
- Inconsistência de data (data da guia vs data do procedimento)
- Divergência de beneficiário (nome, número de matrícula)
- Código de procedimento TUSS incorreto ou desatualizado
- Prazo de envio vencido

**Glosa Clínica (≈32% do universo) `[fonte: cap-03]`:**
- Procedimento não coberto pelo plano
- Indicação clínica não aceita pela operadora
- Limite de utilização excedido
- Divergência entre laudo e código

**Para o cliente:** nomear a classificação com os relatos concretos que ele forneceu.

### Passo 3 — Estimar Perda Financeira

Com os dados do cliente (ou estimativa sinalizada):

```
Perda estimada no período:
  Volume de guias: [N]
  Valor médio por guia: R$ [X] (dado do cliente) OU [INFERÊNCIA — não verificada]
  Taxa de glosa: [%] (dado do cliente)
  
  Glosas no período = N × taxa = [n_glosas]
  Valor em glosa = n_glosas × valor_médio = R$ [valor]
  
  Recuperável (administrativa, 68%): R$ [valor × 0,68]
  Não recuperável (clínica, 32%): R$ [valor × 0,32]
```

### Passo 4 — Estruturar o Raio-X (5 Blocos)

**Bloco 1 — Perfil do Faturamento**
Porte, operadoras, volume, período.

**Bloco 2 — Distribuição das Glosas**
Administrativa vs clínica; quais operadoras; padrões recorrentes.

**Bloco 3 — Perda Estimada**
R$ no período, % do faturamento, % recuperável.

**Bloco 4 — Causa-Raiz das Administrativas**
Os 2-3 campos/erros que concentram o volume (Pareto das glosas).

**Bloco 5 — Próximos Passos**
Ponto de entrada do piloto: o campo/tipo de erro que mais concentra perda.

### Passo 5 — Gate No Invention

- [ ] Dados de mercado (7-18%, 68% administrativas, gap 32 dias) têm `[fonte: cap-03]`?
- [ ] Estimativas não fornecidas pelo cliente têm `[INFERÊNCIA — não verificada]`?
- [ ] ROI 211,7% NÃO aparece neste diagnóstico?
- [ ] Nenhuma promessa de recuperação total foi feita?

### Passo 6 — Entregar e Propor Próximo Passo

Finalizar com UMA sugestão:

> *"As glosas administrativas concentram a maior perda recuperável — [X]% do total. O piloto mais direto seria [campo/tipo]. Quer que eu elabore o roadmap de validação ou prefere ver o ROI estimado com esses números?"*

## Output Esperado

```
RAIO-X DE GLOSAS — [nome/porte do cliente] — [período]
Data: [data]

[Bloco 1 — Perfil do Faturamento]
[Bloco 2 — Distribuição das Glosas]
[Bloco 3 — Perda Estimada]
[Bloco 4 — Causa-Raiz das Administrativas]
[Bloco 5 — Próximos Passos]

⚠️ Premissas: [dados fornecidos pelo cliente vs referências de mercado]
🜂 Hipóteses: [itens que precisam de validação em campo]
```
