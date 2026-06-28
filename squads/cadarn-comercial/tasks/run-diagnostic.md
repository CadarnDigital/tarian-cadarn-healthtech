---

## Task Definition

```yaml
task: runDiagnostic()
responsavel: Caio (caio)
responsavel_type: Agente
squad: cadarn-comercial
templates: []
tarian_portable: true

description: >
  Conduz roteiro de diagnóstico consultivo antes da proposta. Aplica o
  princípio central do VENDE-C: "diagnóstico antes de proposta — sem exceção".
  Usa perguntas abertas de escuta ativa para mapear a dor real do cliente,
  identificar urgência e construir o vínculo necessário para que o cliente
  "se venda a compra" ao descrever o cenário ideal. Opera como médico
  diagnosticando — nunca como vendedor empurrando solução.

Entrada:
  - campo: dados_lead
    tipo: object
    origem: Briefing do Camaleão (pré-reunião) ou GestorFunil
    obrigatório: false
    nota: "Se não fornecido, Caio elicita os dados antes de iniciar"

  - campo: segmento
    tipo: enum
    valores: [imobiliaria, advocacia, estetica, outro]
    origem: Elicitação ou handoff
    obrigatório: true

  - campo: formato
    tipo: enum
    valores: [reuniao, whatsapp]
    default: reuniao
    origem: Elicitação
    obrigatório: false

Saída:
  - campo: mapa_diagnostico
    tipo: object
    campos:
      - dor_principal (em 1 frase)
      - situacao_atual
      - resultado_esperado_90d
      - urgencia_confirmada (sim/não)
      - perfil_disc_confirmado
      - palavras_chave_jtbd
    destino: Caio (para gerar proposta) + Camaleão (revisão de proposta)
    persistido: false
```

---

## Execution Modes

### 1. Diagnóstico em Reunião **[DEFAULT]**
- Roteiro completo de 45-60 min
- Usa briefing do Camaleão (se disponível)
- **Trigger:** `*diagnosticar {lead}`

### 2. Diagnóstico via WhatsApp
- Versão sequencial adaptada para texto
- UMA pergunta por vez, aguardar resposta
- **Trigger:** `*diagnosticar {lead} whatsapp`

---

## Workflow — Diagnóstico em Reunião

### Pré-Reunião — Verificar Briefing

```
task: |
  ANTES de entrar na reunião, verificar se Camaleão gerou briefing:

  SE briefing disponível:
  - Revisar perfil DISC identificado
  - Ler abertura recomendada
  - Memorizar insight Challenger e objeção mais provável
  - Ajustar tom conforme recomendação

  SE briefing NÃO disponível:
  - Usar abertura default (I-style): rapport antes de qualquer pergunta
  - Aplicar regra cultural BR: calor humano → business, nunca o contrário
  - Calibrar no início da conversa pelos sinais DISC (tom, ritmo, tipo de pergunta)
```

### Fase 1 — Abertura e Rapport (0-5 min)

```
task: |
  Calibrada pelo perfil DISC (ver briefing Camaleão).

  REGRA CULTURAL BR (universal):
  Sempre abrir com rapport I-style, INDEPENDENTE do perfil presumido D ou C.
  Cordialidade antes de business — Brasil tem Power Distance 69.

  Abertura default (sem briefing):
  "Antes de qualquer coisa, me fala — como tá sendo o dia a dia de vocês?
  O que tá funcionando bem e o que tá pesando?"

  ANTI-PATTERN:
  NUNCA abrir com: "Então, me conta teus problemas de captação."
  NUNCA abrir com features/preços antes do rapport.
```

### Fase 2 — Diagnóstico da Situação Atual (5-20 min)

```
task: |
  Perguntas de diagnóstico — UMA por vez, escuta ativa entre cada uma.

  PERGUNTAS ABERTAS DE SITUAÇÃO:
  "Como vocês estão captando clientes hoje?"
  "Quais são as principais fontes de novos clientes?"
  "Como tá o volume — está suficiente, apertado, ou tem folga?"

  PERGUNTAS DE PROBLEMA (ir mais fundo):
  "O que mais incomoda nesse processo hoje?"
  "Se isso continuasse exatamente assim por mais 6 meses, seria problemático?
  Quanto custaria?"
  "Tem algum mês que foi especialmente frustrante com captação? O que aconteceu?"

  TÉCNICA DE ESCUTA ATIVA:
  - Pausar após cada resposta (2-3 segundos antes de perguntar)
  - Espelhar: "Entendo — então o maior gap é X?"
  - Anotar palavras EXATAS que o cliente usa (viram headline da proposta)
  - Demonstrar que anotou: "Deixa eu entender direito — você disse que..."

  ADAPTAÇÃO POR SEGMENTO:
  Imobiliária: perguntar sobre ciclo de fechamento, sazonalidade, dependência de indicação
  Advocacia: perguntar sobre captação de casos, visibilidade digital, compliance OAB
  Estética: perguntar sobre agenda, tipo de procedimento, posicionamento de preço
```

