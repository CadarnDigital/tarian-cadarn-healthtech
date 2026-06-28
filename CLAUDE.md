# Tarian — Cadarn Healthtech

> Este é um Tarian Cadarn para produto próprio: sistema de operação digital da Cadarn para o produto **Cadarn Healthtech**.
> Operado por: Fabiano + Gui | Framework: Synkra AIOX

## Produto

- **Nome:** Cadarn Healthtech
- **Domínio:** Saúde Suplementar
- **Vertical:** Healthtech
- **Operador:** Fabiano + Gui
- **Repositório:** CadarnDigital/tarian-cadarn-healthtech
- **Status:** em operação

## Knowledge Base

Carregar SEMPRE o INDEX de domínio antes de qualquer tarefa:
```
.aiox-core/knowledge/domain/INDEX.md
```

### Domain Knowledge (corpus técnico)
Conhecimento especializado do domínio em `.aiox-core/knowledge/domain/`:
- Regulamentação, protocolos, normas do setor
- Benchmarks, pesquisas, dados do mercado
- Carregar conforme INDEX indica por tipo de tarefa

### Produto Knowledge (DNA do produto)
Decisões e identidade do produto em `.aiox-core/knowledge/produto/`:
- `visao.md` — visão, missão, posicionamento
- `icp.md` — perfil do usuário/parceiro ideal
- `roadmap.md` — roadmap de capacidades
- `tom-de-voz.md` — voz do produto

### Operacional (como operar)
Procedimentos em `.aiox-core/knowledge/operacional/`:
- `runbook.md` — procedimentos de operação, onboarding, incidentes

### Cadarn Method (compartilhado)
Frameworks da Cadarn em `.aiox-core/knowledge/cadarn-method/`:
- `metodo-cadarn.md` — As 6 letras C.A.D.A.R.N.
- `funil-5-fases.md` — Atração → Autoridade → Validação → Conversão → Base

## Regras Obrigatórias

1. **Domínio > Opinião** — Todo conteúdo ancorado no corpus técnico do domínio
2. **Carregar INDEX** — Antes de qualquer tarefa, ler `domain/INDEX.md`
3. **Voz do produto** — O produto tem voz própria. Respeitar `tom-de-voz.md`.
4. **Sem invenção de dados** — Fatos sobre domínio vêm do corpus. Inferências são sinalizadas.
5. **Responder em português brasileiro**

## Sistema de Agentes

### Ativação
Use `@agent-name` ou `/AIOX:agents:agent-name`.

### Squads Ativas

| Squad | Agentes ativos | Escopo no produto |
|-------|---------------|-------------------|
| `cadarn-healthtech` | **Llif** | Diagnóstico, ROI, roteiro de venda, apresentação comercial — agente principal do produto |
| `cadarn-comercial` | Caio, Camaleão, Gestor-funil | Pipeline de vendas B2B Healthtech |
| `cadarn-juridica` | Especialista LGPD | Contratos, LGPD Art. 11 (dados de saúde), conformidade TISS |
| `cadarn-operacional` | Account-orchestrator, CS | Onboarding de parceiros (corretoras e clínicas) |

### Skill do produto
```
/cadarn-healthtech:llif
```

### Squad de Produto
Definida em `squads/cadarn-healthtech/` — Llif operacional.

## Git

- Conventional Commits: `feat:`, `fix:`, `docs:`, `refactor:`
- Mensagem em inglês, modo imperativo
- Push EXCLUSIVO via @devops (Gage)

## Cowork

- Project: "Tarian Cadarn Healthtech — Operação"
- Knowledge base carregada: corpus de domínio + DNA do produto
- Conectores: conforme stack do produto

## Convenções de Código

- Python: type hints, Black + Ruff
- TypeScript: sem `any`, componentes arrow function
- SQL: migrations versionadas via Supabase
