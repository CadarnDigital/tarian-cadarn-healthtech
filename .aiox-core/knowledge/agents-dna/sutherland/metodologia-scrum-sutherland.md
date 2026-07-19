<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Especificação Técnica Modular: Metodologia Scrum de Jeff Sutherland


***

> **Nota de Integridade Documental:** Cada afirmação inclui a fonte primária. Conteúdo inferido de materiais públicos está sinalizado como `[inferência aplicada — fonte: X]`. Termos originais em inglês aparecem entre parênteses na primeira menção. Onde há diferença entre versões do *Scrum Guide*, isso é indicado explicitamente.

***

## 📘 MÓDULO 1 — Framework Scrum Segundo Sutherland (Fundamentos)

**Síntese para System Prompt:** Scrum, na visão de Jeff Sutherland, é um framework empírico que transforma a forma como equipes criam valor — baseado em três pilares (Transparência, Inspeção, Adaptação), cinco valores humanos e um conjunto mínimo de papéis, eventos e artefatos que funcionam como um sistema integrado. Cortar qualquer parte compromete o sistema inteiro.

***

### 1.1 Os 3 Pilares do Empirismo (*Empirical Process Control*)

Sutherland, como co-criador do Scrum, fundamenta o framework no que ele chama de **controle empírico de processo** (*empirical process control*): a ideia de que conhecimento vem da experiência e as decisões devem ser tomadas com base no que foi observado — não em planos. Os três pilares são interdependentes: sem Transparência, não há Inspeção genuína; sem Inspeção, não há Adaptação real.[^1][^2]


| Pilar | Como Sutherland Explica | Implicação Prática |
| :-- | :-- | :-- |
| **Transparência** (*Transparency*) | "Todos devem ver a mesma realidade" — boards visíveis, backlog público, impedimentos expostos | Sem transparência, os outros dois pilares ficam cegos [^1] |
| **Inspeção** (*Inspection*) | Revisão frequente do trabalho e do processo (não das pessoas) — Sprint Reviews e Retros são os mecanismos formais | Permite detectar desvios antes que virem crises [^1] |
| **Adaptação** (*Adaptation*) | Ajustar o plano imediatamente quando a inspeção revela problema | É a razão de existir de Sprints curtos — ciclos rápidos de feedback [^2] |


***

### 1.2 Os 5 Valores do Scrum

Introduzidos formalmente no *Scrum Guide* 2016 (incorporados de trabalhos anteriores de Sutherland) e mantidos no *Scrum Guide* 2020. Sutherland os trata como a "cola moral" que sustenta os pilares — sem eles, o framework vira processo vazio.[^3][^2]

1. **Commitment (Comprometimento):** O time se compromete com metas — *Sprint Goal*, não uma lista de tarefas. Compromisso com o objetivo, não com horas trabalhadas.
2. **Focus (Foco):** Durante o Sprint, o time foca *apenas* no que foi planejado. Sutherland é radical aqui: o Sprint é um container de foco.[^4]
3. **Openness (Abertura):** Compartilhar progresso, obstáculos e erros abertamente — mesmo quando é desconfortável.[^1]
4. **Respect (Respeito):** Cada membro do time tem competências distintas e contribuições igualmente válidas.[^1]
5. **Courage (Coragem):** Ter coragem de levantar impedimentos, questionar prioridades e dizer "não está pronto" em vez de simular entrega.[^3]

***

### 1.3 Os 3 Papéis do Scrum

> **Nota de versão:** O *Scrum Guide* 2020 substituiu "Development Team" + "Scrum Master" + "Product Owner" por um único termo — **Scrum Team** — com três *accountabilities*: Product Owner, Scrum Master e Developers. O termo "papel" (*role*) foi substituído por "responsabilidade" (*accountability*).[^2]


| Papel (*Accountability*) | Definição de Sutherland | Analogia Usada |
| :-- | :-- | :-- |
| **Product Owner (PO)** | "A voz do cliente dentro do time" — responsável por maximizar o valor do produto, ordenar o backlog e definir *o quê* será construído | Equivalente ao chefe de produto da Toyota no projeto Prius [^5] |
| **Scrum Master (SM)** | Não é gerente de projeto; é **servant-leader** — remove impedimentos, protege o time de interferências externas e ensina Scrum | Mais próximo de um "coach de processo" do que de um gerente [^5] |
| **Developers (Desenvolvedores)** | Auto-organizados, cross-funcionais — decidem *como* o trabalho será feito dentro do Sprint | Time de rugby que decide a tática no campo, sem microdireção do técnico [^5] |

**Analogia do Rugby (fonte primária do nome "Scrum"):** Sutherland inspirou o nome no artigo de Nonaka e Takeuchi de 1986 (*"The New New Product Development Game"*, Harvard Business Review), em que times de rugby avançam juntos como um bloco (*scrum*) em vez de cada jogador agir isoladamente — `[fonte: Sutherland, "Scrum: The Art of Doing Twice the Work in Half the Time", Cap. 1, 2014]`.

**Analogia do Fighter Pilot (OODA Loop):** Sutherland, ex-piloto de combate da Força Aérea dos EUA (*Top Gun*), usa o conceito de **OODA Loop** (Observar, Orientar, Decidir, Agir) do Coronel John Boyd como metáfora para ciclos de Sprint — quem itera mais rápido vence.[^5]

**Analogia Toyota / Lean:** Sutherland fundamenta o Scrum explicitamente nas pesquisas de Nonaka e Takeuchi sobre desenvolvimento de produto na Toyota, Honda e 3M — times cross-funcionais, metas transcendentes (*transcendent goals*), autonomia para decidir o *como*.[^5]

***

### 1.4 Os Eventos do Scrum

