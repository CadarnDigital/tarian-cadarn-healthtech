---

## Task Definition

```yaml
task: closeDeal()
responsavel: Caio (caio)
responsavel_type: Agente
squad: cadarn-comercial
templates:
  - client-intake-handoff-tmpl.yaml
tarian_portable: true

description: >
  Conduz o fechamento do contrato e dispara o handoff estruturado para
  Squad Operacional, Marketing e Argus. Aplica técnica de fechamento VENDE-C:
  pergunta fechada + próximo passo concreto + Técnica DI preventiva.
  CRÍTICO: o handoff (client-intake-handoff-tmpl.yaml) deve ser preenchido
  ANTES de notificar qualquer squad — onboarding bloqueado sem handoff.

Entrada:
  - campo: mapa_diagnostico
    tipo: object
    origem: Task run-diagnostic.md
    obrigatório: true

  - campo: proposta_aceita
    tipo: string
    origem: Confirmação do cliente
    obrigatório: true

  - campo: dados_contrato
    tipo: object
    origem: Elicitação
    obrigatório: true
    campos:
      - valor_mrr
      - duracao_meses
      - data_inicio
      - forma_pagamento
      - escopo_incluido

Saída:
  - campo: client_intake_handoff
    tipo: yaml
    template: client-intake-handoff-tmpl.yaml
    destino: Kairos + Arc + Argus + Marketing (via handoff)
    persistido: true
    nota: "OBRIGATÓRIO antes de qualquer notificação"
```

---

## Execution Modes

### 1. Fechamento Padrão **[DEFAULT]**
- Lead aceitou proposta → confirmar + preencher handoff + disparar
- **Trigger:** `*fechar {situação}`

### 2. Fechamento com Objeção Final
- Lead hesitando → contornar + fechar
- **Trigger:** `*fechar {situação}` com contexto de objeção pendente

---

## Workflow — Fechamento Padrão

### Fase 1 — Script de Fechamento

```
task: |
  TÉCNICA DE FECHAMENTO VENDE-C:

  [1] Pergunta fechada (sem espaço para "talvez"):
  "Com base em tudo que conversamos, você vê a Cadarn como a escolha certa
  para resolver {dor principal}? Se sim, o próximo passo é {ação concreta}."

  [2] Silêncio estratégico:
  Após fazer a pergunta de fechamento — PARAR. Não falar.
  O próximo a falar é o cliente. Sempre.
  Quebrar o silêncio é matar o fechamento.

  [3] Técnica DI preventiva (antes de "preciso pensar"):
  "Só para já alinhar — se a proposta fizer sentido para você, o que
  normalmente acontece antes de fechar? Tem alguma etapa no processo de vocês?"
  → Antecipar objeção antes que apareça.

  [4] Se aceite verbal:
  "Ótimo! Para darmos o pontapé: envio o contrato por {canal} e agendamos
  a reunião de kickoff para {data}. Funciona?"

  CONTORNO DE OBJEÇÕES FINAIS (se aparecerem):
  "Vou pensar" → "O que você precisa pensar? Qual é a dúvida?
  Vamos marcar 20min depois de você refletir — quando seria bom?"

  "Preciso falar com sócio" → DI: "Quando você vai conversar?
  Posso participar de uma call rápida para garantir que todas as dúvidas
  estejam respondidas?"

  "Está caro" → NUNCA defender. Reforçar valor:
  "Quanto custa manter a situação atual por mais 6 meses?
  [dado do diagnóstico]. Esse plano custa {valor}/mês para resolver isso."

  ANTI-PATTERNS DE FECHAMENTO:
  NUNCA: "Pode pensar com calma, sem pressa."
  NUNCA: defender preço com desculpa.
  NUNCA: oferecer desconto sem solicitação explícita.
  NUNCA: encerrar sem data/próximo passo.
  NUNCA: "Qualquer coisa me fala."
```

### Fase 2 — Indicação (pós-fechamento)

