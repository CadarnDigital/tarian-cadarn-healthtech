---

## Task Definition

```yaml
task: mapProcess()
responsavel: Kairos (Gestor de Processos)
responsavel_type: Agente
squad: cadarn-operacional
templates:
  - process-mapping-tmpl.yaml
  - automation-planning-tmpl.yaml
tarian_portable: true

description: >
  Mapeia processo operacional completo seguindo as 4 Fases Bravy:
  documenta fluxo atual, identifica gaps, planeja implementação na ferramenta,
  define automações e estrutura treinamento. Opcionalmente audita todos os
  processos de um departamento.

Entrada:
  - campo: contexto_processo
    tipo: object
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: mapa_processo
    tipo: markdown
    destino: File system
    persistido: true

  - campo: plano_automacoes
    tipo: markdown
    destino: File system
    persistido: true (se automações identificadas)
```

---

## Execution Modes

### 1. YOLO Mode — Fast (0-1 prompts)
- Processo já descrito pelo usuário
- Gera mapeamento + gaps + plano direto
- **Best for:** Processo simples e conhecido

### 2. Interactive Mode — Balanced (4-6 prompts) **[DEFAULT]**
- Elicita processo passo a passo
- Valida cada etapa com o usuário
- **Best for:** Primeiro mapeamento, processo complexo

### 3. Audit Mode — Departamento inteiro
- Percorre os 6 departamentos e lista processos existentes vs ausentes
- **Trigger:** `*audit-processes`

---

## Workflow — Modo Mapeamento (processo único)

### Fase 1 — Elicitação (Documentação Bravy)

**Passo 1: Identidade do Processo**
```
elicit: true
prompt: |
  Vamos mapear um processo. Antes de qualquer ferramenta, preciso
  entender o processo como ele É hoje (não como deveria ser).

  1. Qual processo vamos mapear? (nome)
  2. De qual departamento? (Comercial, Admin/Financeiro, Jurídico, Projetos, RH, Marketing)
  3. Quem é o dono desse processo? (pessoa responsável)
  4. Com que frequência roda? (diário, semanal, mensal, por demanda)
  5. Qual o objetivo do processo em 1 frase?
  6. Quem recebe o resultado? (cliente externo, outro departamento, gestor)
```

**Passo 2: Trigger e Entradas**
```
elicit: true
prompt: |
  Agora o início do processo:

  1. O que DISPARA esse processo? (evento, data, solicitação)
  2. O que precisa estar pronto ANTES de começar?
     (ex: briefing do cliente, aprovação do gestor, dados no sistema)
  3. De onde vêm essas entradas? (email, formulário, WhatsApp, verbal)
```

**Passo 3: Etapas**
```
elicit: true
prompt: |
  Agora o passo a passo. Me descreva cada etapa NA ORDEM que acontece.
  Para cada uma, diga:
  - O que é feito (ação)
  - Quem faz
  - Que ferramenta usa (ClickUp, WhatsApp, planilha, manual)
  - Quanto tempo leva (estimativa)
  - Tem alguma decisão? (se sim/não, o que acontece em cada caminho)

  Pode listar de forma simples. Eu estruturo depois.
```

**Passo 4: Saídas e Problemas**
```
elicit: true
prompt: |
  Para fechar o mapeamento:

  1. O que o processo ENTREGA no final? (documento, notificação, tarefa concluída)
  2. Para quem vai esse resultado?
  3. Qual o prazo esperado (SLA)?
  4. Onde esse processo MAIS falha hoje? (atrasos, erros, retrabalho)
  5. Já tentou automatizar algo? (o que, deu certo?)
```

### Fase 2 — Gerar Mapeamento

```
task: |
  Com os dados coletados, gerar:

  1. FICHA DO PROCESSO:
     - Identidade completa (nome, departamento, dono, frequência, objetivo)
     - Trigger + Entradas
     - Saídas + SLA

  2. FLUXOGRAMA (Mermaid):
     ```mermaid
     flowchart TD
       A[Trigger] --> B[Etapa 1]
       B --> C{Decisão?}
       ...
     ```

  3. TABELA DE ETAPAS:
     | # | Ação | Responsável | Ferramenta | Tempo | Decisão |
     (todas as etapas documentadas)

  4. ANÁLISE DE GAPS (7 perguntas do template):
     - Documentado? Responsáveis claros? Ferramenta? Ritual? Automação? Treinamento? KPIs?
     - Score: X/7

output: mapa-processo-{nome}.md
```