| Evento | Duração (para Sprint de 2 semanas) | Propósito Central |
| :-- | :-- | :-- |
| **Sprint Planning** | Máx. 4h | Definir *Sprint Goal* e selecionar itens do backlog — responde *por quê*, *o quê* e *como* [^2] |
| **Daily Scrum** (*Daily Stand-up*) | 15 minutos — sem exceção | Inspeção diária do progresso rumo ao *Sprint Goal* — não é reunião de status para gestores [^6] |
| **Sprint Review** | Máx. 2h | Demonstrar o *Increment* para stakeholders e adaptar o backlog com base no feedback [^2] |
| **Sprint Retrospective** | Máx. 1h30 | Inspecionar o *processo* do time e criar um plano de melhoria (Kaizen) para o próximo Sprint [^2] |

> **Posição de Sutherland sobre Retrospectivas:** A Retro é onde o Happiness Metric é aplicado. Sutherland chama de "arma secreta" (*secret weapon retro*) — times que fazem Retros bem implementadas reportaram crescimento de 400% de output no primeiro ano em que aplicaram a técnica.[^5]

***

### 1.5 Os Artefatos + *Definition of Done*

| Artefato | Comprometimento Associado (Scrum Guide 2020) | O que Sutherland Enfatiza |
| :-- | :-- | :-- |
| **Product Backlog** | *Product Goal* — a visão de longo prazo | O PO é responsável por maximizar valor, não por gerenciar horas [^5] |
| **Sprint Backlog** | *Sprint Goal* — o objetivo do Sprint | Time escolhe *como* fazer; gestores não interferem [^4] |
| **Increment** | *Definition of Done* | Deve ser utilizável/demonstrável ao final de cada Sprint — sem exceções [^5] |

**Definition of Done (*DoD*):** Para Sutherland, DoD é o contrato de qualidade do time — "Done = Releasable". Em seu infame alerta de 2014, Sutherland disse que **mais de 80% das equipes nas maiores empresas do Vale do Silício não tinham software funcional ao final do Sprint**, o que ele chamou de "Bad Agile" e "violação grave do Manifesto Ágil".[^7][^5]

***

### 1.6 Tamanho Ideal de Time

Sutherland cita a pesquisa de **J. Richard Hackman** e os estudos militares: o número mágico é **7 ± 2** (*seven plus or minus two*). Ele usa duas analogias:[^8]

- **Navy SEALs:** 4 pessoas é o tamanho ideal para equipes de combate — relações próximas, comunicação instantânea.[^9][^10]
- **Fire Teams militares:** O exército americano reduziu suas unidades básicas de 12 para 4 durante a II Guerra Mundial — grupos de 12 eram "uma turba incontrolável sob pressão".[^9]

**Para times de 3 pessoas (como o caso da agência):** `[inferência aplicada — fonte: Sutherland, "Scrum: The Art of Doing Twice the Work in Half the Time", Cap. 3, 2014]` — Sutherland não fala de times de 3 explicitamente como *sweet spot*, mas o *Scrum Guide* 2020 diz que times menores que 3 "carecem de habilidades e geram pouco valor" e maiores que 9 "geram coordenação excessiva". Um time de 3 é o limite inferior viável.[^2]

***

### 1.7 Velocidade (*Velocity*) e Previsibilidade

Velocity é a **média de story points entregues por Sprint** — não uma meta a ser maximizada, mas um **instrumento de previsibilidade**. Sutherland em 2014 usava velocity para calcular quando um backlog seria concluído: `data prevista = total de pontos no backlog ÷ velocity média`.[^4][^5]

> **Atualização 2025 (LinkedIn de Sutherland):** Sutherland postou que, com IA, "velocity deixou de medir apenas velocidade humana — o futuro é medir sistemas que fazem o trabalho" (*AI Points*). O Scrum Master passa a otimizar os *mecanismos* que aceleram o trabalho, não apenas o output das pessoas.[^11]

***

### ✅ Instruções para o Agente — Módulo 1

1. **Sempre pergunte qual é o *Sprint Goal* antes de qualquer conversa sobre tarefas** — sem objetivo claro, o Sprint vira uma lista de atividades sem direção.
2. **Não permita que o usuário confunda "Scrum Master" com "gerente de projeto"** — se alguém do time acumula o papel de SM, reforce que a função é de *coach* e remoção de impedimentos, não de controle.
3. **Exija *Definition of Done* explícita antes de iniciar qualquer Sprint** — pergunte: "O que significa 'pronto' para este item? Quando vocês saberiam que está realmente entregue?"
4. **Se o time tem 3 pessoas, sinalize que operam no limite mínimo do framework** — reforce a necessidade de cross-funcionalidade máxima e Sprints curtos (1 semana) para ciclos de feedback rápidos.
5. **Cite a origem das analogias** (rugby, Toyota, fighter pilot) quando explicar os princípios — Sutherland usa histórias para tornar conceitos abstratos concretos.

***

***

## 📗 MÓDULO 2 — Princípios de Sutherland para Times Pequenos

**Síntese para System Prompt:** Para Sutherland, times pequenos (3–7 pessoas) são superiores a times grandes — desde que sejam cross-funcionais, auto-organizados e protegidos de interferências externas. O segredo não é apenas o tamanho, mas a combinação de foco singular + autonomia real + melhoria contínua medida pelo *Happiness Metric*.

***

### 2.1 O *Sweet Spot* de 3–7 Pessoas

Sutherland argumenta que times grandes criam overhead de comunicação exponencial — o número de canais de comunicação numa equipe cresce segundo a fórmula $n(n-1)/2$ `[inferência aplicada — fonte: Sutherland, "Scrum: The Art of Doing Twice the Work in Half the Time", Cap. 3, 2014]`. Um time de 7 tem 21 canais; um time de 12 tem 66. A pesquisa de Hackman mostra que **a satisfação e produtividade caem drasticamente acima de 7–8 pessoas**.[^9]

Para times de 3 (como no caso da agência):

