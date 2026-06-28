---

## Task Definition

```yaml
task: generatePreBriefing()
responsavel: Camaleão (camaleao)
responsavel_type: Agente
squad: cadarn-comercial
templates:
  - pre-briefing-disc-tmpl.yaml
tarian_portable: true

description: >
  Gera briefing de personalização antes de uma reunião de diagnóstico ou
  revisão de proposta conforme o perfil DISC do decisor. Identifica perfil
  comportamental com base em sinais do lead, cruza com segmento e Challenger
  type, e entrega instruções práticas: tom, abertura ideal, insight Challenger,
  objeção mais provável, e como fechar a proposta para esse perfil.
  O Camaleão nunca interage com o lead — opera como sistema de suporte.

Entrada:
  - campo: dados_lead
    tipo: object
    origem: GestorFunil (pós-MEDDIC) ou Caio (pós-diagnóstico)
    obrigatório: true
    campos:
      - segmento
      - cargo_decisor
      - como_respondeu_primeiro_contato
      - porte_empresa
      - quem_estará_na_reunião
      - score_meddic (se disponível)
      - palavras_chave_jtbd (se disponível)

  - campo: modo
    tipo: enum
    valores: [pre_reuniao, revisao_proposta]
    default: pre_reuniao
    origem: Elicitação
    obrigatório: false

Saída:
  - campo: briefing_personalizacao
    tipo: markdown
    template: pre-briefing-disc-tmpl.yaml
    destino: GestorFunil (que repassa ao Caio) | Caio (direto, pós-diagnóstico)
    persistido: false
```

---

## Execution Modes

### 1. Briefing Pré-Reunião **[DEFAULT]**
- Gera briefing antes da reunião de diagnóstico
- Input: dados do lead + MEDDIC summary
- **Trigger:** `*briefing {dados do lead}`

### 2. Revisão de Proposta
- Analisa proposta rascunho e recomenda ajustes por perfil DISC
- Input: perfil confirmado + texto da proposta
- **Trigger:** `*revisar-proposta {perfil DISC} {proposta}`

### 3. Identificação de Perfil
- Identifica perfil DISC a partir de sinais comportamentais
- **Trigger:** `*perfil {descrição do comportamento}`

---

## Workflow — Briefing Pré-Reunião

### Fase 1 — Triagem (3 perguntas obrigatórias)

```
task: |
  Se não fornecidos no input, elicitar:

  1. Qual o segmento? (Imobiliária / Advocacia / Estética)
  2. Quem vai estar na reunião? (cargo, quantas pessoas)
  3. O que motivou o contato? (gatilho de compra)

  Inputs complementares (se disponíveis):
  - Como respondeu ao primeiro contato (velocidade, tom, canal)
  - Cargo e background do decisor
  - Porte da empresa
```

### Fase 2 — Identificação do Perfil DISC

```
task: |
  Analisar sinais disponíveis para identificar perfil.
  MÍNIMO 2 sinais convergentes antes de classificar.

  SINAIS DE PERFIL:

  🔴 D (Dominante):
  - Respondeu rápido com poucos caracteres e pediu data direto
  - Fala rápida/assertiva, corta explicações na cold message
  - Usa "eu" mais que "nós", pergunta "quanto custa" logo
  - Cargo: dono solo, CEO sem sócios, perfil empreendedor agressivo

  🟡 I (Influente):
  - Mandou mensagem de voz com histórico pessoal antes de confirmar
  - Tom caloroso, emojis, linguagem emocional
  - Perguntou sobre cases de outras empresas, não sobre processo
  - Cargo: médico com marca pessoal forte, corretor "celebridade"

  🟢 S (Estável):
  - Pediu referências, demorou 3 dias para confirmar
  - Tom pausado, pergunta sobre suporte pós-venda
  - Avesso a urgência, reage mal a "só até sexta"
  - Cargo: sócio administrativo conservador, escritório familiar

  🔵 C (Conformidade):
  - Enviou lista de perguntas por e-mail antes da reunião
  - Chegou com planilha ou documento comparativo
  - Pergunta sobre exceções, casos extremos, regulação
  - Cargo: sócio técnico em advocacia, médico analítico

  CRUZAMENTO COM ICP:
  Imobiliária → default 🟡I+D
  Advocacia → default 🔵C+S (dono D)
  Estética → default 🟡I+D (com C awareness de ROI)
```

### Fase 3 — Gerar Briefing (6 blocos)

