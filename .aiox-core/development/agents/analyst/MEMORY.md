# Analyst Agent Memory (Atlas)

## Active Patterns
<!-- Current, verified patterns used by this agent -->

### Key Patterns
- CommonJS (`require`/`module.exports`), NOT ES Modules
- ES2022, Node.js 18+, 2-space indent, single quotes
- Absolute imports always (never relative `../`)
- kebab-case for files, PascalCase for components

### Project Structure
- `.aiox-core/core/` — Core modules (synapse, session, code-intel, orchestration)
- `.aiox-core/development/` — Agents, tasks, templates, scripts
- `docs/research/` — Research outputs (YYYY-MM-DD-slug format)
- `docs/stories/` — Story files (active development)

### Git Rules
- NEVER push — delegate to @devops
- Conventional commits: `feat:`, `fix:`, `docs:`, `test:`, `chore:`, `refactor:`

### Research Conventions
- Output dir: `docs/research/{YYYY-MM-DD}-{slug}/`
- Use tech-search skill for deep research
- Always include sources and methodology

## Protocolo de Análise de Dados — Data Plugin (absorvido 2026-06-22)

*Extraído do plugin `knowledge-work/data` (Apache 2.0). Conteúdo estável e atemporal.*

### Classificação de complexidade da análise

| Tipo | Quando usar | Output esperado |
|---|---|---|
| **Quick** | Métrica única, filtro simples, lookup factual | Número + contexto + query usada |
| **Full** | Multi-dimensional, tendência, comparação | Insight principal + tabelas + metodologia + próximas perguntas |
| **Formal** | Investigação completa para stakeholders | Executive summary + metodologia + findings + caveats + recomendações |

### Checklist de validação antes de apresentar resultado

Antes de apresentar qualquer análise, verificar:
- **Row count sanity** — número de registros faz sentido?
- **Null check** — há nulos inesperados que distorcem o resultado?
- **Magnitude check** — números estão em faixa razoável?
- **Trend continuity** — série temporal tem gaps inesperados?
- **Aggregation logic** — subtotais somam ao total?

Se qualquer checagem levanta dúvida: investigar e sinalizar como caveat.

### Estatísticas descritivas — regras de ouro

- Sempre reportar **média E mediana** juntas para métricas de negócio. Divergência grande = dados com skew.
- Percentis-chave para contar história completa: p25, p50, p75, p90, p99.
- Outliers: **nunca remover automaticamente**. Investigar: erro de dado, valor genuíno extremo, ou população diferente?

### Análise de tendência

- Moving average 7d para dados diários com sazonalidade semanal.
- Comparações: WoW (semana a semana), MoM, YoY. YoY é padrão para negócios com sazonalidade.
- Taxa de crescimento: simples = (atual - anterior) / anterior. CAGR para períodos multi-anuais.

### Caution — correlação ≠ causalidade

Ao encontrar correlação: checar causalidade reversa, variável confusora, coincidência.
- Correto: "Usuários que usam feature X têm 30% mais retenção"
- Incorreto sem mais evidência: "Feature X causa 30% mais retenção"

### Padrões SQL estáveis (PostgreSQL/Supabase)

```sql
-- Cohort retention (padrão canônico)
WITH cohorts AS (
    SELECT user_id, DATE_TRUNC('month', first_activity_date) as cohort_month FROM users
),
activity AS (
    SELECT user_id, DATE_TRUNC('month', activity_date) as activity_month FROM user_activity
)
SELECT c.cohort_month,
    COUNT(DISTINCT c.user_id) as cohort_size,
    COUNT(DISTINCT CASE WHEN a.activity_month = c.cohort_month THEN a.user_id END) as month_0,
    COUNT(DISTINCT CASE WHEN a.activity_month = c.cohort_month + INTERVAL '1 month' THEN a.user_id END) as month_1
FROM cohorts c LEFT JOIN activity a ON c.user_id = a.user_id
GROUP BY c.cohort_month ORDER BY c.cohort_month;

-- Funnel analysis
WITH funnel AS (
    SELECT user_id,
        MAX(CASE WHEN event = 'page_view' THEN 1 ELSE 0 END) as step_1,
        MAX(CASE WHEN event = 'signup_complete' THEN 1 ELSE 0 END) as step_2
    FROM events WHERE event_date >= CURRENT_DATE - INTERVAL '30 days' GROUP BY user_id
)
SELECT COUNT(*) as total, SUM(step_1) as viewed, SUM(step_2) as converted,
    ROUND(100.0 * SUM(step_2) / NULLIF(SUM(step_1), 0), 1) as conversion_pct FROM funnel;

-- Dedup: manter registro mais recente por chave
WITH ranked AS (
    SELECT *, ROW_NUMBER() OVER (PARTITION BY entity_id ORDER BY updated_at DESC) as rn FROM source_table
)
SELECT * FROM ranked WHERE rn = 1;
```

## Promotion Candidates
<!-- Patterns seen across 3+ agents — candidates for CLAUDE.md or .claude/rules/ -->
<!-- Format: - **{pattern}** | Source: {agent} | Detected: {YYYY-MM-DD} -->

## Archived
<!-- Patterns no longer relevant — kept for history -->
<!-- Format: - ~~{pattern}~~ | Archived: {YYYY-MM-DD} | Reason: {reason} -->
