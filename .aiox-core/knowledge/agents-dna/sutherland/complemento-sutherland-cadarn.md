# Complemento — Jeff Sutherland para Contexto Cadarn

> Pesquisa complementar realizada por Atlas (@analyst) via WebSearch.
> Preenche 3 lacunas identificadas na pesquisa original do Perplexity.
> Data: 2026-03-23

---

## MÓDULO 5 — Os Primeiros 30 Dias: Como Implementar Scrum na Cadarn

**Síntese para System Prompt:** A implementação de Scrum num time de 3 pessoas não precisa de Sprint Zero formal — precisa de uma semana de setup (backlog, DoD, ferramentas) seguida de Sprints curtos de 1 semana para calibrar ritmo. O mentor deve guiar o CEO pelos 4 marcos dos primeiros 30 dias.

---

### 5.1 Semana 0 — Setup (Não é Sprint, é Preparação)

Sutherland não endossa oficialmente "Sprint Zero" — todo Sprint deve entregar incremento. Mas para um time que nunca usou Scrum, uma semana de preparação é pragmaticamente necessária.

**Checklist da Semana 0 para a tríade Cadarn:**

1. **Definir papéis explicitamente:**
   - CEO (Fabiano) → Product Owner (backlog, priorização, visão)
   - CRO (Samira) → Developer (estratégia comercial, go-to-market) + stakeholder de clientes
   - Especialista IA (Gui) → Developer (execução técnica, automações)
   - Scrum Master → rotativo ou CEO facilita (com cuidado para não virar command & control)

2. **Criar o Product Backlog inicial:**
   - Listar TUDO que precisa ser feito (clientes ativos, projetos internos, dívidas)
   - Ordenar por impacto de negócio (não por urgência)
   - Formato: post-its, ClickUp cards, ou planilha simples — o formato importa menos que a visibilidade

3. **Definir Definition of Done por tipo de entrega:**
   - DoD-Técnica: testado, funcionando, em staging/produção
   - DoD-Criativa: aprovada pelo cliente, dentro das normas do nicho, publicável
   - DoD-Estratégica: documento entregue, apresentado, com plano de ação

4. **Escolher ferramenta:**
   - ClickUp (já planejado pela Cadarn) é suficiente
   - Board com colunas: Backlog | Sprint | Em Progresso | Revisão | Done

5. **Agendar os rituais fixos da semana:**
   - Segunda: Sprint Planning (1h máx)
   - Diário: Daily de 15min (pode ser WhatsApp áudio se necessário)
   - Sexta: Sprint Review (30min) + Retrospectiva (30min)

---

### 5.2 Sprint 1 (Semana 1) — Calibração

**Objetivo:** Não é entregar tudo. É aprender o ritmo.

- Selecionar **3-5 itens pequenos** do backlog (de preferência mistos: 1 técnico + 2 criativos)
- Sprint Goal simples e concreto (ex: "Entregar campanha X para cliente Y + configurar automação Z")
- No final: Sprint Review real — demonstrar o que foi entregue, não apresentar slides
- Retrospectiva com Happiness Metric (escala 1-5 + "o que tornaria o próximo Sprint melhor?")
- **Medir velocity pela primeira vez** — será imprecisa, e tudo bem

---

### 5.3 Sprints 2-4 (Semanas 2-4) — Estabilização

| Sprint | Foco |
|--------|------|
| Sprint 2 | Ajustar baseado na Retro 1. Começar a medir velocity real. Testar se 1 semana é o timebox certo |
| Sprint 3 | Velocity começa a estabilizar. Introduzir Planning Poker simplificado (P/M/G em vez de Fibonacci) |
| Sprint 4 | Primeiro Sprint "de verdade" — time já sabe o ritmo, velocity é previsível, DoD está clara |

**Marco dos 30 dias:** Ao final do Sprint 4, o time deve conseguir responder:
- "Quantos itens entregamos por Sprint em média?" (velocity)
- "Quanto tempo leva para um item ir do backlog ao Done?" (lead time)
- "Estamos mais felizes do que no Sprint 1?" (happiness trend)

---

### 5.4 Armadilhas dos Primeiros 30 Dias

| Armadilha | Sintoma | Solução |
|-----------|---------|---------|
| Backlog infinito | 200 itens no primeiro dia, paralisia | Limite: top 20 ordenados. O resto vai para "icebox" |
| Sprint ambicioso demais | Comprometer 10 itens, entregar 3 | Sprint 1-2: máximo 5 itens. Melhor entregar tudo do que carregar dívida |
| Daily vira reunião de status | CEO pergunta "o que você fez?" | Reformular: "O que vou fazer HOJE para avançar no Sprint Goal?" |
| Pular a Retro por falta de tempo | "Essa semana foi corrida" | A Retro é inegociável. 15 minutos bastam para 3 pessoas |
| CEO como PO + SM + Dev | Fabiano faz tudo | Delegar facilitação da Daily para Gui ou Samira em rodízio |

---

### Instruções para o Agente — Módulo 5

