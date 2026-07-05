# Cadarn Healthtech — Guia de Uso Rápido

> 🎋 **Engenharia de Fluxo · Saúde Suplementar**  
> Tarian Cadarn para operação do produto Healthtech. Operado por Fabiano + Gui.

---

## 🚀 **Como começar (5 minutos)**

### Opção 1: Abrir no terminal (alias)
```bash
health
```
Isso abre a sessão Claude do Tarian Healthtech com Llif ativado automaticamente.

### Opção 2: Invocar skill do AIOX Manager
```
@cadarn-healthtech:llif
```

---

## 🎋 **Quem é Llif?**

**Llif** é o Estrategista-Consultor & Arquiteto de Operações em Saúde.

Responsável por:
- 🔍 Diagnósticos de corretoras (20 movimentações cadastrais)
- 🏥 Diagnósticos de clínicas (glosas 30-60 dias, TISS, faturamento)
- 💼 Roteiros de venda consultiva (4 blocos: fiscal, operacional, estratégico)
- 📊 Planilhas de ROI com dados reais do cliente
- 📧 E-mails de convite estruturados
- 🎤 Apresentações comerciais
- 🗺️ Roadmaps de validação (Wizard of Oz → Design Partner)
- 🔄 Crossover (mesmo diagnóstico, dois discursos: corretora × clínica)

---

## 🎯 **Comandos de Llif**

Quando ativado via `@cadarn-healthtech:llif` ou `health`, use:

```
*diagnostico-corretora      → Diagnóstico de corretora (20 itens)
*diagnostico-clinica         → Diagnóstico de clínica (glosas + TISS)
*roteiro-venda-consultiva    → Roteiro 4 blocos
*planilha-roi                → ROI com dados do cliente
*email-convite               → E-mail estruturado (gate obrigatório)
*apresentacao-comercial      → Apresentação (gate obrigatório)
*roadmap-validacao           → Roadmap 3 fases
*crossover                   → Diagnóstico duplo (corretora × clínica)
*help                        → Lista completa de comandos
*exit                        → Encerrar
```

---

## 📚 **Knowledge Base — O que Llif sabe**

### Corpus Técnico (Saúde Suplementar)
Tudo em `.aiox-core/knowledge/domain/`:
- **Cap 01:** Panorama do mercado (regulação ANS, dados macro)
- **Cap 02:** Perfil operacional de corretoras (dores de cadastro, comissão)
- **Cap 03:** Modelo de negócio (Crossover, Efeito Espelho, Insight de Ouro)
- **Cap 04:** Faturamento hospitalar (glosas, TISS, gap de caixa)
- **Cap 05:** Centro de compras e jornada de compra (8 etapas)
- **Cap 06:** Modelo de oferta Cadarn (🜂 **HIPÓTESE a validar**, não fato)
- **Glossário:** Léxico nativo do setor

### DNA do Produto
`.aiox-core/knowledge/produto/`:
- `visao.md` — Visão, missão, posicionamento
- `icp.md` — Perfil ideal de cliente/parceiro
- `roadmap.md` — Roadmap de capacidades
- `tom-de-voz.md` — Voz do produto

### Operacional
`.aiox-core/knowledge/operacional/`:
- `runbook.md` — Procedimentos, onboarding, incidentes

---

## ⚠️ **Regras Obrigatórias**

1. **Domínio > Opinião** — Todo conteúdo ancorado no corpus técnico
2. **Carregar INDEX** — Antes de qualquer tarefa, ler `.aiox-core/knowledge/domain/INDEX.md`
3. **FATO vs HIPÓTESE** — Caps 1-5 = FATO. Cap 6 + ROI 211,7% = HIPÓTESE 🜂 (sempre sinalizar)
4. **Sem invenção** — Fatos vêm do corpus. Inferências sinalizadas com `[INFERÊNCIA — não verificada]`
5. **Tom de voz** — Respeitar `tom-de-voz.md` em toda comunicação

---

## 👥 **Squads Disponíveis**

| Squad | Agentes | Escopo |
|-------|---------|--------|
| **cadarn-healthtech** | Llif | Diagnóstico, ROI, apresentação — principal |
| **cadarn-comercial** | Caio, Camaleão | Pipeline B2B, funil de vendas |
| **cadarn-juridica** | Esp. LGPD | Contratos, LGPD Art. 11 (dados de saúde) |
| **cadarn-operacional** | Account-orchestrator | Onboarding de parceiros |

---

## 📖 **Estrutura do Repositório**

```
tarian-cadarn-healthtech/
├── CLAUDE.md                          ← Configuração técnica completa
├── README.md                          ← Este arquivo
├── README-SETUP.md                    ← Como criar novo Tarian (template)
├── .claude/
│   ├── CLAUDE.md                      ← Rules e configuração do Tarian
│   ├── skills/cadarn-healthtech:llif/ ← Skill invocável de Llif
│   └── rules/                         ← Regras do projeto
├── .aiox-core/
│   ├── constitution.md                ← Constituição do framework AIOX
│   ├── knowledge/
│   │   ├── domain/                    ← Corpus técnico de saúde suplementar
│   │   ├── produto/                   ← DNA, visão, roadmap, tom de voz
│   │   ├── operacional/               ← Runbook de operação
│   │   └── cadarn-method/             ← Método C.A.D.A.R.N.
│   └── development/agents/            ← Definições de agentes
├── squads/
│   ├── cadarn-healthtech/             ← Squad principal (Llif)
│   ├── cadarn-comercial/              ← Cisão comercial
│   ├── cadarn-juridica/               ← Jurídica
│   ├── cadarn-marketing/              ← Marketing
│   └── cadarn-operacional/            ← Operações
└── docs/
    └── stories/                       ← Histórias de desenvolvimento
```

---

## 🔗 **Links Rápidos**

- **Skill de Llif:** `.claude/skills/cadarn-healthtech:llif/SKILL.md`
- **Agent de Llif:** `squads/cadarn-healthtech/agents/llif.md`
- **Domain INDEX:** `.aiox-core/knowledge/domain/INDEX.md`
- **Tom de Voz:** `.aiox-core/knowledge/produto/tom-de-voz-cadarn-healthtech-v1.0.md`
- **Dossiê:** `.aiox-core/knowledge/produto/dossie-marca-cadarn-healthtech-v0.1.md`

---

## ❓ **Próximos Passos**

1. **Ativar Llif:**
   ```bash
   health
   # ou
   @cadarn-healthtech:llif
   ```

2. **Carregar corpus:**
   ```
   Llif pedirá para você escolher a primeira conversa:
   - Delma/corretora (*diagnostico-corretora)?
   - Alexandre/faturamento (*diagnostico-clinica)?
   ```

3. **Usar um comando:**
   ```
   *diagnostico-corretora
   # ou qualquer comando da lista acima
   ```

---

## 📞 **Suporte**

- **Operadores:** Fabiano, Gui
- **Repositório:** github.com/CadarnDigital/tarian-cadarn-healthtech
- **AIOX HQ:** github.com/CadarnDigital/AIOX-Manager
- **Issues:** GitHub Issues no repositório

---

**Última atualização:** 2026-07-05  
**Versão:** 1.0  
**Framework:** Synkra AIOX