- Todos precisam ser **generalistas com especialidade profunda** (*T-shaped skills*)
- A auto-organização é natural — não há hierarquia para atrapalhar
- O risco é **sobrecarga** (*overload*) quando os 3 papéis principais (PO, SM, Dev) precisam ser distribuídos entre 3 pessoas `[inferência aplicada — fonte: Scrum Guide 2020, web:12]`

***

### 2.2 Auto-organização (*Self-Organizing Teams*)

Na visão de Sutherland, times auto-organizados são superiores porque **a inteligência coletiva supera qualquer gerente individual**. Ele cita o estudo de Nonaka e Takeuchi: os melhores times da Toyota não recebiam instruções de *como* fazer — recebiam um objetivo e autonomia total para decidir a execução.[^5]

**Na prática, auto-organização significa:**

1. O time decide quem pega qual item no Sprint Planning — não o gestor.
2. O Daily Scrum é do time, não do chefe — gestores não comparecem para cobrar status.
3. Impedimentos são levantados e resolvidos pelo próprio time sempre que possível.
4. A Retrospectiva é o espaço onde o time muda seus próprios processos — sem aprovação externa.

**Para o trio CEO/CRO/Especialista IA:** `[inferência aplicada — fonte: Scrum Guide 2020 + princípios de Sutherland, web:12][web:27]` A auto-organização num time de 3 exige que o CEO (mesmo sendo o "chefe" fora do Scrum) respeite as decisões técnicas do Especialista IA dentro do Sprint. A hierarquia organizacional deve ser suspensa dentro dos eventos Scrum.

***

### 2.3 "Twice the Work in Half the Time" — Os Multiplicadores

Sutherland documenta o seguinte no livro e entrevistas:[^12][^5]


| Multiplicador | Mecanismo | Fonte |
| :-- | :-- | :-- |
| **Foco singular** | Um time trabalhando 1 projeto > vários times em múltiplos projetos | Cap. 5, "Scrum: The Art of Doing Twice..." (2014) |
| **Eliminação de context-switching** | Cada troca de contexto custa ~23 min de foco — multitasking destrói produtividade [^13] | Cap. 5, ibid. |
| **Feedback loop curto** | Sprints de 1–2 semanas eliminam meses de trabalho na direção errada | Cap. 4, ibid. |
| **Kaizen no topo do backlog** | A melhoria de processo identificada na Retro vira item prioritário no próximo Sprint | InfoQ interview [^5] |
| **Happiness → Performance** | Times felizes são mais produtivos — causalidade demonstrada em pesquisas de Gallup | Sites.google.com/scrumplop.org [^14] |
| **Product Owner medido por valor** | Sutherland mede POs por "receita por ponto de velocity" — incentivo de valor, não de velocidade vazia | InfoQ interview [^5] |

**Resultado reportado por Sutherland:** Time da Scrum Inc. atingiu **400% de crescimento de output em 1 ano** combinando Kaizen na Retro + Happiness Metric.[^5]

***

### 2.4 *Happiness Metric* — A Métrica de Satisfação

Sutherland introduz o *Happiness Metric* no livro como uma das suas "armas secretas" de Retrospectiva. A lógica é baseada em pesquisas de Harvard e Gallup: **felicidade no presente prediz performance futura**.[^14][^15]

**Protocolo do Happiness Metric (conforme Sutherland/Scrum Inc.):**

> *"Como eu me sinto em relação ao meu trabalho, numa escala de 1 a 5? O que tornaria meu próximo Sprint melhor?"*[^15][^5]

**Regras de aplicação:**

1. Feita na *Sprint Retrospective*, antes de qualquer análise de processo.
2. Cada pessoa responde individualmente — sem pressão de grupo.
3. O time identifica **uma única ação** que aumentaria a felicidade no próximo Sprint.
4. Essa ação vira o **Kaizen** — item prioritário no topo do *Sprint Backlog*.[^5]

> **Pesquisa de suporte (Gallup):** Estudo com 2.178 unidades de negócio em 10 grandes organizações mostrou que percepções dos colaboradores têm impacto causal em métricas de negócio como fidelização de clientes, retenção de talentos, receita e lucro.[^14]

***

### 2.5 Sprints Curtos vs. Longos

| Duração | Contexto Recomendado | Riscos |
| :-- | :-- | :-- |
| **1 semana** | Times novos em Scrum, projetos com alta incerteza, equipes pequenas | Overhead de cerimonial pode ser alto se não agilizado |
| **2 semanas** | Sweet spot para a maioria dos times — equilíbrio entre velocidade e profundidade | `[inferência aplicada — Scrum Guide 2020]` |
| **3–4 semanas** | Times experientes com backlog bem refinado | Perde a vantagem de feedback rápido; Sutherland não recomenda para times pequenos |

**Posição de Sutherland:** Sprints mais curtos = aprendizado mais rápido. Para times iniciantes, ele recomenda começar com **1 semana** para criar o hábito de inspecionar e adaptar  `[inferência aplicada — fonte: múltiplas entrevistas e apresentações de Sutherland]`.[^6]

***

### 2.6 Acúmulo de Múltiplos Papéis

O *Scrum Guide* 2020 reconhece explicitamente que os 3 *accountabilities* (PO, SM, Developers) **podem ser acumulados por uma mesma pessoa em times pequenos**, mas **alerta para os conflitos de interesse**.[^2]

**Conflito mais comum (e mais perigoso):** PO + SM na mesma pessoa. O PO quer maximizar o que é entregue; o SM protege o time de sobrecarga. Quando são a mesma pessoa, o time frequentemente aceita mais trabalho do que pode fazer.[^2]

**Para o trio CEO/CRO/Especialista IA** `[inferência aplicada — baseado em princípios do Scrum Guide 2020 + Sutherland, web:12][web:27]`:


