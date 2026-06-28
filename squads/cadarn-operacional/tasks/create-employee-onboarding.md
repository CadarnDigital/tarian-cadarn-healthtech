---

## Task Definition

```yaml
task: createEmployeeOnboarding()
responsavel: Scala (Líder Operacional)
responsavel_type: Agente
squad: cadarn-operacional
template: employee-onboarding-tmpl.yaml
tarian_portable: true

description: >
  Gera um plano de onboarding completo para novo funcionário combinando
  3 frameworks: 5 Cs (Scala), First 100 Days (Arc), Lencioni (Nexus).
  Elicita contexto do cliente/empresa e produz timeline Dia -3 a Dia 100.

Entrada:
  - campo: contexto_empresa
    tipo: object
    origem: Elicitação
    obrigatório: true

  - campo: dados_funcionario
    tipo: object
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: plano_onboarding
    tipo: markdown
    destino: File system
    persistido: true

  - campo: checklist_gestor
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. YOLO Mode — Fast (0-1 prompts)
- Preenche com defaults inteligentes
- Gera plano completo sem perguntar
- **Best for:** Empresa/funcionário já conhecidos, contexto claro

### 2. Interactive Mode — Balanced (5-7 prompts) **[DEFAULT]**
- Elicita contexto passo a passo
- Permite customização por fase
- **Best for:** Primeiro onboarding da empresa, contexto novo

---

## Workflow de Execução

### Fase 0 — Narrativa da Empresa (pré-requisito)

```
check: true
prompt: |
  Antes de criar o onboarding, verificar se o company-narrative já foi preenchido.
  Buscar em: docs/operacional/narrativas/ ou equivalente no projeto do cliente.

  Se NÃO existe:
    → Executar preenchimento do company-narrative-tmpl.yaml com o fundador/CEO
    → Este é o documento-base que alimenta TODO o onboarding
    → Sem ele, as ações de cultura e história ficam genéricas

  Se JÁ existe:
    → Carregar e usar como contexto para as Fases 1-3
```

### Fase 1 — Elicitação de Contexto (Interactive Mode)

**Passo 1: Empresa**
```
elicit: true
prompt: |
  Sobre a empresa que vai receber o funcionário:

  1. Nome da empresa?
  2. Setor/nicho?
  3. Quantas pessoas no time atual?
  4. Quais os valores/cultura declarados? (se houver)
  5. Ferramentas do dia a dia? (ClickUp, Slack, Google, etc.)
  6. Canais de comunicação internos? (WhatsApp, email, etc.)
  7. Já tem rituais fixos? (daily, weekly, etc.)
```

**Passo 2: Funcionário**
```
elicit: true
prompt: |
  Sobre o novo funcionário:

  1. Nome?
  2. Cargo/função?
  3. Quem será o gestor direto?
  4. Data prevista de início?
  5. É remoto, presencial ou híbrido?
  6. Nível de experiência? (júnior, pleno, sênior)
  7. O que a empresa espera dele nos primeiros 90 dias?
```

**Passo 3: Contexto especial**
```
elicit: true
prompt: |
  Alguma situação especial?

  1. É a primeira contratação da empresa? (muda o tom do onboarding)
  2. Substitui alguém que saiu? (cuidado com comparações)
  3. O time tem alguma disfunção conhecida? (conflitos, falta de confiança)
  4. Há urgência na integração? (projeto em andamento)
```

### Fase 2 — Geração do Plano

Após elicitação, executar os 3 agentes em sequência:

#### Step 2.1 — Scala (Estrutura Operacional)
```
agent: lider-operacional
input: contexto_empresa + dados_funcionario
task: |
  Com base no contexto, gerar a camada OPERACIONAL do onboarding:
  - Checklist de Compliance (acessos, equipamento, documentação)
  - Documento de Clarity (expectativas escritas, KPIs 30/60/90)
  - Plano de Culture (como transmitir valores)
  - Definição de Connection (buddy, pontos de contato)
  - Agenda de Checkback (reviews 14d, 30d, 45d, 60d, 90d)
