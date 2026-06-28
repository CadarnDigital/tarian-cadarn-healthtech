---

## Task Definition

```yaml
task: runSalesBlitz()
responsavel: Caio (caio)
responsavel_type: Agente
squad: cadarn-comercial
templates:
  - script-prospeccao-tmpl.yaml
tarian_portable: true
frequencia_recomendada: diária (bloco fixo — BLITZ)

description: >
  Gera lista de leads qualificados por nicho e scripts de abordagem ativa
  personalizados (WhatsApp, Instagram DM, LinkedIn, e-mail) seguindo o
  método VENDE-C (Caio Carneiro) e a filosofia Flávio Augusto de prospecção
  ativa sistemática. O Blitz é um bloco fixo diário na agenda — não opcional.

Entrada:
  - campo: nicho
    tipo: enum
    valores: [imobiliaria, advocacia, estetica, outro]
    origem: Elicitação
    obrigatório: true

  - campo: quantidade_leads
    tipo: int
    default: 10
    origem: Elicitação
    obrigatório: false

  - campo: canal
    tipo: enum
    valores: [whatsapp, instagram_dm, linkedin, email, todos]
    default: whatsapp
    origem: Elicitação
    obrigatório: false

Saída:
  - campo: lista_leads_ganchos
    tipo: markdown
    destino: Caio (execução imediata)
    persistido: false

  - campo: scripts_abordagem
    tipo: markdown
    destino: Caio (execução imediata)
    persistido: false
```

---

## Execution Modes

### 1. Blitz Nicho Específico **[DEFAULT]**
- Gera X leads do nicho com gancho personalizado
- Scripts de cold message calibrados por canal e nicho
- **Trigger:** `*blitz {nicho} {quantidade}` (ex: `*blitz imobiliaria 10`)

### 2. Blitz Multi-nicho
- Distribui leads entre 2-3 nichos do ICP
- **Trigger:** `*blitz todos {quantidade_total}`

### 3. Gerar Script Isolado
- Gera apenas script para um canal específico sem lista de leads
- **Trigger:** `*prospectar {nicho} {canal}`

---

## Workflow — Blitz Nicho Específico

### Fase 1 — Elicitação (se não fornecido no comando)

```
elicit: true
prompt: |
  Para montar o blitz de hoje:

  1. Qual o nicho? (Imobiliária / Advocacia / Estética premium)
  2. Quantos leads quero abordar hoje? (default: 10)
  3. Canal principal? (WhatsApp / Instagram DM / LinkedIn / E-mail)
  4. Tenho algum lead específico com contexto para personalizar? (sim/não)
```

### Fase 2 — Perfil de Prospecção do Nicho

```
task: |
  Ativar frame do nicho:

  IMOBILIÁRIA:
  - Perfil: corretor/imobiliária premium, DISC I+D, decide rápido
  - Gatilho: concorrente crescendo no digital, alta Selic, queda de visitas
  - Gancho: "Vi que vocês atuam em [bairro/região]. Pergunta rápida..."
  - Sazonalidade: março e setembro são picos de abertura
  - Canal preferido: WhatsApp (áudio após 2-3 trocas de texto)
  - NUNCA: proposta na cold message

  ADVOCACIA:
  - Perfil: sócio administrador, DISC C+S, formal, avesso a risco
  - Gatilho: colega ganhando visibilidade digital, nova lei, queda de indicações
  - Gancho: referência a área específica do escritório + conformidade OAB
  - Canal: LinkedIn (primeiro) → E-mail → WhatsApp (formal, nunca áudio)
  - NUNCA: chamar de "proposta de marketing" — chamar de "Plano de Posicionamento"

  ESTÉTICA PREMIUM:
  - Perfil: médico proprietário, DISC I+D, ego atrelado à marca pessoal
  - Gatilho: concorrente dominando Instagram, novo procedimento, sazonalidade verão
  - Gancho: referência ao procedimento/especialidade específica + marca pessoal
  - Canal: Instagram DM (primeiro) → WhatsApp (após resposta inicial)
  - URGÊNCIA SAZONAL > qualquer argumento de ROI
```

