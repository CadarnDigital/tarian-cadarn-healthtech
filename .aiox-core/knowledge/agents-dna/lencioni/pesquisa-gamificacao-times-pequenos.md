# Pesquisa: Gamificação para Times Pequenos (3-10 pessoas) — Módulos 2-4

> Pesquisa realizada por Alex (@analyst) via WebSearch + WebFetch.
> Data: 2026-03-25
> Status: v1.0 — complemento aos Módulos 1-2 existentes
> Contexto: Agências premium high-ticket (imobiliárias, escritórios de advocacia, clínicas de estética, arquitetura)

---

## ESCOPO DESTE DOCUMENTO

- **Módulo 2 (complemento):** Mecânicas 5 e 6 (Streaks + Feedback Loops curtos)
- **Módulo 3:** Integração Gamificação + Lencioni (Five Dysfunctions, Working Genius, Ideal Team Player, Death by Meeting)
- **Módulo 4:** Anti-patterns e Armadilhas — o que NÃO fazer

---

# MÓDULO 2 (complemento) — MECÂNICAS 5 E 6

---

## 2.5 Streaks (Sequências) para Hábitos Operacionais

**Síntese para System Prompt:** Streaks (sequências de atividade consecutiva) exploram aversão à perda (loss aversion) e o efeito Zeigarnik para criar hábitos operacionais. Em times pequenos, streaks funcionam quando medem hábitos de equipe (não individuais), têm "streak freezes" para evitar burnout, e focam no processo correto (não em atividade vazia). Streaks sem propósito viram prisão psicológica — o time mantém a sequência pela sequência, não pelo resultado.

---

### 2.5.1 Como Streaks Funcionam — Mecânica Psicológica

