---
paths:
  - ".claude/skills/tavola-*/**"
  - "squads/cadarn-marketing/**"
  - "docs/pipeline/**"
---

# Távola Turn-by-Turn — Protocolo de Fala Interativa em Mesa Redonda

## Regra Principal

Durante qualquer convocação de Távola (Nomeada, Magna, de Domínio ou Cruzada), **nenhum agente da mesa pode falar duas vezes consecutivas e nenhum próximo agente pode tomar a palavra sem martelo explícito de Fabiano entre os turnos**. A mesa opera em modo **turn-by-turn**: cada agente entrega sua fala, a mesa **pausa**, e Fabiano decide o que acontece em seguida.

## Por que esta regra existe

Quando a mesa dispara todas as falas em cascata única ("Cadarn abre → Camy → Caio → Mozi → Coel → Logos → consolidação"), três coisas ruins acontecem:

1. **Fabiano perde o controle do ritmo.** A mesa avança sem ele, e quando chega o consolidado, já passou o ponto onde ele teria corrigido o rumo. Correções retroativas são mais caras que correções em tempo real.
2. **Qualidade e tokens são gastos em cima de pressupostos errados.** Se Fabiano discordaria da primeira âncora, todas as âncoras seguintes foram produzidas em cima de uma premissa que ele rejeita. O trabalho vira retrabalho.
3. **O raciocínio de Fabiano não entra na mesa.** O valor real de uma Távola não é a opinião dos agentes isolada — é a fricção entre a opinião dos agentes e o julgamento de Fabiano. Em cascata única, essa fricção é comprimida para o fim da sessão, quando já é tarde.

Turn-by-turn preserva a ergonomia real do modo como Fabiano pensa: **ouve uma voz → reage → ajusta → passa adiante**. É o ritmo natural de uma reunião de verdade, não de um relatório.

## Fluxo obrigatório

Cada turno corresponde a **1 spawn de subagente real** via Agent tool (modelo Conductor-Hub). O condutor NÃO fala pelo agente; ele spawna o agente como subagente isolado.

```
Condutor spawna Agente A via Agent tool
  (briefing: persona compactada + MEMORY.md + contexto + instrução)
    ↓
Agente A retorna contribuição (âncora, análise, proposta)
    ↓
Condutor apresenta o resultado a Fabiano
    ↓
[PAUSA] — mesa em standby
    ↓
Fabiano interage:
  - Pode concordar ("passa", "próximo", "avança", "pode seguir")
  - Pode corrigir ("volta pro A, preciso que ele reveja X")
  - Pode aprofundar ("A, me explica melhor Y antes de seguir")
  - Pode ignorar e redirecionar ("pula A, chama direto o C")
  - Pode pausar a mesa inteira ("segura a mesa, preciso pensar")
    ↓
Condutor recebe o sinal e decide:
  - Re-spawn Agente A com briefing ajustado se Fabiano pediu revisão
  - Spawn Agente B (próximo) se Fabiano bateu martelo
  - Pula para Agente C se Fabiano redirecionou
  - Segura a mesa em standby se Fabiano pediu pausa
    ↓
Próximo spawn (ou re-spawn do mesmo agente)
    ↓
[PAUSA] — novamente
    ↓
... e assim até fechar todos os turnos previstos no protocolo da Távola
```

**Regra de ouro:** até que Fabiano dê um gatilho explícito de passagem, a mesa fica em standby. Silêncio de Fabiano **não é** autorização para o próximo agente falar.

## Gatilhos de passagem de turno

Fabiano pode usar linguagem livre, mas o agente condutor deve reconhecer estes padrões como martelo de avanço:

| Intenção | Exemplos de gatilho |
|---|---|
| **Avançar para o próximo** | "passa", "próximo", "avança", "pode seguir", "segue a mesa", "pode chamar X" |
| **Voltar ao agente atual** | "volta pro A", "reformula", "me explica melhor", "não entendi", "tenta de novo" |
| **Pular agentes** | "pula A, chama C direto", "sem passar pelo A, vai pro B" |
| **Pausar a mesa** | "segura", "pausa", "espera", "deixa eu pensar", "antes de seguir eu quero falar" |
| **Encerrar a mesa** | "fecha a mesa", "chega", "já tenho o que precisava", "consolida" |

