---

## Task Definition

```yaml
task: mapClientJourney()
responsavel: Arc (Client Success)
responsavel_type: Agente
squad: cadarn-operacional
templates:
  - client-journey-8phases-tmpl.yaml
  - client-onboarding-first100days-tmpl.yaml
tarian_portable: true

description: >
  Mapeia a jornada do cliente nas 8 fases (Coleman), diagnostica em qual fase
  está, identifica gaps e gera plano de onboarding First 100 Days personalizado.

Entrada:
  - campo: contexto_empresa
    tipo: object
    origem: Elicitação
    obrigatório: true

  - campo: dados_cliente
    tipo: object
    origem: Elicitação
    obrigatório: true (para onboarding) | false (para diagnóstico genérico)

Saída:
  - campo: diagnostico_jornada
    tipo: markdown
    destino: File system
    persistido: true

  - campo: plano_onboarding
    tipo: markdown
    destino: File system
    persistido: true (se cliente específico)
```

---

## Execution Modes

### 1. Diagnóstico — Mapear estado atual
- Analisa jornada genérica da empresa (não cliente específico)
- Identifica em quais fases a empresa é forte/fraca
- Gera recomendações de melhoria por fase
- **Trigger:** `*mapear-jornada` (sem argumento)

### 2. Onboarding — Cliente específico **[DEFAULT com argumento]**
- Elicita dados do cliente
- Gera plano First 100 Days personalizado com timeline
- **Trigger:** `*mapear-jornada {cliente}` ou `*onboarding-cliente {cliente}`

### 3. Fase — Diagnóstico pontual
- Identifica fase atual de um cliente e recomenda ações
- **Trigger:** `*fase {cliente}`

---

## Workflow — Modo Diagnóstico (genérico)

### Fase 1 — Elicitação

**Passo 1: A Empresa**
```
elicit: true
prompt: |
  Vamos mapear como sua empresa conduz a jornada do cliente.

  1. Qual o serviço/produto principal?
  2. Ticket médio?
  3. Ciclo de venda médio (dias)?
  4. Quantos clientes ativos?
  5. Taxa de churn atual (se sabe)?
  6. Quem cuida do pós-venda hoje? (pessoa, cargo)
```

**Passo 2: Por Fase**
```
elicit: true
prompt: |
  Agora vou percorrer as 8 fases e perguntar o que vocês fazem em cada uma.

  FASE 1 — ASSESS (cliente pesquisando):
  - Como o cliente te encontra? (Google, indicação, redes, etc.)
  - Tem conteúdo educativo publicado? (blog, vídeo, etc.)
  - Como é o primeiro contato? (formulário, WhatsApp, ligação)

  FASE 2 — ADMIT (momento da compra):
  - O que acontece quando o cliente assina?
  - Quem faz o contato de boas-vindas?
  - Quanto tempo entre assinar e receber primeiro contato?

  FASE 3 — AFFIRM (0-48h):
  - O cliente recebe algo nas primeiras 24h?
  - Envia cronograma de próximos passos?
  - Usa mais de 1 canal (email + WhatsApp + vídeo)?

  (continuar para as 8 fases)
```

### Fase 2 — Diagnóstico

```
task: |
  Com base nas respostas, gerar diagnóstico por fase:

  Para cada fase (1-8):
  - STATUS: Saudável / Alerta / Crítico / Inexistente
  - EVIDÊNCIA: o que a empresa faz (ou não faz)
  - GAPS: touchpoints ausentes, canais não utilizados
  - IMPACTO: como esse gap afeta retenção/receita
  - RECOMENDAÇÃO: ação prioritária para melhorar

  RESUMO:
  - Fases mais fortes
  - Fases mais fracas (prioridade de correção)
  - Estimativa de impacto: "Se corrigir AFFIRM, churn pode cair X%"
  - Quick wins (ações de baixo esforço e alto impacto)

output: diagnostico-jornada-{empresa}.md
```

---

## Workflow — Modo Onboarding (cliente específico)

### Fase 1 — Elicitação

