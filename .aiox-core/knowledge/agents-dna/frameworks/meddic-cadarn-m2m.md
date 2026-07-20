# M2M — MEDDIC Adaptado para PMEs de Serviços Premium (Brasil)
# Fonte: Pesquisa Perplexity — GestorFunil Prompt B | MEDDIC (Napoli & Dunkel) + JTBD
# ETL: Echo v2.0 | 2026-03-25

---

## FRAMEWORK-PRINCIPAL: MEDDIC Adaptado para ICP Cadarn

### Premissa
- MEDDIC original: criado por Jack Napoli e Dick Dunkel na PTC (anos 1990), triplicou vendas de US$300M para US$1B.
- Adaptação BR: ciclos mais curtos, Economic Buyer = dono, conversa começa no WhatsApp.
- ICP: Imobiliárias (2-15 corretores), Advocacia (2-20 advogados), Estética Premium (médico proprietário).
- Ticket: R$5.000–R$30.000/mês | Ciclo: 7–45 dias por segmento.

---

## VARIÁVEL-M: Métricas (Metrics)

**Definição:** O cliente consegue dizer, em números, o quanto o problema custa — ou o quanto quer crescer.

**Pergunta-chave:**
> "Me conta: hoje você tem uma noção de quantos leads chegam por mês, e quantos viram clientes? Você sabe quanto cada cliente novo vale pra você no ano?"

**Sinais:**
- ✅ Qualificado: "Fecho em média 3 imóveis/mês mas quero chegar a 8. Cada imóvel me dá R$6k de comissão."
- ❌ Não qualificado: "Não sei bem, a gente vai fechando conforme aparece."

**Por segmento:**
- Imobiliária: taxa de conversão visitas→contrato, ticket médio de comissão, meta de imóveis/mês
- Advocacia: custo de aquisição por cliente, valor médio de causa/contrato, % indicação vs. digital
- Estética: ticket médio por paciente, procedimentos/mês, taxa de retorno

---

## VARIÁVEL-E: Comprador Econômico (Economic Buyer)

**Definição:** Quem assina o contrato e libera o pagamento — em PMEs brasileiras, quase sempre o dono.

**Pergunta-chave:**
> "Quando você decide contratar um serviço assim, você mesmo resolve ou tem mais alguém que precisa dar um ok — sócio, financeiro?"

**Sinais:**
- ✅ Qualificado: "Sou sócio majoritário, decido sozinho" ou "Preciso alinhar com meu sócio, mas ele topa o que eu trouxer."
- ❌ Não qualificado: "Quem decide é meu sócio que tá fora do país" / "Preciso aprovar no conselho" (sem prazo).

**Por segmento:**
- Imobiliária: dono/diretor comercial — normalmente a mesma pessoa
- Advocacia: sócio-administrador; em bancas com 2 sócios, ambos precisam alinhar
- Estética: médico proprietário — quase sempre único decisor, pode ter gestor financeiro

---

## VARIÁVEL-D1: Critérios de Decisão (Decision Criteria)

**Definição:** O que o cliente vai usar para comparar você com a concorrência ou com "não fazer nada".

**Pergunta-chave:**
> "Se você fosse contratar uma consultoria de marketing agora, o que seria inegociável pra você? O que faria você falar 'não, esse aqui não é o certo'?"

**Sinais:**
- ✅ Qualificado: "Preciso de alguém que entenda do mercado imobiliário, não quero agência genérica. E quero ver cases."
- ❌ Não qualificado: "Tô só pesquisando o mercado, ainda não sei o que quero."

**Por segmento:**
- Imobiliária: experiência em captação de proprietários, rapidez nos resultados
- Advocacia: discrição + posicionamento de autoridade (não pode parecer "comercial demais")
- Estética: estética visual premium das peças, Google Ads para procedimentos high-ticket, resultados em <60 dias

---

## VARIÁVEL-D2: Processo de Decisão (Decision Process)

**Definição:** Quais passos reais de "tenho interesse" até "assinar o contrato".

**Pergunta-chave:**
> "Imaginando que a proposta faça sentido pra você — como seria o processo daí até a gente fechar? Tem alguma etapa que costuma travar?"

**Sinais:**
- ✅ Qualificado: "Eu apresento pro meu sócio semana que vem, se aprovar a gente fecha em seguida."
- ❌ Não qualificado: "A gente tem que ver com o jurídico, financeiro… pode demorar uns 3 meses." (sem urgência)