| Pessoa | Papel Primário | Papel Secundário | Conflito a Monitorar |
| :-- | :-- | :-- | :-- |
| **CEO** | Product Owner (visão, backlog, priorização) | Parcial SM (facilitação) | Tendência de comando: respeitar autonomia técnica |
| **CRO** | Developer (estratégia comercial, go-to-market) | Co-PO para backlog de clientes | Urgências de clientes que contaminam o Sprint |
| **Especialista IA** | Developer (execução técnica) | Arquiteto de produto | Tendência de super-comprometimento técnico |


***

### 2.7 Rituais Mínimos Viáveis — O que NÃO Cortar

Mesmo num time de 3, Sutherland é claro: **não existe "Scrum light" legítimo**. O que pode ser adaptado é a *duração* dos eventos, não a *existência* deles.[^16]

**O que é inegociável:**

1. ✅ **Sprint com duração fixa** — mesmo que seja 1 semana, o timebox é sagrado.
2. ✅ **Daily Scrum de 15 min** — Sutherland diz que esta foi a primeira prática que implementou em 1993, inspirada em pesquisas sobre neurociência de frequência de feedback.[^17]
3. ✅ **Sprint Review com demonstração real** — não slides, não relatórios: produto funcionando (ou entregável utilizável).[^5]
4. ✅ **Sprint Retrospective com Happiness Metric** — o motor de melhoria contínua.[^5]
5. ✅ **Definition of Done** — sem ela, nada está "pronto" de verdade.[^4]

**O que pode ser comprimido num time de 3:**

- Sprint Planning pode durar 1h (em vez de 4h) se o backlog estiver bem refinado.
- Backlog Refinement pode ser integrado ao Planning em times pequenos `[inferência aplicada — Scrum Guide 2020, web:12]`.

***

### ✅ Instruções para o Agente — Módulo 2

1. **Quando o usuário disser "somos apenas 3, não temos tempo para cerimônias"** — responda que Sutherland mostrou que a *ausência* de rituais cria mais retrabalho e reuniões informais do que os rituais em si. Peça para cronometrar um Sprint sem os eventos e comparar.
2. **Inicie toda Retrospectiva com o Happiness Metric** — pergunta literal: "De 1 a 5, como você se sente sobre seu trabalho agora? O que tornaria o próximo Sprint melhor para você?"
3. **Sempre que houver acúmulo de papéis, nomeie explicitamente qual papel a pessoa está exercendo em cada momento** — "Agora você está falando como Product Owner ou como Developer?"
4. **Proteja o Sprint de urgências externas** — se uma demanda chegar no meio do Sprint, pergunte: "Isso é tão urgente que justifica cancelar o Sprint atual? Se não, vai para o backlog."
5. **Meça velocity a partir do 2º Sprint** — nos primeiros 2 Sprints, o foco é calibrar o ritmo, não bater metas.

***

***

## 📕 MÓDULO 3 — Anti-Patterns e Erros Graves

**Síntese para System Prompt:** Sutherland identifica padrões de falha recorrentes que destroem o Scrum silenciosamente. O mais perigoso é o "Scrum de fachada" — equipes que executam os rituais sem os princípios. O segundo mais perigoso é a interferência gerencial que destrói a auto-organização. O terceiro é o multitasking, que Sutherland trata com linguagem de combate.

***

### 3.1 *Waterfall* Disfarçado de Scrum

Sutherland descreve o "waterfall em disfarce" (*waterfall in disguise*) como o anti-padrão mais comum: o time usa Sprints como "mini-fases" do waterfall — um Sprint para requisitos, outro para design, outro para desenvolvimento.[^12]

**Como identificar:**

- O Sprint não termina com um *Increment* utilizável — só com documentos ou wireframes.
- O backlog tem itens como "Fase 1: Levantamento" e "Fase 2: Desenvolvimento".
- Não existe *Definition of Done* com critério de aceite funcional.
- A *Sprint Review* vira apresentação de PowerPoint, não demonstração.

**Frase de Sutherland (InfoQ, 2014):** "Mais de 80% dos times nas maiores empresas do Vale do Silício não tinham software funcional ao final do Sprint. Isso não é Scrum. É Bad Agile."[^5]

***

### 3.2 Command \& Control vs. Servant-Leadership

O Scrum Master não gerencia — ele serve. Quando gestores assumem a Daily Scrum como reunião de status, eles destroem o pilar da auto-organização. Sutherland usa a analogia do **técnico de rugby que dá orientações táticas no intervalo, mas não entra em campo**.[^5]

**Comportamentos de command \& control que invalidam o Scrum:**

- Gestor atribui tarefas individualmente no Planning (em vez de o time auto-organizar).
- Daily Scrum vira prestação de contas ao gerente ("o que você fez ontem?").
- Sprint Goal é alterado pelo gestor no meio do Sprint.
- Retrospectiva é supervisionada por alguém de fora do time.

***

### 3.3 Sprint sem *Definition of Done* Clara

Sutherland é direto: **sem DoD, "Done" não existe — existe "quase done"**, que é infinitamente pior do que trabalho não iniciado. Trabalho "quase pronto" acumula dívida técnica (ou criativa) invisível e mascara o real progresso.[^7][^4]

**Para o contexto da agência martech**, a ausência de DoD é especialmente perigosa porque "pronto" pode significar coisas diferentes para o time interno e para o cliente.

***

### 3.4 Planning sem Estimativa

Sutherland defende o uso de **story points** e **Planning Poker** (*Estimation Poker*) como ferramenta de **alinhamento de entendimento**, não de controle gerencial `[inferência aplicada — fonte: Sutherland, "Scrum: The Art of Doing Twice the Work in Half the Time", Cap. 6, 2014]`.

**O ponto central:** Quando pessoas divergem na estimativa (ex.: alguém dá 3 pontos e outra pessoa dá 13), a divergência revela **falta de entendimento compartilhado do item** — e é isso que o Planning Poker explicita. A estimativa absoluta importa menos do que o **debate gerado pelas divergências**.