### Fase 3 — Diagnóstico de Urgência e JTBD (20-35 min)

```
task: |
  PERGUNTAS JTBD (embutidas na conversa, não como checklist):

  GATILHO DE URGÊNCIA:
  "O que aconteceu nos últimos 2-3 meses que fez buscar uma solução agora?"
  → Revela o evento que gerou urgência. CRUCIAL para proposta.

  FRUSTRAÇÃO COM TENTATIVAS ANTERIORES:
  "Já tentou resolver isso de outra forma? Agência, freelancer, ads por conta?
  Como foi?"
  → Revela o que NÃO funciona. Diferencial: "aqui é diferente porque..."

  VISÃO DE FUTURO (JTBD central):
  "Se em 6 meses esse problema estivesse resolvido, como seria?
  Como você saberia que funcionou?"
  → ANOTAR LITERALMENTE. Essas palavras viram o headline da proposta.
  → Exemplo: cliente diz "queria ter agenda cheia sem depender de indicação"
    → Proposta: "Agenda cheia sem depender de indicação — esse é o plano."

  INSIGHT CHALLENGER (do briefing Camaleão ou do segmento):
  Momento: depois que o lead descreveu o problema — antes da solução.
  "A maioria dos {segmento} que vejo enfrenta exatamente isso.
  O que me chama atenção é que {insight calibrado pelo gatilho}."
  → Não citar concorrente pelo nome. Citar o padrão do mercado.
```

### Fase 4 — Confirmação de Autoridade e Processo (35-45 min)

```
task: |
  ECONOMIC BUYER + DECISION PROCESS (MEDDIC):
  "Para que a proposta seja aproveitada da melhor forma —
  além de você, tem alguém que precisaria estar envolvido nessa decisão?
  Sócio, gerente, alguém do financeiro?"

  Se há outros decisores:
  "Faz sentido incluir {nome} numa próxima conversa antes de montar a proposta?
  Ou você consegue alinhar internamente?"

  TÉCNICA DI (Decisão Imediata):
  Se sinal de indecisão ou múltiplos decisores:
  "Só para já alinhar — quando você conversa com {sócio/cônjuge/contador},
  o que costuma ser a principal preocupação deles com esse tipo de investimento?"
  → Antecipar objeção ANTES que ela apareça depois.
```

### Fase 5 — Encerramento do Diagnóstico

```
task: |
  Com base no diagnóstico, confirmar o que foi mapeado:

  "Deixa eu resumir o que entendi para ter certeza que tô capturando certo:
  [1] A situação hoje é: {situação em 1 frase}
  [2] O que mais pesa é: {dor principal}
  [3] O que você quer alcançar em 90 dias: {resultado esperado}
  Faz sentido?"

  Aguardar confirmação do cliente. Ajustar se necessário.
  → Este resumo CONFIRMA a dor e alinha expectativa antes da proposta.

  PRÓXIMO PASSO:
  NUNCA encerrar sem próximo passo agendado.
  "Com base em tudo isso, consigo estruturar uma proposta específica para vocês.
  Posso enviar até {data}? E agendamos {X dias} depois para percorrer juntos?"

  ANTI-PATTERN:
  NUNCA: "Qualquer coisa me avisa."
  SEMPRE: próximo passo com data e hora.

output: mapa-diagnostico-{lead}.md
```

---

## Workflow — Diagnóstico via WhatsApp

```
task: |
  Versão sequencial — aguardar resposta entre cada mensagem.

  Msg 1 (abertura): "Oi {nome}! Quero entender melhor o contexto de vocês.
  Como tá sendo a captação hoje?"

  Msg 2 (aprofundar dor): "Entendi. O que mais incomoda nesse processo hoje?"

  Msg 3 (urgência JTBD): "E o que aconteceu recentemente que fez buscar
  uma solução agora?"

  Msg 4 (tentativas): "Já tentou resolver isso de alguma forma?
  Como foi a experiência?"

  Msg 5 (visão de futuro): "Se em 6 meses isso estivesse resolvido,
  como seria? O que você saberia que funcionou?"

  Msg 6 (processo/autoridade): "Só para alinhar — na hora de tomar a decisão,
  você decide sozinho ou costuma consultar alguém?"

  → Após 6 mensagens: "Com base no que você me contou, consigo montar
  uma proposta específica. Posso enviar até {data}?"
```

---

## Integração com Outros Agentes

- **Camaleão:** Fornece briefing pré-reunião (DISC + abertura + insight + objeções)
- **Camaleão:** Recebe perfil DISC confirmado para revisão de proposta
- **GestorFunil:** Mapa de diagnóstico alimenta variáveis I e M do MEDDIC

---

*Squad Cadarn Comercial — Task v1.0*
*Framework: VENDE-C (Caio Carneiro) + SPIN Selling (Rackham) + JTBD (Christensen)*
*"O foco não pode estar em você — tem que estar na descoberta."*
