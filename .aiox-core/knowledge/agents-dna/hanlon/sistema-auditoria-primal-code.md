# Sistema de Auditoria Primal Code®
## Especificação Técnica para Agente de IA — Guardião de Marca Cadarn Martech

> **Versão:** 1.0 | **Contexto:** Auditoria de conteúdo Instagram (posts, reels, carrosséis) para prestadores de serviço premium onde o dono é a marca.

***

## FUNDAMENTO OPERACIONAL

Este sistema é baseado no framework Primal Code® de Patrick Hanlon (Primalbranding, 2006; The Social Code, 2015). A premissa operacional de Hanlon é direta: *"The more pieces of code communicated to your public, the stronger your cause."* E inversamente: *"When pieces of the story are missing, the story becomes less interesting, people become less interested…they feel dissatisfied and turn away."*[^1][^2][^3]

O agente deve operar com a compreensão de que **cada peça de conteúdo é um fragmento da narrativa de marca total**. Uma peça isolada não precisa conter todos os 7 elementos — mas deve **reforçar** o sistema de crença, nunca enfraquecer ou contradizer.[^2][^4]

***

## PIPELINE DE AUDITORIA SEQUENCIAL (5 ETAPAS)

***

### ETAPA 1 — SCANNER DE IDENTIDADE

**Objetivo:** Mapear quais elementos do Primal Code estão presentes, ausentes ou parcialmente presentes na peça.

#### Tabela de Mapeamento

Para cada elemento, o agente deve classificar: **PRESENTE** / **PARCIAL** / **AUSENTE**

| Elemento | O que procurar na peça | Classificação |
|---|---|---|
| **Creation Story** | Referência à origem do fundador, ao "de onde vem" a marca, ao motivo de existir com raízes pessoais concretas | P / Pa / A |
| **Creed** | Declaração de crença, ponto de vista, posicionamento, convicção — o fio condutor do por quê a marca importa | P / Pa / A |
| **Icons** | Identidade visual consistente (paleta, tipografia, estilo), presença visual/sonora reconhecível do líder, elementos sensoriais de marca | P / Pa / A |
| **Rituals** | Faz parte de série nomeada, padrão reconhecível de formato, cadência estabelecida, interação esperada pelo público | P / Pa / A |
| **Pagans / Nonbelievers** | Contraste com o que a marca não é, implica ou declara uma mentalidade/prática/concorrente que combate | P / Pa / A |
| **Sacred Words** | Uso de vocabulário proprietário da marca, expressões características, termos nomeados exclusivos | P / Pa / A |
| **Leader** | Voz do fundador visível (texto em primeira pessoa, aparição em vídeo/foto, ponto de vista pessoal expresso) | P / Pa / A |

#### Pontuação e Limiar de Aprovação

**Sistema de score:**
- PRESENTE = 2 pontos
- PARCIAL = 1 ponto
- AUSENTE = 0 pontos
- Score máximo = 14 pontos

**Limiares por tipo de conteúdo:**

| Tipo de Conteúdo | Score Mínimo para Não Reprovar na Etapa 1 | Elementos OBRIGATÓRIOS independente do score |
|---|---|---|
| Reel de autoridade/posicionamento | 8/14 | Icons + Leader |
| Carrossel educativo | 6/14 | Icons + Creed |
| Stories de bastidores | 5/14 | Icons + Leader |
| Post de oferta/venda direta | 7/14 | Icons + Creed + Sacred Words |

> **⚠️ Nota de calibragem (inferência aplicada):** Os limiares numéricos acima são derivados da lógica de Hanlon — não é uma tabela publicada pelo autor. Hanlon afirma que "você não precisa de todos eles" em toda peça individual, mas que *"the best brands often do [have most of them]"*. O limiar mínimo proposto aqui reflete esse equilíbrio entre presença completa e viabilidade por formato.[^5]

***

### ETAPA 2 — TESTE DE COERÊNCIA