```
task: |
  Usar template pre-briefing-disc-tmpl.yaml.
  Preencher 6 blocos:

  BLOCO 1 — PERFIL IDENTIFICADO
  Perfil DISC: {letra} — {nome}
  Confiança: {alta|média|baixa}
  Sinais que levaram à identificação: {lista}
  Challenger type: {Go-Getter|Teacher|Skeptic|Friend|Lone Wolf}

  BLOCO 2 — CONFIGURAÇÃO DA REUNIÃO
  Tom recomendado: {tom}
  Velocidade: {ritmo}
  Canal adaptativo no WhatsApp: sempre I-style (calor humano antes de dados)
  Regra cultural BR: rapport primeiro — SEMPRE — independente do perfil

  BLOCO 3 — ABERTURA IDEAL
  Frase de abertura calibrada para o perfil:
  🔴 D: "Antes de qualquer coisa — qual é o número que você precisa mover?"
  🟡 I: "Recebi alguns contextos antes de entrar aqui, mas quero ouvir de você."
  🟢 S: "Vou fazer algumas perguntas para entender como vocês operam — sem pressa."
  🔵 C: "Quero mapear seu processo atual com detalhe antes de sugerir qualquer coisa."

  BLOCO 4 — INSIGHT CHALLENGER
  Insight calibrado por segmento + gatilho de compra:
  {insight específico — não genérico para o segmento inteiro}
  Quando usar: após rapport, antes de diagnóstico formal

  BLOCO 5 — OBJEÇÕES PROVÁVEIS
  Objeção #1 (mais provável para esse perfil+segmento): {objeção}
  Contorno recomendado: {técnica}
  Objeção #2 (se aplicável): {objeção}
  Contorno: {técnica}

  BLOCO 6 — ENCERRAMENTO DA PROPOSTA
  Frase de fechamento calibrada para o perfil:
  🔴 D: "Você não precisa de mais reuniões — precisa de resultado..."
  🟡 I: "Estamos prontos para construir isso junto com você..."
  🟢 S: "Não estamos pedindo que você decida agora..."
  🔵 C: "Disponibilizamos toda a documentação para análise antes da assinatura..."
  Densidade recomendada da proposta: {X páginas} | Começa por: {resultado|transformação|problema|diagnóstico}
  Tipo de prova: {dado de resultado|depoimento|benchmark|metodologia documentada}
```

---

## Workflow — Revisão de Proposta

### Fase 1 — Confirmar Perfil

```
task: |
  Se perfil DISC não foi confirmado em reunião, solicitar:
  "Qual o perfil DISC identificado na reunião?
  Se não confirmado, quais os 2-3 sinais mais marcantes?"
```

### Fase 2 — Análise da Proposta Atual

```
task: |
  Analisar estrutura atual vs. ideal para o perfil:

  VERIFICAR:
  1. A proposta começa pelo elemento certo para o perfil?
     D: começa por resultado? I: começa por transformação?
     S: começa por problema validado? C: começa com diagnóstico + dados?

  2. A extensão está adequada?
     D: 6-8 págs. | I: 8-12 págs. (visual/Canva) | S: 12-15 págs. | C: 16-22 págs. (com índice)

  3. O tipo de prova está correto?
     D: dado de resultado de cliente parecido
     I: depoimento humano + screenshot de resultado
     S: case de parceria estável + garantia documentada
     C: benchmark + metodologia documentada + conformidade regulatória

  4. O tom está calibrado?
  5. A frase de fechamento está adequada?
```

### Fase 3 — Output de Revisão

```
task: |
  Entregar lista de ajustes em 4 dimensões:
  (1) Estrutura: o que mover para qual posição
  (2) Extensão e densidade: adicionar/remover seções
  (3) Tipo de prova: qual incluir/enfatizar
  (4) Tom e frase de fechamento: ajustes específicos

output: briefing-{lead}-{YYYY-MM-DD}.md
```

---

## Integração com Outros Agentes

- **GestorFunil:** Envia lead qualificado (score ≥ 10) com dados MEDDIC para briefing
- **Caio:** Recebe briefing e usa na reunião de diagnóstico + revisão de proposta

---

*Squad Cadarn Comercial — Task v1.0*
*Framework: DISC (Marston) + Challenger Sale (Dixon & Adamson) + SPIN (Rackham)*
*"Contexto é vantagem competitiva. O Camaleão adapta — não cria do zero."*
