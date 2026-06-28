---

## Task Definition

```yaml
task: runLgpdAudit()
responsavel: Shield (Especialista LGPD)
responsavel_type: Agente
squad: cadarn-juridica
templates:
  - lgpd-audit-tmpl.yaml
tarian_portable: true

description: >
  Auditoria completa de compliance LGPD para agências Martech e seus
  clientes. Verifica bases legais, subprocessadores, consentimento,
  políticas, incidentes e gera relatório com gaps e plano de ação.

Entrada:
  - campo: contexto_auditoria
    tipo: enum [martech, imobiliaria, whatsapp, cookies, site, campanha]
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: relatorio_lgpd
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Checklist Rápido (1-2 prompts)
- Checklist por contexto, sem aprofundamento
- **Trigger:** `*checklist {tipo: martech | imobiliaria | whatsapp | cookies}`

### 2. Auditoria Completa (4-6 prompts) **[DEFAULT]**
- Pipeline 7 etapas com relatório detalhado
- **Trigger:** `*auditar {operação, site ou campanha}`

### 3. Gerar Documento (2-3 prompts)
- Política de privacidade, cookies, LIA, RIPD, cláusulas
- **Trigger:** `*gerar {tipo de documento}`

---

## Workflow — Auditoria Completa

### Fase 1 — Escopo

**Passo 1: Contexto**
```
elicit: true
prompt: |
  🛡️ Auditoria LGPD — Shield

  1. O que será auditado? (site, app, campanha, operação interna, contrato)
  2. Quem é o controlador dos dados? (sua empresa ou cliente)
  3. Tipos de dados pessoais tratados? (nome, e-mail, CPF, localização, etc.)
  4. Ferramentas/plataformas usadas? (Meta, Google, Supabase, WhatsApp, IA, etc.)
  5. Já tem política de privacidade publicada? (sim/não)
```

### Fase 2 — Pipeline de 7 Etapas

```
task: |
  Executar pipeline de auditoria:

  ETAPA 1 — MAPEAMENTO DE DADOS
  - Quais dados pessoais são coletados
  - Por quais canais (site, WhatsApp, formulários, ads)
  - Onde são armazenados (banco, planilha, CRM)

  ETAPA 2 — BASES LEGAIS (Art. 7 LGPD)
  - Para cada tratamento: qual base legal?
  - Consentimento necessário? Coletado corretamente?
  - Legítimo interesse documentado (LIA)?

  ETAPA 3 — SUBPROCESSADORES
  - Lista de todos os terceiros que recebem dados
  - DPA verificado para cada um?
  - Transferência internacional? Base legal (Art. 33)?

  ETAPA 4 — DIREITOS DOS TITULARES (Art. 18)
  - Canal de atendimento existe?
  - Prazo de resposta definido (15 dias)?
  - Processo de exclusão implementado?

  ETAPA 5 — SEGURANÇA (Art. 46)
  - Criptografia em trânsito e repouso?
  - Controle de acesso (quem vê o quê)?
  - Plano de incidentes (notificação em 48h)?

  ETAPA 6 — DOCUMENTAÇÃO
  - Política de privacidade atualizada?
  - Registro de atividades de tratamento (ROPA)?
  - Termos de uso atualizados?

  ETAPA 7 — IA E AUTOMAÇÃO
  - Dados pessoais em interfaces web de IA? (PROIBIDO sem opt-out)
  - API com zero data retention?
  - Disclosure de uso de IA ao cliente?

  Para cada etapa: CONFORME / NÃO CONFORME / PARCIAL
```

### Fase 3 — Relatório

```
task: |
  Gerar relatório usando template lgpd-audit-tmpl.yaml:

  1. Resumo Executivo
  2. Score geral: X/7 etapas conformes
  3. Detalhamento por etapa
  4. Gaps críticos (ordenados por risco)
  5. Plano de ação (máx 5 itens prioritários)
  6. Documentos a gerar (política, termos, LIA, etc.)
  7. Disclaimer obrigatório

output: auditoria-lgpd-{contexto}-{data}.md
```

---

## Output

```
{output_dir}/
├── auditoria-lgpd-{contexto}-{data}.md     # Relatório completo
├── checklist-lgpd-{tipo}-{data}.md          # Checklist (modo rápido)
└── politica-privacidade-{empresa}-{data}.md # Documento gerado (modo gerar)
```

**Output dir padrão:** `docs/juridico/lgpd/`

---

*Squad Cadarn Jurídica — Task v1.0*
*Framework: LGPD (Lei 13.709/2018) + Bruno Bioni (Data Privacy Brasil)*