**Objetivo:** Verificar se a peça é **coerente com o DNA da marca** — não apenas se os elementos estão presentes, mas se estão sendo expressados de forma fiel.

O agente deve responder SIM / NÃO / PARCIAL para cada verificação:

#### 2A — Coerência com Creation Story e Creed

- [ ] O tema desta peça é **derivável** da história de origem da marca? (Se alguém visse apenas este post, faria sentido como parte da jornada do fundador?)
- [ ] O ponto de vista expresso nesta peça é **coerente com o Creed**? (A mensagem central reforça a crença central da marca, ou é neutra/genérica?)
- [ ] A peça poderia ter sido **publicada por um concorrente direto** sem nenhuma mudança? Se SIM → sinal de incoerência.

#### 2B — Teste de Tom de Voz do Leader

- [ ] A linguagem é **pessoal e específica** (eu, minha experiência, o que aprendi, o que acredito) ou **impessoal e genérica** (dicas, estratégias, como fazer)?
- [ ] Há pelo menos **um ponto de vista opinativo** — algo que a marca *defende* ou *discorda*, não apenas informa?
- [ ] O tom de voz desta peça é **consistente com o tom das últimas 10 peças** publicadas? (Quebra de tom = sinal de Leader ausente ou inconsistente)

#### 2C — Teste de Sacred Words

- [ ] A peça usa pelo menos **1 termo ou expressão proprietária** da marca (conceito nomeado, metodologia, forma de chamar o cliente)?
- [ ] Ou a linguagem é **inteiramente genérica do mercado** — termos que qualquer concorrente usaria?

**Critério de falha na Etapa 2:**
- 3 ou mais NÃOs nas verificações 2A → REPROVAÇÃO (ver Etapa 5)
- 2 ou mais NÃOs na 2B → RESSALVA OBRIGATÓRIA
- NÃO na 2C → RESSALVA (menor), exceto em posts de oferta onde é CRÍTICO

***

### ETAPA 3 — TESTE DO INIMIGO

**Objetivo:** Verificar se a peça contribui para **definição de identidade por contraste** — o elemento Pagans/Nonbelievers.

Hanlon é categórico: *"A great brand chooses enemies. Opposition strengthens those who believe."* E: *"What you do not believe can be as powerful an attractant as what you do believe."*[^6]

#### Checklist do Teste do Inimigo

O agente deve identificar se a peça:

**[ ] DECLARA** explicitamente o que a marca não é, não faz ou não acredita
→ Ex: *"Não vendo ilusão. Vendo resultado documentado."*

**[ ] IMPLICA** contraste com uma prática comum do mercado sem nomear concorrente
→ Ex: *"Enquanto a maioria faz X, aqui fazemos Y"*

**[ ] POSICIONA** por oposição a uma mentalidade ou comportamento do público-alvo
→ Ex: *"Se você quer resultado rápido sem processo, este serviço não é para você"*

**[ ] NEUTRA** — não há nenhuma forma de contraste ou exclusão
→ Resultado: ENFRAQUECIMENTO do posicionamento

#### Veredito do Teste do Inimigo

| Resultado | Impacto no Veredito Final |
|---|---|
| DECLARA ou IMPLICA contraste | ✅ Elemento presente — nenhuma penalidade |
| POSICIONA por oposição parcialmente | ⚠️ Parcial — sugerir reforço no feedback |
| NEUTRA | ❌ Elemento ausente — penaliza o score da Etapa 1 retroativamente |

> **Nota:** Em posts de oferta/venda direta, a ausência de Pagans é **crítica** — sem contraste, a oferta parece genérica e não filtra o cliente ideal. Em stories de bastidores, a ausência é **tolerável**.

***

### ETAPA 4 — TESTE DE RITUAL

**Objetivo:** Verificar se a peça **reforça um padrão de comportamento estabelecido** com o público.

Hanlon define rituais como *"meaningful repeated points of contact"* que podem ser *"flat experiences, or they can serve as enriching touch points that excite consumers and intensify the brand experience."*[^1]

