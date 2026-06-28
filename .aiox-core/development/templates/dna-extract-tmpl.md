---
template_id: dna-extract-tmpl
version: "1.0"
purpose: "Template para DNA-EXTRACT.md — inteligência consolidada de um especialista, pronta para injeção em agente-clone"
created_at: "2026-03-20"
agent: knowledge-miner
---

# DNA-EXTRACT: {specialist_name}

> **Domínio:** {domain}
> **Fonte:** {source_path}
> **Módulos processados:** {module_count}
> **Extraído em:** {extracted_at}
> **Minerador:** Athena (knowledge-miner)

---

## 1. Conceitos-Chave

> Definições e termos fundamentais do especialista. Cada entrada é um conceito que o agente-clone DEVE conhecer.

| Conceito | Definição | Contexto de uso |
|----------|-----------|-----------------|
| {conceito_1} | {definição} | {quando usar} |
| {conceito_2} | {definição} | {quando usar} |
| ... | ... | ... |

---

## 2. Frameworks e Modelos

> Estruturas reutilizáveis criadas ou ensinadas pelo especialista. Cada framework deve ter nome, etapas e quando aplicar.

### 2.1 {framework_name}

- **Origem:** {módulo/aula onde aparece}
- **Propósito:** {o que resolve}
- **Etapas:**
  1. {etapa_1}
  2. {etapa_2}
  3. {etapa_3}
- **Quando aplicar:** {contexto}
- **Resultado esperado:** {output}

### 2.2 {framework_name_2}

_(repetir estrutura)_

---

## 3. Regras e Princípios

> O que o especialista defende como verdade inegociável. Cada regra deve ser acionável.

| # | Regra | Justificativa | Fonte |
|---|-------|---------------|-------|
| 1 | {regra} | {por que é importante} | {módulo/aula} |
| 2 | {regra} | {justificativa} | {fonte} |
| ... | ... | ... | ... |

---

## 4. Anti-Patterns

> O que o especialista condena. Erros, práticas ruins, armadilhas comuns.

| # | Anti-Pattern | Por que é ruim | O que fazer em vez |
|---|-------------|----------------|---------------------|
| 1 | {erro} | {consequência} | {alternativa correta} |
| 2 | {erro} | {consequência} | {alternativa} |
| ... | ... | ... | ... |

---

## 5. Táticas Acionáveis

> Do/don't com contexto de quando aplicar. Separadas por categoria.

### Categoria: {categoria_1}

| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| {tática} | DO | {contexto} | {como executar} |
| {tática} | DON'T | {contexto} | {por que evitar} |

### Categoria: {categoria_2}

_(repetir estrutura)_

---

## 6. Métricas e Benchmarks

> Números de referência citados pelo especialista. Incluir contexto para não serem aplicados fora de escopo.

| Métrica | Valor/Range | Contexto | Fonte |
|---------|-------------|----------|-------|
| {métrica} | {valor} | {quando se aplica} | {módulo} |
| ... | ... | ... | ... |

---

## 7. Vocabulário Signature

> Termos e expressões recorrentes que definem a voz do especialista. Essencial para voice_dna do agente-clone.

### Termos que SEMPRE usa
- **{termo_1}** — {significado no contexto do especialista}
- **{termo_2}** — {significado}

### Expressões recorrentes
- "{expressão_1}"
- "{expressão_2}"

### Termos que NUNCA usa (ou condena)
- **{termo_proibido_1}** — {por que evita}
- **{termo_proibido_2}** — {por que evita}

### Metáforas e analogias frequentes
- "{metáfora_1}" — {contexto}
- "{metáfora_2}" — {contexto}

---

## Metadados de Extração

```yaml
extraction_stats:
  total_files_processed: {N}
  total_lines_analyzed: {N}
  concepts_extracted: {N}
  frameworks_extracted: {N}
  rules_extracted: {N}
  anti_patterns_extracted: {N}
  tactics_extracted: {N}
  metrics_extracted: {N}
  vocabulary_terms: {N}
  dedup_removals: {N}
  confidence_score: "{0-100}%"
```

---

_Extraído por Athena (knowledge-miner) v1.0 — {extracted_at}_
