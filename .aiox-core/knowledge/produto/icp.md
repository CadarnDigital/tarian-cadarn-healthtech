# ICP — Cadarn Healthtech

> Fonte: Corpus IA caps 02-05, DNA-EXTRACT

## ICP Primário — Corretora de Planos de Saúde

**Perfil:** PME corretora de planos de saúde, ES e Brasil
**Dor central:** Cadastro de beneficiários manual, comissões desconciliadas, venda perdida por demora no processo

**Centro de compras (3 papéis):**
- **Econômico:** proprietário-gestor (autoridade final)
- **Técnico:** gerente operacional (validador do processo)
- **Usuário:** analista de cadastro/comissão

**Gatilho de compra:** Perda de comissão por erro de cadastro; cliente cancelando por demora; crescimento travado por backoffice manual

**Oferta de entrada:** Diagnóstico de 20 movimentações (Raio-X de cadastro) — baixo risco, alto sinal

---

## ICP Secundário — Clínica / Hospital

**Perfil:** Clínica ou hospital de médio porte com faturamento interno
**Dor central:** Glosas (68% administrativas, evitáveis), gap de caixa 32 dias, rejeição de guias TISS

**Centro de compras (3 papéis):**
- **Econômico:** diretoria financeira
- **Técnico:** coordenador de faturamento / TI
- **Usuário:** equipe de faturamento TISS

**Gatilho de compra:** Glosa acima de 7%; caixa represado; auditoria ANS pendente

**Oferta de entrada:** Raio-X de glosas (análise de lote XML TISS anonimizado) — prova técnica antes de qualquer compromisso

---

## Anti-ICP

- Operadoras de plano (são reguladoras, não clientes)
- Corretoras de grande porte com TI próprio robusto
- Clínicas sem faturamento TISS (sem o problema central)

---

## Dados de referência do mercado

- Glosa média: 7-18% do faturamento bruto (68% de natureza administrativa — evitáveis) `[fonte: cap-04]`
- Gap de caixa médio: 32 dias `[fonte: cap-04]`
- Reajuste <30 vidas: 14,24% (2024) `[fonte: cap-02]`
- VCMH médio: 15,1% `[fonte: cap-01]`

---

## LGPD Art. 11 — alerta permanente

Dados de beneficiários e guias TISS são **dados sensíveis de saúde**.
Gate @aegis obrigatório antes de qualquer flow com dados reais.
