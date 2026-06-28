---

## Task Definition

```yaml
task: createContentStrategy()
responsavel: Pulso (Social Media) + Cadarn (Estrategista)
responsavel_type: Agente
squad: cadarn-marketing
templates:
  - calendario-editorial-tmpl.yaml
tarian_portable: true
depends_on:
  - run-diagnostic (recomendado)
  - create-brand-positioning (recomendado)

description: >
  Estratégia de conteúdo completa: pilares de conteúdo, calendário editorial,
  formatos por canal, frequência, Jornada 5-fases (Kiso) e integração com
  Console S.I.C. (Método Cadarn). Gera o plano que alimenta toda a produção.

Entrada:
  - campo: contexto_estrategia
    tipo: object
    origem: Diagnóstico + Brand Positioning ou Elicitação
    obrigatório: true

Saída:
  - campo: estrategia_conteudo
    tipo: markdown
    destino: File system
    persistido: true

  - campo: calendario_editorial
    tipo: yaml
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. YOLO Mode — Fast (0-1 prompts)
- Diagnóstico e posicionamento já existem
- Gera estratégia + calendário direto
- **Best for:** Renovação mensal do calendário

### 2. Interactive Mode — Balanced (4-6 prompts) **[DEFAULT]**
- Elicita pilares, frequência e objetivos
- **Best for:** Primeiro planejamento estratégico

---

## Workflow — Modo Interactive

### STEP 1 — Fundação Estratégica (elicit)

```yaml
elicit:
  prompt: |
    Para montar a estratégia de conteúdo, preciso definir:
    1. Objetivo principal: alcance / engajamento / conversão / autoridade?
    2. Canais prioritários (máximo 3 para começar)
    3. Frequência possível (posts/semana — ser realista)
    4. A marca tem conteúdo em vídeo? (Reels, YouTube, etc.)
    5. Tem equipe de produção ou é solo?
    6. Período do calendário (30, 60 ou 90 dias?)
```

### STEP 2 — Pilares de Conteúdo (Método Cadarn)

```yaml
action: generate
agent: Cadarn (Estrategista)
framework: Console S.I.C. + 5 Leis Imutáveis
output: pilares
format: |
  PILAR 1 — [nome]: descrição, objetivo de funil, % do calendário
  PILAR 2 — [nome]: descrição, objetivo de funil, % do calendário
  PILAR 3 — [nome]: descrição, objetivo de funil, % do calendário
  PILAR 4 — [nome]: (opcional) descrição, objetivo de funil, % do calendário

  DISTRIBUIÇÃO POR FASE (Jornada 5-fases Kiso):
  Descoberta (30%) | Engajamento (35%) | Conversão (20%) | Retenção (15%)
```

### STEP 3 — Calendário Editorial

```yaml
action: generate
agent: Pulso (Social Media)
template: calendario-editorial-tmpl.yaml
output: calendario_editorial
spec: |
  Para cada slot:
  - Data e dia da semana
  - Canal
  - Pilar de conteúdo
  - Formato (Reel, Carrossel, Stories, Post estático, Live, etc.)
  - Tema/gancho (1 linha)
  - Fase da jornada (Descoberta/Engajamento/Conversão/Retenção)
  - Agente responsável pela criação (Logos, Magnética, Iris, Pixel)
  - Status: [ ] Pendente
```

### STEP 4 — Regras de Canal

```yaml
action: generate
agent: Pulso
sections:
  - instagram:
      formatos: "Reels (60%), Carrossel (25%), Stories (10%), Post (5%)"
      horarios: "Baseado no público — definir com Métrica após 2 semanas"
      hashtags: "Máx 5, alta relevância, teoria de grafos (Kiso)"
  - whatsapp:
      uso: "Lista de transmissão, Status, Catálogo"
      frequencia: "Máx 2x/semana — respeitar canal íntimo"
  - site_blog:
      uso: "SEO long-tail, autoridade, captação orgânica"
  - youtube:
      uso: "Se aplicável — conteúdo longo, autoridade"
```

### STEP 5 — Validação (elicit)

```yaml
elicit:
  prompt: |
    📋 Estratégia + Calendário prontos. Revise:
    1. Os pilares fazem sentido para o negócio?
    2. A frequência é sustentável?
    3. Os formatos são viáveis com a estrutura atual?
    4. Quer ajustar algum tema/gancho?
```

---

## Quality Gates

- [ ] Pilares de conteúdo definidos com % de distribuição
- [ ] Calendário com pelo menos 30 dias preenchidos
- [ ] Cada slot com formato, pilar, fase da jornada e agente responsável
- [ ] Distribuição 30/35/20/15 respeitada (Jornada 5-fases)
- [ ] Máximo 3 canais prioritários
- [ ] Regras de canal documentadas

---

*Squad Cadarn Marketing — Task: Content Strategy*
*Agentes: Cadarn (Estrategista) + Pulso (Social Media)*