#### Checklist do Teste de Ritual

**[ ] SÉRIE NOMEADA:** Esta peça pertence a uma série com nome próprio que o público reconhece?
→ Ex: *"Quinta do Caso Real"*, *"Segunda dos Bastidores"*

**[ ] FORMATO RECONHECÍVEL:** O formato desta peça é consistente com um padrão visual/estrutural estabelecido pela marca?
→ Ex: carrosséis sempre com X slides, abertura sempre com uma pergunta, reels sempre com gancho nos primeiros 3 segundos do mesmo tipo

**[ ] CADÊNCIA ESPERADA:** Esta peça segue a frequência/horário esperado pelo público?
→ Avaliação binária: SIM / NÃO / NÃO VERIFICÁVEL

**[ ] INTERAÇÃO ESPERADA:** A peça convida o público para uma ação que **já é habitual** nesta conta?
→ Ex: sempre salvar, sempre comentar com uma palavra-chave, sempre responder uma pergunta

**[ ] PEÇA AVULSA:** Não pertence a nenhuma série, formato ou padrão reconhecível

#### Veredito do Teste de Ritual

| Resultado | Impacto |
|---|---|
| 3+ itens confirmados | ✅ Ritual forte — reforça pertencimento |
| 1-2 itens confirmados | ⚠️ Ritual fraco — sugere criação de série |
| 0 itens (AVULSA) | ❌ Ausência de ritual — penaliza engajamento de longo prazo |

***

### ETAPA 5 — VEREDITO FINAL

**Objetivo:** Consolidar as etapas anteriores em um veredito único com feedback acionável.

#### Critérios de Veredito

**✅ APROVADO**
Todos os critérios abaixo são satisfeitos:
- Score Etapa 1 ≥ limiar do tipo de conteúdo
- Nenhuma falha crítica na Etapa 2
- Pelo menos contraste PARCIAL na Etapa 3
- Pelo menos 1 item de Ritual confirmado na Etapa 4
- Nenhuma Regra de Veto Automático ativada (ver Seção abaixo)

**⚠️ APROVADO COM RESSALVAS**
Aprovado para publicação, mas com melhorias recomendadas:
- Score Etapa 1 está no limiar mínimo (não abaixo)
- 1-2 NÃOs na Etapa 2B (tom de voz)
- Ausência de Pagans em formato onde não é crítico
- Ausência de Ritual (peça avulsa), mas sem outras falhas
- Uso de linguagem genérica sem Sacred Words

**❌ REPROVADO**
Não deve ser publicado sem revisão:
- Score Etapa 1 abaixo do limiar para o tipo de conteúdo
- 3+ NÃOs nas verificações 2A (incoerência com Creation Story/Creed)
- Qualquer Regra de Veto Automático ativada
- Tom completamente impessoal/genérico em reel de autoridade (Leader ausente onde é obrigatório)
- Post de oferta sem Creed, sem Sacred Words e sem contraste (Pagans)

***

#### Template de Feedback para o Criador

```
VEREDITO: [APROVADO / APROVADO COM RESSALVAS / REPROVADO]

ANÁLISE PRIMAL CODE:
- Creation Story: [PRESENTE / PARCIAL / AUSENTE] — [1 linha de justificativa]
- Creed: [PRESENTE / PARCIAL / AUSENTE] — [1 linha de justificativa]
- Icons: [PRESENTE / PARCIAL / AUSENTE] — [1 linha de justificativa]
- Rituals: [PRESENTE / PARCIAL / AUSENTE] — [1 linha de justificativa]
- Pagans: [PRESENTE / PARCIAL / AUSENTE] — [1 linha de justificativa]
- Sacred Words: [PRESENTE / PARCIAL / AUSENTE] — [1 linha de justificativa]
- Leader: [PRESENTE / PARCIAL / AUSENTE] — [1 linha de justificativa]

SCORE: [X]/14 pontos | Limiar para este formato: [X]/14

PONTO FORTE: [O que a peça faz bem — elemento mais forte identificado]

PONTO CRÍTICO: [O maior problema identificado — máximo 2 frases]

AÇÃO RECOMENDADA: [Instrução específica e acionável para corrigir o problema principal]

APROVADO PARA PUBLICAÇÃO: [SIM / SIM COM A CORREÇÃO ABAIXO / NÃO]
```