output: camada_operacional
```

#### Step 2.2 — Arc (Jornada Emocional)
```
agent: client-success
input: contexto_empresa + dados_funcionario + camada_operacional
task: |
  Com base no contexto, gerar a camada de EXPERIÊNCIA do onboarding:
  - Mapeamento das 8 fases adaptadas (AFFIRM a ADVOCATE)
  - Touchpoints emocionais por fase (ligação CEO, kit boas-vindas, celebração)
  - Canais de comunicação por fase (mínimo 3)
  - Momentos de risco (buyer's remorse, semana 2-3 de adaptação)
  - KPIs de experiência por fase
output: camada_experiencia
```

#### Step 2.3 — Nexus (Integração Cultural)
```
agent: rh-pessoas
input: contexto_empresa + dados_funcionario + camada_operacional + camada_experiencia
task: |
  Com base no contexto, gerar a camada CULTURAL do onboarding:
  - Plano de Working Genius assessment (quando aplicar, como usar resultado)
  - Avaliação Ideal Team Player (checkpoints Humble/Hungry/Smart)
  - Briefing de Five Dysfunctions para o novo membro (simplificado)
  - Recomendações de integração com dinâmica atual do time
  - Alertas culturais específicos (se há disfunções conhecidas)
output: camada_cultural
```

### Fase 3 — Montagem e Entrega

#### Step 3.1 — Unificar Camadas
```
task: |
  Combinar as 3 camadas numa timeline única usando o template
  employee-onboarding-tmpl.yaml como base.
  Adaptar cada ação ao contexto específico da empresa/funcionário.
  Resolver conflitos de agenda entre as camadas.
output: plano_unificado.md
```

#### Step 3.2 — Gerar Checklist do Gestor
```
task: |
  Extrair do plano unificado um checklist executável para o gestor direto.
  Formato: lista de checkboxes com data, ação e responsável.
  Ordenado cronologicamente (Dia -3 a Dia 100).
output: checklist_onboarding.md
```

#### Step 3.3 — Gerar Comunicações Prontas
```
task: |
  Gerar templates de comunicação prontos para uso:
  - Mensagem de boas-vindas (WhatsApp/SMS) — Dia -3
  - Email com cronograma da primeira semana — Dia -1
  - Script da ligação do líder — Dia -2
  - Mensagem de celebração de 100 dias — Dia 100
output: comunicacoes_onboarding.md
```

### Fase 4 — Validação

```
checklist:
  - [ ] Todas as datas estão corretas e relativas à data de início?
  - [ ] Nenhuma ação depende só de email (mínimo 3 canais)?
  - [ ] Expectativas estão ESCRITAS, não apenas verbais?
  - [ ] Working Genius assessment está agendado antes do dia 15?
  - [ ] Review de 90 dias tem critério GO/NO-GO claro?
  - [ ] Checklist do gestor está em formato executável?
  - [ ] Comunicações prontas estão no tom da empresa (não genéricas)?
```

---

## Output — Arquivos Gerados

```
{output_dir}/
├── plano-onboarding-{funcionario}.md     # Timeline completa Dia -3 a Dia 100
├── checklist-gestor-{funcionario}.md      # Checklist executável para o gestor
└── comunicacoes-{funcionario}.md          # Templates de mensagens prontos
```

**Output dir padrão:** `docs/operacional/onboarding/` (ou equivalente no projeto do cliente)

---

## Notas para Replicação Tarian

Ao instalar este processo num Tarian de cliente:

1. **Parametrizar:** Substituir todos os `{{params}}` do template com dados reais do cliente
2. **Adaptar tom:** Comunicações devem refletir a marca do CLIENTE, não da Cadarn
3. **Escalar:** Para empresas com >10 funcionários, considerar automação via ClickUp (Kairos)
4. **Medir:** Implementar KPIs desde o primeiro onboarding para ter baseline

---

*Squad Cadarn Operacional — Task v1.0*
*Combina: Scala (5 Cs) + Arc (First 100 Days) + Nexus (Lencioni)*