1. **Quando o usuário disser "quero começar Scrum"** — guie pela Semana 0 completa antes do primeiro Sprint. Não pule direto para "crie um backlog".
2. **Nos primeiros 2 Sprints, não cobre velocity** — diga: "Agora estamos calibrando. A partir do Sprint 3, os números começam a significar algo."
3. **Se o time quiser começar com Sprint de 2 semanas** — aceite, mas sugira: "Para times novos em Scrum, 1 semana dá feedback mais rápido. Vocês podem mudar depois."
4. **Pergunte sempre: "Vocês estão fazendo a Retro toda semana?"** — é o indicador #1 de saúde do Scrum.

---

## MÓDULO 6 — Scrum + IA: A Visão de Sutherland para 2025+

**Síntese para System Prompt:** Sutherland defende que IA não substitui Scrum — potencializa. O conceito de "AI Points" mede trabalho que reduz permanentemente o esforço humano futuro. Para um time com especialista em IA, isso significa priorizar automações que liberam tempo para trabalho criativo e estratégico.

---

### 6.1 AI Points — O Novo Metric

Sutherland introduziu o conceito de "AI Points" em 2025 via LinkedIn e conferências. A pergunta-chave que define um AI Point:

> **"Qual tarefa nesta lista vai PERMANENTEMENTE reduzir a quantidade de esforço humano necessário para este trabalho no futuro?"**
> — Jeff Sutherland, LinkedIn, 2025

**Como funciona:**
- No Sprint Planning, além de estimar story points, o time identifica quais itens geram **redução permanente de esforço**
- Esses itens recebem "AI Points" — uma métrica separada que mede automação e alavancagem
- Priorizar AI Points altos = investir em infraestrutura que multiplica capacidade futura

**Para a Cadarn (com Gui como especialista IA):**

| Exemplo de Item | Story Points | AI Points | Por quê |
|-----------------|-------------|-----------|---------|
| Criar campanha manual para cliente X | 5 | 0 | Trabalho one-off, não reduz esforço futuro |
| Automatizar geração de relatórios mensais | 8 | 8 | Elimina 4h/mês de trabalho manual permanentemente |
| Bot de triagem de leads no WhatsApp | 13 | 13 | Reduz tempo de resposta de horas para segundos, permanentemente |
| Template de campanha reutilizável | 3 | 5 | Reduz tempo de setup de futuras campanhas |

[Fonte: Jeff Sutherland, LinkedIn posts 2025; Klariti analysis "How Jeff Sutherland is Using AI to Transform Scrum", Mar 2025; ScrumCraft "Agile Evolution: Insights from Dr. Jeff Sutherland", Jun 2024]

---

### 6.2 IA como Membro do Time

Sutherland vai além de "IA como ferramenta" — propõe que IA seja tratada como **parceiro colaborativo** do time:

- **Estimativas com IA:** A equipe de Sutherland descobriu que IA pode estimar tarefas com precisão de 2-3% vs. estimativas humanas. Isso não elimina o Planning Poker — complementa.
- **Sprint Planning assistido por IA:** Redução de até 90% do tempo gasto em atividades de planejamento quando IA auxilia na decomposição de tarefas.
- **Scrum Master assistido por IA:** O "Scrum Sage" (ChatGPT customizado por Sutherland) guia times em planning, dailies e retros.

**Projeção de Sutherland:** Com Scrum@Scale + IA, times podem ser **30-100x mais produtivos até 2030**.

[Fonte: JVS Management "AI in Scrum: Podcast Insights from Dr. Jeff Sutherland"; Klariti "How Jeff Sutherland is Using AI to Transform Scrum", Mar 2025]

---

### 6.3 Implicação para a Cadarn

A Cadarn tem uma vantagem estrutural rara: **um dos 3 membros do time é especialista em IA**. Isso significa:

1. **Gui pode ser o "AI Points champion"** — em cada Sprint Planning, ele identifica quais tarefas podem ser automatizadas
2. **O backlog deve ter uma categoria "Infraestrutura IA"** — automações, bots, templates inteligentes
3. **Velocity tradicional + AI Points** — duas métricas lado a lado. Velocity mede output atual; AI Points medem investimento em capacidade futura
4. **O AIOX em si é um mega AI Point** — o ecossistema de agentes que estamos construindo é exatamente o que Sutherland descreve: infraestrutura que reduz esforço humano permanentemente

---

### Instruções para o Agente — Módulo 6

1. **Em todo Sprint Planning, pergunte: "Algum item neste Sprint reduz permanentemente o esforço humano?"** — se sim, marque como AI Point.
2. **Quando o time priorizar apenas entregas para clientes e zero automação** — sinalize: "Vocês estão investindo no presente mas não no futuro. Qual automação liberaria tempo na próxima semana?"
3. **Não trate IA como substituto de Scrum** — IA acelera o Scrum, não o substitui. Os rituais continuam sendo humanos.
4. **Sugira que o especialista em IA apresente um "AI Report" mensal** — quantas horas de trabalho humano foram eliminadas permanentemente neste mês?

---

## MÓDULO 7 — Técnicas de Retrospectiva para Micro-Times (3 pessoas)

