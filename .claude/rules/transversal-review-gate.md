---
paths:
  - "squads/cadarn-marketing/**"
  - "docs/pipeline/**"
  - "docs/produtos/**"
  - "squads/cadarn-comercial/**"
  - "squads/cadarn-juridica/**"
---

# Transversal Review Gate — Grafia + Dick (client-facing only)

## Regra Principal

Grafia e Dick só são acionados em artefatos que serão lidos por alguém **além de Fabiano e dos agentes do framework**. Artefatos internos — que vivem apenas no terminal entre Emrys, Fabiano e os agentes — NÃO passam por nenhum dos dois revisores.

## Por que esta regra existe

O ativo intelectual Cadarn merece português impecável e clareza conceitual **quando sai da máquina**. Dentro da máquina (entre Fabiano e os agentes), o custo de zelo burocrático não se paga: gera fadiga de decisão, inflação de token e atrito no fluxo iterativo de criação.

A regra separa o que é entregue ao mundo externo (qualidade inegociável) do que é comunicação interna técnica (velocidade prevalece).

## Teste de acionamento (uma única pergunta)

> *"Alguém além de Fabiano e dos agentes do framework vai ler isso?"*

- **SIM** → gate ativo (Grafia automático + Dick sob demanda)
- **NÃO** → sem gate, entrega direta

## Nunca aciona (artefatos internos)

Estes caminhos e tipos são categoricamente internos. Zero gate.

- `memory/` — todas as memórias do projeto e do usuário
- `.claude/rules/` — rules do framework
- `.claude/settings*.json` — configurações
- `.aiox-core/development/agents/` — definições de agentes
- `.aiox-core/development/tasks/` — tasks do framework
- `.aiox-core/development/templates/` — templates do framework
- `.aiox-core/development/workflows/` — workflows do framework
- `.aiox-core/data/` — dados do framework
- `squads/*/squad.yaml` — manifestos de squad
- `docs/stories/` — stories técnicas (leitor é Fabiano + agentes)
- `docs/plans/` — planos internos
- `docs/qa/` — relatórios QA
- `docs/ecosystem/` — playbooks internos
- `.aiox/handoffs/` — artefatos de handoff entre agentes
- Checkpoints, logs, snapshots de sessão
- YAMLs de configuração e manifesto em qualquer lugar
- Código-fonte (`.ts`, `.py`, `.tsx`, `.sql`) — coberto por @qa
- Commits, branches, operações git

## Sempre aciona (artefatos client-facing / públicos)

Estes artefatos sairão da máquina e serão lidos por leitor externo.

### Destinos que ativam o gate

- **Cliente direto** — qualquer cliente ativo no Tarian
- **Cliente do cliente** — audiência final, pacientes, seguidores, compradores
- **Público externo** — site, landing, redes sociais, anúncios, imprensa
- **Terceiros formais** — parceiros, fornecedores, investidores, órgãos reguladores

### Tipos de artefato client-facing

- Copy, posts, roteiros, carrosséis, stories, anúncios (Squad MKT)
- Landing pages, hero sections, manifestos públicos, sites
- Pareceres, contratos, avisos, termos entregues ao cliente (Squad Jurídica)
- Propostas, pitches, decks enviados a prospects (Squad Comercial)
- E-mails, mensagens, newsletters, DMs para cliente ou audiência
- Documentos compartilhados via Drive, Notion ou Canva com leitor externo
- Briefings formais entregues ao cliente final
- Relatórios de performance entregues ao cliente
- Qualquer texto que sai do terminal em forma de entrega formal

## Comportamento dos revisores

### Grafia — apply-and-report (automático no gate)

**O que corrige**

- Ortografia e acentuação
- Concordância verbal e nominal
- Pontuação
- Regência verbal e nominal
- Uso de crase
- Ambiguidades gramaticais óbvias

**Comportamento**

- Corrige direto no arquivo
- Reporta: `"Grafia: correções aplicadas — [lista]"`
- NÃO pede autorização
- NÃO bloqueia a entrega
- Se zero erros, reporta: `"Grafia: nenhuma correção necessária"`

### Dick — on-demand (não automático)

**Quando ativa**

- Comando explícito por Fabiano: `*dick {caminho}`
- Nudge inteligente da Regência (Emrys) em artefatos de leitor leigo externo

**Nudge da Regência (Emrys)**

Em artefatos cujo leitor final é leigo externo (cliente do cliente, público, audiência final), Emrys sinaliza (não força):

> *"Esse vai pro cliente final. Quer que eu chame o Dick antes?"*

Fabiano decide sim ou não em uma palavra. Sem fadiga, sem imposição.

**Artefatos que acionam nudge automático do Emrys**

- Copy final para site, landing, hero section
- Anúncios de tráfego pago
- Posts, roteiros, carrosséis, reels da Squad MKT
- Manifestos, pitches e decks externos
- Pareceres jurídicos traduzidos para leigo
- Newsletters, e-mails marketing, DMs
- Qualquer artefato explicitamente marcado como "vai pro cliente final"

**Comportamento do Dick quando convocado**

- Avalia clareza conceitual para leitor leigo
- Propõe simplificações em lista numerada
- Aguarda decisão: `"aceitar todas / rejeitar todas / parcial [n1, n2]"`
- NUNCA corrige sem autorização

## Gatilho

**Comando formal:** `*gate {caminho-do-arquivo}`

- Qualquer agente Cadarn pode rodar ao concluir um artefato client-facing
- Obrigatório antes de declarar entrega final **quando o artefato é client-facing**
- Inaplicável a artefatos internos — não há gate a rodar

## Enforcement

1. **Grafia é inegociável em client-facing** — nenhum artefato que sai da máquina escapa
2. **Grafia é inaplicável em interno** — não rodar nem por zelo
3. **Emrys intercepta violações** — se um agente declarar artefato client-facing como entregue sem passar pelo gate, Emrys bloqueia e força o gate antes de liberar
4. **Nudge do Dick é dever da Regência** — Emrys deve sinalizar Dick em client-facing de leitor leigo, nunca esquecer, nunca forçar
5. **Dick é domínio soberano de Fabiano** — ninguém além da Regência (em forma de nudge) convoca Dick

## Casos de dúvida

Se ficar na zona cinzenta ("é interno ou client-facing?"), pergunte a Fabiano em uma linha:

> *"Isso vai sair da máquina? Se sim, ativo o gate."*

Na dúvida, o default é **tratar como interno** (sem gate) — o custo de um gate desnecessário é maior que o custo de uma decisão de revisão adiada.

## Relação com outras regras

- Complementa `squad-mkt-insights.md` — copy MKT client-facing passa pelo gate E consulta caderno de insights
- Complementa `specialist-handoff-mandatory.md` — especialista produz, Grafia revisa a forma quando o artefato sai
- Sob autoridade de Emrys (Regência) — violações em client-facing são interceptadas pela Regência

## Severidade

- **MUST** para artefatos client-facing
- **Inaplicável** para artefatos internos

Violação em client-facing compromete a qualidade da entrega Cadarn e fere o ativo intelectual da marca. Aplicar gate em artefato interno compromete a velocidade e o bom senso do framework.

---

*Rule: transversal-review-gate | Criada: 2026-04-11 | Reescrita: 2026-04-11 (simplificação "client-facing only") | Mantenedor: Emrys (Regência) | Severidade: MUST (client-facing) / inaplicável (interno)*