### Fase 3 — Plano de Implementação (Fases 2-4 Bravy)

```
task: |
  Com base no mapeamento e gaps:

  FASE 2 — FERRAMENTA:
  - Onde criar no ClickUp (Space→Folder→List)
  - Statuses recomendados
  - Campos personalizados necessários
  - Views úteis (Board, Calendar, etc.)

  FASE 3 — AUTOMAÇÃO:
  Para cada etapa repetitiva ou propensa a erro:
  - Automação recomendada (Nativa, Make, IA)
  - Prioridade (Matriz Impacto x Esforço)
  - Desenho do fluxo (trigger → steps → output)

  FASE 4 — TREINAMENTO:
  - SOP resumido (máximo 1-2 páginas)
  - Sessão de treinamento (30-60 min)
  - Ritual vinculado (Daily ou Weekly, baseado em maturidade)
  - Período de acompanhamento (2 semanas)

output: plano-implementacao-{nome}.md
```

### Fase 4 — Validação

```
checklist:
  - [ ] Processo documentado como É (não como deveria ser)?
  - [ ] Fluxograma gerado e legível?
  - [ ] Todas as etapas têm responsável?
  - [ ] Gaps identificados com score?
  - [ ] Hierarquia ClickUp definida (Space→Folder→List)?
  - [ ] Automações priorizadas (Matriz Impacto x Esforço)?
  - [ ] Ritual vinculado definido?
  - [ ] SOP tem máximo 1-2 páginas?
  - [ ] 5 Axiomas respeitados?
```

---

## Workflow — Modo Auditoria (departamento/empresa)

### Passo 1
```
elicit: true
prompt: |
  Vou auditar os processos. Para cada departamento, vou listar
  os processos que DEVERIAM existir e verificar se estão mapeados.

  1. Qual escopo? (1 departamento específico ou empresa inteira)
  2. Já usa ferramenta de gestão? (ClickUp, etc.)
  3. Quantos processos estima ter hoje (documentados ou não)?
```

### Passo 2 — Varredura
```
task: |
  Para cada departamento no escopo, listar:

  | Departamento | Processo Esperado | Status | Score |
  |-------------|-------------------|--------|-------|
  | Comercial | Pipeline de vendas | Documentado / Parcial / Ausente | X/7 |
  | Comercial | Qualificação de leads | ... | ... |
  | ... | ... | ... | ... |

  Processos esperados por departamento (referência JP):
  - Comercial: pipeline, qualificação, proposta, follow-up, pós-venda
  - Admin/Financeiro: faturamento, cobrança, pagamentos, contabilidade
  - Jurídico: contratos, compliance, LGPD
  - Projetos: briefing, execução, entrega, review
  - RH: recrutamento, onboarding, avaliação, offboarding
  - Marketing: calendário editorial, produção, publicação, relatório

  RESULTADO:
  - Total processos esperados: X
  - Documentados: X (X%)
  - Parciais: X
  - Ausentes: X
  - Score geral de maturidade

  TOP 3 processos para mapear PRIMEIRO (maior impacto):
  1. {{processo}} — razão
  2. {{processo}} — razão
  3. {{processo}} — razão

output: auditoria-processos-{empresa}.md
```

---

## Output — Arquivos Gerados

### Mapeamento único
```
{output_dir}/
├── mapa-processo-{nome}.md             # Ficha + fluxograma + etapas + gaps
└── plano-implementacao-{nome}.md       # Fases 2-4 Bravy (ferramenta + automação + treino)
```

### Auditoria
```
{output_dir}/
└── auditoria-processos-{empresa}.md    # Varredura completa + priorização
```

**Output dir padrão:** `docs/operacional/processos/`

---

## Integração com Outros Agentes

- **Scala (Líder):** Recebe auditoria para alimentar diagnóstico operacional (KPI-3, KPI-5)
- **Vault (Financeiro):** Processos financeiros (faturamento, cobrança) mapeados aqui
- **Nexus (RH):** Processos de RH (recrutamento, onboarding) mapeados aqui
- **Arc (Client Success):** Processo de onboarding de cliente mapeado e automatizado
- **Coel (Brand Guardian):** Auditoria de tom_de_voz em SOPs que tocam o cliente

---

*Squad Cadarn Operacional — Task v1.0*
*Framework: JP da Bravy — 4 Fases + 5 Axiomas*