```
task: |
  PRIORIDADE MÁXIMA — Pedir indicação no momento de máxima satisfação.
  Momento: logo após o "sim" — antes de qualquer burocracia.

  "Antes de qualquer coisa — fico feliz que fechamos isso.
  Me dá 3 a 5 nomes de colegas {do segmento} que passam pelo mesmo problema
  que você descreveu. Posso ser útil para eles também."

  TÉCNICA FLÁVIO AUGUSTO:
  - "Empresa que não pede indicação paga mais CAC."
  - Pedir no MOMENTO DE MAIOR SATISFAÇÃO (pós-sim, não pós-entrega)
  - Pedir NOMES específicos, não "se souber de alguém"
  - 50-80% dos fechamentos vêm de indicação

  OUTPUT: lista de indicações → entra no blitz do dia seguinte (*blitz por indicação)
```

### Fase 3 — Preenchimento do Client Intake Handoff

```
task: |
  GATE OBRIGATÓRIO: preencher ANTES de notificar qualquer squad.
  "Sem handoff preenchido = onboarding bloqueado." (regra squad.yaml)

  Usar template client-intake-handoff-tmpl.yaml.

  Seções a preencher:
  [1] IDENTIFICAÇÃO: nome, cargo, empresa, segmento, porte, cidade
  [2] CONTATO: WhatsApp, e-mail, canal preferido, melhor horário
  [3] CONTRATO: serviços, MRR, duração, data início, pagamento
  [4] CONTEXTO DA VENDA: dor principal, situação atual, resultado 90d,
      motivo escolha Cadarn, fornecedor anterior, comprometimentos feitos
      CRÍTICO: comprometimentos_feitos — Arc precisa saber exatamente
      o que foi prometido durante a venda para cumprir.
  [5] PERFIL DO DECISOR: DISC, estilo, sensibilidades, motivação primária
  [6] RESTRIÇÕES: tópicos sensíveis, canais proibidos, identidade visual
  [7] HANDOFF TARGETS: Kairos, Arc, Marketing, Argus

  CHECKLIST DE CAIO (validar antes de enviar):
  - [ ] Dor principal em 1 frase clara
  - [ ] Resultado esperado 90 dias específico (não "crescer")
  - [ ] Comprometimentos feitos durante a venda listados
  - [ ] Perfil DISC preenchido (mesmo confiança baixa)
  - [ ] Restrições de conteúdo/canal informadas
  - [ ] Stakeholders adicionais identificados
  - [ ] Data de início confirmada com cliente
  - [ ] Handoff para Kairos e Arc disparados
```

### Fase 4 — Disparo dos Handoffs

```
task: |
  ORDEM DOS HANDOFFS (após handoff preenchido):

  [URGENTE — em <4h do fechamento]
  1. Kairos (gestor-processos):
     "Novo cliente fechado — configurar projeto no ClickUp."
     Enviar: client-intake-handoff preenchido.

  2. Arc (client-success):
     "Novo cliente — iniciar fase AFFIRM. Contato em <24h."
     Enviar: client-intake-handoff + comprometimentos feitos destacados.

  [ALTA — em <24h do fechamento]
  3. Argus (account-orchestrator):
     "Cadastrar {cliente} no portfólio — iniciar monitoramento de health score."
     Enviar: dados do contrato + segmento + ticket.

  [GATE — Marketing só após Arc confirmar kickoff]
  4. Marketing (squad-marketing / Consultora):
     NÃO notificar agora.
     Arc sinaliza quando ACTIVATE estiver concluído.
     "Marketing NÃO inicia antes do sinal de Arc — protege fase AFFIRM/ACTIVATE."

  CONFIRMAÇÃO FINAL PARA CAIO:
  "Handoffs disparados:
  ✅ Kairos — projeto no ClickUp (<4h)
  ✅ Arc — fase AFFIRM iniciada (<24h)
  ✅ Argus — cliente no portfólio
  ⏳ Marketing — aguardando sinal de Arc (kickoff)"

output: client-intake-handoff-{cliente}-{YYYY-MM-DD}.yaml
```

---

## Integração com Outros Agentes

- **Kairos:** Recebe handoff para configurar ClickUp em <4h
- **Arc:** Recebe handoff para iniciar fase AFFIRM em <24h
- **Argus:** Cadastra cliente no portfólio e inicia health score baseline
- **Marketing:** Recebe sinal de Arc após kickoff (NUNCA antes)

---

*Squad Cadarn Comercial — Task v1.0*
*Framework: VENDE-C (Caio Carneiro) + Filosofia Flávio Augusto (indicação pós-fechamento)*
*"Nunca termine sem agendar a próxima." + "Nunca feche sem pedir indicação."*
