---
task: Planilha de ROI com Dados Reais do Cliente
responsavel: Llif
responsavel_type: agent
versao: 1.0
criado_em: 2026-06-28
tier_de_fonte: 🜂 (Cap. 6 — projeção Cadarn; cálculo real com dado do cliente)
Entrada: |
  - volume_mensal: número de operações por mês (guias ou cadastros)
  - custo_operacao_atual: custo mensal estimado (equipe + tempo + retrabalho)
  - valor_medio_operacao: valor médio por operação (R$)
  - taxa_glosa_atual: percentual de glosa atual (opcional)
  - tempo_ciclo_atual: dias médios do ciclo (opcional)
Saida: |
  - planilha_roi: cálculo estruturado com inputs reais
  - referencia_211: ROI 211,7% apresentado APENAS como referência marcada 🜂
  - roi_calculado: ROI real baseado nos dados do cliente
  - payback_estimado: meses para recuperar o investimento
Checklist:
  - "[ ] Coletar TODOS os inputs do cliente antes de calcular"
  - "[ ] NUNCA usar 211,7% como benchmark — é projeção Cadarn (Cap. 6)"
  - "[ ] Calcular ROI com dado real do cliente"
  - "[ ] Sinalizar toda estimativa não fornecida como [INFERÊNCIA — não verificada]"
  - "[ ] Apresentar 3 cenários (conservador / base / otimista)"
  - "[ ] Verificar gate No Invention antes de entregar"
---

# *planilha-roi — ROI com Dados Reais do Cliente

Calcula o retorno sobre investimento com os dados reais fornecidos pelo cliente. O ROI 211,7% do Cap. 6 é referência marcada — o número entregue ao cliente é sempre recalculado com os dados reais dele.

## ALERTA DE ARMADILHA (CRÍTICO)

> **ROI 211,7% é projeção Cadarn (Cap. 6), NÃO benchmark de mercado.**
> Apresentar 211,7% como resultado esperado = violação Art. IV Constitution.
> Este número entra na planilha APENAS como referência marcada `[HIPÓTESE CADARN — a validar]`.
> O número que o cliente vê é o ROI calculado com os dados REAIS dele.

## Protocolo de Elicitação

Coletar TODOS antes de calcular. UMA pergunta por vez:

```
1. "Quantas operações vocês processam por mês — guias enviadas ou cadastros feitos?"
2. "Qual o custo mensal estimado dessa operação — equipe, tempo, retrabalho?"
   (Ajudar: N pessoas × R$ X/mês = R$ Y/mês)
3. "Qual o valor médio por guia ou cadastro?"
4. "Qual o percentual de glosa atual (ou retrabalho)? Pode ser estimativa."
```

Se o cliente não souber algum dado: registrar como `[INFERÊNCIA — não verificada]` e usar referência de mercado sinalizada.

## Workflow de Cálculo

### Estrutura da Planilha

```
SITUAÇÃO ATUAL (baseline do cliente)
  Volume mensal: [N] operações
  Custo mensal: R$ [C] (dado do cliente OU [INFERÊNCIA])
  Taxa de problema (glosa/retrabalho): [G]%
  Operações com problema: [N × G]
  Custo do problema: R$ [N × G × custo_por_operacao]

SITUAÇÃO COM CADARN HEALTECH [HIPÓTESE CADARN — a validar]
  Redução de retrabalho estimada: [X]% (hipótese — validar no piloto)
  Tempo de ciclo reduzido: [Y] dias (hipótese — validar no piloto)
  Volume processável com mesma equipe: [Z]% a mais (hipótese)

CÁLCULO DE ROI
  Economia mensal estimada: R$ [valor] [HIPÓTESE CADARN — a validar]
  Investimento mensal Cadarn Healtech: R$ [proposta — a definir]
  ROI mensal = (economia − investimento) / investimento × 100 = [X]%
  ROI anualizado = [Y]%
  Payback = [Z] meses

REFERÊNCIA [HIPÓTESE CADARN — a validar]
  ROI Cadarn Cap. 6 (projeção interna): 211,7%
  Contexto: projeção baseada em cenário modelado, não em cliente real.
  Não usar como promessa. Usar como referência de potencial.
```

### 3 Cenários

| Cenário | Premissa | ROI estimado | Payback |
|---|---|---|---|
| Conservador (−30% sobre base) | Resultado abaixo do esperado | [calc] | [meses] |
| Base (premissas confirmadas) | Resultado conforme modelo | [calc] | [meses] |
| Otimista (+20% sobre base) | Resultado acima do esperado | [calc] | [meses] |

### Gate No Invention

- [ ] Dados do cliente: separados de estimativas?
- [ ] Estimativas: sinalizadas com `[INFERÊNCIA — não verificada]`?
- [ ] ROI 211,7%: aparece apenas como referência marcada `[HIPÓTESE CADARN — a validar]`?
- [ ] ROI calculado: baseado nos dados reais do cliente, não na projeção Cadarn?
- [ ] Nenhuma promessa de resultado sem condicional explícita?

## Output Esperado

```
PLANILHA DE ROI — [nome/porte do cliente]
Data: [data] | Dados fornecidos em: [data da coleta]

SITUAÇÃO ATUAL
  [tabela com os dados do cliente]

SITUAÇÃO COM CADARN HEALTECH [HIPÓTESE CADARN — a validar]
  [tabela com as hipóteses]

CÁLCULO DE ROI
  [3 cenários]

REFERÊNCIA DO CAP. 6 [HIPÓTESE CADARN — a validar]
  ROI interno modelado: 211,7% (projeção Cadarn, não benchmark de mercado)

⚠️ PREMISSAS
  [dados fornecidos vs estimativas sinalizadas]
  
🜂 HIPÓTESES: todo este cálculo precisa de validação no piloto.
   Os números reais aparecem DURANTE a operação, não antes.
```