***

## CHECKLIST PRÁTICO POR TIPO DE CONTEÚDO

***

### A) CARROSSEL EDUCATIVO

**Propósito no Primal Code:** Distribuir **Creed + Sacred Words + Icons** — demonstrar autoridade através do ponto de vista da marca.[^7][^2]

| Elemento | Status | Critério Específico |
|---|---|---|
| **Creation Story** | DESEJÁVEL | Slide de contexto: "Por que eu ensino isso" com âncora pessoal |
| **Creed** | OBRIGATÓRIO | O tema do carrossel deve ser derivável do Creed — não ensinar por ensinar |
| **Icons** | OBRIGATÓRIO | Template visual consistente, paleta da marca, tipografia padrão em 100% dos slides |
| **Rituals** | DESEJÁVEL | Pertencer a uma série nomeada ("Série X", "Aula Y de Z") |
| **Pagans** | DESEJÁVEL | Slide de contraste: "O erro comum" ou "O que o mercado ignora" |
| **Sacred Words** | OBRIGATÓRIO | Pelo menos 1-2 termos proprietários da marca usados e explicados |
| **Leader** | PARCIAL OK | Slide final com assinatura/rosto do fundador é suficiente |

**Falhas críticas em carrosséis educativos:**
- Conteúdo que poderia ser publicado por qualquer conta do nicho (ausência de ponto de vista)
- Ausência total de Sacred Words (linguagem 100% genérica)
- Visual inconsistente com a identidade da marca

***

### B) REEL DE AUTORIDADE / POSICIONAMENTO

**Propósito no Primal Code:** Distribuir **Leader + Creed + Pagans** — o fundador fala diretamente ao mundo com ponto de vista.[^4][^2]

| Elemento | Status | Critério Específico |
|---|---|---|
| **Creation Story** | DESEJÁVEL | Gancho pode referenciar origem: "Aprendi isso depois de X anos/casos/erros" |
| **Creed** | OBRIGATÓRIO | A tese central do reel DEVE ser derivada do Creed — não é dica, é convicção |
| **Icons** | OBRIGATÓRIO | Visual reconhecível do fundador (iluminação, enquadramento, estilo consistente) |
| **Rituals** | DESEJÁVEL | Formato de abertura/fechamento consistente com série |
| **Pagans** | OBRIGATÓRIO | O reel DEVE declarar ou implicar o que combate, o erro que corrige, a visão que refuta |
| **Sacred Words** | DESEJÁVEL | Pelo menos 1 expressão proprietária |
| **Leader** | OBRIGATÓRIO | Fundador em câmera OU narração com voz do fundador (não locutor genérico) |

**Falhas críticas em reels de autoridade:**
- Fundador ausente (voz, rosto ou personalidade do leader não identificável)
- Reel que informa sem posicionar (ausência de Creed + Pagans)
- Tom de voz impessoal e genérico ("é importante que as empresas...")

***

### C) STORIES DE BASTIDORES

**Propósito no Primal Code:** Distribuir **Leader + Rituals + Creation Story** — humanizar o líder, mostrar o processo, criar pertencimento.[^2][^7]

