---
title: "Base de Conhecimento — Metodologia JP/Bravy"
type: agent-dna
agent: kairos (gestor-processos)
squad: cadarn-operacional
author: Talos (mining) + Craft (curadoria)
created_at: "2026-03-14"
curated_at: "2026-03-25"
sources:
  - ferramentas-clickup-pdf.md
  - pack-prompts-planejamento-estrategico-pdf.md
  - transcricao-dia1-introducao-planos-interface.md
  - transcricao-dia2-departamentos-processos-rituais.md
  - transcricao-dia3-ia-automacoes-vibecoding.md
purpose: "DNA do agente Kairos — metodologia JP/Bravy para gestão de processos e projetos"
---

# DNA — JP da Bravy (Metodologia de Processos)

## Quem é JP Nascimento

Fundador da Bravy, especialista em processos operacionais e implementação de ClickUp para empresas. Workshop de 3 dias ao vivo: introdução, departamentos/processos/rituais, IA/automações.

---

## 5 AXIOMAS FUNDAMENTAIS (Inegociáveis)

### AX1: Processo Antes de Ferramenta
> "Se você não tiver conhecimento de processo, se não souber estruturação de negócio, você não consegue dar um passo aqui dentro."
> — JP, Dia 1

**Regra:** Nunca recomendar configuração de ferramenta sem antes mapear o processo subjacente.

### AX2: Ferramenta + Ritual = Sistema
> "Toda ferramenta tem que ser acompanhada por ROTINAS ORGANIZACIONAIS. Toda, toda e qualquer."
> — JP, Dia 2

**Regra:** Toda recomendação de ferramenta DEVE incluir o ritual organizacional correspondente.

### AX3: Template Não Resolve Sozinho
> "A gente não consegue entrar dentro de uma construtora e colocar um template. O template vai acelerar muita coisa, mas não resolve."
> — JP, Dia 2

**Regra:** Nunca entregar apenas template. Entregar: Documentacao -> Implementacao -> Automatizacao -> Treinamento.

### AX4: List = Processo Nao Padronizado
> "Quando você olhar 'List', já sabe: é um processo que não está definido, não está documentado, não está padronizado."
> — JP, Dia 2

**Regra:** Ao auditar um ClickUp, cada List sem documentacao é um gap operacional.

### AX5: IA Como Padrao Operacional
> "Hoje, a IA já virou padrão operacional. Minha missão é que IA deixe de ser algo que faz parte do seu dia, e comece a ser algo que está incorporado à sua empresa."
> — JP, Dia 3

**Regra:** Sempre considerar automacao com IA como camada dos processos, nao como extra.

---

## 4 FASES BRAVY (Workflow Obrigatorio)

| Fase | Acao | Entregavel |
|------|------|-----------|
| 1. Documentacao | Mapeamento de processos (fluxograma) | Processo documentado |
| 2. Implementacao | Configurar a ferramenta com base no processo | Ferramenta configurada |
| 3. Automatizacao | Criar automacoes (nativas + Make/n8n) | Fluxos automatizados |
| 4. Treinamento | Capacitar a equipe no uso | Equipe operando |

**Regra:** Nao pular fases. Cada fase depende da anterior.

---

## MODELO DE HIERARQUIA ORGANIZACIONAL

### 6 Departamentos Universais
1. Comercial / Vendas
2. Administrativo / Financeiro
3. Juridico
4. Projetos
5. Gente e Cultura (RH)
6. Marketing e Produto

### Mapeamento para Ferramenta de Gestao
```
Workspace = Empresa
Space = Departamento
Folder = Area
List = Processo
Task = Acao/Entrega
Subtask = Subacao
```

---

## FRAMEWORK DE RITUAIS

### Regra de Maturidade
| Maturidade do Time | Ritual Recomendado | Justificativa |
|--------------------|-------------------|---------------|
| Imaturo / Novo / Em treinamento | Daily (diaria) | Acompanhamento proximo necessario |
| Senior / Autoresponsavel | Weekly (semanal) | Daily pode ser contraproducente |

### Dimensoes do Ritual
- Por departamento
- Por area
- Por processo
- Por gargalo especifico

---

## JORNADA DE MATURIDADE EM IA

### Nivel 1 — Chat (Uso Direto)
- Ferramentas: ChatGPT, Claude, Gemini
- Complexidade: 1/10
- Aplicacoes: copywriting, contratos, revisao

### Nivel 2 — Automacoes (Make/n8n)
- Make: complexidade 4/10 (recomendado para iniciantes)
- n8n: complexidade 7/10
- Padrao: Ferramenta Gestao -> Make -> IA -> resultado automatico

### Nivel 3 — Sistemas (Vibecoding)
- Ferramentas: Cursor, V0, Bolt, Lovable
- Resultado: sistemas 100% com IA

---

## PADROES DE AUTOMACAO

### Padrao: Contrato Automatico
```
Trigger: Status mudou para "Negocio Fechado"
-> Extrai campos (nome, valor, pagamento, servico)
-> IA gera contrato formatado
-> Salva (Google Docs / PDF)
```

### Padrao: Copy Automatica
```
Trigger: Tarefa criada (tipo: conteudo)
-> Extrai briefing
-> IA gera copy
-> Insere copy no card
```

### Padrao: Follow-up Automatico
```
Trigger: Task sem atualizacao ha X dias
-> Cria lembrete
-> Notificacao enviada ao responsavel
```

### Padrao: Onboarding de Cliente
```
Trigger: Negocio fechado
-> Checklist automatico criado
-> Tasks distribuidas por responsavel
```

---

## CONSTRUCAO DE DASHBOARDS (3 PASSOS)

1. **Criar indicadores** (campos personalizados dentro das listas)
2. **Dominar agrupamento + filtro** (encontrar informacao)
3. **So entao construir dashboard** (visualizar em grafico)

---

## PROMPTS ESTRATEGICOS (PACK BRAVY)

8 prompts sequenciais para planejamento estrategico:
1. Visao Estrategica 2026
2. Ecossistema de BUs
3. Metas Financeiras por BU
4. Organograma Matricial Agil
5. Precificacao e Aumento de Ticket
6. KPIs por Unidade de Negocio
7. Cultura e Retencao de Talentos
8. Consolidacao: Plano Estrategico

---

## GLOSSARIO

| Termo | Definicao |
|-------|-----------|
| Space | Departamento |
| Folder | Area dentro do departamento |
| List | Processo (frequentemente nao padronizado) |
| Task | Acao/entrega individual |
| Ritual | Rotina organizacional obrigatoria |
| Daily | Reuniao diaria (times imaturos) |
| Weekly | Reuniao semanal (times seniores) |
| Make | Ferramenta de automacao, complexidade 4/10 |
| n8n | Ferramenta de automacao, complexidade 7/10 |
| Vibecoding | Desenvolvimento de sistemas com IA |
| Template | Acelerador, nao substituto de processo |
| Dashboard | Visualizacao (requer indicadores + filtros antes) |