**Passo 1: O Cliente**
```
elicit: true
prompt: |
  Vamos criar o plano de onboarding para um cliente específico.

  1. Nome do cliente / empresa?
  2. Serviço contratado?
  3. Valor do contrato?
  4. Data de fechamento?
  5. Quem é o gestor de conta?
  6. Quem são os stakeholders do lado do cliente?
  7. Alguma situação especial? (urgência, substituição de fornecedor, etc.)
```

**Passo 2: Contexto**
```
elicit: true
prompt: |
  Para personalizar o onboarding:

  1. O que o cliente mais valoriza? (velocidade, qualidade, transparência, etc.)
  2. Qual o resultado que ele espera nos primeiros 90 dias?
  3. Tem alguma preocupação específica expressa durante a venda?
  4. Canal preferido de comunicação? (WhatsApp, email, ligação)
  5. Quem da equipe vai atender este cliente?
```

### Fase 2 — Geração do Plano

```
task: |
  Usar o template client-onboarding-first100days-tmpl.yaml como base.
  Personalizar CADA ação com:
  - Nome do cliente e stakeholders
  - Canais preferidos
  - Resultado esperado específico
  - Equipe de atendimento

  Gerar:
  1. Timeline completa Dia 0 a Dia 100 (todas as ações com data, responsável, canal)
  2. Checklist do gestor de conta (checkboxes executáveis)
  3. Templates de comunicação prontos:
     - Mensagem de boas-vindas (WhatsApp)
     - Email de kickoff
     - Script do vídeo personalizado
     - Mensagem de celebração (ACCOMPLISH)
     - Mensagem de marco 100 dias

output:
  - plano-onboarding-{cliente}.md
  - checklist-gestor-{cliente}.md
  - comunicacoes-{cliente}.md
```

### Fase 3 — Validação

```
checklist:
  - [ ] Contato em <24h está garantido (ação AF-01/AF-02)?
  - [ ] Mínimo 3 canais na fase AFFIRM?
  - [ ] Kickoff agendado na semana 1?
  - [ ] Entrega parcial planejada antes do dia 21?
  - [ ] Review de 30 dias no calendário?
  - [ ] KPIs definidos por fase?
  - [ ] Templates de comunicação personalizados (não genéricos)?
  - [ ] Celebração de ACCOMPLISH planejada?
  - [ ] Indicação NÃO é pedida diretamente?
```

---

## Workflow — Modo Fase (diagnóstico pontual)

```
task: |
  Para o cliente {nome}:

  1. Percorrer fases 1-8 com perguntas rápidas
  2. Identificar fase ATUAL (última com critérios atendidos)
  3. Listar:
     - Fase atual + evidências
     - Riscos da fase atual
     - 3 ações prioritárias para avançar para a próxima fase
     - KPIs a monitorar

output: diagnostico-fase-{cliente}.md
```

---

## Output — Arquivos Gerados

### Diagnóstico (genérico)
```
{output_dir}/
└── diagnostico-jornada-{empresa}.md
```

### Onboarding (cliente específico)
```
{output_dir}/
├── plano-onboarding-{cliente}.md       # Timeline Dia 0 a 100
├── checklist-gestor-{cliente}.md       # Checklist executável
└── comunicacoes-{cliente}.md           # Templates de mensagens
```

**Output dir padrão:** `docs/operacional/client-success/` (ou equivalente no projeto do cliente)

---

## Integração com Outros Agentes

- **Scala (Líder):** Recebe KPIs de client success para dashboard operacional
- **Nexus (RH):** Aplica mesma lógica de 8 fases para employee onboarding
- **Kairos (Processos):** Automatiza touchpoints recorrentes via ClickUp + Make
- **Vault (Financeiro):** Churn impacta MRR — alertar se churn >10%
- **Coel (Brand Guardian):** `brand_touchpoints` em cada comunicação para auditoria

---

*Squad Cadarn Operacional — Task v1.0*
*Framework: Joey Coleman — Never Lose a Customer Again (First 100 Days)*
