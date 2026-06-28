---
task: Crossover — Mesmo Diagnóstico, Dois Discursos
responsavel: Llif
responsavel_type: agent
versao: 1.0
criado_em: 2026-06-28
tier_de_fonte: 🜂 (posicionamento Cadarn — a validar)
Entrada: |
  - base_diagnostica: resultado de *diagnostico-corretora ou *diagnostico-clinica
  - persona_a: corretora (Integrador / Previsor Atuarial)
  - persona_b: clínica / hospital (Auditor / Defensor de Receita)
Saida: |
  - discurso_corretora: versão do diagnóstico na lente comercial
  - discurso_clinica: versão do diagnóstico na lente de faturamento
  - diferenca_de_linguagem: tabela mostrando os ajustes de vocabulário
Checklist:
  - "[ ] Ter a base diagnóstica (de *diagnostico-corretora ou *diagnostico-clinica)"
  - "[ ] Sinalizar: o posicionamento Crossover é 🜂"
  - "[ ] Manter a mesma dor estrutural nas duas versões"
  - "[ ] Vocabulário nativo de cada persona"
  - "[ ] NÃO inventar dados diferentes — é a mesma base, duas linguagens"
---

# *crossover — Crossover de Posicionamento

> `[HIPÓTESE CADARN — a validar]` O Crossover é o posicionamento estratégico do Efeito Espelho das Ineficiências — duas personas espelhando a mesma Demora, duas linguagens, uma solução.

## Por Que o Crossover Existe

A saúde suplementar tem duas pontas que sofrem da mesma Demora mas não se reconhecem como "o mesmo problema":

- **Corretora:** perde venda porque o cadastro não sai, a guia volta, a comissão não fecha
- **Clínica/Hospital:** perde receita porque a glosa entra, o prazo passa, a contestação não acontece

A dor estrutural é idêntica (a Demora), mas o vocabulário, o locus de controle e o paper-trail são completamente diferentes.

## Os Dois Discursos

### Persona A — Corretora: Integrador / Previsor Atuarial

| Elemento | Corretora |
|---|---|
| Papel no centro de compras | Influenciador/usuário `[fonte: cap-04]` |
| Lente principal | Comercial: carteira, cadastro, sinistro |
| Vocabulário nativo | "guia voltou", "venda perdida", "cadastro travado", "comissão represada" |
| Métrica de dor | Vendas perdidas por atraso, custo de retrabalho de cadastro |
| Gatilho de compra | "quero crescer sem contratar mais pessoas" |
| Frame | Integrador (conecta cliente ao plano) + Previsor (antecipa sinistro da carteira) |

**Exemplo de abertura para corretora:**
> *"Quantas vendas vocês perderam no último mês porque o cadastro não saiu a tempo? A Demora começa aí — e é onde a gente entra."*

### Persona B — Clínica/Hospital: Auditor / Defensor de Receita

| Elemento | Clínica/Hospital |
|---|---|
| Papel no centro de compras | Decisor financeiro / usuário `[fonte: cap-04]` |
| Lente principal | Faturamento: glosa, TISS, contestação, caixa |
| Vocabulário nativo | "lote rejeitado", "campo em desacordo", "prazo de 30 dias", "contestação em aberto" |
| Métrica de dor | Percentual de glosa, gap de caixa, custo de equipe de faturamento |
| Gatilho de compra | "quero reduzir glosa sem contratar mais gente de faturamento" |
| Frame | Auditor (identifica inconsistência antes do envio) + Defensor de Receita (recupera o que é da clínica) |

**Exemplo de abertura para clínica:**
> *"Qual o percentual de guias que voltam da [operadora]? E quanto do tempo da equipe vai para recontestar? A Demora custa mais do que parece no balanço."*

## Workflow de Crossover

### Passo 1 — Identificar a Base Comum

A partir do diagnóstico (corretora ou clínica), extrair a dor estrutural compartilhada:

- Onde exatamente a Demora aparece?
- Qual o custo financeiro estimado (dado do cliente)?
- Qual o processo que está parando?

### Passo 2 — Refratar na Linguagem de Cada Persona

Para cada elemento da base diagnóstica, traduzir:

| Elemento | Corretora (Integrador/Previsor) | Clínica/Hospital (Auditor/Defensor) |
|---|---|---|
| A Demora | "a venda que escapa" | "o faturamento que fica represado" |
| O gargalo | "cadastro travado" | "lote rejeitado" |
| O custo | "comissão não fechada" | "glosa administrativa" |
| A solução | "processo que libera o cadastro no prazo" | "framework que pega a inconsistência antes do envio" |
| O resultado | "mais vendas com a mesma equipe" | "menos glosa, caixa que respira" |

### Passo 3 — Gate No Invention

- [ ] Os dados são os mesmos da base diagnóstica (não inventados por persona)?
- [ ] O posicionamento Crossover está marcado como 🜂?
- [ ] Cada versão usa vocabulário nativo (não importado de slide)?

## Output Esperado

```
CROSSOVER — [base diagnóstica resumida]
Data: [data]

DISCURSO A — CORRETORA (Integrador / Previsor Atuarial)
  Abertura: [texto]
  A Demora que eles conhecem: [vocabulário nativo]
  O que resolvemos: [em linguagem de corretora]
  O resultado: [em linguagem comercial]

DISCURSO B — CLÍNICA/HOSPITAL (Auditor / Defensor de Receita)
  Abertura: [texto]
  A Demora que eles conhecem: [vocabulário nativo]
  O que resolvemos: [em linguagem de faturamento]
  O resultado: [em linguagem de caixa]

TABELA DE DIFERENÇA DE LINGUAGEM
  [tabela elemento × persona A × persona B]

🜂 O posicionamento Crossover é hipótese Cadarn — validar com o primeiro piloto real.
```
