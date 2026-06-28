---

## Task Definition

```yaml
task: qualifyLead()
responsavel: GestorFunil (gestor-funil)
responsavel_type: Agente
squad: cadarn-comercial
templates:
  - meddic-scoring-tmpl.yaml
tarian_portable: true

description: >
  Qualifica leads recebidos do Caio via MEDDIC scoring adaptado para PMEs
  premium brasileiras. Avalia 6 variáveis (Metrics, Economic Buyer, Decision
  Criteria, Decision Process, Identify Pain, Champion), aplica knock-outs,
  calcula score total e emite decisão: Avançar / Requalificar / Nutrir /
  Descartar. Score ≥ 10 = proposta autorizada.

Entrada:
  - campo: dados_lead
    tipo: object
    origem: Caio (após triagem) ou elicitação direta
    obrigatório: true
    campos:
      - segmento (imobiliaria | advocacia | estetica)
      - nome_lead
      - empresa
      - impressao_caio (descrição livre do primeiro contato)
      - informacoes_coletadas (o que já se sabe sobre o lead)

Saída:
  - campo: ficha_meddic
    tipo: markdown
    template: meddic-scoring-tmpl.yaml
    destino: Caio (se aprovado) | Nutrição (se rejeitado)
    persistido: true
```

---

## Execution Modes

### 1. Qualificação Completa via Discovery Call/WhatsApp **[DEFAULT]**
- Conduz discovery 20min (call) ou sequência de 6 perguntas (WhatsApp)
- Preenche todas as variáveis MEDDIC
- Emite decisão + briefing ao Camaleão (se score ≥ 10)
- **Trigger:** `*qualificar {dados do lead}`

### 2. Requalificação
- Lead em nutrição volta ao pipeline com novas informações
- Atualiza score parcialmente sem refazer tudo
- **Trigger:** `*score {lead} {nova informação}`

### 3. Benchmark por Segmento
- Exibe métricas de referência do funil para calibrar expectativas
- **Trigger:** `*benchmark {segmento}`

---

## Workflow — Qualificação Completa

### Fase 1 — Intake do Lead (recebido de Caio)

```
task: |
  Receber handoff do Caio após triagem rápida.
  Confirmar dados iniciais:
  - Segmento
  - Nome/empresa
  - Canal de contato (WhatsApp/Ligação/Reunião)
  - O que Caio sabe: dor aparente, autoridade presumida, fit inicial

  Definir modo de discovery: Call 20min vs. WhatsApp sequencial
  Regra: se lead preferiu WhatsApp → WhatsApp. Se aceitou reunião → call.
```

### Fase 2 — Discovery (Call 20 min)

```
task: |
  Conduzir call de discovery estruturada em 20 minutos:

  [0-3 min] Rapport + contexto
  "Antes de qualquer coisa, quero entender o momento de vocês.
  Me conta como tá sendo a captação hoje?"

  [3-8 min] Dor + Métricas (MEDDIC: I + M)
  P1 (Pain): "O que mais preocupa na captação? Se continuasse assim 6 meses?"
  P2 (Metrics): "Quantos clientes novos/mês? Quanto cada um representa?"

  [8-13 min] Urgência + Processo (MEDDIC: D2 + JTBD)
  P3 (JTBD): "O que aconteceu nos últimos meses que fez buscar solução agora?"
  P4 (Decision Process): "Se a proposta fizer sentido, como seria até fechar?
  Tem alguma etapa que costuma travar?"

  [13-17 min] Critérios + Champion/EB (MEDDIC: D1 + C + E)
  P5 (Criteria): "O que seria inegociável numa consultoria? O que faria dizer 'não'?"
  P6 (Champion + EB): "Além de você, tem alguém que precisa estar alinhado
  quando for pra proposta — sócio, financeiro?"

  [17-20 min] Próximo passo claro
  "Com base no que conversamos, faz sentido eu estruturar uma proposta específica
  para vocês. Posso enviar até {data}? E se surgir dúvida, tudo bem chamar no {canal}?"

  REGRA: Seguir como conversa — não como checklist.
  Se resposta evasiva: reformular com mais contexto.
  UMA pergunta por vez — nunca bombardear.
```