Se a instrução de Fabiano não se encaixar em nenhum desses padrões e a próxima ação estiver ambígua, o agente condutor **DEVE perguntar** ao invés de avançar. Avançar em dúvida = violação da regra.

## Aplicabilidade

| Tipo de Távola | Regra se aplica? | Observação |
|---|---|---|
| **Távola Nomeada** (ex: `/tavola-pipeline`) | ✅ Obrigatória | Todas as âncoras do protocolo são turn-by-turn |
| **Távola Magna** (`/tavola-magna`) | ✅ Obrigatória | Mais crítico ainda, porque são 6 squads em jogo |
| **Távola de Domínio** (`/squad-mkt:*` completa, `/forja`) | ✅ Obrigatória | Vale para convocação plena de uma squad |
| **Távola Cruzada** (2-3 squads efêmera) | ✅ Obrigatória | Protocolo explícito mesmo sendo efêmera |
| **Távola Express** (1-3 agentes efêmera) | 🟡 Recomendada | Conversacional por natureza, mas ajuda em sessões densas |
| **Fala de agente solo** (ex: `@dev` implementando) | ❌ Não se aplica | Regra é para mesa redonda, não para execução individual |
| **Mesa redonda informal** (sem skill ativa) | ✅ Obrigatória | Se há mais de 1 agente falando, vale a regra |

## Comportamento esperado do agente condutor

O **agente condutor** é quem opera como lead operacional da Távola (ex: Cadarn no `/tavola-pipeline`, Emrys na `/tavola-magna`, o líder de squad em Távolas de Domínio). No modelo Conductor-Hub, o condutor opera no contexto principal e **spawna subagentes reais** via Agent tool. É responsabilidade do condutor:

1. **Spawnar 1 agente por turno** via Agent tool, com briefing completo (persona + MEMORY.md + contexto + instrução). NUNCA falar pelo agente diretamente.
2. **Apresentar a contribuição do subagente** a Fabiano e anunciar a pausa. A estrutura da resposta deve deixar claro que a mesa parou.
3. **Não antecipar o próximo.** Depois de apresentar a fala de Camy, o condutor não pode escrever "o próximo é Caio, que provavelmente vai dizer X".
4. **Reconhecer gatilhos de passagem** conforme tabela acima.
5. **Re-spawnar com briefing ajustado** quando Fabiano pede revisão. O re-spawn inclui a correção/feedback de Fabiano no contexto.
6. **Pedir clarificação em dúvida** ao invés de avançar por suposição.
7. **Manter a memória do ponto da mesa.** Se Fabiano pausou na Camy e vai responder daqui a 2 horas, o condutor retoma exatamente na Camy.

## Anti-patterns

### ❌ ERRADO — Cascata única
```
Cadarn abre →
Camy fala →
Caio fala →
Mozi fala →
Coel fala →
Logos fala →
Consolidação →
"Você aprova?"
```
Isso é um **relatório**, não uma mesa redonda. Viola a regra.

### ❌ ERRADO — Antecipar o próximo
```
Camy: "Minha análise é X."
Condutor: "A próxima palavra é com Caio, que provavelmente vai focar em fechamento high-ticket."
```
Isso viola porque coloca expectativa no próximo sem que Fabiano tenha autorizado a passagem.

### ❌ ERRADO — Avançar no silêncio
```
Camy: "Minha análise é X."
[Fabiano não respondeu nada ainda]
Caio: "Vou comentar em cima da Camy..."
```
Silêncio não é martelo. Esperar.

### ❌ ERRADO — Condutor fala pelo agente (sem spawn)
```
Condutor: "Agora como Camy: minha análise é X."
```
Isso viola o modelo Conductor-Hub. O condutor deve spawnar Camy como subagente real via Agent tool.

