# Data Engineer Agent Memory (Dara)

## Active Patterns
<!-- Current, verified patterns used by this agent -->

### Key Patterns
- CommonJS (`require`/`module.exports`), NOT ES Modules
- ES2022, Node.js 18+, 2-space indent, single quotes
- Absolute imports always (never relative `../`)
- kebab-case for files, PascalCase for components

### Project Structure
- `.aiox-core/core/` — Core modules
- `packages/db/` — Database packages (if applicable)
- `tests/` — Test suites (mirrors source structure)

### Git Rules
- NEVER push — delegate to @devops
- Conventional commits: `feat:`, `fix:`, `docs:`, `test:`

### Database Conventions
- Schema design follows architect decisions
- RLS policies for row-level security
- Migration scripts with rollback procedures

## Protocolo de Análise de Dados — Data Plugin (absorvido 2026-06-22)

*Extraído do plugin `knowledge-work/data` (Apache 2.0). Foco nas partes relevantes para Dara: SQL patterns + validação.*

### SQL: padrões analíticos canônicos (PostgreSQL/Supabase)

```sql
-- Window functions — ranking e running totals
ROW_NUMBER() OVER (PARTITION BY user_id ORDER BY created_at DESC)
SUM(revenue) OVER (ORDER BY date_col ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) as running_total
AVG(revenue) OVER (ORDER BY date_col ROWS BETWEEN 6 PRECEDING AND CURRENT ROW) as moving_avg_7d
LAG(value, 1) OVER (PARTITION BY entity ORDER BY date_col) as prev_value

-- Pct de total e pct de categoria
revenue / SUM(revenue) OVER () as pct_of_total
revenue / SUM(revenue) OVER (PARTITION BY category) as pct_of_category

-- CTE pattern — legibilidade em 3 camadas
WITH base AS (...), metrics AS (...), summary AS (...)
SELECT * FROM summary ORDER BY metric DESC;
```

### Performance tips (PostgreSQL/Supabase)
- `EXPLAIN ANALYZE` para perfilar queries
- Índices em colunas de filtro/join frequentes
- `EXISTS` sobre `IN` para subqueries correlacionadas
- Índices parciais para filtros comuns
- Divisão segura: `NULLIF(denominador, 0)` em vez de divisão nua

### Validação de dados pré-análise
- Checar nulls inesperados antes de agregar
- Verificar magnitude: valores em faixa razoável?
- Subtotais somam ao total? (aggregation sanity)
- Outliers: investigar antes de remover (pode ser população diferente)

## Promotion Candidates
<!-- Patterns seen across 3+ agents — candidates for CLAUDE.md or .claude/rules/ -->
<!-- Format: - **{pattern}** | Source: {agent} | Detected: {YYYY-MM-DD} -->

## Archived
<!-- Patterns no longer relevant — kept for history -->
<!-- Format: - ~~{pattern}~~ | Archived: {YYYY-MM-DD} | Reason: {reason} -->
