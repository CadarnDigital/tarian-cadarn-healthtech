---
task: Roteiro de Venda Consultiva — 4 Blocos
responsavel: Llif
responsavel_type: agent
versao: 1.0
criado_em: 2026-06-28
tier_de_fonte: FATO (método Challenger Cap. 5 + centro de compras Cap. 4) + 🜂 para recomendações Cadarn
Entrada: |
  - persona: corretora / clínica / hospital / faturamento
  - porte: pequeno / médio / grande
  - dor_identificada: principal problema mapeado (do diagnóstico ou hipótese)
  - momento_venda: primeiro contato / pós-diagnóstico / proposta
Saida: |
  - roteiro_4_blocos: roteiro completo para a reunião
  - perguntas_abertura: perguntas Challenger calibradas por persona
  - argumentos_objecao: 3 objeções prováveis com resposta
Checklist:
  - "[ ] Identificar persona e calibrar linguagem (corretora × clínica)"
  - "[ ] Construir abertura com a Demora nomeada (não com IA)"
  - "[ ] Elaborar bloco Fiscal com métricas de mercado citadas"
  - "[ ] Construir Operacional com a causa-raiz do cliente"
  - "[ ] Bloco Estratégico nomeia o resultado sem prometer número"
  - "[ ] Preparar 3 objeções prováveis com resposta"
  - "[ ] Verificar: IA entra no passo 3, não na abertura"
---

# *roteiro-venda-consultiva — Roteiro de 4 Blocos

Produz roteiro completo para reunião de venda consultiva, seguindo o método Challenger (Cap. 5) e a jornada de 8 etapas do centro de compras (Cap. 4).

## Protocolo de Elicitação

```
1. "É corretora de saúde, clínica ou hospital de faturamento?"
2. "Qual o porte — pequeno (1-10 pessoas), médio (10-50) ou grande (50+)?"
3. "Qual a principal dor que o diagnóstico identificou (ou sua hipótese)?"
4. "É primeiro contato, pós-diagnóstico ou reunião de proposta?"
```

## Os 4 Blocos do Roteiro

### Bloco 1 — Abertura (nomeando a Demora, não a IA)

**Objetivo:** estabelecer que Llif/Cadarn Healthtech entende o mercado de dentro.

**Para corretora:**
> *"Antes de qualquer coisa, quero entender: no último mês, quantas vezes uma venda atrasou porque o cadastro não saiu a tempo? E quantas perderam porque a guia voltou na hora errada?"*

**Para clínica/hospital:**
> *"Vou te perguntar algo direto: qual o percentual de guias que voltam da [operadora X] antes de você receber o pagamento? E quanto do tempo da equipe vai para recontestar essas glosas?"*

**Princípio Challenger:** provocar antes de propor. A pergunta abre o diagnóstico, não fecha a venda.

### Bloco 2 — Fiscal (métricas de mercado + dados do cliente)

**Objetivo:** mostrar que o problema tem dimensão financeira mensurável.

**Referências de FATO para usar:**
- Glosa: 7–18% das contas, 68% de origem administrativa `[fonte: cap-03]`
- Gap de caixa: 32 dias médio `[fonte: cap-03]`
- VCMH: 15,1% a.a. (pressão sobre margens) `[fonte: cap-01]`
- Reajuste < 30 vidas: 14,24% (2024) `[fonte: cap-01]`

**Script:**
> *"No mercado, 68% das glosas são administrativas — erro de campo, código errado, prazo vencido. No seu caso, com [volume] guias por mês, isso representa em torno de R$ [estimativa] represados. Isso está na sua conta ou no esquecimento?"*

**Sinalizar:** se os dados do cliente não foram confirmados, usar referência com `[fonte: cap-03]` e perguntar para calibrar.

### Bloco 3 — Operacional (a causa-raiz, com IA no passo 3)

**Objetivo:** mostrar como resolve — com processo, não com promessa de tecnologia.

**Estrutura:**
1. Nomear o gargalo específico (do diagnóstico ou do que o cliente disse)
2. Descrever o processo que resolve (sem citar IA primeiro)
3. IA entra como mecanismo: *"Para isso, usamos frameworks operacionais que processam os dados e agentes que executam cada etapa"*

**Script:**
> *"O que acontece hoje é [causa-raiz identificada]. O que fazemos é entrar nesse ponto específico — não no processo inteiro — e [descrever o fluxo]. Usamos frameworks que processam os dados em tempo real e agentes que executam cada etapa sem precisar de pessoa para isso."*

**Sinalizar 🜂:** se a causa-raiz foi inferida (não confirmada pelo cliente), dizer: *"Estou partindo do que você descreveu — me corrija se eu errei."*

### Bloco 4 — Estratégico (resultado sem prometer número)

**Objetivo:** conectar a solução ao resultado de negócio sem fazer promessa sem lastro.

**Para corretora:**
> *"Quando o cadastro sai no prazo, a venda não escapa. Quando a comissão é conciliada sem retrabalho, a equipe tem mais tempo para o cliente. Não é transformação — é o processo funcionando."*

**Para clínica/hospital:**
> *"Quando a glosa administrativa para de entrar, o caixa respira. Não precisamos prometer resultado antes de entender os seus números — por isso o próximo passo é um piloto, não um contrato."*

**NUNCA fazer:** citar 211,7% de ROI aqui. Esse número é para `*planilha-roi`, com dados reais.

## 3 Objeções Prováveis

### Objeção 1 — "Já tentamos automatizar antes"
> *"O que costuma falhar não é a automação — é a automação que chega antes do diagnóstico. Não viemos com solução. Viemos com um raio-X. O que deu errado antes foi o ponto de partida, não a intenção."*

### Objeção 2 — "Não quero mexer no sistema que está funcionando"
> *"Não mudamos o sistema de vocês. Entramos no processo onde ele para. O que muda é o passo específico onde o [gargalo] acontece — o resto fica como está."*

### Objeção 3 — "Quantas pessoas vou precisar demitir?"
> *"Esse não é o argumento que a Cadarn Healthtech usa. O que entregamos é capacidade — mais volume com a mesma equipe. O que você faz com isso é decisão de gestão, não de contrato com a gente."*

## Output Esperado

```
ROTEIRO DE VENDA CONSULTIVA — [persona] / [porte]
Momento: [primeiro contato / pós-diagnóstico / proposta]

BLOCO 1 — ABERTURA
[pergunta(s) de abertura calibradas]

BLOCO 2 — FISCAL
[métricas + quantificação com dados do cliente]

BLOCO 3 — OPERACIONAL
[causa-raiz + como resolve + IA no passo 3]

BLOCO 4 — ESTRATÉGICO
[resultado de negócio sem prometer número]

OBJEÇÕES PROVÁVEIS
1. [objeção] → [resposta]
2. [objeção] → [resposta]
3. [objeção] → [resposta]

🜂 Hipóteses: [dados que precisam de confirmação do cliente]
```
