---
task: Roadmap de Validação em 3 Fases
responsavel: Llif
responsavel_type: agent
versao: 1.0
criado_em: 2026-06-28
tier_de_fonte: 🜂 (Anexo A — estado de projeto, a validar)
Entrada: |
  - persona_piloto: corretora / clínica / hospital
  - porte: pequeno / médio / grande
  - ponto_entrada: faturamento / cadastro / conciliação
  - prazo_disponivel: semanas disponíveis para o piloto
Saida: |
  - roadmap_3_fases: roadmap estruturado com critérios de avanço
  - metricas_gate: o que precisa acontecer em cada fase para avançar
Checklist:
  - "[ ] Coletar persona, ponto de entrada e prazo"
  - "[ ] Sinalizar: todo o roadmap é 🜂 (doutrina Cadarn a validar)"
  - "[ ] Incluir critério de avanço (gate) entre fases"
  - "[ ] NÃO prometer resultado antes da Fase 1"
  - "[ ] Identificar quem do cliente precisa estar envolvido em cada fase"
---

# *roadmap-validacao — Roadmap de Validação em 3 Fases

> **AVISO DE TIER EPISTÊMICO:** Todo este roadmap é `[HIPÓTESE CADARN — a validar]`.
> As 3 fases são a doutrina atual — precisam de validação com o primeiro cliente real.

## As 3 Fases

### Fase 1 — Wizard of Oz (Semanas 1-2)
**Conceito:** o cliente vê o resultado como se fosse automatizado; a operação por trás é manual/híbrida. Objetivo: validar se a entrega tem valor antes de automatizar.

**O que acontece:**
- Llif/Cadarn Healthtech opera manualmente o ponto de entrada identificado
- Cliente acompanha o output (relatório, processamento, devolutiva)
- Medir: o cliente percebe valor? Qual a dor que mais incomoda após o Wizard?

**Gate para Fase 2:**
- [ ] O cliente confirmou que o output tem valor?
- [ ] O volume do ponto de entrada está mapeado?
- [ ] Alguma automação foi identificada como prioritária?

**Para [persona]:** adaptar o foco do Wizard — corretora foca em cadastro; clínica foca em glosa administrativa.

### Fase 2 — Design Partner (Semanas 3-6)
**Conceito:** o cliente co-projeta a solução. A Cadarn Healthtech constrói enquanto valida. O cliente é informado de cada decisão de design.

**O que acontece:**
- Mapear o processo completo com o cliente (fluxograma real, não idealizado)
- Identificar os 2-3 pontos de maior impacto
- Construir o primeiro agente/framework funcional para o ponto de entrada
- Testar com dados reais (XML TISS anonimizado ou amostra acordada)

**Gate para Fase 3:**
- [ ] O agente/framework funciona no ambiente real do cliente?
- [ ] O cliente consegue acompanhar sem depender da Cadarn Healthtech para operar?
- [ ] O ROI do ponto de entrada foi validado com dado real?

### Fase 3 — Escala Assistida (Semanas 7-12)
**Conceito:** expansão para outros pontos da operação, com suporte assistido. O cliente assume gradualmente, com a Cadarn Healthtech como backstop.

**O que acontece:**
- Expandir para o segundo ponto de entrada (identificado na Fase 2)
- Documentar o processo (runbook operacional)
- Medir ROI acumulado com dados reais
- Decisão de escala: contrato de operação continuada ou produto instalado

**Gate de conclusão:**
- [ ] O ROI acumulado justifica a escala?
- [ ] O cliente tem autonomia operacional com suporte definido?
- [ ] O contrato de continuidade (BPO ou produto) foi proposto?

## Output Esperado

```
ROADMAP DE VALIDAÇÃO [HIPÓTESE CADARN — a validar]
Cliente: [persona / porte]
Ponto de entrada: [faturamento / cadastro / conciliação]

FASE 1 — WIZARD OF OZ (Semanas 1-2)
  Objetivo: [específico para o ponto de entrada]
  Entregáveis: [lista]
  Gate para avançar: [critérios]
  Quem do cliente: [papel/nome]

FASE 2 — DESIGN PARTNER (Semanas 3-6)
  Objetivo: [específico]
  Entregáveis: [lista]
  Gate para avançar: [critérios]
  Quem do cliente: [papel/nome]

FASE 3 — ESCALA ASSISTIDA (Semanas 7-12)
  Objetivo: [específico]
  Entregáveis: [lista]
  Gate de conclusão: [critérios]
  Decisão: [BPO / produto / encerrar]

⚠️ Premissas: [o que precisa ser verdade para o roadmap funcionar]
🜂 Todo este roadmap precisa de validação com o primeiro cliente real.
```
