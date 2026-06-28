---
task: Apresentação Comercial (deck ou documento)
responsavel: Llif
responsavel_type: agent
versao: 1.0
criado_em: 2026-06-28
tier_de_fonte: Tom de Voz v1.0 + Dossiê v0.1 + FATO (Caps 1-5) + 🜂 (Cap 6/Anexo A)
gate_transversal: OBRIGATÓRIO (Grafia + Dick sob demanda)
Entrada: |
  - persona: corretora / clínica / hospital / faturamento
  - porte: pequeno / médio / grande
  - diagnostico: resultado do diagnóstico (se disponível) ou hipótese
  - tipo_entrega: BPO / produto / piloto
  - formato: deck (slides) ou documento texto
Saida: |
  - apresentacao: estrutura completa (6 seções)
  - copy_cada_secao: texto pronto para cada slide/seção
Checklist:
  - "[ ] Coletar persona, porte, diagnóstico e tipo de entrega"
  - "[ ] Estruturar em 6 seções (sem prometer número antes do ROI)"
  - "[ ] Seção de ROI usa planilha real do cliente OU referência 🜂 marcada"
  - "[ ] IA entra na seção Operacional (passo 3), nunca na abertura"
  - "[ ] Gate transversal obrigatório antes de qualquer envio"
---

# *apresentacao-comercial — Apresentação Comercial

Produz estrutura e copy de apresentação comercial. GATE TRANSVERSAL OBRIGATÓRIO.

## ALERTA DE GATE

> Peça client-facing — passa por Grafia antes de qualquer envio.
> Nudge para Dick obrigatório (Emrys sinaliza a Fabiano).

## Estrutura da Apresentação (6 Seções)

### Seção 1 — Quem é a Cadarn Healthtech
**Objetivo:** estabelecer credibilidade sem hype.

**Copy base:**
> "Cadarn Healthtech — Engenharia de Fluxo para saúde suplementar.
> Trabalhamos com corretoras e unidades de faturamento que querem
> crescer sem precisar contratar para isso."

Incluir: origem Cadarn, vínculo com o Método C.A.D.A.R.N.

### Seção 2 — O Problema que Resolvemos (a Demora)
**Objetivo:** nomear a dor específica antes de qualquer solução.

**Para corretora:**
> "A Demora mora no cadastro que trava, na guia que volta, na venda que escapa
> porque a resposta chegou tarde. Ela não adoece o paciente — ela trava o
> negócio de quem cuida dele."

**Para clínica/hospital:**
> "68% das glosas são administrativas: campo errado, código desatualizado,
> prazo vencido. Receita que deveria ter entrado, não entrou." `[fonte: cap-03]`

### Seção 3 — Diagnóstico do Cliente (dados reais)
**Objetivo:** mostrar que entendemos o caso específico.

Se diagnóstico foi feito: inserir os dados reais.
Se não foi feito: usar referências de mercado sinalizadas + propor diagnóstico como próximo passo.

### Seção 4 — Como Resolvemos (Operacional — IA no passo 3)
**Objetivo:** descrever o processo, não a tecnologia.

**Estrutura:**
1. Entrada: onde entramos na operação (ponto específico)
2. Processo: o que acontece (frameworks operacionais + agentes)
3. Saída: o que muda (relatório, tempo, volume)

**IA entra aqui:**
> "Usamos frameworks operacionais que processam os dados e squads de agentes
> que executam cada etapa. O resultado é um agente auditor que confere tudo
> e entrega relatório de desempenho."

### Seção 5 — Resultado / ROI
**Objetivo:** mostrar o retorno estimado com os dados do cliente.

**Se planilha-roi foi feita:** usar o ROI calculado com dados reais.
**Se não foi feita:**

> "[HIPÓTESE CADARN — a validar] Internamente, modelamos ROI de 211,7% no
> primeiro ano. Mas o número que importa é o seu — e calculamos juntos
> com os dados reais da operação."

**NUNCA:** apresentar 211,7% como resultado garantido ou benchmark.

### Seção 6 — Próximos Passos
**Objetivo:** proposta clara de piloto ou diagnóstico.

> "Proposta: piloto de [prazo] focado em [escopo]. Você acompanha em tempo
> real. Só avançamos para o contrato se os números justificarem."

## Regras de Copy (Tom de Voz v1.0)

- Sem travessão (—)
- Sem "parceria" antes do resultado
- Sem ROI 211,7% como promessa
- Sem "solução end-to-end" genérica
- IA entra na seção 4, nunca na seção 1 ou 2

## Gate

- [ ] Grafia revisou?
- [ ] Nudge para Dick sinalizado a Fabiano?
- [ ] ROI 211,7%: marcado como 🜂 se presente?
- [ ] Nenhuma promessa sem dado do cliente?
