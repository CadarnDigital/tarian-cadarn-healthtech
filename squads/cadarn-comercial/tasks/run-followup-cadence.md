---

## Task Definition

```yaml
task: runFollowupCadence()
responsavel: GestorFunil (gestor-funil)
responsavel_type: Agente
squad: cadarn-comercial
templates:
  - followup-cadence-tmpl.yaml
tarian_portable: true

description: >
  Define e executa cadência de follow-up sistemático pós-proposta por
  segmento e estágio do lead. "70% não compram no primeiro contato." —
  a cadência é o diferencial entre perder e fechar. Cada toque tem canal,
  mensagem e próximo passo definidos. Nunca pressão — sempre valor antes
  de cobrança. Inclui cadência de nutrição para leads não qualificados.

Entrada:
  - campo: segmento
    tipo: enum
    valores: [imobiliaria, advocacia, estetica, outro]
    origem: Elicitação ou handoff
    obrigatório: true

  - campo: estagio
    tipo: enum
    valores: [pos_proposta, nutricao, reativacao]
    default: pos_proposta
    origem: Elicitação
    obrigatório: true

  - campo: dados_lead
    tipo: object
    origem: Ficha MEDDIC ou histórico de contato
    obrigatório: false
    nota: "Opcional mas melhora personalização"

Saída:
  - campo: cadencia_completa
    tipo: markdown
    template: followup-cadence-tmpl.yaml
    destino: Caio (execução)
    persistido: false
```

---

## Execution Modes

### 1. Cadência Pós-Proposta **[DEFAULT]**
- D+0 a D+10 com canal, mensagem e ação por dia
- **Trigger:** `*cadencia {segmento} pos_proposta`

### 2. Cadência de Nutrição
- Lead score 4-6 → sequência 30 dias de conteúdo de valor
- **Trigger:** `*cadencia {segmento} nutricao`

### 3. Cadência de Reativação
- Lead frio → reativar após 30-90 dias de silêncio
- **Trigger:** `*cadencia {segmento} reativacao`

---

## Workflow — Cadência Pós-Proposta

### Regras Gerais (todos os segmentos)

```
task: |
  REGRAS DE FOLLOW-UP:
  - Max 2-3 toques/semana por contato
  - Valor ANTES de cobrança — nunca abrir com "o que achou?"
  - Canal calibrado por segmento e preferência do lead
  - UMA pergunta por mensagem (Caio Carneiro — VENDE-C)
  - Fechar SEMPRE com próximo passo ou saída elegante
  - Texto SEMPRE primeiro — áudio só com permissão

  ANTI-PATTERNS:
  NUNCA: "Oi, vim ver se você viu a proposta"
  NUNCA: pressão artificial ("só até sexta!")
  NUNCA: múltiplos canais simultâneos no mesmo dia
  NUNCA: reenviar proposta sem contexto novo
  NUNCA: "qualquer dúvida me avisa" — sempre fechar com próximo passo
```

### Cadência por Segmento — Pós-Proposta