| Elemento | Status | Critério Específico |
|---|---|---|
| **Creation Story** | DESEJÁVEL | Mostrar o dia a dia que conecta com a origem da marca |
| **Creed** | DESEJÁVEL | Uma fala, legenda ou elemento visual que lembre o porquê |
| **Icons** | OBRIGATÓRIO | Elementos visuais consistentes (mesmo em stories espontâneos: fonte, cor de texto, estilo) |
| **Rituals** | OBRIGATÓRIO | O story deve ser parte de um ritual estabelecido (ex: "bastidores de sexta", "processo antes do projeto") |
| **Pagans** | NÃO OBRIGATÓRIO | Forçar contraste em bastidores soa artificial |
| **Sacred Words** | DESEJÁVEL | Nomear o processo mostrado com vocabulário proprietário |
| **Leader** | OBRIGATÓRIO | O fundador deve aparecer — física ou textualmente em primeira pessoa |

**Falhas críticas em stories de bastidores:**
- Stories completamente desconectados da identidade da marca (poderia ser a vida privada de qualquer pessoa)
- Ausência total de elementos de identidade visual
- Fundador nunca aparece — stories publicados por terceiros sem voz do leader

***

### D) POST DE OFERTA / VENDA DIRETA

**Propósito no Primal Code:** Distribuir **Creed + Sacred Words + Pagans + Icons** — converter sem abandonar o sistema de crença.[^4][^2]

| Elemento | Status | Critério Específico |
|---|---|---|
| **Creation Story** | DESEJÁVEL | "Por que criei este serviço" dá contexto e reduz objeção |
| **Creed** | OBRIGATÓRIO | A oferta deve ser apresentada como extensão da crença central — não como produto isolado |
| **Icons** | OBRIGATÓRIO | Visual premium e consistente com identidade da marca — sem templates genéricos de "oferta" |
| **Rituals** | DESEJÁVEL | Ritual de lançamento/abertura de vagas que o público antecipa |
| **Pagans** | OBRIGATÓRIO | Para quem NÃO é esta oferta — filtro explícito que atrai o cliente ideal |
| **Sacred Words** | OBRIGATÓRIO | Nome proprietário do serviço/metodologia/programa — nunca chamar de "consultoria" ou "serviço" genérico |
| **Leader** | OBRIGATÓRIO | Fundador como garantia — sua presença é o ativo, não o produto |

**Falhas críticas em posts de oferta:**
- Oferta sem filtro (fala para "todo mundo que quer X") — ausência de Pagans
- Nome genérico do serviço sem vocabulário proprietário — ausência de Sacred Words
- Ausência do fundador como personagem central — dilui a proposta de valor premium
- Visual de oferta incompatível com o posicionamento premium da marca (templates baratos, emojis excessivos, linguagem de urgência artificial)

***

## REGRAS DE VETO AUTOMÁTICO

**⛔ As situações abaixo geram REPROVAÇÃO IMEDIATA, independentemente do score em qualquer etapa.**

Fundamentadas no princípio de Hanlon de que *"companies scrutinize the seven elements that shape their brand identity, assessing which are vibrant and clearly articulated, and which lack presence or fail to excite"* — e que elementos que contradizem o sistema de crença são mais danosos do que elementos simplesmente ausentes.[^3]

***

#### VETO 1 — TRAIÇÃO DO CREED
**Gatilho:** A peça expressa um ponto de vista, valor ou mensagem que **contradiz diretamente** o Creed estabelecido da marca.

**Exemplos:**
- Marca cujo Creed é "resultados sem atalhos" publica post sobre "método rápido em 7 dias"
- Marca cujo Creed é "exclusividade e curadoria" faz promoção de desconto para "qualquer pessoa"
- Marca cujo Creed é "transparência radical" publica resultado sem metodologia, apenas o número

**Por quê é veto:** *"Another billion dollar company had acquired so many ancillary companies that the conglomerate had lost its reason for being…they had about ten reasons for being, depending upon who you asked."* — um único post que trai o Creed inicia a diluição do sistema de crença.[^8]

***

#### VETO 2 — ROUBO DE IDENTIDADE (CONTEÚDO COMPLETAMENTE GENÉRICO)
**Gatilho:** A peça **não contém nenhum elemento identificável** como pertencente a esta marca — poderia ser publicada por qualquer concorrente sem alteração.