**Posição de Sutherland sobre *No Estimates*:** Sutherland não apoia a corrente "*\#noestimates*" — para ele, estimativas (mesmo imperfeitas) são necessárias para previsibilidade e para o PO tomar decisões de priorização baseadas em valor/esforço.[^4]

***

### 3.5 Retrospectivas Ignoradas ou Superficiais

Sutherland é enfático: **a Retro é o único evento que melhora os outros eventos**. Times que pulam a Retro ficam presos nos mesmos problemas indefinidamente — sem mecanismo de melhoria sistêmica.[^5]

**Anti-patterns na Retro:**

- Retro vira sessão de reclamações sem ação concreta.
- Sem Kaizen no topo do backlog — a melhoria fica no papel.
- Retro realizada somente quando "tem tempo" (i.e., raramente).
- Sem o Happiness Metric, perde-se o diagnóstico emocional do time.[^15]

***

### 3.6 Multitasking — A Posição Radical de Sutherland

Sutherland dedica um capítulo inteiro ao anti-padrão do multitasking no livro. A posição dele é baseada em pesquisa de neurociência:[^13]

> *"Tudo bem, Sutherland — mas eu dirijo uma empresa. Tenho equipes trabalhando em cinco projetos simultâneos. Não tenho condições de fazer diferente."* — frase que Sutherland usa para representar o argumento típico, antes de demolí-lo com dados.[^13]

**Os dados que Sutherland cita:**


| Projetos Simultâneos | Tempo Perdido em Context-Switching | Tempo Produtivo Real |
| :-- | :-- | :-- |
| 1 | 0% | 100% |
| 2 | ~20% | ~80% por projeto |
| 3 | ~40% | ~60% por projeto |
| 5 | ~75% | ~25% por projeto |

`[Fonte: Sutherland, "Scrum: The Art of Doing Twice the Work in Half the Time", Cap. 5, 2014 — baseado em pesquisas de Gerald Weinberg sobre context-switching]`

**Para o trio CEO/CRO/Especialista IA:** O maior risco de multitasking não é entre Sprints — é *dentro* do Sprint, quando a CRO tenta responder urgências de clientes enquanto deveria estar executando itens comprometidos. O Sprint é o "container de foco".[^4]

***

### 3.7 *ScrumBut* — Times que Fingem Usar Scrum

O termo *ScrumBut* foi definido formalmente no Scrum.org (co-fundado por Schwaber, que co-criou o Scrum com Sutherland): "Usamos Scrum, **mas** [desculpa], então [adaptação que invalida o princípio]".[^16]

**Exemplos de ScrumBut em agências:**


| ScrumBut | Problema Real Mascarado |
| :-- | :-- |
| "Usamos Scrum, **mas** nossos Sprints são de 6 semanas porque clientes demandam muito" | Falta de proteção do Sprint; backlog mal gerenciado |
| "Usamos Scrum, **mas** pulamos a Retro quando estamos com pressa" | Time que nunca melhora seus próprios processos |
| "Usamos Scrum, **mas** o CEO define as tarefas no Daily" | Ausência de auto-organização; Scrum de fachada |
| "Usamos Scrum, **mas** não definimos DoD para entregas criativas" | "Done" arbitrário; retrabalho invisível |
| "Usamos Scrum, **mas** o backlog é confidencial para o cliente" | Falta de Transparência — pilar fundamental destruído |

**Scrum.org sobre ScrumBut:** "ScrumButs significam que o Scrum expôs uma disfunção que contribui para o problema, mas é muito difícil de corrigir. O ScrumBut retém o problema enquanto modifica o Scrum para torná-lo invisível."[^16]

***

### ✅ Instruções para o Agente — Módulo 3

1. **Quando o usuário disser "nosso Sprint não termina com entrega utilizável"** — identifique imediatamente se é waterfall disfarçado. Pergunte: "O que exatamente vocês entregam ao final do Sprint? Um cliente poderia usar isso hoje?"
2. **Quando o CEO/gestor estiver dominando as decisões técnicas dentro do Sprint** — sinalize o anti-pattern de command \& control. Use a analogia do técnico de rugby: "Você define o objetivo (Sprint Goal), o time define o caminho."
3. **Quando alguém disser "não temos tempo para Retrospectiva"** — responda: "A Retrospectiva é a única reunião que economiza tempo em todas as outras. Pular a Retro é como não parar para afiar o machado porque está muito ocupado cortando lenha."
4. **Identifique ScrumButs ativamente** — quando o usuário descrever seu processo, mapeie os elementos que estão sendo pulados e nomeie como ScrumBut. Não use o termo de forma pejorativa — use como diagnóstico.
5. **Sobre multitasking:** Se a agência está gerenciando múltiplos clientes com o mesmo time de 3, alerte sobre o custo de context-switching. Pergunte: "Quantos clientes ativos existem simultaneamente? Cada Sprint tem foco em quais clientes?"

***

***

## 📙 MÓDULO 4 — Scrum Aplicado a Martech e Agências (Não-Software)

**Síntese para System Prompt:** Sutherland sempre defendeu que o Scrum não é exclusivo de software — ele foi usado em equipes de jornalismo (NPR/Arab Spring), educação, marketing, finanças e governo. Para agências de martech, os princípios são os mesmos; o que muda é a *definição de "Increment"* e a *Definition of Done* para entregas criativas e de serviço.

***

### 4.1 Scrum Fora do Software — Posição de Sutherland

Sutherland escreveu o livro de 2014 explicitamente para **não-desenvolvedores** — seu editor do Random House exigiu que menos de 20% dos exemplos fossem de TI. Os exemplos não-software que ele usa:[^5]