```
task: |
  Usar template followup-cadence-tmpl.yaml.

  ══════════════════════════════════════
  IMOBILIÁRIA (ciclo 30-60 dias, 6-9 toques)
  ══════════════════════════════════════
  D+0 (envio): WhatsApp + mensagem de envio personalizada
  D+2: "Conseguiu dar uma olhada? Tem algum ponto que queira entender melhor?"
  D+5: WhatsApp — compartilhar dado de resultado relevante para imobiliária
       ("Corretor do {bairro} gerou X leads em {período} com esse mesmo processo")
  D+7: "Faz sentido conversarmos 20 minutos sobre a proposta?"
       Se lead abrindo mas não respondendo: "Vi que você acessou — ficou com dúvida?"
  D+10: Reativação com nova perspectiva (sazonalidade ou dado de mercado)
  D+15: "Se não fizer sentido agora, tudo bem — fico disponível se o contexto mudar."
  D+21: Conteúdo de valor (artigo, dado de mercado) sem CTA direto
  D+30: "Passando para fechar o ciclo de contato. Faz sentido mantermos contato?"
        Se não: cheque pré-datado (D+60)

  ══════════════════════════════════════
  ADVOCACIA (ciclo 45-90 dias, 8-12 toques)
  ══════════════════════════════════════
  D+0 (envio): E-mail formal + WhatsApp conciso
  D+3: E-mail: "Ficou alguma dúvida sobre a proposta — especialmente em relação
       ao processo dentro das diretrizes da OAB?"
  D+7: LinkedIn: compartilhar insight de posicionamento para escritórios
  D+10: WhatsApp formal: "Alguma atualização no processo de decisão de vocês?"
  D+14: E-mail: Documento complementar (conformidade OAB ou caso de uso similar)
  D+21: "Faz sentido incluir {sócio} numa conversa rápida sobre a proposta?"
        (DI — técnica de decisão imediata)
  D+30: "Posso preparar uma versão simplificada focada em {ponto específico
         que o lead levantou}?"
  D+45: Saída elegante ou cheque pré-datado

  ══════════════════════════════════════
  ESTÉTICA PREMIUM (ciclo 14-30 dias, 5-7 toques)
  ══════════════════════════════════════
  D+0 (envio): WhatsApp + Instagram (se preferir)
  D+2: "Doutora/Dr. {nome} — conseguiu dar uma olhada?"
  D+4: Compartilhar resultado visual de clínica similar (antes/depois de agenda)
       "Clínica parecida com a sua, mesmo perfil, resultado em 60 dias: {dados}"
  D+7: "Tem algum procedimento ou área que você sente que poderia crescer mais?"
       (reabre diagnóstico com nova angular)
  D+10: "Se fizer sentido, posso preparar um plano focado especificamente em
         {procedimento prioritário}."
  D+14: Saída elegante ou proposta revisada
  D+21: Cheque pré-datado (sazonalidade próxima)
```

### Cadência de Nutrição (score 4-6)

```
task: |
  Lead não qualificado agora. Manter relacionamento por 30 dias.

  REGRA: Nutrir = entregar valor sem vender.
  Conteúdo: resolver o problema identificado na discovery (Pain = 1).
  Objetivo: quando urgência aumentar, Cadarn já está na mente.

  Semana 1: Conteúdo educativo sobre o problema do lead (não sobre Cadarn)
  Semana 2: Case de empresa similar que resolveu o mesmo problema
  Semana 3: Dado de mercado relevante para o segmento do lead
  Semana 4: Check-in leve: "Aconteceu alguma mudança no contexto de vocês?"

  Ao fim dos 30 dias:
  → Requalificar: *qualificar {lead} {nova informação}
  → Score não mudou: manter ciclo por mais 30 dias ou descartar
```

### Cadência de Reativação (lead frio)

```
task: |
  Ver task: reativar {lead frio} (Caio) e template reativacao-lead-tmpl.yaml.

  Lead perdido há 30-90 dias. Gatilho: mudança de contexto ou sazonalidade.

  Mensagem de reativação: cheque pré-datado + nova perspectiva
  "Oi {nome}! Desde nossa última conversa, {dado novo do segmento/mercado}.
  Me veio você na cabeça. Faz sentido uma conversa rápida?"

output: cadencia-{lead}-{segmento}-{YYYY-MM-DD}.md
```

---

## Integração com Outros Agentes

- **Caio:** Executor da cadência. GestorFunil define, Caio executa.
- **Camaleão:** Se lead responde após toque D+7+, gerar novo briefing atualizado

---

*Squad Cadarn Comercial — Task v1.0*
*Framework: VENDE-C (Caio Carneiro) + Ciclo PME BR por segmento (pesquisa aprofundada)*
*"70% não compram no primeiro contato. Cadência é o diferencial."*
