---
task: Diagnóstico de Corretora — 20 Movimentações Cadastrais
responsavel: Llif
responsavel_type: agent
versao: 1.0
criado_em: 2026-06-28
tier_de_fonte: FATO (Caps 1-2 + Glossário) + porta 🜂 sinalizada para recomendações Cadarn
Entrada: |
  - persona: corretora de saúde (papel no centro de compras: influenciador/usuário)
  - volume_mensal: número aproximado de operações por mês
  - tipo_predominante: cadastro novo / inclusão / exclusão / portabilidade
  - gargalo_percebido: onde o cliente sente mais atrito
Saida: |
  - diagnostico_pdf: diagnóstico estruturado em 5 blocos
  - hipotese_demora: onde a Demora foi identificada (com tier epistêmico marcado)
  - proximo_passo: sugestão de trilha (piloto ou aprofundamento)
Checklist:
  - "[ ] Coletar inputs mínimos (persona, volume, tipo, gargalo)"
  - "[ ] Identificar onde a Demora aparece (fatos do cliente vs hipótese Cadarn)"
  - "[ ] Aplicar tier epistêmico: FATO cita [fonte: cap-0X]; hipótese sinaliza 🜂"
  - "[ ] Estruturar diagnóstico em 5 blocos (template)"
  - "[ ] Verificar gate No Invention antes de entregar"
---

# *diagnostico-corretora — Diagnóstico de 20 Movimentações Cadastrais

Produz um diagnóstico estruturado das movimentações cadastrais da corretora, identificando onde a Demora está travando o fluxo comercial. Usa o template `llif-diagnostico-tmpl.md`.

## Protocolo de Elicitação (executar antes de qualquer diagnóstico)

Se os inputs não foram fornecidos no comando, perguntar UMA por vez:

```
1. "Qual o tipo de operação que mais trava — cadastro novo, inclusão, exclusão ou portabilidade?"
2. "Quantas operações vocês processam por mês, aproximadamente?"
3. "Onde o problema aparece primeiro — no recebimento do documento, na digitação, na análise da operadora, ou na devolução?"
```

Aguardar resposta antes de prosseguir.

## Workflow

### Passo 1 — Mapear a Demora

Com os inputs coletados, identificar onde a Demora se manifesta:

**Causas comuns (Caps 1-2 + Glossário — FATO):**
- Documentação incompleta ou em formato inadequado (foto vs digitalização)
- Campo obrigatório ausente ou preenchido incorretamente para o padrão da operadora
- Prazo regulatório de análise da operadora (5-30 dias úteis conforme ANS)
- Retrabalho por devolutiva: documento reprocessado manualmente

**Classificar:**
- Causa administrativa (processo interno da corretora)? → alta probabilidade de resolução por BPO
- Causa regulatória (prazo ANS, decisão de operadora)? → fora do escopo de BPO, nomear limite

### Passo 2 — Quantificar o Custo da Demora

Estimar com os dados do cliente:

```
Custo de operação estimado:
  Pessoas na equipe de cadastro: [N]
  Custo médio mensal por pessoa: [R$ estimado do cliente ou referência 🜂]
  Percentual do tempo em retrabalho: [% estimado pelo cliente]
  
  Custo de retrabalho estimado = (N × custo) × percentual
  [Sinalizar se baseado em dado do cliente ou em hipótese 🜂]
```

**ARMADILHA:** Não usar ROI 211,7% aqui. Este comando é diagnóstico, não proposta.

### Passo 3 — Estruturar o Diagnóstico (5 Blocos)

Usar `llif-diagnostico-tmpl.md`. Preencher:

**Bloco 1 — Contexto**
Tipo de corretora, volume, operadoras principais, equipe.

**Bloco 2 — Onde a Demora Aparece**
Listar as 3 maiores fricções identificadas com tier epistêmico correto.

**Bloco 3 — Custo Estimado**
Quantificação baseada nos dados fornecidos pelo cliente (sinalizar inferências).

**Bloco 4 — O Que é Resolvível**
Separar: administrativo (escopo BPO) vs regulatório (fora do escopo).

**Bloco 5 — Próximos Passos**
Propor trilha: piloto focalizado em [tipo de operação] ou aprofundamento com [dado específico].

### Passo 4 — Gate No Invention

Antes de entregar, verificar:

- [ ] Toda afirmação de FATO tem `[fonte: cap-0X]`?
- [ ] Toda recomendação Cadarn tem `[HIPÓTESE CADARN — a validar]`?
- [ ] Nenhum número foi inventado? (ou está sinalizado com `[INFERÊNCIA — não verificada]`)
- [ ] O ROI 211,7% NÃO aparece neste diagnóstico?

### Passo 5 — Entregar e Propor Próximo Passo

Entregar o diagnóstico. Finalizar com UMA sugestão clara de próximo passo:

> *"Com esse mapeamento, o piloto mais direto seria [X]. Quer que eu elabore um roadmap de validação ou prefere primeiro ver o ROI estimado com os seus números?"*

## Output Esperado

```
DIAGNÓSTICO DE CORRETORA — [nome/porte do cliente]
Data: [data]

[Bloco 1 — Contexto]
[Bloco 2 — Onde a Demora Aparece]
[Bloco 3 — Custo Estimado]
[Bloco 4 — O Que é Resolvível]
[Bloco 5 — Próximos Passos]

⚠️ Premissas: [dados fornecidos pelo cliente vs estimativas]
🜂 Hipóteses: [itens que precisam de validação em campo]
```