- **NPR/Arab Spring (2011):** Seu filho liderou cobertura jornalística do Cairo com 2 Daily Scrums por dia — o time venceu todos os prêmios principais de jornalismo daquele ano.[^5]
- **EduScrum (Holanda):** Estudantes de química usando Scrum — aprendizado 40% mais rápido que turmas tradicionais, com "Definition of Fun" além de "Definition of Done".[^5]
- **OpenView Venture Partners:** Fundo de venture capital usando Scrum em *todos* os departamentos (marketing, finanças, vendas) — "3x mais trabalho em 1/3 do tempo".[^5]
- **Marketing e vendas:** Sutherland menciona explicitamente que incentivou governos, marketing, finanças e vendas a usarem Scrum por mais de uma década.[^5]

***

### 4.2 Adaptando "*Increment*" para Entregas Não-Código

O *Scrum Guide* 2020 define Increment como "um passo concreto em direção ao *Product Goal*" — deve ser "utilizável" ao final de cada Sprint. Para agências, "utilizável" precisa ser redefinido por tipo de entrega:[^2]


| Tipo de Entrega | O que significa "Increment utilizável" |
| :-- | :-- |
| **Campanha digital** | Campanha ao ar (ou em aprovação final do cliente) com métricas de rastreamento ativas |
| **Conteúdo/Copy** | Conteúdo publicado ou aprovado pelo cliente para publicação imediata |
| **Automação/Bot** | Funcionalidade em ambiente de staging testada e pronta para go-live |
| **Design/Landing page** | Versão aprovada pelo cliente, responsiva, com todos os elementos finais |
| **Relatório estratégico** | Documento entregue, apresentado ao cliente e com plano de ação definido |
| **Campanha para imobiliária** | Anúncios no ar, landing page ativa, CRM integrado com leads chegando |
| **Conteúdo para clínica de estética** | Posts aprovados pela dermatologista, conformes com CFM, agendados na ferramenta |
| **Material para escritório de advocacia** | Conteúdo revisado por advogado responsável, dentro das normas da OAB |

`[Inferência aplicada — baseado em: Wrike/DoD para marketing, web:21; Berriault and Associates, web:24; princípios do Scrum Guide 2020, web:12]`

***

### 4.3 *Definition of Done* para Entregas Criativas

Para entregas criativas, a DoD deve incluir **critérios de qualidade + critérios de aprovação + critérios de conformidade**. Exemplo para agência martech:[^18]

**DoD para campanha de performance (imobiliária):**

1. ✅ Briefing do cliente documentado e aprovado
2. ✅ Copies testados com variantes A/B
3. ✅ Design alinhado com identidade visual do cliente
4. ✅ Rastreamento (UTM, pixel) configurado e testado
5. ✅ Budget aprovado e campanhas ativas
6. ✅ Dashboard de métricas acessível ao cliente
7. ✅ Aprovação formal do cliente registrada (e-mail ou sistema)

**DoD para conteúdo jurídico (escritório de advocacia):**

1. ✅ Revisado pelo advogado responsável pela área
2. ✅ Sem afirmações que configurem publicidade vedada pela OAB
3. ✅ Fonte/referência legal citada quando necessário
4. ✅ Aprovação escrita do sócio responsável registrada

`[Inferência aplicada — baseado em: Berriault and Associates, web:24; Wrike DoD para marketing, web:21]`

***

### 4.4 Backlog Misto: Entregas Técnicas + Criativas no Mesmo Sprint

Um dos maiores desafios de uma agência martech é ter itens de natureza completamente diferente no mesmo backlog — automações técnicas (alto esforço, baixa frequência) e entregas criativas (menor esforço individual, alta cadência).

**Recomendação de estrutura** `[inferência aplicada — baseado em Scrum Guide 2020 + práticas de agências ágeis]`:


| Dimensão | Recomendação |
| :-- | :-- |
| **Backlog único ou separado?** | Um backlog por cliente com *Product Goal* específico — mas um *Sprint Backlog* unificado do time priorizado pelo valor total |
| **Estimativa** | Story points por complexidade — uma automação de alto esforço pode valer 8 pontos; um post de Instagram bem estruturado vale 1 ponto |
| **Definition of Done** | DoD *por tipo de item*, não global — crie categorias: DoD-Técnico, DoD-Criativo, DoD-Estratégico |
| **Sprint Goal** | Mínimo 1 Sprint Goal por Sprint que conecte as entregas mistas num tema coerente (ex.: "Lançar campanha de captação para [cliente X] com automação de qualificação de leads") |
| **Priorização** | Ordenar por impacto esperado de negócio — não por urgência do cliente |


***

### 4.5 Gestão de Múltiplos Clientes no Scrum

Este é o ponto mais crítico e menos documentado diretamente por Sutherland para o contexto de agências. A seguir, síntese baseada nos princípios do Scrum@Scale (de Sutherland, 2020) e na lógica do framework `[inferência aplicada — Scrum@Scale Guide, web:22; Scrum Guide 2020, web:12]`:

**Opção A — Backlog por Cliente (mais simples, recomendado para até 3–4 clientes ativos):**

- Cada cliente tem seu *Product Backlog* com seu *Product Goal*
- O CEO/PO mantém uma **lista mestre de prioridades inter-clientes** para decisão de alocação de Sprint
- O Sprint Planning começa com a pergunta: "Qual cliente gera mais valor esta semana?"
- Risco: fragmentação de foco — o time pode saltar entre contextos de cliente

**Opção B — Backlog Unificado (recomendado quando os clientes compartilham natureza similar):**

- Um único backlog com itens marcados por cliente/projeto
- O PO (CEO) é responsável por ordenar itens de diferentes clientes com base em impacto de negócio total
- A Scrum@Scale usa o conceito de **MetaScrum** para coordenação de múltiplos backlogs[^19]
- Risco: PO sobrecarregado; decisões de priorização politicamente complexas

**Proteção do Sprint contra demandas urgentes de clientes:**


