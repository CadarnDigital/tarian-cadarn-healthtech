---
paths:
  - "docs/clientes/**"
  - "squads/plano-tatico-cadarn/**"
---
# Plano Tático CADARN — Isolamento Multi-Cliente (MUST)

## Regra Principal

**Todo agente da squad `plano-tatico-cadarn` opera sobre EXATAMENTE 1 cliente ativo por sessão.** Dados de clientes diferentes NUNCA se cruzam. Misturar contextos é violação grave da governança da squad.

A squad é projetada para ser **reutilizável** entre clientes — os agentes (persona, lógica, princípios) são imutáveis; os dados (artefatos, validações, decisões) são estritamente isolados por cliente.

## Por que esta regra existe

A jornada CADARN (6 capítulos) produz artefatos sensíveis: diagnóstico financeiro, vulnerabilidades estratégicas, decisões de posicionamento, métricas internas. Vazamento entre clientes implicaria:

1. **Quebra de confidencialidade** — dado de cliente A aparecendo em material de cliente B é falha grave e potencialmente jurídica
2. **Decisão contaminada** — agente que mistura contextos pode aplicar padrão de um cliente em outro inadequadamente
3. **Perda de credibilidade** — colaborador futuro que detectar vazamento perde confiança no framework inteiro

A squad foi desenhada multi-cliente desde a fundação justamente para evitar esse risco — esta rule formaliza o isolamento.

## Arquitetura do Isolamento

```
IMUTÁVEL (agentes + lógica)        MUTÁVEL (dados por cliente)
──────────────────────────         ──────────────────────────
squads/plano-tatico-cadarn/        docs/clientes/{slug}/cadarn/
  agents/                            cap-01-clareza/
    c-claritate.md                     cap-01-pdf-robusto.md
    {outros agentes}                 cap-02-arquitetura/
  templates/                           arquitetura-tatica.md
  data/                              cap-03-dados/
  memory/                              validacao-dados.md
                                     cap-04-acao/
                                       plano-acao.md
                                     cap-05-rastreio/
                                       metricas-rastreio.md
                                     cap-06-norma/
                                       protocolo-norma.md
                                     _meta/
                                       cliente.yaml
                                       handoffs.log
```

## Protocolo Obrigatório por Agente

### Step 1 — Identificação do cliente ativo

ANTES de qualquer trabalho substantivo, o agente DEVE identificar o cliente ativo. Hierarquia de identificação:

1. **Variável de contexto explícita** — `*set-cliente {slug}` foi chamado nesta sessão
2. **Frontmatter de artefato em leitura** — o agente está revisando um artefato e o frontmatter declara o cliente
3. **Pergunta a Fabiano** — quando nenhuma das anteriores resolve

**NUNCA presumir cliente.** Em dúvida → parar e perguntar.

### Step 2 — Operação isolada

- **LER apenas** `docs/clientes/{slug-ativo}/cadarn/`
- **ESCREVER apenas** em `docs/clientes/{slug-ativo}/cadarn/`
- **NUNCA acessar** path de outro cliente, mesmo para "consultar referência"
- **NUNCA copiar** dado de cliente A para cliente B sem autorização explícita de Fabiano

### Step 3 — Sinalização de troca

Se durante uma sessão a tarefa muda para outro cliente, o agente DEVE:

1. Encerrar o trabalho do cliente anterior (salvar estado, fechar artefato)
2. Comunicar explicitamente: *"Trocando contexto: {cliente A} → {cliente B}"*
3. Confirmar o novo cliente com Fabiano antes de prosseguir
4. Aplicar Step 1 novamente

### Step 4 — Atualização do handoffs.log

Toda mudança de estado em artefato (criação, validação, entrega) gera entrada em:
```
docs/clientes/{slug}/cadarn/_meta/handoffs.log
```

Formato de entrada:
```
{YYYY-MM-DD HH:MM} | {agente} | {capitulo} | {acao} | {artefato} | {status}
```

Exemplo:
```
2026-05-12 14:30 | claritate | cap-01-clareza | criado | cap-01-pdf-robusto.md | rascunho
2026-05-12 15:45 | claritate | cap-01-clareza | validado | cap-01-pdf-robusto.md | entregue
```

## Estrutura de Cada Cliente

Quando um cliente entra na jornada CADARN, o agente cria a estrutura inicial:

```
docs/clientes/{slug}/cadarn/
  _meta/
    cliente.yaml          # Frontmatter do cliente
    handoffs.log          # Log de transições
  cap-01-clareza/         # Criado quando Cap. 1 começa
    cap-01-pdf-robusto.md   # Artefato final
  cap-02-arquitetura/     # Criado quando Cap. 2 começa
    arquitetura-tatica.md
  ...
```

Frontmatter mínimo de `_meta/cliente.yaml`:

```yaml
slug: {kebab-case-sem-acentos}
nome: "{Nome do cliente / projeto}"
segmento: "{segmento principal}"
data_inicio: "{YYYY-MM-DD}"
capitulo_atual: 0      # 0 = pré-intake (Sonda) pendente; avança a 1 quando a Sonda concluir ou Fabiano dispensar
status: ativo
responsavel_cadarn: "Fabiano"
```

## Anti-patterns

```
❌ "Vou consultar como ficou o Briefing do Alex pra inspirar o do Vinicius"
   → VIOLAÇÃO. Cliente B não acessa dado de cliente A. Use o template.

❌ "O agente lembrou de um padrão que viu em outro cliente"
   → VIOLAÇÃO se vier de memória de cliente específico.
   ✅ OK se vier da memória persistente do AGENTE (squads/.../memory/),
      onde só entram aprendizados generalizáveis sem dado identificável.

❌ "Esqueci de chamar *set-cliente e fui escrevendo direto"
   → VIOLAÇÃO. Agente DEVE parar e identificar cliente antes.

❌ "Vou aproveitar que tô na sessão do Alex pra responder rapidinho
   uma pergunta do Vinicius"
   → VIOLAÇÃO. Trocar de cliente exige sinalização explícita + nova
   confirmação.
```

## Aprendizado Cruzado (permitido com restrição)

A memória persistente de cada agente (`squads/plano-tatico-cadarn/memory/{agente}.md`) pode acumular **padrões generalizáveis** observados entre clientes — desde que:

- **NÃO** contenha dado identificável de cliente específico
- **NÃO** mencione cifras, nomes, slugs, segmentos específicos ligados a cliente real
- **Apenas** registre padrões abstratos (ex: "em segmento X, vulnerabilidade Y é recorrente")

Exemplo válido na memória do Claritate:
> "Em clientes de procedimento único de alto ticket, a hierarquia de
> criticidade frequentemente coloca Perdas Invisíveis (recompra/upsell
> ausente) acima de Perdas Visíveis."

Exemplo INVÁLIDO:
> "No cliente Alex, identificamos R$ 12k/mês de perda invisível em..."

## Relação com outras rules

| Rule | Relação |
|---|---|
| `anti-impersonation-fail-loud.md` | Quando agente não tem certeza do cliente ativo, FAIL LOUD — pergunta, não inventa |
| `one-question-per-turn.md` | Pergunta sobre cliente é uma pergunta, vale a regra |
| `specialist-handoff-mandatory.md` | Sub-agentes spawnados pelo lead herdam o cliente ativo do lead |
| `no-promessa-sem-lastro.md` | Lastro empírico do Objetivo CADARN é do cliente ativo, não cruzado |
| `atlas-save-mandatory.md` | Pesquisa do Atlas salva em `_inbox/` é cross-cliente; aplicação ao caso é por cliente |

## Severidade

**MUST** — Violação compromete confidencialidade, governança e credibilidade da Cadarn. Toda violação detectada exige:

1. Investigação imediata da extensão do vazamento
2. Notificação a Fabiano
3. Correção do artefato afetado
4. Registro do incidente
5. Revisão do agente envolvido (memória, lógica) para evitar repetição

## Aplicabilidade

Aplica-se a **TODOS** os agentes da squad `plano-tatico-cadarn`, presentes e futuros. Aplica-se também a qualquer agente externo invocado pela squad (ex: Atlas chamado por Claritate para pesquisa) durante o tempo em que opera no contexto de um cliente da squad.

---

*Rule: plano-tatico-cadarn-multi-cliente | Criada: 2026-05-12 | Origem: Fundação da Squad Plano Tático CADARN | Autoridade: Fabiano + Mesa Cadarn (Morgan, Aria, Cosmo) | Severidade: MUST*