| Mecanismo | Descrição | Fonte |
|-----------|-----------|-------|
| **Aversão à perda** (Loss Aversion) | Perder um streak de 30 dias dói mais do que o prazer de construí-lo. Quanto mais longo, mais doloroso quebrá-lo | Kahneman & Tversky (1979), Prospect Theory |
| **Efeito Zeigarnik** | O cérebro fica "incomodado" com tarefas incompletas — manter um streak ativo cria tensão que puxa a pessoa de volta | [The Psychology Behind Duolingo's Streak Feature](https://www.justanotherpm.com/blog/the-psychology-behind-duolingos-streak-feature) |
| **Sunk Cost Fallacy** | "Já investi 45 dias nesse streak, não posso perder agora" — mesmo que a atividade já não agregue valor | [Streak Creep — The Decision Lab](https://thedecisionlab.com/insights/consumer-insights/streak-creep-the-perils-of-too-much-gamification) |
| **Formação de hábito** | Streaks de 21-66 dias criam automatismo (Lally et al., 2010 — European Journal of Social Psychology) | [Duolingo Blog — How Streaks Build Habit](https://blog.duolingo.com/how-duolingo-streak-builds-habit/) |

---

### 2.5.2 Streaks no Duolingo e Wordle — Lições Transferíveis

| App | Mecânica | O que funciona | O que falha |
|-----|----------|---------------|-------------|
| **Duolingo** | Dias consecutivos de prática. ~10M usuários com streaks > 1 ano (dez/2024). Push notifications agressivas ("Don't let Duo down!") | Retenção 3x maior com streak ativo. Streak Freeze (item comprado) como "rede de segurança" | **Streak Anxiety:** atividade vira obrigação, não aprendizado. Usuários relatam "ansiedade existencial" ao quase perder o streak. Quebra do streak → abandono total da plataforma |
| **Wordle** | Um puzzle por dia. Streak = dias consecutivos acertando. Sem recuperação — perdeu, voltou a zero | Restrição (1/dia) cria ritual sagrado. Puzzle compartilhado (todos resolvem o mesmo) cria conexão social. Baixo compromisso de tempo (~5 min) | Sem streak freeze → frustração. Perda do streak por bug técnico gera revolta. Sem sistema de recuperação |
| **Snapchat** | "Snapstreaks" — troca de snaps por dias consecutivos | Engagement altíssimo entre adolescentes | Documentado como fonte de ansiedade social. Perda do streak = abandono permanente da plataforma |

**Fontes:**
- [Orizon — Duolingo's Gamification Secrets](https://www.orizon.co/blog/duolingos-gamification-secrets)
- [Streak Creep — The Decision Lab](https://thedecisionlab.com/insights/consumer-insights/streak-creep-the-perils-of-too-much-gamification)
- [UX Magazine — Psychology Tricks That Make Wordle Addictive](https://uxmag.com/articles/the-fascinating-psychology-tricks-that-make-wordle-so-addictive)
- [Trophy.so — Psychology of Streaks](https://trophy.so/blog/the-psychology-of-streaks-how-sylvi-weaponized-duolingos-best-feature-against-them)

---

### 2.5.3 Quando Streaks AJUDAM vs. PREJUDICAM em Times Pequenos

| Contexto | Streaks AJUDAM | Streaks PREJUDICAM |
|----------|---------------|-------------------|
| **Hábito operacional de equipe** | "7 semanas consecutivas com Weekly Tactical realizada no horário, com pauta e decisões documentadas" | "30 dias consecutivos de Daily Check-in" (forçar Daily em time de 3 que já se fala o dia todo) |
| **Qualidade de entrega** | "4 sprints consecutivos sem prazo estourado" | "120 emails respondidos em sequência" (atividade ≠ resultado) |
| **Cultura de feedback** | "3 meses consecutivos com peer feedback trocado entre todos" | "Streak de elogios no Slack" (feedback forçado vira genérico) |
| **Processo de atendimento** | "12 semanas consecutivas com NPS do cliente > 9" | "Streak de tarefas fechadas no ClickUp" (fechar tarefas mal feitas para manter o streak) |

---

### 2.5.4 Aplicação para Agências Premium (Imobiliária, Advocacia, Estética, Arquitetura)

| Segmento | Streak Recomendado | Periodicidade | Streak Freeze? |
|----------|-------------------|---------------|----------------|
| **Imobiliária** | Semanas consecutivas com follow-up de leads em < 2h | Semanal | Sim — 1 freeze por mês (feriado, viagem) |
| **Escritório de Advocacia** | Semanas consecutivas com atualização de status ao cliente (proativa, não reativa) | Semanal | Sim — 1 freeze (audiência complexa) |
| **Clínica de Estética** | Semanas consecutivas com confirmação de agenda 48h antes + pós-atendimento em 24h | Semanal | Não — equipe deve cobrir ausências |
| **Arquitetura** | Quinzenas consecutivas com report de progresso ao cliente (com fotos/renders) | Quinzenal | Sim — 1 freeze (fase de aprovação) |

**Regra de ouro:** Streaks em agências premium medem **hábitos de excelência no atendimento**, nunca volume de atividade.

---

### 2.5.5 Design de Streaks Saudáveis — Princípios

1. **Streak de equipe, não individual** — Em time de 3-10, o streak é do TIME. Isso reforça accountability mútua (Lencioni, Dysfunction #4) sem criar competição tóxica
2. **Periodicidade semanal, não diária** — Profissionais premium não respondem bem a "daily streaks" que parecem microgerenciamento. Semanal dá ritmo sem sufocar
3. **Streak Freeze obrigatório** — Sem rede de segurança, o streak vira prisão. 1 freeze por mês evita burnout e o "efeito Snapchat" (abandonar tudo ao perder)
4. **Threshold, não perfeição** — "4 de 5 leads respondidos em < 2h" mantém o streak. 100% é inatingível e desmotivante
5. **Celebração nos milestones** — Semana 4, 8, 12. Marco público (não ranking). "Time X completou 12 semanas de excelência em follow-up"
6. **Reset não é punição** — Se o streak quebra, comunicar como "novo ciclo", não como fracasso. Mostrar o histórico: "3 ciclos completos de 8+ semanas"
7. **Medir o hábito certo** — O streak deve medir o hábito que gera o resultado, não o resultado em si (resultado tem variáveis externas)

---

### 2.5.6 O Risco do "Streak Creep"

**Termo cunhado por:** The Decision Lab (behavioral science consultancy).

**Definição:** Quando a quantificação do comportamento (o streak) se torna mais importante que o comportamento em si. O time mantém o streak por obrigação, não por valor.

**Sinais de Streak Creep:**
- Time reclama do streak como "mais uma métrica para alimentar"
- Qualidade da atividade cai mas o streak continua (ex: Daily Check-in de 5 min vira 30 segundos "só para não perder")
- Ansiedade visível quando o streak está em risco
- Ninguém lembra POR QUE o streak existe

**Antídoto:** Revisão trimestral (no Quarterly Off-Site de Lencioni): "Esse streak ainda mede algo que importa? Ou virou um número que mantemos por inércia?"

**Fonte:** [Streak Creep — The Decision Lab](https://thedecisionlab.com/insights/consumer-insights/streak-creep-the-perils-of-too-much-gamification)

---

### Instruções para o Agente — Mecânica 5 (Streaks)

1. **Streaks são para HÁBITOS DE EQUIPE, não métricas individuais** — "O streak é do time. Se um membro falha, o time decide se usa o freeze ou não. Isso É accountability."
2. **Periodicidade mínima: semanal** — "Streaks diários em agência premium = microgerenciamento. Semanal é o ritmo certo."
3. **Sempre incluir Streak Freeze** — "Sem rede de segurança, o streak vira fonte de ansiedade, não de orgulho."
4. **Se o time reclama do streak** — diagnosticar Streak Creep: "O streak está medindo algo que importa ou virou métrica de vaidade?"
5. **Nunca gamificar volume** — "Streak de emails enviados = lixo. Streak de follow-ups com qualidade no prazo = excelência operacional."
6. **Celebrar milestones, não rankings** — "Ninguém compete. O time celebra junto ao atingir 4, 8, 12 semanas."
7. **Revisão obrigatória no Quarterly Off-Site** — "Todo streak é reavaliado a cada trimestre. Morreu a relevância? Mata o streak."

---

## 2.6 Feedback Loops Curtos (Reconhecimento Daily/Weekly)

**Síntese para System Prompt:** Feedback loops curtos (daily/weekly recognition) são sistemas de reconhecimento entre pares que operam em ciclos de 1-7 dias. Para profissionais sofisticados em times pequenos, o reconhecimento deve ser específico (comportamento + impacto), contextual (ligado ao trabalho real), entre pares (não top-down), e com substância (nunca genérico). "Bom trabalho!" sem contexto é pior que silêncio — infantiliza e erode credibilidade.

---

### 2.6.1 Fundamentos — Por que Feedback Curto Funciona

| Princípio | Descrição | Evidência |
|-----------|-----------|-----------|
| **Recência** (Recency Effect) | Feedback próximo ao evento é 3-5x mais eficaz que feedback no final do trimestre | Gallup (2024): funcionários que recebem feedback semanal são 5x mais engajados |
| **Especificidade** | "Você conduziu a reunião com o cliente de forma que ele fechou no ato" > "Bom trabalho na reunião" | [AIHR — Peer Recognition in the Workplace](https://www.aihr.com/blog/peer-recognition/) |
| **Direção peer-to-peer** | Reconhecimento entre pares tem 35.7% mais impacto que reconhecimento do gestor | [DavidsonMorris — Peer to Peer Recognition](https://www.davidsonmorris.com/peer-to-peer-recognition/) |
| **Frequência** | 77% dos funcionários reportam maior produtividade quando existe peer recognition; 37% mais propensos a "ir além" | [Tremendous — How to Build Peer-to-Peer Recognition](https://www.tremendous.com/blog/peer-to-peer-recognition/) |

---

### 2.6.2 Micro-Recognition vs. Recognition Formal — A Distinção Crítica

| Dimensão | Micro-Recognition (Daily/Weekly) | Recognition Formal (Mensal/Trimestral) |
|----------|--------------------------------|---------------------------------------|
| **Frequência** | Diária a semanal | Mensal, trimestral ou anual |
| **Quem dá** | Qualquer par (peer-to-peer) | Liderança, RH, comitê |
| **Formato** | 1-2 frases, específico, contextual | Cerimônia, prêmio, destaque público |
| **Exemplo** | "Samira, o jeito que você reagiu ao cliente difícil ontem protegeu a relação e abriu porta pra upsell" | "Melhor profissional do trimestre" |
| **Risco** | Virar genérico se não houver substância | Virar política se critérios não forem claros |
| **Para agência premium** | O mecanismo PRIMÁRIO — é o que muda cultura | Complemento — celebra resultados consolidados |

---

### 2.6.3 O Problema do Reconhecimento Patronizing (Condescendente)

Para profissionais sofisticados (advogados, corretores de alto padrão, esteticistas com anos de formação, arquitetos), reconhecimento genérico é percebido como:

1. **Infantilização** — "Parabéns pelo bom trabalho!" para um advogado sênior soa condescendente
2. **Manipulação transparente** — Profissionais experientes reconhecem gamificação superficial instantaneamente
3. **Erosão de credibilidade** — Quem elogia sem substância perde autoridade para dar feedback crítico

**Antídoto — O Framework SBI (Situation-Behavior-Impact):**

| Elemento | Descrição | Exemplo (imobiliária) |
|----------|-----------|----------------------|
| **S** — Situação | Quando e onde aconteceu | "Na visita ao apartamento da Rua X ontem à tarde..." |
| **B** — Comportamento | O que a pessoa FEZ especificamente | "...você percebeu que o cliente hesitou no preço e redirecionou a conversa para o potencial de valorização do bairro..." |
| **I** — Impacto | Qual foi o resultado concreto | "...e ele pediu para fazer a proposta na hora. Isso acelerou o ciclo em 2 semanas." |

**Fonte do framework SBI:** Center for Creative Leadership (CCL). Amplamente documentado em literatura de feedback executivo.

---

### 2.6.4 Implementação Prática — Rituais de Feedback Curto

#### Ritual 1: "Spotlight" na Weekly Tactical (5 min)

Integrado à Weekly Tactical de Lencioni (45-90 min). Nos últimos 5 minutos:

- Cada membro nomeia 1 colega + 1 ação específica da semana que gerou impacto
- Formato SBI obrigatório (não aceitar "bom trabalho" genérico)
- Rotativo: semanas pares, grupo A nomeia grupo B e vice-versa (em times > 5)
- Registro em canal dedicado (Slack, ClickUp comment, ou doc compartilhado)

**Para time de 3 (Tríade Cadarn):** Cada pessoa fala sobre os outros 2. Leva 3-4 minutos.

#### Ritual 2: "Props" Assíncrono (Daily)

Canal dedicado no Slack/Teams/WhatsApp Business. Regras:

- Qualquer membro pode postar a qualquer momento
- Formato: emoji relevante + nome + SBI em 1-2 linhas
- Sem obrigação de frequência (voluntário = autêntico)
- Sem reações obrigatórias (não forçar "curtidas")

**Exemplo real:**
> "Gui, aquele script que você ajustou hoje de manhã economizou 2h no report do cliente Fernandez. A automação já rodou e o cliente recebeu o report antes do prazo."

#### Ritual 3: "Retrospectiva de Excelência" na Monthly Strategic (15 min)

Na Monthly Strategic de Lencioni (2-4h). Bloco dedicado:

- Revisar os "Spotlights" e "Props" do mês
- Identificar padrões: "O que está funcionando bem COMO TIME?"
- Conectar ao resultado coletivo (Lencioni, Dysfunction #5 — Results)
- Extrair 1 aprendizado replicável

---

### 2.6.5 Ferramentas e Plataformas

| Ferramenta | Tipo | Para times de 3-10 | Custo | Nota |
|-----------|------|-------------------|-------|------|
| **Slack + canal dedicado** | DIY, assíncrono | Ideal | Gratuito | Simples, sem overhead. Props no canal #reconhecimento |
| **Bonusly** | Plataforma peer recognition | Bom | ~$3/user/mês | Pontos entre pares, budget mensal, integrações |
| **Kudos** | Plataforma enterprise | Overkill para < 10 | ~$5/user/mês | Melhor para 50+ pessoas |
| **15Five** | Feedback + check-in | Bom | ~$4/user/mês | High Fives (peer recognition) + weekly check-ins |
| **ClickUp + Custom Fields** | DIY, integrado | Ideal se já usa ClickUp | Incluído | Props como comments em tasks + custom field "reconhecimento da semana" |
| **Google Form + Sheet** | DIY, budget zero | Funcional | Gratuito | Formulário semanal "Quem te ajudou esta semana?" |

**Recomendação para agência premium (3-10 pessoas):** Slack (canal dedicado) + ritual na Weekly Tactical. Sem necessidade de plataforma dedicada. Overhead de ferramenta nova > benefício para times pequenos.

**Fontes:**
- [Kudos — Best Employee Recognition Platforms 2025](https://www.kudos.com/blog/best-employee-recognition-platforms)
- [Lattice — Top Employee Feedback Tools 2025](https://lattice.com/articles/employee-feedback-tools)
- [Vantage Circle — Employee Recognition Trends 2025](https://www.vantagecircle.com/en/blog/trends-in-employee-recognition/)

---

### 2.6.6 O que NÃO Fazer — Anti-patterns de Feedback Loops

| Anti-pattern | Por quê é tóxico | Alternativa |
|-------------|------------------|-------------|
| **"Obrigatório elogiar 1 pessoa por dia"** | Forçar elogio = elogio genérico = inflação de reconhecimento | Voluntário, mas com ritual semanal que cria oportunidade |
| **Ranking de quem dá mais reconhecimento** | Gamificar o reconhecimento em si perverte o propósito | Nunca rankear. Reconhecimento não é competição |
| **"Estrelinhas" ou "medalhas" visuais** | Infantiliza profissionais seniores. Advogado com 15 anos de banca não quer "badge de feedback" | Texto com substância. Sem badges |
| **Reconhecimento APENAS top-down** | CEO elogiando = hierarquia reforçada, não cultura de pares | CEO participa COMO PAR, não como "o que distribui elogios" |
| **Reconhecimento público sem consentimento** | Nem todos querem destaque. Introvertidos podem se sentir expostos | Perguntar: "Posso compartilhar isso com o time?" |
| **Ignorar reconhecimento em semanas ruins** | Silêncio após semana difícil comunica "só reconheço quando tudo vai bem" | Reconhecer esforço mesmo quando resultado não veio |

---

### Instruções para o Agente — Mecânica 6 (Feedback Loops)

1. **Formato SBI é obrigatório** — "Situação, Comportamento, Impacto. Se não tem os 3 elementos, não é reconhecimento — é ruído."
2. **Peer-to-peer, não top-down** — "O CEO fala por ÚLTIMO e como par. Nunca como 'o chefe que distribui parabéns'."
3. **Integrar aos rituais Lencioni existentes** — "Spotlight de 5 min na Weekly Tactical. Não crie reunião nova — injete nos rituais que já existem."
4. **Voluntário, com oportunidade estruturada** — "Não force elogio. Crie o momento (ritual semanal) e o canal (Slack). A autenticidade vem da liberdade."
5. **Se o reconhecimento virar genérico** — intervir: "Isso foi específico? Qual comportamento exato? Qual impacto? Refaça."
6. **Nunca gamificar o próprio reconhecimento** — "Quem deu mais elogios ganha pontos? NÃO. Isso perverte todo o sistema."
7. **Adaptar ao perfil do profissional** — "Advogado quer substância factual. Esteticista quer reconhecimento do cuidado com o cliente. Corretor quer reconhecimento da habilidade de negociação. Conheça o público."

---

# MÓDULO 3 — INTEGRAÇÃO GAMIFICAÇÃO + LENCIONI

**Síntese para System Prompt:** Gamificação e frameworks Lencioni são COMPLEMENTARES quando a gamificação reforça saúde organizacional (confiança, conflito saudável, comprometimento, accountability, resultados coletivos). São DESTRUTIVOS quando a gamificação cria competição individual que corrói confiança (Dysfunction #1). A regra inviolável: toda mecânica de jogo deve passar pelo teste — "Isso fortalece ou enfraquece a confiança entre os membros do time?"

---

## 3.1 Gamificando as Five Dysfunctions (O Framework de Reforço)

### Princípio Arquitetural

A pirâmide de Lencioni é sequencial — não se pode gamificar accountability (nível 4) sem ter confiança (nível 1). Portanto, a gamificação TAMBÉM deve ser implementada de baixo para cima.

| Nível | Disfunção | Mecânica de Gamificação | Tipo | O que NÃO fazer |
|-------|-----------|------------------------|------|-----------------|
| **1. Confiança** | Ausência de confiança | **"Vulnerability Rounds"** — em cada Weekly, 1 pessoa compartilha um erro recente + o que aprendeu. Streak de equipe: semanas consecutivas com vulnerability round completa | Cooperativa | Nunca rankear "quem é mais vulnerável". Nunca forçar — confiança é construída, não mandada |
| **2. Conflito** | Medo de conflito | **"Devil's Advocate Rotation"** — papel rotativo de "advogado do diabo" que DEVE questionar a decisão principal da semana. Badge simbólico (não infantil): "Desafiador da Semana" | Cooperativa | Nunca punir quem discorda. Nunca premiar "quem discordou mais" (vira discordância artificial) |
| **3. Comprometimento** | Falta de comprometimento | **"Decision Log + Execution Score"** — ao final de cada Weekly, documentar decisões. Score da semana: % de decisões da semana anterior que foram executadas como combinado | Transparência | Nunca usar o score para punir. É ferramenta de visibilidade, não de julgamento |
| **4. Accountability** | Evitação de accountability | **"Peer Check-in Pairs"** — duplas rotativas que se cobram semanalmente. Streak: semanas consecutivas com check-in entre pares realizado | Peer-to-peer | Nunca centralizar accountability no líder. O LÍDER não cobra — o PAR cobra |
| **5. Resultados** | Inatenção a resultados | **"Team Scoreboard"** — placar público com 3-5 KPIs do TIME (não individuais). Milestone celebration: quando o time atinge um marco, celebração coletiva | Coletiva | Nunca ter leaderboard individual. Nunca premiar resultado individual quando o time falhou coletivamente |

---

### 3.1.1 Detalhe: Vulnerability Rounds (Nível 1 — Confiança)

**Inspiração:** Personal Histories Exercise de Lencioni (Five Dysfunctions, Cap. 12) + princípio de gamificação cooperativa.

**Mecânica:**
1. Na Weekly Tactical, antes do lightning round, 1 pessoa (rotativo) compartilha:
   - Um erro profissional recente (não precisa ser grave)
   - O que aprendeu com ele
   - O que faria diferente
2. Os outros 2+ membros respondem com 1 frase de validação (não conselho)
3. Se todos compartilharam no mês → milestone: "Mês de Vulnerabilidade Completa"

**Por que funciona:** Lencioni define confiança como "vulnerability-based trust" — a disposição de ser vulnerável diante dos colegas. Gamificar (levemente) a prática regular de vulnerabilidade normaliza o comportamento.

**Fonte:** Lencioni, P. "The Five Dysfunctions of a Team" (2002), Capítulo 12 — "Understanding and Overcoming the Five Dysfunctions"

---

### 3.1.2 Detalhe: Team Scoreboard (Nível 5 — Resultados)

**Inspiração:** Publication of Goals (Five Dysfunctions) + princípio de "collective quests" da gamificação cooperativa.

**Mecânica:**
1. Dashboard público (ClickUp, Notion, ou quadro físico) com 3-5 KPIs do TIME
2. KPIs devem ser de RESULTADO, não de atividade (ver Módulo 4 — Vanity Metrics)
3. Atualização semanal na Weekly Tactical (lightning round inclui check de cada KPI)
4. Milestones trimestrais com celebração coletiva (não premiação individual)

**Exemplos por segmento:**

| Segmento | KPIs do Time (exemplos) |
|----------|------------------------|
| Imobiliária | NPS do comprador; Tempo médio de fechamento; % de leads convertidos em visita |
| Advocacia | Satisfação do cliente (survey); Prazo médio de resposta; % de processos no prazo |
| Estética | Taxa de retorno de clientes; NPS pós-procedimento; % de agendas sem no-show |
| Arquitetura | Satisfação do cliente no milestone; % de entregas no prazo; Indicações ativas |

**Fonte:** Lencioni, P. "The Five Dysfunctions of a Team" (2002) — "Inattention to Results"; [ScienceDirect — Gamification of Cooperation Framework](https://www.sciencedirect.com/science/article/pii/S0268401222000834)

---

## 3.2 Gamificando o Working Genius (Alocação por Gênio)

### Princípio: Gamificação como Ferramenta de Autoconhecimento, Não de Competição

O Working Genius já é um assessment (não é competitivo por natureza). A gamificação aqui serve para:
1. **Tornar os gênios visíveis no dia a dia** (não só no assessment inicial)
2. **Celebrar quando alguém opera no seu gênio** (reforço positivo)
3. **Sinalizar quando alguém está preso em frustração** (alerta amigável)

| Mecânica | Descrição | Frequência |
|----------|-----------|-----------|
| **"Genius Spotting"** | Nos "Props" assíncronos, incluir qual gênio a pessoa usou: "Gui, sua Invention brilhou quando propôs a solução X" | Contínuo |
| **"Genius Allocation Score"** | No Quarterly Off-Site, cada membro avalia: "Quanto do meu tempo esta semana/mês foi nos meus gênios vs. frustrações?" (escala 1-5) | Trimestral |
| **"Gap Alert"** | Se um tipo de Working Genius não está coberto no time, gamificar a compensação: "Ninguém tem Enablement como gênio. Quem assumiu como competência esta semana?" | Semanal (revisão) |
| **"Genius Swap"** | Quando alguém identifica que está operando em frustração há muito tempo, pode pedir "swap" com alguém cuja competência/gênio cubra aquela atividade | Sob demanda |

**Conexão com Lencioni:**
- Working Genius + gamificação reforça Dysfunction #5 (Results) — alocar gênios corretamente MELHORA resultados
- Também reforça Dysfunction #1 (Trust) — dizer "isso é minha frustração, preciso de ajuda" exige vulnerabilidade

**Fonte:** Lencioni, P. "The 6 Types of Working Genius" (2022); [Working Genius Official](https://www.workinggenius.com/)

---

## 3.3 Gamificando o Ideal Team Player (Humble/Hungry/Smart)

### ALERTA: Esta é a gamificação mais perigosa do framework Lencioni

Gamificar Humble/Hungry/Smart diretamente (ex: "pontos por ser humilde") é **absurdo** e **contraproducente**. Humildade performada para ganhar pontos é o oposto de humildade.

### Abordagem Correta: Reconhecimento Comportamental (não premiação)

| Virtude | O que gamificar | O que NUNCA gamificar |
|---------|----------------|---------------------|
| **Humble** | Reconhecer publicamente quando alguém compartilha crédito: "Samira mencionou a contribuição do Gui na apresentação ao cliente" | Ranking de "quem é mais humilde" (paradoxo: competir em humildade DESTRÓI humildade) |
| **Hungry** | Reconhecer quando alguém busca aprendizado por conta própria ou assume responsabilidade extra sem ser pedido | Premiar "horas extras" ou "quem trabalhou mais" (hungry ≠ workaholic) |
| **Smart** (people-smart) | Reconhecer quando alguém adaptou comunicação ao contexto: "O jeito que você abordou o cliente introvertido foi preciso" | Premiar "quantidade de interações" (smart ≠ extrovertido) |

**Formato:** Integrar ao ritual de "Spotlight" na Weekly Tactical. Quando alguém reconhece um colega, pode opcionalmente marcar qual virtude foi demonstrada. Isso EDUCA o time sobre as 3 virtudes sem criar competição.

**Fonte:** Lencioni, P. "The Ideal Team Player" (2016), Cap. 4 — "The Model"

---

## 3.4 Gamificando o Death by Meeting (4 Tipos de Reunião)

### Mecânica: Rituais como "Fases do Jogo"

| Tipo de Reunião | Mecânica Gamificada | Streak Possível |
|----------------|--------------------|-----------------|
| **Daily Check-in** (5 min) | Timer visual. Se exceder 5 min, o "time perdeu o round". Não há punição — apenas visibilidade | Dias consecutivos sem exceder 5 min |
| **Weekly Tactical** (45-90 min) | Lightning Round com timer (30 seg/pessoa). Se alguém traz tema estratégico, "flag" — vai para Monthly. Score: % de itens táticos resolvidos na semana | Semanas com 100% dos itens documentados |
| **Monthly Strategic** (2-4h) | "Deep Dive Score" — ao final, cada membro avalia (1-5): "Debatemos de verdade ou foi superficial?" Média < 3 = alerta | Meses com média > 4 |
| **Quarterly Off-Site** (1 dia) | "Clarity Test" — ao final, cada membro responde as 6 perguntas de clareza de Lencioni (Org Health). Comparar respostas. Score: grau de alinhamento | Trimestres com alinhamento > 80% |

**Gamificação do score de reuniões** (referência acadêmica): Pesquisa sobre gamificação de task force meetings demonstrou que avaliação gamificada (+3 a -3) por reunião aumentou engajamento, segurança psicológica e coesão de equipe. [Gamification of Task Force Meetings — SCIRP](https://www.scirp.org/pdf/ojl_2330727.pdf)

**Regra fundamental:** A gamificação das reuniões serve para PROTEGER a estrutura (não misturar tipos, respeitar tempo, documentar decisões). Não serve para premiar "melhor contribuição" — isso cria performatividade.

---

## 3.5 O Teste Fundamental: Gamificação + Confiança

**Toda mecânica de gamificação DEVE passar por este gate:**

```
TESTE DE CONFIANÇA (gate obrigatório)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Pergunta 1: "Essa mecânica exige que alguém PERCA para outro GANHAR?"
→ Se SIM → VETO. Redesenhar como cooperativa.

Pergunta 2: "Essa mecânica pode ser usada para envergonhar alguém publicamente?"
→ Se SIM → VETO. Adicionar proteções de privacidade.

Pergunta 3: "Essa mecânica recompensa performance individual em detrimento do time?"
→ Se SIM → VETO. Converter para métrica de equipe.

Pergunta 4: "Se o membro mais introvertido do time participasse, ele se sentiria confortável?"
→ Se NÃO → REDESENHAR com opção de participação assíncrona/privada.

Pergunta 5: "Essa mecânica reforça qual nível da pirâmide Lencioni?"
→ Se NENHUM → Não implementar. Gamificação sem propósito organizacional é decoração.
```

**Fonte do conceito:** [inference] Derivado da integração entre princípios de cooperative gamification ([ScienceDirect — Gamification of Cooperation](https://www.sciencedirect.com/science/article/pii/S0268401222000834)), psychological safety (Edmondson, 1999 — "Psychological Safety and Learning Behavior in Work Teams"), e Five Dysfunctions de Lencioni.

---

### Instruções para o Agente — Módulo 3 (Gamificação + Lencioni)

1. **Gate de Confiança é inviolável** — "Toda mecânica de gamificação passa pelo Teste de Confiança. 1 VETO = redesenhar ou descartar."
2. **Pirâmide sequencial vale para gamificação** — "Não gamifique accountability se não há confiança. Não gamifique resultados se não há comprometimento."
3. **Cooperative > Competitive, SEMPRE** — "Em times de 3-10, competição individual é veneno. Toda mecânica deve ser cooperativa ou de equipe."
4. **Working Genius é reconhecimento, não competição** — "Genius Spotting celebra. Nunca rankear gênios."
5. **Ideal Team Player NÃO se gamifica diretamente** — "Humildade performada para ganhar pontos é o oposto de humildade. Apenas reconheça comportamentos quando emergem naturalmente."
6. **Reuniões gamificadas protegem estrutura** — "Timer, flag de temas fora de escopo, decision log. A gamificação serve a disciplina, não ao entretenimento."
7. **Se alguém pergunta 'quem ganhou?'** — problema: "Ninguém ganha. O TIME ganha quando opera saudável. Se a pergunta é 'quem ganhou', a gamificação está errada."

---

# MÓDULO 4 — ANTI-PATTERNS E ARMADILHAS

**Síntese para System Prompt:** Gamificação falha mais do que funciona. Os 7 anti-patterns letais para times pequenos são: leaderboards que destroem colaboração, pointsification (pontos sem significado), infantilização de profissionais seniores, recompensas extrínsecas que matam motivação intrínseca (overjustification effect), vanity metrics gamificadas (atividade ≠ resultado), imposição sem opt-in, e gaming the system (Lei de Goodhart). Cada anti-pattern tem antídoto específico. A regra mais importante: se a gamificação não passa no Teste de Confiança (Módulo 3.5), ela não existe.

---

## 4.1 Leaderboards que Destroem Colaboração

### O Problema

Leaderboards (rankings públicos) são o elemento de gamificação mais popular E o mais destrutivo em times pequenos.

**Evidência:**
- Em times onde há leaderboard competitivo, o time perdedor demonstra menor performance, menor confiança e menor engajamento (ScienceDirect, 2024) — [As it unfolds: Team-based gamification on performance](https://www.sciencedirect.com/science/article/pii/S1041608024001584)
- Leaderboards criam "clustering" entre membros do time e incentivam "ética de trabalho adversa" como intimidação e pressão (MDPI, 2019) — [Gamification Risks to Enterprise Teamwork](https://www.mdpi.com/2079-8954/7/1/9)
- Elementos mais citados como causadores de efeitos negativos: badges, leaderboards, competições e pontos (ScienceDirect, 2022) — [Negative effects of gamification in education software](https://www.sciencedirect.com/science/article/abs/pii/S0950584922002518)
- Leaderboards geram ansiedade e ciúme, e "podem desencorajar colaboração" (Wiley, 2024) — [Use of leaderboards in education: systematic review](https://onlinelibrary.wiley.com/doi/10.1111/jcal.13077)

### Por que é Letal em Times Pequenos (3-10)

| Fator | Impacto |
|-------|---------|
| **Visibilidade total** | Com 5 pessoas, TODOS sabem quem está em último. Não há anonimato |
| **Relações interpessoais** | Em time de 3, o "último lugar" é 33% do time. Desmotivar 33% é destruir o time |
| **Destruição de confiança** | Leaderboard individual viola diretamente Lencioni Dysfunction #1 (Trust) e #5 (Results coletivos) |
| **Efeito Loser** | Quem está embaixo desiste. Com 5 pessoas, se 2 desistem, o time acabou |

### Antídoto

**Substituir leaderboard individual por Team Scoreboard (ver 3.1.2).** Se absolutamente necessário rankear algo, rankear EQUIPES contra um PADRÃO (não contra outras equipes): "Nosso time está em 85% do target" — não "Nosso time está em 3o lugar".

---

## 4.2 Pointsification (Pontos sem Significado)

### Origem do Termo

**Cunhado por:** Margaret Robertson, game designer, em 2010.

**Definição:** "A aplicação dos aspectos MENOS essenciais dos jogos (pontos, badges, leaderboards) como se fossem os MAIS essenciais." Robertson argumenta que "pontos são a parte menos importante de um jogo" — o que importa é game thinking, mecânicas de decisão, narrativa, e progressão significativa.

**Reforço crítico por:** Ian Bogost, professor de Georgia Tech, em 2011, que propôs o termo "exploitationware" (software de exploração) como nome mais honesto para o que a indústria chama de "gamificação". Artigo seminal: [Persuasive Games: Exploitationware — Game Developer](https://www.gamedeveloper.com/design/persuasive-games-exploitationware)

**Pesquisa acadêmica recente:** Frontiers in Education (2023) publicou estudo diferenciando formalmente pointsification de gamificação, argumentando que a maioria dos estudos sobre "gamificação" na verdade estuda pointsification, gerando resultados mistos que não representam gamificação real. [Frontiers — A point with pointsification?](https://www.frontiersin.org/journals/education/articles/10.3389/feduc.2023.1212994/full)

### Sinais de Pointsification

- Pontos dados por ações triviais (login, abrir email, "participar" de reunião)
- Pontos sem conexão com resultado ou aprendizado
- Badges sem significado ("Badge de Primeiro Login" — e daí?)
- Pontos inflacionados (todos têm milhares, ninguém sabe o que significam)
- Profissionais perguntam: "Isso serve pra quê?"

### Antídoto

Cada ponto ou badge deve responder: **"Isso representa qual competência, resultado ou comportamento que importa para o time?"** Se não responde → é pointsification → não implementar.

---

## 4.3 Infantilização de Profissionais Premium

### O Problema Específico

Agências premium atendem e empregam profissionais sofisticados. A estética da gamificação em apps (estrelinhas, animações, personagens, badges coloridos) é percebida como:

| Percepção | Exemplo |
|-----------|---------|
| **"Isso é coisa de criança"** | Badge com emoji de estrela para advogado com 20 anos de carreira |
| **"Estão me tratando como vendedor de telemarketing"** | Ranking de ligações para corretor de imóvel de R$ 5M |
| **"Transparentemente manipulador"** | Notificação push "Você está quase perdendo seu streak!" para esteticista com pós-graduação |
| **"Desrespeito à minha experiência"** | Nível "Iniciante → Especialista" para arquiteto com 15 anos de prática |

### Antídoto: Gamificação Invisível (Stealth Gamification)

Usar mecânicas de jogo SEM a estética de jogo:

| Mecânica de Jogo | Implementação "Invisível" para Premium |
|-----------------|---------------------------------------|
| **Streak** | "Semanas consecutivas de excelência em follow-up" — sem chama, sem animação. Número limpo em dashboard |
| **Feedback loop** | Ritual SBI na Weekly Tactical — é gamificação (reconhecimento + ciclo curto), mas parece "gestão profissional" |
| **Progression** | "Nosso time evoluiu de 72% para 89% no NPS este trimestre" — progressão sem "níveis" ou "badges" |
| **Challenge** | "Meta trimestral do time: reduzir tempo de resposta de 4h para 2h" — challenge sem competição |
| **Team scoreboard** | Dashboard limpo com 3-5 KPIs. Nada de "placar de jogo" — apenas visualização de dados |

**Princípio:** A mecânica é a mesma. A EMBALAGEM muda. Para profissionais premium, a gamificação deve ser **estrutural e funcional**, nunca **estética e lúdica**.

---

## 4.4 Overjustification Effect (Recompensas Extrínsecas Matando Motivação Intrínseca)

### Origem e Definição

**Pesquisadores originais:** Edward Deci (1971) e Richard Ryan — criadores da Self-Determination Theory (SDT).

**Definição:** O overjustification effect (efeito de superjustificação) ocorre quando uma recompensa externa esperada (dinheiro, prêmio, pontos) DIMINUI a motivação intrínseca para realizar uma tarefa. A pessoa que fazia algo por prazer ou propósito passa a fazer pela recompensa — e quando a recompensa desaparece, a motivação desaparece também.

**Estudo seminal:** Deci (1971) demonstrou que pagar pessoas para resolver puzzles que elas já faziam voluntariamente REDUZIU o tempo que dedicavam aos puzzles quando o pagamento parou.

**Meta-análise:** Deci, Koestner & Ryan (1999) — "A Meta-Analytic Review of Experiments Examining the Effects of Extrinsic Rewards on Intrinsic Motivation" (Psychological Bulletin). Confirmou que **todas as recompensas tangíveis esperadas contingentes à tarefa diminuem confivelmente a motivação intrínseca**.

**Fontes:**
- [Ryan & Deci (2000) — SDT Paper](https://selfdeterminationtheory.org/SDT/documents/2000_RyanDeci_SDT.pdf)
- [Wikipedia — Overjustification Effect](https://en.wikipedia.org/wiki/Overjustification_effect)
- [Medium — Overjustification Effect and Gamification](https://medium.com/gamification-curated/why-the-overjustification-effect-is-the-catch-22-of-gamification-5022a4e9ad79)

### As 3 Necessidades Psicológicas (SDT)

Gamificação saudável REFORÇA as 3 necessidades básicas da SDT:

| Necessidade | Descrição | Gamificação que REFORÇA | Gamificação que DESTRÓI |
|------------|-----------|------------------------|------------------------|
| **Autonomia** | Sentir-se no controle das próprias escolhas | Opt-in, escolha de desafios, personalização | Gamificação mandatória, rankings forçados |
| **Competência** | Sentir-se capaz e eficaz | Progressão significativa, feedback de melhoria | Leaderboards onde 80% está "perdendo" |
| **Relatedness** | Sentir-se conectado aos outros | Desafios de equipe, reconhecimento peer-to-peer | Competição individual que isola |

### Aplicação Prática

**Pergunte antes de implementar qualquer recompensa:**
1. "O time já faz isso sem recompensa?" → Se SIM, **não** adicione recompensa extrínseca. Reconheça e celebre, mas não pague/premie.
2. "A recompensa vai substituir o propósito?" → Se há risco, use recompensas informacionais (feedback, progresso) em vez de recompensas tangíveis (prêmios, bônus).
3. "Se tirarmos a recompensa, o comportamento continua?" → Se NÃO, a gamificação está criando dependência, não hábito.

---

## 4.5 Vanity Metrics Gamificadas (Atividade ≠ Resultado)

### O Problema

Gamificar métricas de ATIVIDADE em vez de métricas de RESULTADO cria a ilusão de produtividade.

| Vanity Metric (Atividade) | Metric que Importa (Resultado) |
|--------------------------|-------------------------------|
| Emails enviados | Leads convertidos |
| Ligações realizadas | Reuniões marcadas que geraram proposta |
| Horas trabalhadas | Entregas concluídas no prazo |
| Tasks fechadas no ClickUp | Tasks fechadas COM QUALIDADE aceita pelo cliente |
| Posts publicados | Engajamento qualificado (leads, não likes) |
| Reuniões realizadas | Decisões tomadas e executadas |

**O risco Goodhart (ver 4.7):** Quando você gamifica "tasks fechadas", as pessoas vão fechar tasks. Inclusive tasks mal feitas, divididas artificialmente para inflar o número, ou tasks irrelevantes. O número sobe. A qualidade desce.

### Framework CLEAR para Métricas de Gamificação

| Letra | Critério | Teste |
|-------|----------|-------|
| **C** | Comprehensible | O time entende instantaneamente o que a métrica significa? |
| **L** | Leading | A métrica sinaliza problemas ANTES de aparecerem no resultado? |
| **E** | Enduring | A métrica se mantém relevante ao longo do tempo? |
| **A** | Actionable | O time pode agir diretamente para melhorar a métrica? |
| **R** | Relevant | A métrica está conectada ao resultado que importa para o cliente/negócio? |

**Fonte:** [MotivaCraft — Gamification Metrics: What to Track and What to Ignore](https://www.motivacraft.com/gamification-metrics-what-to-track-and-what-to-ignore-for-real-results/)

---

## 4.6 Gamificação sem Opt-in (Imposição = Resistência)

### O Problema

Gamificação mandatória viola a necessidade de Autonomia da SDT (ver 4.4). Quando pessoas são FORÇADAS a participar de um "jogo", a reação natural é resistência, cinismo, ou compliance mínimo.

**Evidências:**
- "Quando organizações tentam impor um jogo aos funcionários em vez de convidá-los a jogar, isso vai contra a natureza da autonomia" — [Springer — Ethics in Gamification](https://link.springer.com/article/10.1007/s10676-016-9401-5)
- "Funcionários europeus respondem melhor à gamificação quando ela aumenta seu senso de controle sobre o trabalho, não quando o restringe" — [Albi Marketing — Gamification in Hybrid Workplace](https://albimarketing.com/blog/gamification-and-employee-engagement-reimagining-motivation-in-europes-hybrid-workplace/)
- "Gamificação pode sair pela culatra se funcionários a percebem como injusta, coerciva ou enganosa" — [TerryBerry — Gamification for Employee Engagement](https://www.terryberry.com/blog/gamification-for-employee-engagement/)

### O Teste Ético de Opt-in

Duas perguntas (framework de Interaction Design Foundation):
1. **"Há transparência sobre o propósito do design?"** — O time sabe POR QUE a gamificação existe?
2. **"O usuário optou por participar, implícita ou explicitamente?"** — Se ambas são SIM → sistema ético. Se alguma é NÃO → redesenhar.

**Fonte:** [Interaction Design Foundation — Legal and Ethical Considerations in Gamification](https://www.interaction-design.org/literature/book/gamification-at-work-designing-engaging-business-software/chapter-8-58-legal-and-ethical-considerations)

### Aplicação para Times Pequenos

| Errado | Certo |
|--------|-------|
| "A partir de segunda, todos usam o sistema de streaks" | "Estamos testando streaks para [hábito X]. Quem quer participar do piloto?" |
| "Reconhecimento peer-to-peer é obrigatório" | "Criamos o canal #reconhecimento. Quem quiser usar, está lá. Vamos testar por 30 dias" |
| "Quem não participar será notado" | "Depois de 30 dias, revisamos juntos: funcionou? Ajustamos? Ou descartamos?" |

---

## 4.7 Gaming the System (Lei de Goodhart)

### Definição

**Lei de Goodhart (1975):** "Quando uma medida se torna um alvo, ela deixa de ser uma boa medida."

**Quem cunhou:** Charles Goodhart, economista britânico, conselheiro do Bank of England. Originalmente aplicada à política monetária. Popularizada por Marilyn Strathern na forma: "When a measure becomes a target, it ceases to be a good measure."

**Fonte:** [Wikipedia — Goodhart's Law](https://en.wikipedia.org/wiki/Goodhart's_law); [KPItree — Goodhart's Law Framework](https://kpitree.co/guides/frameworks/goodharts-law)

### Aplicação à Gamificação

Quando você gamifica uma métrica (torna-a visível, rastreável, e associada a reconhecimento), ela se torna um ALVO. E quando se torna alvo, as pessoas otimizam PARA a métrica, não para o resultado que a métrica deveria representar.

| Métrica Gamificada | Gaming Previsível | Resultado Real |
|-------------------|-------------------|----------------|
| "Tasks fechadas por semana" | Dividir 1 task em 5 sub-tasks artificiais | Número sobe, qualidade cai |
| "Tempo de resposta ao cliente" | Responder "Recebi, retorno em breve" em 30 seg | Tempo de resposta cai, tempo de resolução não muda |
| "Reuniões realizadas" | Agendar reuniões desnecessárias | Mais reuniões, menos trabalho real |
| "Posts publicados" | Publicar conteúdo genérico/reciclado | Volume sobe, engajamento cai |
| "NPS do time" | Pedir NPS apenas a clientes satisfeitos | NPS sobe, realidade não muda |

### Antídotos

1. **Múltiplas métricas complementares** — Gamificar "tempo de resposta" + "satisfação do cliente na resolução" impede gaming de uma sem impactar a outra
2. **Métricas de outcome, não de output** — "Cliente renovou contrato" é mais difícil de gaming do que "emails enviados"
3. **Revisão trimestral** — "Essa métrica ainda está medindo o que queremos? Ou o time está otimizando para o número?"
4. **Transparência sobre Goodhart** — Ensinar o time sobre a Lei de Goodhart. Quando todos sabem do risco, o gaming é mais difícil de esconder

---

## 4.8 Tabela Consolidada — Os 7 Anti-patterns

| # | Anti-pattern | Quem Documentou | Risco Principal | Antídoto |
|---|-------------|----------------|-----------------|----------|
| 1 | **Leaderboards destrutivos** | ScienceDirect (2024), MDPI (2019) | Destruição de colaboração e confiança | Team Scoreboard (coletivo, não individual) |
| 2 | **Pointsification** | Margaret Robertson (2010), Ian Bogost (2011) | Mecânica vazia, cinismo | Game thinking > game elements. Propósito antes de pontos |
| 3 | **Infantilização** | [inference] Padrão observado em literatura de gamificação premium | Perda de credibilidade com profissionais seniores | Stealth gamification — mecânica funcional, sem estética lúdica |
| 4 | **Overjustification Effect** | Deci (1971), Deci & Ryan (SDT) | Motivação intrínseca substituída por dependência de recompensa | Recompensas informacionais (feedback, progresso) > tangíveis (prêmios) |
| 5 | **Vanity Metrics** | Framework CLEAR (MotivaCraft) | Ilusão de produtividade, atividade sem resultado | Métricas CLEAR. Resultado > Atividade |
| 6 | **Sem Opt-in** | Springer (2016), SDT (Autonomia) | Resistência, cinismo, compliance mínimo | Convite + piloto + revisão. Nunca imposição |
| 7 | **Gaming the System** | Goodhart (1975), Strathern | Métricas corrompidas, falsa sensação de sucesso | Métricas múltiplas, de outcome, revisão trimestral |

---

### Instruções para o Agente — Módulo 4 (Anti-patterns)

1. **Antes de implementar QUALQUER gamificação, checar os 7 anti-patterns** — "Essa mecânica cai em algum dos 7? Se sim, redesenhar."
2. **Leaderboard individual em time < 10 = VETO automático** — "Sem exceção. Time pequeno + ranking individual = destruição de confiança."
3. **Se profissional sênior demonstra cinismo** — "A gamificação está infantilizando. Mudar para stealth gamification imediatamente."
4. **Se o time está 'fazendo por fazer'** — diagnosticar overjustification: "Estão fazendo pelo ponto ou pelo propósito? Se for pelo ponto, remover a recompensa extrínseca."
5. **Se métricas sobem mas resultado não** — diagnosticar Goodhart: "Estão otimizando para o número ou para o resultado? Revisar métricas."
6. **Opt-in é inegociável** — "Gamificação imposta é controle, não engajamento. Sempre convite + piloto + revisão."
7. **Pointsification é o default da indústria** — "Se a proposta é 'vamos dar pontos por X', perguntar: 'Qual o game thinking por trás? Qual decisão o membro toma? Qual é a progressão significativa?' Se não responde → é pointsification → não implementar."
8. **Teste final antes de qualquer implementação:**
   ```
   "Se removermos essa gamificação amanhã, o time sentiria falta?
   Ou sentiria alívio?"
   → Se ALÍVIO → a gamificação está errada.
   → Se FALTA → a gamificação tem valor real.
   ```

---

## Referências Consolidadas

### Livros

| Obra | Autor | Ano | Relevância |
|------|-------|-----|-----------|
| "The Five Dysfunctions of a Team" | Patrick Lencioni | 2002 | Pirâmide de confiança, accountability, resultados |
| "The Ideal Team Player" | Patrick Lencioni | 2016 | Humble/Hungry/Smart — 3 virtudes |
| "The 6 Types of Working Genius" | Patrick Lencioni | 2022 | Alocação por gênio |
| "Death by Meeting" | Patrick Lencioni | 2004 | 4 tipos de reunião |
| "The Advantage" | Patrick Lencioni | 2012 | Saúde organizacional > estratégia |
| "Actionable Gamification" | Yu-kai Chou | 2015 | Octalysis Framework (8 Core Drives) |
| "Reality Is Broken" | Jane McGonigal | 2011 | Gamificação positiva e propósito |
| "Intrinsic Motivation and Self-Determination in Human Behavior" | Deci & Ryan | 1985 | SDT original |

### Artigos Acadêmicos e Pesquisas

| Fonte | Ano | URL |
|-------|-----|-----|
| "Gamification is not Working: Why?" — SAGE Journals | 2025 | [Link](https://journals.sagepub.com/doi/abs/10.1177/15554120241228125) |
| "Gamification of cooperation: A framework" — ScienceDirect | 2022 | [Link](https://www.sciencedirect.com/science/article/pii/S0268401222000834) |
| "Team-based gamification on performance, confidence, engagement" — ScienceDirect | 2024 | [Link](https://www.sciencedirect.com/science/article/pii/S1041608024001584) |
| "Gamification Risks to Enterprise Teamwork: Taxonomy" — MDPI | 2019 | [Link](https://www.mdpi.com/2079-8954/7/1/9) |
| "A point with pointsification?" — Frontiers in Education | 2023 | [Link](https://www.frontiersin.org/journals/education/articles/10.3389/feduc.2023.1212994/full) |
| "Negative effects of gamification in education software" — ScienceDirect | 2022 | [Link](https://www.sciencedirect.com/science/article/abs/pii/S0950584922002518) |
| "Leaderboard Positions and Stress" — ResearchGate | 2021 | [Link](https://www.researchgate.net/publication/352295291_Leaderboard_Positions_and_Stress-Experimental_Investigations_into_an_Element_of_Gamification) |
| "Gamification of Task Force Meetings" — SCIRP | — | [Link](https://www.scirp.org/pdf/ojl_2330727.pdf) |
| "Gamification in the Workplace: Enhancing Employee..." — Acadlore | 2024 | [Link](https://library.acadlore.com/JIMD/2024/3/1/JIMD_03.01_01.pdf) |
| "SDT and Facilitation of Intrinsic Motivation" — Ryan & Deci | 2000 | [Link](https://selfdeterminationtheory.org/SDT/documents/2000_RyanDeci_SDT.pdf) |

### Artigos e Blogs

| Fonte | URL |
|-------|-----|
| Streak Creep — The Decision Lab | [Link](https://thedecisionlab.com/insights/consumer-insights/streak-creep-the-perils-of-too-much-gamification) |
| Persuasive Games: Exploitationware — Ian Bogost | [Link](https://www.gamedeveloper.com/design/persuasive-games-exploitationware) |
| Dark Side of Gamification — Growth Engineering | [Link](https://www.growthengineering.co.uk/dark-side-of-gamification/) |
| Overjustification Effect and Gamification — Medium | [Link](https://medium.com/gamification-curated/why-the-overjustification-effect-is-the-catch-22-of-gamification-5022a4e9ad79) |
| Goodhart's Law and Gamification of Metrics — Medium | [Link](https://tdevroome.medium.com/goodharts-law-and-gamification-of-metrics-ff697ac86575) |
| AIHR — Peer Recognition in the Workplace | [Link](https://www.aihr.com/blog/peer-recognition/) |
| Gamification Metrics — MotivaCraft | [Link](https://www.motivacraft.com/gamification-metrics-what-to-track-and-what-to-ignore-for-real-results/) |
| Duolingo Gamification Secrets — Orizon | [Link](https://www.orizon.co/blog/duolingos-gamification-secrets) |
| Psychology of Wordle — UX Magazine | [Link](https://uxmag.com/articles/the-fascinating-psychology-tricks-that-make-wordle-so-addictive) |
| Ethics in Gamification — Springer | [Link](https://link.springer.com/article/10.1007/s10676-016-9401-5) |
| Gamification Legal/Ethical — IDF | [Link](https://www.interaction-design.org/literature/book/gamification-at-work-designing-engaging-business-software/chapter-8-58-legal-and-ethical-considerations) |

### Ferramentas e Plataformas

| Ferramenta | URL |
|-----------|-----|
| Working Genius Assessment | [workinggenius.com](https://www.workinggenius.com/) |
| Five Behaviors (Lencioni licensed) | [fivebehaviors.com](https://www.fivebehaviors.com/) |
| The Table Group (Lencioni's org) | [tablegroup.com](https://www.tablegroup.com/) |