| Situação | Resposta Scrum |
| :-- | :-- |
| Cliente pede algo urgente no dia 3 do Sprint | Registrar no backlog; avaliar no próximo Sprint Planning |
| Urgência que ameaça relação comercial crítica | Conversar com o time: justifica cancelar o Sprint? Se sim, cancelar formalmente e replanejar |
| Urgências recorrentes do mesmo cliente | Reservar capacidade no Sprint para "buffer de demandas urgentes" (ex.: 20% da velocity) |
| Cliente com demandas conflitantes entre si | PO decide com base em critério explícito (receita, LTV, prazo contratual) — documentado no backlog |

`[Inferência aplicada — baseado em Scrum Guide 2020, web:12; Scrum@Scale Guide, web:22; princípios de Sutherland sobre Product Owner, web:27]`

***

### 4.6 Duração de Sprint para Agências

Para contextos de agência com múltiplos clientes e entregas mistas, **Sprints de 1 semana** apresentam vantagens específicas `[inferência aplicada — princípios de Sutherland sobre Sprints curtos, web:5]`:

**Prós de Sprint de 1 semana para agência:**

- Ciclo de aprovação de cliente cabe dentro do Sprint
- Urgências de clientes têm menos tempo para acumular antes da próxima janela de priorização
- Retrospectivas semanais criam melhoria contínua mais rápida
- Menor impacto quando um cliente muda de direção

**Contras:**

- Overhead de cerimonial pode ser alto (Planning + Retro toda semana)
- Itens técnicos complexos (automações, integrações) podem não caber num Sprint de 1 semana

**Solução híbrida** `[inferência aplicada]`: Sprint de **2 semanas** com **mini-check-in no Day 5** (não é um evento formal — é uma inspeção informal de progresso). Reservar **os primeiros 2 dias do Sprint** para entregas criativas (menor incerteza) e os **últimos 3 dias** para revisão, integração e entrega.

***

### 4.7 Exemplos por Nicho

**Imobiliária:**

- *Sprint Goal* típico: "Gerar 20 leads qualificados para imóveis de alto padrão no bairro X via campanha de performance + automação de follow-up"
- *DoD*: Campanha no ar, automação testada com lead fictício, dashboard acessível ao corretor
- Risco Scrum: Urgência de "fechar um anúncio agora" que quebra o Sprint toda semana

**Clínica de Estética Avançada:**

- *Sprint Goal* típico: "Lançar campanha de captação para procedimento Y com conteúdo educativo aprovado pela diretora médica"
- *DoD*: Conteúdo revisado pela médica, dentro das normas CFM, publicado e com pixel ativo
- Risco Scrum: Aprovação médica como gargalo — incluir a médica como stakeholder do Sprint Review

**Escritório de Advocacia:**

- *Sprint Goal* típico: "Publicar 4 conteúdos de autoridade em direito tributário aprovados pela banca + 1 campanha de captação de consultas"
- *DoD*: Revisão jurídica aprovada, sem violação OAB, publicado com CTA para consulta agendada
- Risco Scrum: Advogados não têm tempo para Sprint Reviews — agendar revisões assíncronas com deadline dentro do Sprint

`[Inferência aplicada — baseado em princípios do Scrum Guide 2020 + adaptações de DoD para serviços profissionais, web:24][web:21]`

***

### ✅ Instruções para o Agente — Módulo 4

1. **Para cada novo cliente da agência, defina um *Product Goal* explícito** — "O que este cliente quer alcançar nos próximos 3 meses? Essa é a estrela-guia para priorização do backlog dele."
2. **Nunca aceite "pronto" sem verificar os critérios da DoD correspondente ao tipo de entrega** — pergunte: "Isso é uma entrega técnica ou criativa? Qual é a DoD para este tipo?"
3. **Quando o cliente pedir algo urgente no meio do Sprint** — ensine a resposta padrão: "Anotamos no backlog. Na próxima Sprint Planning (em X dias), avaliamos se entra como prioridade máxima. Se for uma emergência que ameaça o negócio do cliente, podemos discutir cancelar o Sprint atual — mas isso é exceção, não regra."
4. **Quando houver conflito de prioridade entre clientes** — peça ao CEO/PO para aplicar critério explícito: "Qual cliente gera mais impacto de negócio para a agência esta semana? Documente o critério para que a equipe entenda a lógica."
5. **Adapte o Definition of Done por nicho** — não use uma DoD genérica. Pergunte: "Este conteúdo precisa de aprovação da médica/advogada/arquiteta antes de ser publicado? Isso está na DoD?"
6. **Para entregas técnicas e criativas no mesmo Sprint** — use o Sprint Goal como "cola temática" que conecta os dois tipos de entrega num objetivo de negócio único.

***

***

## 📊 Tabela-Resumo: Mapeamento de Papéis Scrum → Trio da Agência

| Accountability Scrum | Quem no Trio | Responsabilidades Chave | Conflitos a Monitorar |
| :-- | :-- | :-- | :-- |
| **Product Owner** | CEO | Backlog, priorização, Sprint Goal, relacionamento com clientes | Tendência de micro-gerir execução técnica |
| **Scrum Master** | CEO (parcial) + Rotativo | Facilitar eventos, remover impedimentos, proteger o time | CEO como SM + PO = risco de sobrecarga de Sprint |
| **Developers** | CEO + CRO + Especialista IA | Executar itens do Sprint, auto-organizar o *how*, participar do Planning | CRO respondendo urgências de clientes durante o Sprint |

`[Inferência aplicada — baseado em Scrum Guide 2020, web:12 + InfoQ interview Sutherland, web:27]`

***

## 📚 Referências Primárias Utilizadas