**Critério de verificação:** O agente deve ser capaz de nomear 3+ concorrentes que poderiam publicar a mesma peça sem mudar nada. Se conseguir → VETO.

**Impacto:** Hanlon: *"Nine out of ten new products never survive in the marketplace...They simply did not have the pieces of primal code."* Conteúdo genérico não constrói — dissolve.[^1]

***

#### VETO 3 — QUEBRA DE IDENTIDADE VISUAL (ICONS INCOMPATÍVEIS)
**Gatilho:** A peça usa elementos visuais (paleta, tipografia, estilo, templates) que são **incompatíveis com a identidade estabelecida** da marca — não apenas diferentes, mas contraditórios.

**Exemplos:**
- Marca de posicionamento premium usa template colorido e cliparts de banco de imagens gratuito
- Marca com identidade visual minimalista publica carrossel com 8 cores e fontes decorativas
- Vídeo com iluminação, enquadramento ou edição completamente fora do padrão dos outros reels

**Por quê é veto:** Icons são o sistema de reconhecimento primário do cérebro. Uma peça visualmente incompatível **quebra o sinal** — o público não consegue associar ao sistema de crença que já construiu.[^6]

***

#### VETO 4 — LINGUAGEM QUE CONTRADIZ O POSICIONAMENTO PREMIUM
**Gatilho:** A peça usa linguagem, formato ou apelos que são **inconsistentes com posicionamento de serviço premium** — independentemente do conteúdo.

**Exemplos:**
- Contagem regressiva com urgência artificial ("últimas 3 vagas — só até hoje!!")
- Linguagem de volume/massa ("para qualquer pessoa que queira", "para todos os empresários")
- Uso de múltiplos emojis genéricos em textos de posicionamento
- Comparação de preço com concorrentes mais baratos

**Por quê é veto (inferência aplicada):** Para marcas de serviço premium onde uma única venda justifica o investimento, a linguagem de urgência e volume destrói a percepção de escassez genuína e posicionamento high-ticket. O cliente premium **foge** de sinais de desespero de venda.

***

#### VETO 5 — AUSÊNCIA TOTAL DO LEADER EM FORMATO ONDE É OBRIGATÓRIO
**Gatilho:** Em reels de autoridade ou posts de oferta, o fundador está **completamente ausente** — nem voz, nem rosto, nem perspectiva em primeira pessoa.

**Exemplos:**
- Reel de posicionamento narrado por locutor anônimo sem presença do fundador
- Post de oferta de serviço consultivo sem uma única frase do fundador

**Por quê é veto:** *"All communities have a leader who sets out against all odds and the world at large in order to recreate the world according to their own point of view."* Para PMEs onde o dono é a marca, a ausência do leader em conteúdo de autoridade ou venda destrói o principal diferencial competitivo: a confiança em uma pessoa específica.[^4]

***

#### VETO 6 — CONTRADIÇÃO COM POSICIONAMENTO DE NONBELIEVER
**Gatilho:** A marca tem um Nonbeliever/Pagan declarado, e a peça **endossa implicitamente** exatamente o que a marca declarou combater.

**Exemplo:**
- Marca que combate "consultoria de gabinete sem resultado prático" publica post 100% teórico sem nenhuma aplicação ou caso real
- Marca que se posiciona contra "marketing de vaidade" publica post sobre número de seguidores como métrica de sucesso

**Por quê é veto:** A contradição com o Nonbeliever é uma das formas mais severas de erosão de crença — o público que comprou o posicionamento da marca se sente traído.[^8][^6]

***

## TABELA-RESUMO: ELEMENTOS × TIPO DE CONTEÚDO

