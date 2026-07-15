---
documento: Checkpoint — Sessão Llif & Cadarn Healthtech (21–28 junho 2026)
tipo: resumo-executivo-consolidado
data_sessao: 2026-06-21 a 2026-06-28
status: consolidação para referência (originais inalterados)
consolidado_em: 2026-07-15
nota: "Não altera os arquivos originais. Serve como snapshot da conversa."
---

# Checkpoint — Sessão Llif & Cadarn Healthtech

**Período:** 21–28 de junho de 2026  
**Tema central:** Design do agente Llif, decisões de squad, marca, tom de voz e corpus IA  
**Decisões marteladas:** A, B, C (blueprint)

---

## Resumo Executivo da Sessão

Entre 21 e 28 de junho, você estava:

1. **Nomeando a unidade** — Cadarn Healthtech (marca aprovada 2026-06-22)
2. **Nomeando o agente** — Llif (galês para "fluxo/corrente")
3. **Definindo a jogada** — Engenharia de Fluxo (BPO Tech + IA)
4. **Pedindo pesquisas** — 17 pesquisas health-* para alimentar o Corpus IA
5. **Desenhando automações** — Trio da Eficiência (onboarding, conciliação, sinistralidade)
6. **Martelando decisões de squad** — 3 decisões estruturantes (A, B, C)

---

## 1. Nome & Posicionamento

### Unidade: **Cadarn Healthtech**

| Elemento | Valor |
|----------|-------|
| **Nome** | Cadarn Healthtech (raiz galesa + descriptor) |
| **Posicionamento** | Engenharia de Fluxo para saúde suplementar |
| **Frase-síntese** | "Onde a saúde emperra, nós fazemos fluir." |
| **Símbolo** | Bambu — firme porque flui |
| **Antagonista** | "A Demora" (gargalo, lentidão, cadastro travado) |
| **Tipo de unidade** | 2ª vertical de negócio da Cadarn (não é vertical da Martech) |
| **Status de marca** | v0.1 — em construção (aprovado 2026-06-22 por Samira) |

**Herança:** Martech = Engenharia de Receita (marketing/vendas); Health = Engenharia de Fluxo (operação).

---

### Agente: **Llif**

| Dimensão | Definição |
|----------|-----------|
| **Nome** | Llif (galês: fluxo/corrente) |
| **Herança nomeada** | Casa com galês da Cadarn (Cadarn, Cadw, Emrys, Tarian) |
| **Vocação** | Estrategista-Consultor + Arquiteto de Operações em Saúde |
| **Não é** | Vendedor de software nem SDR |
| **É** | Insider que entende o mercado melhor que o cliente |
| **Status de agente** | Aprovado design; criação pendente (Sonnet) |
| **Namespacing skill** | `cadarn-healthtech:llif` (prepara para cisão comercial) |

---

## 2. As 3 Camadas do Corpus na Mente de Llif

| Camada | Conteúdo | Como vive em Llif |
|--------|----------|-------------------|
| **Domínio** | Caps 1–2 + Glossário (Corpus IA) | Fluência nativa — fala vidas, glosa, TISS, sinistralidade, Fator R sem hesitar |
| **Munição comercial** | Caps 3–4–5 (Corpus IA) | Playbook em confiança — usa agora em validação; cinde para comercial em operação |
| **Doutrina + estado** | Cap 6 + Anexo A (Corpus IA) | A jogada + o backlog vivo; status epistêmico explícito (hipótese, não fato) |

---

## 3. Automações: Trio da Eficiência

A oferta estruturada em 3 produtos encadeados (Entrada → Manutenção → Retenção):

### **Produto 1 — Automação de Onboarding (Entrada)**

Ataca o "Gargalo da Foto de Documento":
- **Problema:** equipe perde horas digitando dados de documentos em foto (WhatsApp)
- **Solução:** OCR com IA extrai foto (RG/CPF/CNH) como JSON estruturado → analista confere (1 min vs 10 de digitação) → RPA digita no portal da operadora
- **Tecnologia:** Claude Vision (Haiku 4.5) + Prompt Caching + Playwright RPA
- **Economia:** ~50 horas/mês devolvidas; 16h → 1h em digitação

### **Produto 2 — Automação de Conciliação (Manutenção/Financeiro)**

Operacionaliza o "Cavalo de Troia":
- **Problema:** corretora não sabe quais vidas foram faturadas (divergências entre base ativa e fatura operadora)
- **Solução:** algoritmo cruza vidas ativas × faturadas da operadora → aponta divergências automaticamente
- **Valor:** recuperação imediata de dinheiro pago por vidas indevidas
- **Entrada de menor atrito:** começa por conciliação de comissões

### **Produto 3 — Consultoria de Sinistralidade (Retenção)**

Capacita decisões estratégicas:
- **Problema:** corretora chega à renovação no escuro (sem dados de uso/sinistralidade)
- **Solução:** dashboards preditivos + comunicação automática de alertas sobre contratos em risco
- **Valor:** corretora munida de argumento técnico; retém contratos que seriam perdidos
- **Complemento:** Regra 5/50 (5% dos beneficiários = ~50% dos custos)