**Por segmento:**
- Imobiliária: rápido — dono decide em 3–7 dias; risco é o sócio silencioso
- Advocacia: mais lento — reunião entre sócios + garantia de compliance OAB
- Estética: decisão rápida no impulso, pode travar na etapa financeira; ajuda ter parcelamento

---

## VARIÁVEL-I: Identificar a Dor (Identify Pain)

**Definição:** O problema concreto que está custando dinheiro ou oportunidade AGORA — e que o cliente reconhece como urgente.

**Pergunta-chave:**
> "O que tá te incomodando mais hoje no lado de captação de clientes? Tem algo que, se continuasse assim por mais 6 meses, seria realmente problemático?"

**Sinais:**
- ✅ Qualificado: "Minha agenda tá cheia de indicação, mas se eu depender só disso mês que vem posso ficar no zero."
- ❌ Não qualificado: "Tá indo bem, mas sempre é bom melhorar." (sem dor real, sem urgência)

**Por segmento:**
- Imobiliária: dependência de portais (ZAP/OLX) com leads frios e caros; perda de proprietários para concorrência digital
- Advocacia: agenda vazia, dependência de indicações secas, invisibilidade no Google para o nicho
- Estética: sazonalidade que derruba faturamento; buracos na agenda mesmo com equipe contratada

---

## VARIÁVEL-C: Campeão (Champion)

**Definição:** A pessoa que vai "vender" sua solução para os outros decisores quando você não estiver na sala.

**Pergunta-chave:**
> "Tem alguém na sua equipe que já falou 'precisamos resolver isso de marketing' — uma pessoa que tá mais por dentro dessa necessidade e que me ajudaria a apresentar a proposta internamente?"

**Sinais:**
- ✅ Qualificado: coordenador comercial da imobiliária que já pesquisou soluções e quer apresentar ao dono
- ❌ Não qualificado: somente o dono, desengajado, delegou pesquisa para assistente sem influência

**Por segmento:**
- Imobiliária: gerente comercial ou corretor sênior que sente a dor de leads ruins
- Advocacia: advogado associado responsável pelo marketing da banca ou sócio mais jovem/digital
- Estética: gerente da clínica ou recepcionista-chefe que gerencia agenda e vê ociosidade

---

## SCORING-GESTORFUNIL

### Pontuação por Variável

| Variável | 0 — Desconhecido | 1 — Parcial | 2 — Confirmado |
|----------|-------------------|-------------|----------------|
| Métricas | Não sabe nenhum número | Sabe meta mas não KPIs | Números claros + meta definida |
| Economic Buyer | Não identificado | Identificado sem acesso | Na conversa, é o decisor final |
| Critérios | Não falou nada | 1 critério vago | 2+ critérios claros e específicos |
| Processo | Não sabe próximos passos | Sabe passos sem prazo | Passos mapeados + prazo real |
| Dor | Não expressou dor | Dor vaga ("poderia melhorar") | Dor específica, quantificada, urgente |
| Campeão | Ninguém identificado | Interesse sem influência interna | Pessoa comprometida com acesso ao EB |

### Thresholds de Ação

| Score Total | Ação |
|-------------|------|
| 10–12 | ✅ Avançar para proposta formal imediatamente |
| 7–9 | 🔄 Requalificar em até 7 dias (falta info, não qualificação negativa) |
| 4–6 | 🌱 Nutrir com conteúdo por 30 dias + nova call |
| 0–3 | ❌ Descartar ou arquivar (reavaliar em 90 dias se estratégico) |

### KNOCK-OUTS (variáveis eliminatórias)
- **Economic Buyer = 0** → Está conversando com quem não decide. Sem acesso ao decisor, não há deal.
- **Identify Pain = 0** → Sem dor reconhecida = sem urgência. Proposta vira "interessante, mas depois."

COMPORTAMENTO-DO-AGENTE:
- Se EB ou Pain = 0: NÃO gerar proposta — redirecionar para nutrição ou pedir introdução ao decisor real.
- Score ≥ 10 + EB ≥ 1 + Pain ≥ 1: gerar proposta e agendar apresentação.
- Score 7-9: follow-up com 1 pergunta cirúrgica para confirmar variável faltante.

---

## SEQUÊNCIA-DISCOVERY-20MIN