### ✅ CERTO — Turn-by-turn com spawns reais
```
Condutor: "Abertura: tema, objetivo, output esperado.
           Fabiano, topa o escopo? Primeiro agente será Camy."

[PAUSA — aguarda Fabiano]

Fabiano: "Topo. Passa pra Camy."

Condutor: [spawna Camy via Agent tool com briefing completo]
Camy (subagente): "Minha âncora é: [análise]."
Condutor: "Camy respondeu: [apresenta a contribuição]. Fabiano?"

[PAUSA — aguarda Fabiano]

Fabiano: "Camy, volta. Não concordei com o item 2."

Condutor: [re-spawna Camy com feedback de Fabiano no briefing]
Camy (subagente): "Reformulando: [nova análise]."
Condutor: "Camy reformulou: [apresenta]. Fabiano?"

[PAUSA — aguarda Fabiano]

Fabiano: "Agora sim. Passa pro Caio."

Condutor: [spawna Caio via Agent tool]
...
```

## Exceções autorizadas

Existem situações em que a cascata é aceitável, mas todas exigem **autorização explícita prévia** de Fabiano na abertura da sessão:

1. **"Fabiano pede cascata":** Se Fabiano disser *"manda a mesa inteira de uma vez, depois eu reajo"*, a regra fica suspensa para aquela sessão específica.
2. **"Távola de consolidação":** Sessões cujo único objetivo é consolidar material já decidido em sessões anteriores (ex: fechar um arquivo formal). Nesses casos, o trabalho da mesa é sintetizar, não debater — cascata é eficiente.
3. **"Relato histórico":** Se Fabiano pedir *"me mostra o que a mesa decidiu na semana passada"*, isso é recuperação, não deliberação. Cascata aceita.

**Fora essas 3 exceções, turn-by-turn é o default absoluto.**

## Como Fabiano sinaliza a exceção

Linguagem natural serve, mas os padrões mais comuns:

- *"Manda a mesa inteira, depois eu reajo"*
- *"Cascata liberada"*
- *"Pode disparar tudo de uma vez"*
- *"Não precisa pausar entre as âncoras hoje"*

Se a autorização de exceção não foi dada, o default turn-by-turn está em vigor.

## Relação com outras regras

- **Complementa `tavolas-nomeadas.md`** — aquela define a estrutura da Távola (composição, protocolo), esta define **como** a fala flui dentro do protocolo
- **Complementa `orion-delegation.md`** — Emrys, ao convocar uma Távola, deve aplicar esta regra
- **Complementa `specialist-handoff-mandatory.md`** — quando um agente da mesa precisa passar o bastão para um especialista fora da mesa, o handoff também respeita turn-by-turn (Fabiano aprova a passagem)
- **Reforça feedback `feedback_one_question.md`** — o padrão de "uma pergunta por vez" é a versão conversacional desta regra em formato de mesa
- **Reforça feedback `feedback_squad_completa.md`** — todos os mandatórios falam, mas **em turnos**, não em rajada

## Severidade

**MUST** para Távolas Nomeadas, Magnas, de Domínio e Cruzadas.
**SHOULD** para Távolas Express (conversacional por natureza).

Violação em Távola Nomeada/Magna compromete o controle de Fabiano sobre o processo deliberativo e gera retrabalho. Emrys, quando presente, deve **interceptar** cascatas não autorizadas e reiniciar a mesa no primeiro ponto onde o turn-by-turn foi rompido.

## Governança

- **Autoridade:** Fabiano (criador da regra) + Emrys (enforcement)
- **Enforcement ativo:** Emrys monitora todas as Távolas e intercepta violações
- **Revisão:** Quando uma Távola for sentida como "pesada demais" ou "rápida demais" — indica que a regra precisa ser calibrada
- **Origem:** Sessão da Távola Pipeline em 2026-04-11 (primeira Wave da B3 "A Marca de Quem Chegou"), onde a cascata única foi identificada como anti-pattern pelo próprio Fabiano em tempo real

---

*Rule: tavola-turn-by-turn | Criada: 2026-04-11 | Atualizada: 2026-04-12 (Conductor-Hub: cada turno = 1 spawn via Agent tool) | Autor: Fabiano + Emrys | Severidade: MUST (Nomeadas/Magna/Domínio/Cruzada) / SHOULD (Express)*