---

## 4. Decisões Marteladas (Blueprint Squad)

| # | Decisão | Conteúdo | Martelo |
|---|---------|----------|---------|
| **A** | Squad vs Standalone | Nasce como **squad `cadarn-healthtech`** com 1 agente (Llif), não standalone | ✅ Fabiano 2026-06-28 |
| **B** | Cânone: "Via 3 Híbrido" | Copiar DNA-EXTRACT + Tom de Voz + Dossiê para squad; Corpus IA bruto fica na HQ como lastro | ✅ Fabiano 2026-06-28 |
| **C** | Namespacing | Skill: `cadarn-healthtech:llif` (namespaced — prepara para cisão comercial com N agentes no futuro) | ✅ Fabiano 2026-06-28 |

**Justificativas:**
- A: cisão comercial já decidida → squad comuta evolução; cânone compartilhado (Tom, Dossiê, DNA) é config de *unidade*
- B: Corpus IA bruto permanece na HQ como lastro histórico; cânone operacional migra com a squad ao tarian-health
- C: prepare a família de agentes; hoje 1 (Llif), amanhã N (comercial, operações, etc)

---

## 5. Tom de Voz (v1.0 — Fechado)

**Herança:** Hermès Tech (técnico sem ser hermético, preciso sem ser frio, estratégico sem ser acadêmico)  
**Diferença vs Martech:** intensidade aspiracional *média* (cliente quer resolver, não transformar)

### Polaridade — O que é / O que não é

| É | Não é |
|---|---|
| Direto | Vendedor de software genérico |
| Técnico e preciso | Cheio de hype tecnológico |
| Confiável — sabe o que faz | Frio ou distante |
| Cirúrgico — nomeia o problema específico | Consultor de PowerPoint |
| Honesto sobre o que entrega | Promessa sem lastro |
| Especialista que propõe diagnóstico conjunto | Quem chega com solução antes de escutar |

### Como falar sobre IA e tecnologia

**Nomeia o que faz — não o que é:**

| Em vez de | Diga |
|-----------|------|
| "inteligência artificial avançada" | "frameworks operacionais que processam os dados" |
| "machine learning" | "squads de agentes que executam cada etapa" |
| "transformação digital" | "a operação cresce sem inchar" |
| "solução completa inovadora" | "um agente auditor que confere tudo" |
| "automatização total" | "elimina o gargalo onde ele aparece" |

### Frases-chave por momento da venda

**Posicionamento:**
> "Onde a saúde emperra, nós fazemos fluir."

**Qualificação (1ª reunião):**
> "A Demora tem um custo. Calculamos junto antes de propor qualquer coisa."

**Proposta de escopo:**
> "Começamos onde dói mais. Depois seguimos por onde ela ainda se esconde."  
> "Use a máquina para conquistar tempo. O humano, para conquistar o cliente."

### Palavras de uso condicionado

**Princípio (martelo Fabiano 2026-06-23):** Sem vetos. Qualquer palavra pode ser usada — desde que haja uma **razão específica** naquele contexto.

| Palavra | Quando pode usar |
|---------|------------------|
| "inovador / inovação" | Ao comparar com processo antigo específico ("o jeito antigo exige digitação; o nosso não") |
| "disruptivo" | Quase nunca. Só se contraste com incumbente específico |
| "eficiência" | Ao quantificar: "reduz de X para Y horas" — nunca como adjetivo solto |
| "substituir pessoas / cortar folha" | Nunca como argumento de venda |
| "transformação" | Só para resultado de longo prazo, nunca como promessa de entrada |

---

## 6. Marca — Dossiê Mestre (v0.1, em construção)

**Missão Oficial (fechada 2026-06-23):**

> "Quem trabalha com saúde conhece um adversário que ninguém colocou no organograma: a Demora. Ela mora na guia que não anda, no cadastro que trava, na venda que escapa porque a resposta chegou tarde, no documento que faltava e ninguém viu a tempo. A Demora não adoece o paciente; ela trava o crescimento de quem cuida dele, porque crescer, no jeito antigo, significa inchar a operação. A Cadarn Healthtech existe para tirar a Demora do caminho. Podemos assumir a operação inteira para você, ou levar a nossa inteligência para dentro da sua: frameworks operacionais que processam os dados, squads de agentes que executam cada etapa e um agente auditor que confere tudo e entrega relatórios de desempenho que orientam a operação e até a gestão da equipe. É a Engenharia de Fluxo. Começamos onde a Demora mais dói hoje, e seguimos por onde ela ainda se esconde. A operação cresce sem inchar. Use a máquina para conquistar tempo. O humano, para conquistar o cliente."

**Antagonista — "A Demora":**
- **NÃO é:** "inimiga da saúde" nem "adoece o paciente"
- **É:** inimiga da *operação/negócio* de quem trabalha com saúde
- **Efeito:** trava o crescimento; no jeito antigo, crescer = inchar a operação
- **Resposta Cadarn:** crescer sem inchar (fluxo + eficiência)