| Fonte | Tipo | Cobertura Neste Documento |
| :-- | :-- | :-- |
| Sutherland, J. (2014). *Scrum: The Art of Doing Twice the Work in Half the Time*. Crown Business | Livro primário | Módulos 1, 2, 3 (todos os princípios fundamentais) |
| *The 2020 Scrum Guide* — Sutherland \& Schwaber. scrumguides.org | Guia oficial | Módulos 1, 2, 4 (papéis, eventos, artefatos, DoD) |
| InfoQ Interview with Jeff Sutherland (Nov. 2014) — infoq.com | Entrevista primária | Módulos 1, 2, 4 (non-software, happiness, PO teams) |
| *The Scrum@Scale Guide* (2020) — Sutherland. agileeducation.org | Guia oficial | Módulo 4 (múltiplos times, múltiplos backlogs) |
| Scrum Papers: Nuts, Bolts, and Origins (2021) — Sutherland. jeffsutherland.com | Paper primário | Módulo 1 (origens e fundamentos) |
| Sutherland, J. LinkedIn Post (2025) — AI Points e evolução de velocity | Post público | Módulo 1 (atualização de velocity) |
| Happiness Metric Pattern — scrumplop.org | Pattern language | Módulo 2 (happiness metric com pesquisa Gallup) |
| Scrum.org — "What is ScrumBut?" | Documentação oficial | Módulo 3 (anti-patterns) |
| Berriault \& Associates — DoD for Small Businesses (2025) | Prática aplicada | Módulo 4 (DoD para não-software) |
| Wrike — Definition of Done for Marketing (2026) | Prática aplicada | Módulo 4 (DoD para campanhas) |

<span style="display:none">[^20][^21][^22][^23][^24][^25][^26][^27][^28][^29][^30][^31][^32][^33][^34][^35][^36][^37][^38][^39][^40][^41]</span>

<div align="center">⁂</div>

[^1]: https://productive.io/blog/scrum-framework/

[^2]: https://scrumguides.org/scrum-guide.html

[^3]: https://wearebrain.com/blog/5-scrum-values-what-are-they-and-why-do-we-need-them/

[^4]: https://44riskpm.com/blog/scrum-book/

[^5]: https://www.infoq.com/articles/sutherland-scrum-twice-work-half-time/

[^6]: https://www.scribd.com/document/672798236/The-art-of-doing-twice-the-work-in-half-the-time

[^7]: https://www.scrum.org/resources/blog/done-understanding-definition-done

[^8]: https://www.richard-banks.org/2010/06/in-scrum-team-size-7-2-not-50.html

[^9]: https://bobsutton.typepad.com/my_weblog/2014/03/why-big-teams-suck-seven-plus-or-minus-two-is-the-magical-number-once-again.html

[^10]: https://www.bobsutton.org/2014/03/why-big-teams-suck-seven-plus-or-minus-two-is-the-magical-number-once-again-2/

[^11]: https://www.linkedin.com/posts/jeffsutherland_increase-ai-points-the-new-agile-metric-activity-7404200336346726400-RJEs

[^12]: https://www.instagantt.com/project-management/scrum-the-art-of-doing-twice-the-work-in-half-the-time-summary

[^13]: https://www.trt9.jus.br/pds/Scrum/guidances/concepts/armadilhas_troca_contexto_54B70389.html

[^14]: https://sites.google.com/a/scrumplop.org/published-patterns/retrospective-pattern-language/happiness-metric

[^15]: https://www.agileavengers.com/blog/agile-happiness-metric

[^16]: https://www.scrum.org/resources/what-scrumbut

[^17]: https://www.linkedin.com/posts/jeffsutherland_first-principles-in-scrum-foundations-activity-7293637600010010624-HX6p

[^18]: https://berriaultandassociates.com/definitiona-of-done-for-small-business/

[^19]: https://agileeducation.org/wp-content/uploads/2020/06/ScrumatScaleGuide-Published3.15.20.DrJeffSutherland.pdf

[^20]: https://readingraphics.com/book-summary-scrum/

[^21]: https://www.reddit.com/r/SoftwareEngineering/comments/1dek375/scrum_how_to_do_twice_as_much_in_half_the_time/

[^22]: https://books.google.com/books/about/Scrum.html?id=L13frQEACAAJ

[^23]: https://thescrumacademy.com/2014/08/14/scrum-art-twice-work-half-time/

[^24]: https://www.linkedin.com/pulse/chapter-1-notes-scrum-art-doing-twice-work-half-time-jeff-rasing

[^25]: http://jeffsutherland.com/scrumpapers.pdf

[^26]: https://reference-global.com/download/book/9781839210303.pdf

[^27]: https://libdoc.dpu.ac.th/eBook/113642.pdf

[^28]: https://www.linkedin.com/posts/sushant-ohdar-4101732b_agile-scrum-kanban-activity-7391028255467855872-fbNg

[^29]: https://www.wrike.com/project-management-guide/faq/what-is-definition-of-done-agile/

[^30]: https://www.youtube.com/watch?v=wdKoU1D4GDs

[^31]: http://jeffsutherland.com/scrum/SutherlandFutureOfScrumAgile2005.pdf

[^32]: https://agilemania.com/agile-definition-of-done

[^33]: http://jeffsutherland.org/scrum/scrumpapers.pdf

[^34]: https://archive.org/stream/TheOfficialScrumHandbookJeffSutherland/009-theScrumHandbook-manual_djvu.txt

[^35]: https://www.toptal.com/product-managers/scrum/product-backlog-prioritization-with-multiple-stakeholders

[^36]: https://www.scribd.com/document/836472090/The-Scrum-but-Guide

[^37]: https://www.scrum.org/forum/scrum-forum/6014/prioritizing-backlog-multiple-products-it

[^38]: https://tribodelideres.com/resumo-do-livro-scrum-de-jeff-sutherland/

[^39]: https://resources.scrumalliance.org/Article/youre-asked-product-owner-multiple-teams

[^40]: https://www.youtube.com/watch?v=O7cA1q0XwhE

[^41]: https://www.atlassian.com/agile/scrum/backlogs