### Fase 3 — Discovery via WhatsApp (sequencial)

```
task: |
  Conduzir qualificação por WhatsApp em 6 mensagens sequenciais.
  Aguardar resposta antes de enviar a próxima.

  Msg 1: "Oi {nome}! Quero entender o momento de vocês.
  O que tá funcionando na captação e o que preocupa?"

  Msg 2 (após resposta): "Faz sentido. Quantos clientes novos/mês
  e quanto cada um representa pro faturamento?"

  Msg 3: "E o que mudou nos últimos meses que fez buscar uma solução agora?"

  Msg 4: "Já tentou agência, freelancer ou ads por conta própria? Como foi?"

  Msg 5: "Se em 6 meses isso estivesse resolvido, como seria?
  O que seria inegociável?"

  Msg 6: "Tem mais alguém que precisaria estar alinhado quando
  for pra proposta — sócio, gerente?"

  REGRA DE OURO: NUNCA 2 perguntas no mesmo bloco.
  REGRA: Max 4 linhas por mensagem. Texto sempre primeiro.
```

### Fase 4 — MEDDIC Scoring

```
task: |
  Usar template meddic-scoring-tmpl.yaml.
  Pontuar cada variável de 0 a 2:
  0 = desconhecido | 1 = parcial | 2 = confirmado

  VERIFICAR KNOCK-OUTS PRIMEIRO:
  Se Economic Buyer = 0 → BLOQUEAR. Conversando com quem não decide.
  Se Identify Pain = 0 → BLOQUEAR. Sem dor = sem urgência = "depois".

  CALCULAR SCORE TOTAL (max 12):
  10-12 → ✅ Avançar para proposta
  7-9   → 🔄 Requalificar em 7 dias
  4-6   → 🌱 Nutrir 30 dias + nova call
  0-3   → ❌ Descartar (reavaliar 90 dias se estratégico)
```

### Fase 5 — Output por Decisão

```
task: |
  DECISÃO: AVANÇAR (score ≥ 10)
  ─────────────────────────────────────────
  1. Solicitar briefing ao Camaleão:
     Input: segmento + score MEDDIC + sinais de perfil detectados
     Output esperado: briefing pré-reunião em 6 blocos

  2. Ao receber briefing do Camaleão, passar para Caio com:
     - Score MEDDIC completo + variáveis mapeadas
     - Palavras-chave do lead (JTBD — usar no headline da proposta)
     - Cadência recomendada por segmento
     - Briefing do Camaleão anexo
     - Gerar ficha_meddic preenchida (template meddic-scoring-tmpl.yaml)

  DECISÃO: REQUALIFICAR (score 7-9)
  ─────────────────────────────────────────
  Gerar 1 pergunta cirúrgica para a variável com menor score.
  Agendar retorno em 7 dias.
  Mensagem: "Ficou uma dúvida — {pergunta específica}"

  DECISÃO: NUTRIR (score 4-6)
  ─────────────────────────────────────────
  Definir sequência de nutrição 30 dias.
  Delegar cadência ao GestorFunil (*cadencia {segmento} nutricao)
  Conteúdo: resolver dor identificada, sem pressão de venda.

  DECISÃO: DESCARTAR (score 0-3 ou knockout)
  ─────────────────────────────────────────
  Mensagem de saída elegante:
  "Nesse momento não parece que faz sentido avançar, mas fico disponível
  se o contexto mudar. Posso marcar um contato daqui 90 dias?"
  Reavaliar em 90 dias se estratégico (segmento prioritário).

output: ficha-meddic-{lead}-{YYYY-MM-DD}.md
```

---

## Integração com Outros Agentes

- **Caio:** Fonte do lead (pós-triagem) + receptor (se aprovado com briefing)
- **Camaleão:** Recebe score ≥ 10 para gerar briefing de personalização pré-reunião
- **Argus:** Se lead é reativação de cliente antigo, consultar health score histórico

---

*Squad Cadarn Comercial — Task v1.0*
*Framework: MEDDIC (Jack Napoli & Dick Dunkel) + JTBD (Christensen) + Ciclo PME BR*
*"Score ≥ 10 = proposta. Abaixo = nutrir. Knock-out = parar. Sem exceções."*