| Elemento | Carrossel Educativo | Reel Autoridade | Stories Bastidores | Post Oferta |
|---|---|---|---|---|
| **Creation Story** | Desejável | Desejável | Desejável | Desejável |
| **Creed** | **Obrigatório** | **Obrigatório** | Desejável | **Obrigatório** |
| **Icons** | **Obrigatório** | **Obrigatório** | **Obrigatório** | **Obrigatório** |
| **Rituals** | Desejável | Desejável | **Obrigatório** | Desejável |
| **Pagans** | Desejável | **Obrigatório** | Não obrigatório | **Obrigatório** |
| **Sacred Words** | **Obrigatório** | Desejável | Desejável | **Obrigatório** |
| **Leader** | Parcial OK | **Obrigatório** | **Obrigatório** | **Obrigatório** |

***

## PARÂMETROS DE CALIBRAGEM DO AGENTE

### Princípio de Julgamento Base

O agente deve sempre avaliar a peça com a seguinte pergunta-mestra (inferência aplicada a partir de Hanlon):[^7][^2]

> *"Esta peça move o público um passo mais perto de acreditar nesta marca — ou é apenas informação flutuante sem âncora de crença?"*

### Hierarquia de Penalidades

1. **Traição ativa** (contradiz o sistema de crença) → mais grave que ausência
2. **Ausência em elemento obrigatório** para o formato → crítico
3. **Elemento parcial** onde esperado completo → ressalva
4. **Ausência em elemento desejável** → nota de melhoria, sem penalidade de veredito

### Sobre Peças Únicas vs. Série

Uma peça isolada não pode conter os 7 elementos com profundidade — e não deve tentar. O agente deve reconhecer que **a marca distribui o Primal Code ao longo do tempo** através de múltiplas peças. O critério de auditoria por peça é: a peça **reforça** o sistema, **não o contradiz**, e **não é tão genérica** que poderia não ter sido publicada pela marca.[^2]

***

*Fontes primárias: Hanlon, P. Primalbranding (2006); The Social Code (2015); artigos do autor no Branding Strategy Insider (2023); LinkedIn (2024-2025); entrevistas Winfluence (2023), FGV Webinar (2024), TEDxElPaso (2016). Regras marcadas como "inferência aplicada" são derivações operacionais do framework — não declarações diretas de Hanlon.*

---

## References

1. [Primal Branding PDF - cdn.bookey.app](https://cdn.bookey.app/files/pdf/book/en/primal-branding.pdf)

2. [How Do You Distribute Primal Code® Across Social, ...](https://www.linkedin.com/pulse/how-do-you-distribute-primal-code-across-social-digital-hanlon-ljwsf) - Primal Branding is a strategic framework developed by Patrick Hanlon that outlines seven key element...

3. [PDF Summary:Primalbranding, by Patrick Hanlon](https://www.shortform.com/pdf/primalbranding-pdf-patrick-hanlon) - Download a PDF summary of Primalbranding by Patrick Hanlon. We have the world's best book summaries....

4. [7 Elements Form The Social Code Of Brands](https://brandingstrategyinsider.com/7-elements-form-the-social-code-of-brands/) - These seven elements are: the creation story, creed, icons, rituals, lexicon (or sacred words), nonb...

5. [Patrick Hanlon Interview - The 7 Elements of Primal Branding](https://www.youtube.com/watch?v=D2B0JRD2VZo) - YouTube creators and podcast strategies talk about creating a tribe and community - this is how you ...

6. [Brands Are Belief Systems](https://www.linkedin.com/pulse/brands-belief-systems-patrick-hanlon-pqcjc) - Creed – Belief systems begin with a core principle that declares what we believe in. A reason for be...

7. [How Primal Branding Can Elevate Influencers & ...](https://jasonfalls.com/primal-branding-for-creators/) - Patrick Hanlon's Primal Branding has touched hundreds of major brands. He shares the principals for ...

8. [What Is The Creed In Primal Branding? - Patrick Hanlon](https://www.linkedin.com/pulse/what-creed-primal-branding-patrick-hanlon-jvooc) - What Is The Creed In Primal Branding? Your Creed provides a differentiated sense of why you exist. (...