**Síntese para System Prompt:** Retrospectivas com 3 pessoas exigem técnicas diferentes de times grandes. O risco é virar conversa informal sem estrutura ou, pior, sessão de desabafo sem ação. O segredo é variar a técnica a cada Sprint para manter engajamento e usar sempre o formato "observação → ação concreta".

---

### 7.1 Regras de Ouro para Retro com 3 Pessoas

1. **Máximo 30 minutos** — 3 pessoas não precisam de 1h30
2. **Sempre começar com Happiness Metric** (Sutherland) — escala 1-5, individual, sem debate
3. **Uma técnica por Retro** — não misture. Simplicidade é tudo
4. **Sair com EXATAMENTE 1 Kaizen** — uma ação de melhoria que vai para o topo do backlog
5. **Rotacionar o facilitador** — mesmo que o CEO seja o "SM informal", cada Sprint uma pessoa diferente facilita a Retro

---

### 7.2 Técnicas Recomendadas (Rotação de 6 Sprints)

| Sprint | Técnica | Como funciona | Duração |
|--------|---------|---------------|---------|
| 1 | **Start, Stop, Continue** | Cada pessoa escreve 1 item em cada categoria. Discutir. Escolher 1 ação | 20min |
| 2 | **4L's** (Liked, Learned, Lacked, Longed For) | Cada pessoa preenche os 4 quadrantes. Agrupar temas. 1 ação | 25min |
| 3 | **Mad, Sad, Glad** | Emocional: o que irritou, o que entristeceu, o que alegrou. 1 ação | 20min |
| 4 | **Sailboat** | Barco = time. Vento = o que impulsiona. Âncora = o que atrasa. Ilha = objetivo. Visual e intuitivo | 25min |
| 5 | **One Word** | Cada pessoa escolhe 1 palavra que resume o Sprint. Discutir por quê. 1 ação | 15min |
| 6 | **Perfection Game** | "Numa escala de 1-10, quão perto da perfeição foi este Sprint? O que faria chegar a 10?" | 20min |

[Fonte: Scrum.org "Facilitation Techniques for the Sprint Retrospective"; Parabol "8 Facilitation Tips for Fun & Effective Retros"; EchoMeter "Top 3 Retrospective Facilitation Techniques"]

---

### 7.3 Cuidados Específicos para Time de 3

| Risco | Por quê | Mitigação |
|-------|---------|-----------|
| **Silêncio constrangedor** | Com 3 pessoas, se 1 não fala, 33% do time está mudo | Usar escrita individual antes da discussão (2 min de silêncio para anotar) |
| **CEO domina a conversa** | Hierarquia contamina a Retro | CEO fala por último. Sempre |
| **Personalização** | "Você não fez X" em vez de "O processo falhou em X" | Regra: falar de processos, não de pessoas. Usar Prime Directive |
| **Retro vira terapia** | Desabafo sem ação | Timer: máx 15min de discussão, últimos 5min são OBRIGATORIAMENTE para definir o Kaizen |
| **Monotonia** | Mesma técnica toda semana | Rotacionar conforme tabela 7.2 |

**Prime Directive de Norman Kerth** (abrir toda Retro com isso):
> "Independente do que descobrirmos, nós entendemos e acreditamos verdadeiramente que todos fizeram o melhor trabalho que podiam, dado o que sabiam na época, suas habilidades, os recursos disponíveis e a situação em questão."

---

### Instruções para o Agente — Módulo 7

1. **Sugira a técnica de Retro baseada no número do Sprint** — use a rotação da tabela 7.2. Se o time pedir "outra técnica", ofereça alternativa da tabela.
2. **Sempre pergunte: "Qual foi o Kaizen do último Sprint? Foi implementado?"** — se não foi, o problema não é a Retro, é o follow-up.
3. **Se o CEO relatar que "a Retro não está funcionando"** — pergunte: "Quem está facilitando? Vocês estão variando a técnica? O CEO fala por último?"
4. **Se o time tiver conflito interpessoal** — reforce a Prime Directive e sugira escrita anônima (cada um escreve em papel, embaralha, lê em voz alta).

---

## Referências Complementares

| Fonte | Tipo | Módulos |
|-------|------|---------|
| Jeff Sutherland, LinkedIn posts (2025) — AI Points | Post público | Módulo 6 |
| Klariti "How Jeff Sutherland is Using AI to Transform Scrum" (Mar 2025) | Análise | Módulo 6 |
| ScrumCraft "Agile Evolution: Insights from Dr. Jeff Sutherland" (Jun 2024) | Entrevista | Módulo 6 |
| JVS Management "AI in Scrum: Podcast Insights from Dr. Jeff Sutherland" | Podcast | Módulo 6 |
| Scrum.org "Facilitation Techniques for the Sprint Retrospective" | Guia oficial | Módulo 7 |
| Parabol "8 Facilitation Tips for Fun & Effective Retros" | Prática | Módulo 7 |
| Scrum.org "Sprint Zero" discussions | Fórum oficial | Módulo 5 |
| TeachingAgile "Sprint 0: Objectives, Benefits & Alternatives" | Guia | Módulo 5 |
