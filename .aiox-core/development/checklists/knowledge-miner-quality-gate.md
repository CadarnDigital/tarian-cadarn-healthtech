# Quality Gate: Knowledge Miner (Athena)

**Checklist ID:** knowledge-miner-quality-gate
**Version:** 1.0
**Purpose:** Validar DNA-EXTRACT.md antes de ser usado para criar agente-clone
**Agent:** @knowledge-miner (Athena)

---

## Blocking (VETO se falhar)

| # | Check | Critério | Veto se falhar | Ação de correção |
|---|-------|----------|----------------|-----------------|
| B1 | Completude de seções | Todas as 7 seções do template presentes | "DNA-EXTRACT incompleto — seção {N} ausente" | Rodar *mine novamente com foco na dimensão faltante |
| B2 | Rastreabilidade | Cada regra/framework tem campo "Fonte" preenchido | "Itens sem rastreabilidade — viola Artigo IV (No Invention)" | Adicionar fonte ou remover item não rastreável |
| B3 | Zero invenção | Nenhum dado sem correspondência no material M2M fonte | "Dados fabricados detectados — remover imediatamente" | Cruzar cada item contra material fonte |
| B4 | Volume mínimo: conceitos | >= 5 conceitos-chave extraídos | "Conceitos insuficientes — material pode ser raso" | Revisar material ou expandir escopo de busca |
| B5 | Volume mínimo: frameworks | >= 2 frameworks/modelos identificados | "Frameworks insuficientes — verificar profundidade do M2M" | Reprocessar com foco em estruturas sequenciais |
| B6 | Volume mínimo: regras | >= 5 regras/princípios extraídos | "Regras insuficientes — especialista sub-representado" | Buscar marcadores linguísticos de convicção |
| B7 | Formato template | Segue estrutura de dna-extract-tmpl.md | "Formato incorreto — não é injetável em agente-clone" | Regenerar usando template correto |
| B8 | Frontmatter válido | Header com specialist_name, domain, source_path, extracted_at | "Metadados de extração ausentes" | Adicionar frontmatter obrigatório |

**Regra:** 100% dos blocking checks DEVEM passar.

---

## Recommended (WARNING se falhar)

| # | Check | Critério | Warning se falhar |
|---|-------|----------|-------------------|
| R1 | Vocabulário signature | >= 5 termos always_use identificados | "Vocabulário fraco — voice_dna do clone será genérica" |
| R2 | Métricas/benchmarks | >= 1 número de referência citado | "Sem benchmarks — agente não terá referências numéricas" |
| R3 | Anti-patterns | >= 3 anti-patterns documentados | "Poucos anti-patterns — agente pode cometer erros do especialista" |
| R4 | Táticas DO/DON'T | >= 5 táticas acionáveis | "Poucas táticas — agente terá pouca orientação prática" |
| R5 | Cross-references | >= 2 conceitos aparecem em múltiplos módulos | "Baixa cross-referência — pode indicar extração superficial" |
| R6 | Confidence score | >= 70% | "Confidence abaixo do ideal — revisar antes de criar agente" |
| R7 | Metadados de extração | Seção extraction_stats preenchida | "Stats ausentes — dificulta auditoria futura" |

**Regra:** >= 80% dos recommended checks devem passar (>= 6 de 7).

---

## Approval Criteria

```text
PASS:     100% blocking + >= 80% recommended
CONDITIONAL: 100% blocking + < 80% recommended (pode publicar com plano de melhoria)
FAIL:     Qualquer blocking falhou (VETO — não usar para criar agente)
```

---

_Checklist Version: 1.0 — Created: 2026-03-20_
