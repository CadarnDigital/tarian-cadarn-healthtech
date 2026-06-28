# One Question Per Turn — Pergunta Única por Turno

## Regra Principal

**Um agente Cadarn NUNCA empilha perguntas no mesmo turno.** Uma pergunta = um turno = uma resposta esperada de Fabiano.

Se duas decisões pendentes existem no mesmo momento, o agente apresenta **apenas a primeira**, aguarda o martelo, e só então apresenta a segunda no próximo turno.

## Por que esta regra existe

Empilhar perguntas no mesmo turno cria três falhas concretas:

1. **Sobrecarga cognitiva.** O humano segura uma pergunta de cada vez na memória de trabalho. Empilhar duas obriga a guardar a primeira na cabeça enquanto processa a segunda — aumenta erro e demora.

2. **Resposta ambígua aplicada na pergunta errada.** Se a primeira pergunta usa `A/B/C/D` e a segunda usa `sim/não`, uma resposta curta como "B" ou "sim" pode ser aplicada no campo errado. O agente parte pra ação acreditando ter martelo, sem ter.

3. **Pergunta secundária passa batido.** Quando uma pergunta é apresentada como "pergunta de clareza" no meio de uma proposta principal, o foco do leitor vai pro item dominante. A segunda pergunta vira ruído visual, é esquecida, e o item correspondente segue **sem martelo de Fabiano**. Resultado: o agente improvisa ou aplica default, e a decisão entra no projeto sem aprovação. **Mesma raiz da invenção sem base empírica** — forma diferente, falha equivalente.

## Aplicação

### O que conta como "empilhar"

- Pergunta A/B/C/D + pergunta sim/não no mesmo turno.
- Pergunta principal + "pergunta de clareza" no mesmo turno.
- Bullet escondido com `Diga só sim ou não` no fim de uma mensagem que já tem opções.
- Pergunta retórica que de fato espera resposta + pergunta direta.
- Item da agenda explicitamente seguido de "e mais uma coisa rápida".

### O que NÃO conta como empilhar (exceção única)

**Sub-decisão condicional encadeada** — quando a segunda pergunta só faz sentido condicionalmente à primeira e é parte intrínseca da mesma decisão.

**Exemplo válido:**
> *"Manter copy atual ou reescrever? Se reescrever, prefere tom A ou B?"*

Aqui é uma única decisão com galho condicional. Conta como uma pergunta.

**Exemplo INVÁLIDO (continua sendo empilhamento):**
> *"Doctrine onde — fim da Home ou abertura do Método? Aliás, o mantra B3 também sai dessa sessão? Diga só sim ou não."*

São duas decisões independentes. Empilhamento clássico.

### Como o agente lida com a segunda pergunta

A segunda pergunta não some — fica registrada:

- Em **task** (TaskCreate) com status `pending`, descrição clara da pergunta pendente.
- Em **handoff artifact** se ocorre troca de agente.
- Como **bullet de "próximas decisões"** se a sessão tem agenda visível.

No próximo turno, o agente puxa a pergunta registrada e apresenta sozinha.

## Enforcement

- **Emrys (Regência) intercepta empilhamento** em qualquer mensagem de qualquer agente. Se um agente tentar enviar duas perguntas, Emrys segura a segunda e devolve só a primeira.
- **Auto-detecção pelo agente:** antes de enviar uma mensagem com pergunta, o agente conta quantos pontos de interrogação requerem martelo. Se for >1 e não for sub-decisão condicional, reescreve a mensagem com só a primeira.
- **Em Távola:** essa rule reforça `tavola-turn-by-turn.md`. Empilhar pergunta dentro de turno de Távola é violação dupla.

## Relação com outras regras

| Rule | Relação |
|---|---|
| `tavola-turn-by-turn.md` | Esta rule estende o princípio dela pra TODA interação, não apenas Távolas. Em Távolas, ambas valem. |
| `anti-impersonation-fail-loud.md` | Mesma raiz: agente não improvisa, espera martelo explícito. Empilhar pergunta abre brecha pra martelo aplicado errado, equivalente a inventar sem base. |
| `feedback_one_question.md` (MEMORY) | Promovido para rule formal. Era preferência registrada → vira regra com enforcement. |
| `specialist-handoff-mandatory.md` | Quando especialista para e devolve pergunta a Fabiano, devolve UMA pergunta. |

## Severidade

**MUST** — aplicável a TODOS os agentes Cadarn em qualquer interação com Fabiano (Forja, MKT, Comercial, Conselho, Ops, Jurídica, transversais Grafia/Dick/Coel, Emrys/Regência).

Violação compromete governança: decisões entram no projeto sem martelo, agentes improvisam baseado em respostas ambíguas, e a fronteira entre "proposta da mesa" e "decisão de Fabiano" se borra.

## Origem

Incidente Mesa Site Cadarn × Imobiliário, 2026-04-25 (Sessão de revisão pós-pivot 18/04).

Emrys, ao apresentar a proposta "Tríade como TRÊS COMANDOS" com 4 opções (A/B/C/D), enfiou no meio da mesma mensagem uma "pergunta de clareza" sobre o mantra B3 com formato sim/não. Fabiano flagrou em tempo real:

> *"tem um momento que faz uma pergunta pedindo para dizer sim ou não e depois tem um momento de texto e outras opções, consegue entender como isso confunde um humano e pode até mesmo passar batido?"*

A rule foi proposta por Emrys após autoanálise, aprovada por Fabiano em 3 pontos (nome, severidade MUST, exceção única) e formalizada nesta sessão.

---

*Rule: one-question-per-turn | Criada: 2026-04-25 | Promovida de: feedback_one_question.md | Autoridade: Fabiano + Emrys | Severidade: MUST*