---

## 7. Pesquisas Pedidas (17 arquivos health-*)

As seguintes pesquisas foram solicitadas e executadas (2026-06-26 a 2026-06-27) para alimentar o Corpus IA:

```
docs/pesquisas/2026-06-26_health-pesquisa-001.md
docs/pesquisas/2026-06-26_health-bpo-faturamento.md
docs/pesquisas/2026-06-26_health-comportamento-compra-gpt.md
docs/pesquisas/2026-06-26_health-persona-decisor-gpt.md
docs/pesquisas/2026-06-26_health-perfil-corretoras-gemini-gv.md
docs/pesquisas/2026-06-26_health-perfil-corretoras-gpt.md
docs/pesquisas/2026-06-26_health-perfil-corretoras-gemini-br.md
docs/pesquisas/2026-06-26_health-personas-bpo-gemini.md
docs/pesquisas/2026-06-26_health-concorrentes-bpo-gemini.md
docs/pesquisas/2026-06-26_health-vendas-b2b-gemini.md
docs/pesquisas/2026-06-26_health-modelo-negocio-gpt.md
docs/pesquisas/2026-06-26_health-modelo-negocio-gemini.md
docs/pesquisas/2026-06-26_health-corretoras-quantidade-gv.md
docs/pesquisas/2026-06-27_health-dossie-mesa-gpt.md
docs/pesquisas/2026-06-27_health-dossie-gemini-brasil.md
docs/pesquisas/2026-06-27_health-dossie-estrategico-ia-backoffice-es.md
docs/pesquisas/2026-06-27_health-estrategia-oferta-gemini.md
```

**Consolidadas em:** Corpus IA (9 capítulos + 2 anexos + DNA-EXTRACT.md)

---

## 8. Artefatos Originais (Inalterados)

Todos os arquivos abaixo foram criados/atualizados nesta sessão e permanecem como originais:

| Arquivo | Data | Versão | Status |
|---------|------|--------|--------|
| `design-brief-llif-v1.0.md` | 2026-06-28 | 1.0 | Aprovado |
| `blueprint-squad-cadarn-healthtech-v1.0.md` | 2026-06-28 | 1.0 | Aprovado-completo |
| `tom-de-voz-cadarn-healthtech-v1.0.md` | 2026-06-23 | 1.0 | Fechado |
| `dossie-marca-cadarn-healthtech-v0.1.md` | 2026-06-23 | 0.1 | Em construção |
| `gaps-corpus-auditoria-2026-06-27.md` | 2026-06-27 | — | Auditoria (273 gaps identificados) |
| `prompts-icp-research.md` | — | — | Prompts para pesquisa manual |

**Corpus IA:**
- `00-indice.md` — Índice de 6 capítulos + 2 anexos
- `01-mercado-saude-suplementar.md` — Panorama geral
- `02-corretora-perfil-operacao.md` — Perfil e processos
- `03-corretora-modelo-negocio.md` — Modelo financeiro
- `04-faturamento-saude-clinicas-bpo.md` — Lado do prestador
- `05-decisor-jornada-compra.md` — Personas e jornada
- `06-cadarn-modelo-oferta.md` — Oferta Cadarn (prescritivo)
- `07-anexo-perguntas-estrategicas.md` — Backlog vivo
- `08-anexo-glossario.md` — Dicionário de jargões
- `DNA-EXTRACT.md` — Concentrado 88% confidence (7 dimensões: conceitos, frameworks, regras, anti-patterns, táticas, métricas, vocabulário)

---

## 9. Status Pós-Sessão

| Item | Status |
|------|--------|
| **Marca aprovada** | ✅ Samira, 2026-06-22 |
| **Decisões A, B, C marteladas** | ✅ Fabiano, 2026-06-28 |
| **Tom de Voz fechado** | ✅ Fabiano, 2026-06-23 |
| **Corpus IA consolidado** | ✅ 9 arquivos + índice + DNA-EXTRACT |
| **Pesquisas pedidas (17 files)** | ✅ Concluídas 2026-06-26/27 |
| **Design Brief Llif** | ✅ Aprovado |
| **Criação de agente (Sonnet)** | ⏳ Pendente |
| **Validação de squad** | ⏳ Pendente (*validate-squad cadarn-healthtech) |
| **Martelo de entrada** | ⏳ Pendente (Delma corretora vs Alexandre faturamento) |

---

## 10. Próximas Ações

1. **Fase Sonnet:** Athena extrai DNA → @squad-creator forja persona (YAML + MEMORY-semente) ancorada no Tom v1.0 + Dossiê v0.1
2. **Validação squad:** `*validate-squad cadarn-healthtech` (6/6 checks)
3. **Martelo de entrada:** Fabiano escolhe por qual ponta começar (Delma ou Alexandre)
4. **Primeira conversa:** diagnóstico com persona escolhida

---

**Consolidado em:** 2026-07-15  
**Referência:** Não altera os arquivos originais. Serve como snapshot da conversa para fácil retomada.