### Estrutura dos 20 Minutos
```
0–3 min   → Rapport + contexto do negócio (deixe o lead falar)
3–8 min   → Perguntas 1 e 2 (Dor + Métricas)
8–13 min  → Perguntas 3 e 4 (JTBD + Processo de Decisão)
13–17 min → Perguntas 5 e 6 (Critérios + Campeão)
17–20 min → Próximo passo claro
```

### 6 Perguntas em Ordem Natural

**P1 — Abre a dor (Identify Pain)**
Introdução: "Antes de falar sobre o que a gente faz, quero entender bem o momento de vocês..."
> "Como tá sendo a captação de clientes hoje? O que tá funcionando bem e o que mais te preocupa?"

**P2 — Ancora em números (Metrics)**
Introdução: "Entendi. Para eu conseguir te propor algo que faça sentido financeiro..."
> "Você tem uma ideia de quantos clientes novos entram por mês hoje, e quanto cada um representa pro seu faturamento?"

**P3 — JTBD: Por que agora?**
Introdução: "Uma coisa que me ajuda muito a entender a urgência..."
> "O que aconteceu nos últimos 2–3 meses que fez você começar a procurar uma solução agora, e não daqui 6 meses?"

**P4 — Processo + JTBD: O que já tentou (Decision Process)**
Introdução: "Antes de você, muitos dos nossos clientes já tentaram outras coisas..."
> "O que você já tentou fazer pra resolver isso antes — agência, freelancer, ads por conta? E como foi? Como você imagina que seria o processo de decisão pra contratar algo novo?"

**P5 — Critérios + JTBD: Visão de futuro (Decision Criteria)**
Introdução: "Pra eu entender o que seria sucesso pra você..."
> "Se daqui 6 meses isso estivesse resolvido — como seria o seu negócio? E o que seria inegociável numa parceria pra chegar lá?"

**P6 — Campeão + Economic Buyer**
Introdução: "Uma última coisa antes de eu pensar na proposta..."
> "Além de você, tem mais alguém na empresa que sente essa dor no dia a dia — ou que precisaria estar alinhado quando a gente for pra próxima etapa?"

### Versão WhatsApp (uma pergunta por vez)

| Etapa | Mensagem |
|-------|----------|
| 1. Abertura | "Oi [nome]! Antes de qualquer coisa, quero entender o momento de vocês. Me conta: o que tá funcionando bem na captação de clientes hoje, e o que mais te preocupa?" |
| 2. Métricas | "Faz sentido. Você tem uma noção de quantos clientes novos entram por mês e quanto cada um representa pro faturamento?" |
| 3. Urgência | "E o que mudou nos últimos meses que fez você buscar uma solução agora?" |
| 4. Histórico | "Já tentou agência, freelancer ou rodar os próprios anúncios antes? Como foi essa experiência?" |
| 5. Visão | "Se em 6 meses isso estivesse resolvido, como seria seu negócio? E o que seria inegociável numa parceria?" |
| 6. Decisor | "Tem mais alguém que precisaria estar alinhado quando a gente for pra proposta — sócio, gerente?" |

REGRA DE OURO WHATSAPP: nunca enviar 2 perguntas no mesmo bloco. A segunda é ignorada 80% das vezes.

---

## INTEGRAÇÃO-JTBD

As 3 perguntas JTBD se encaixam DENTRO das perguntas 3, 4 e 5 — não são seção separada.

| Pergunta JTBD | Onde encaixar | O que revela além do MEDDIC |
|---------------|---------------|----------------------------|
| "Por que agora e não daqui 6 meses?" | P3 (após dor + métricas) | Gatilho de urgência real: perdeu cliente, sazonalidade, sócio pressionando. Eleva Pain de 1→2. |
| "O que já tentou antes?" | P4 (com Decision Process) | Frustração com soluções anteriores = diferenciação. Qualifica critério de decisão implícito. |
| "Como seria se resolvido?" | P5 (com Decision Criteria) | Cliente se vende a compra ao descrever cenário de sucesso. Reforça Métricas e ancora valor. |

**Dica:** Quando o lead descreve a visão de futuro (JTBD 3), anotar as palavras EXATAS dele — viram o headline da proposta.

COMPORTAMENTO-DO-AGENTE:
- Seguir a sequência P1→P6 como ritmo de conversa, não como checklist.
- No WhatsApp: uma pergunta por vez, aguardar resposta.
- Se lead responder com resposta curta/evasiva: reformular com mais contexto, não insistir na mesma pergunta.
- Anotar palavras-chave do lead para reutilizar na proposta (espelhamento).