### Fase 3 — Geração da Lista de Leads com Ganchos

```
task: |
  Gerar lista de {quantidade} leads com perfil e gancho personalizado.

  FORMATO POR LEAD:
  ─────────────────────────────────────────
  Lead {N}: {nome/empresa ou tipo genérico}
  Segmento: {sub-nicho específico}
  Canal de abordagem: {canal}
  Gancho personalizado: {referência específica ao contexto do lead}
  Primeiro passo: {ação concreta — DM, WhatsApp, etc.}
  ─────────────────────────────────────────

  REGRAS:
  - Cada lead tem gancho DIFERENTE — nunca mensagem genérica
  - Gancho é sempre baseado em algo observável (post, bairro, especialidade, evento)
  - Incluir "saída fácil" na abordagem: "se não fizer sentido, sem problema"
```

### Fase 4 — Scripts de Abordagem por Canal

```
task: |
  Usar template script-prospeccao-tmpl.yaml como base.

  Gerar scripts calibrados para o nicho e canal:

  ESTRUTURA WHATSAPP (cold message):
  [1] Saudação curta (max 1 linha) → PAUSA
  [2] Identificação + contexto (max 2 linhas)
  [3] Gancho personalizado
  [4] UMA pergunta aberta
  → Total: max 4 linhas / 160 chars

  ESTRUTURA INSTAGRAM DM:
  [1] Gancho contextual (referência a post/conteúdo)
  [2] Elogio genuíno e específico
  [3] "Vou ser bem direto aqui..."
  [4] UMA pergunta
  [5] Transição para WhatsApp

  ESTRUTURA LINKEDIN:
  [1] Conexão com área de atuação
  [2] Problema relevante para o nicho
  [3] Credencial Cadarn (sem soar vendedor)
  [4] Proposta de conversa rápida

  ESTRUTURA E-MAIL (advocacia):
  Subject: referência à área jurídica (não "marketing")
  [1] Quem sou + contexto
  [2] Observação específica sobre o escritório
  [3] Problema que o mercado deles enfrenta
  [4] Proposta de 20min de conversa
  Assinatura: formal, sem emojis

  CADÊNCIA DE FOLLOW-UP (genérica — detalhamento: consultar GestorFunil):
  D+0: Envio do cold message
  D+2: "Conseguiu ver minha mensagem?"
  D+7: Conteúdo de valor do nicho
  D+10: Reativação ou encerramento elegante
```

### Fase 5 — Output Final

```
task: |
  Entregar ao Caio:

  BLITZ DO DIA — {data}
  Nicho: {nicho} | Canal: {canal} | Meta: {quantidade} leads

  ─── LISTA DE LEADS ───
  {lista com ganchos personalizados}

  ─── SCRIPTS PRONTOS ───
  Script Cold Message ({canal}):
  {script principal}

  Script Follow-up D+2:
  {script}

  Script Follow-up D+7 (conteúdo de valor):
  {script}

  ─── REGRAS DO BLITZ ───
  ✓ Uma mensagem por lead — sem bombardear
  ✓ Máx 2-3 toques/semana por contato
  ✓ Texto SEMPRE primeiro (áudio só com permissão)
  ✓ Fechar SEMPRE com próximo passo ou saída elegante
  ✓ Lead que responde → triagem imediata (*triagem)
```

---

## Integração com Outros Agentes

- **GestorFunil:** Recebe leads que responderam positivamente para qualificação MEDDIC
- **Camaleão:** Gera briefing antes de reunião de diagnóstico com lead quente

---

*Squad Cadarn Comercial — Task v1.0*
*Framework: VENDE-C (Caio Carneiro) + Filosofia Flávio Augusto (prospecção ativa)*
*"BLITZ = bloco fixo diário de prospecção na agenda. Não é opcional."*
