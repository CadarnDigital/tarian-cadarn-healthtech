---
task: E-mail de Convite para Diagnóstico ou Piloto
responsavel: Llif
responsavel_type: agent
versao: 1.0
criado_em: 2026-06-28
tier_de_fonte: Tom de Voz v1.0 + frases por momento da venda
gate_transversal: OBRIGATÓRIO antes de envio (Grafia + Dick sob demanda)
Entrada: |
  - destinatario_persona: gestor operacional / decisor financeiro
  - ponto_de_entrada: corretora / clínica / faturamento
  - contexto_aproximacao: indicação / warm outbound / frio
  - nome_destinatario: nome do contato (se disponível)
  - empresa: nome da empresa (se disponível)
Saida: |
  - email_convite: e-mail completo (assunto + corpo + assinatura)
  - variantes: 2 versões (curta e extensa) quando aplicável
Checklist:
  - "[ ] Coletar persona, ponto de entrada e contexto"
  - "[ ] Calibrar tom: gestor operacional (dor concreta) vs decisor financeiro (resultado de negócio)"
  - "[ ] Nomear a Demora com precisão — NÃO citar IA na abertura"
  - "[ ] CTA claro e único (diagnóstico de 30 minutos)"
  - "[ ] Sem travessão (—) em copy (Tom de Voz v1.0)"
  - "[ ] Gate transversal antes de entregar para envio (Grafia obrigatório)"
---

# *email-convite — E-mail de Convite para Diagnóstico ou Piloto

Produz e-mail de convite client-facing. GATE TRANSVERSAL OBRIGATÓRIO antes de qualquer envio.

## ALERTA DE GATE

> Esta é uma peça client-facing. Antes de usar, Grafia deve revisar.
> Ativar: `*gate squads/cadarn-healthtech/tasks/[arquivo gerado]`
> Dick: nudge automático (leitor pode ser leigo — Emrys sinaliza a Fabiano)

## Protocolo de Elicitação

```
1. "O e-mail vai para gestor operacional ou decisor financeiro?"
2. "É corretora, clínica ou faturamento hospitalar?"
3. "Como chegou até esse contato — indicação, warm outbound ou frio?"
4. "Tem o nome e a empresa?"
```

## Calibração por Persona

| Persona | Gatilho principal | Tom |
|---|---|---|
| Gestor operacional | Dor concreta: "a guia voltou", "o cadastro travou" | Direto, processo |
| Decisor financeiro | Resultado de negócio: "receita represada", "venda que não fechou" | Resultado, negócio |

## Templates Base

### Template A — Gestor Operacional (dor concreta)

```
Assunto: [nome], quanto tempo a equipe passa refazendo o que já foi feito?

[nome],

Uma pergunta direta: no último mês, quantas guias voltaram da [operadora]?
E quantas horas da sua equipe foram para recontestar?

Meu nome é [nome], da Cadarn Healtech. Trabalhamos com corretoras e clínicas
de saúde suplementar que estão cansadas de perder tempo com o mesmo problema.

Não venho com solução. Venho com um diagnóstico de 30 minutos: olhamos
juntos onde a operação está parando e o que seria resolvível sem mudar
o sistema que já existe.

Sem compromisso. Só clareza.

Você teria 30 minutos esta semana?

[assinatura]
```

### Template B — Decisor Financeiro (resultado de negócio)

```
Assunto: [nome], quanto está represado no faturamento de [empresa]?

[nome],

No mercado de saúde suplementar, 68% das glosas são administrativas.
Campo errado, código desatualizado, prazo vencido. Receita que deveria
ter entrado, não entrou.

A Cadarn Healtech trabalha com gestores que querem resolver esse
gargalo sem precisar contratar mais pessoas.

Proponho uma conversa de 30 minutos: analisamos os números de [empresa]
e mapeamos o que está represado e o que seria recuperável.

Sem compromisso de contrato — só de clareza.

Você teria disponibilidade esta semana?

[assinatura]
```

### Template C — Pós-diagnóstico (proposta de piloto)

```
Assunto: Próximo passo — piloto [empresa]

[nome],

Com base no que conversamos, o ponto de entrada mais direto é [gargalo].

Nossa proposta: um piloto de [prazo] focado em [escopo]. Você acompanha
os resultados em tempo real. Só avançamos se os números justificarem.

Estou disponível para detalhar na próxima semana. O que funciona melhor
para você?

[assinatura]
```

## Regras de Tom (Tom de Voz v1.0)

- **SEM travessão (—) em copy** — marca de texto gerado por IA
- **SEM "parceria"** antes do piloto estar rodando
- **SEM "solução end-to-end"** sem desdobrar o que cada etapa cobre
- **SEM "garantimos conformidade"** — nomear o processo, não dar garantia genérica
- **SEM IA abrindo a mensagem** — nomear o problema, não a tecnologia
- Usar VCMH, glosa, TISS no corpo quando relevante para a persona

## Gate Antes de Entregar

- [ ] Grafia revisou ortografia e gramática?
- [ ] Sem travessão no copy?
- [ ] CTA único e claro (30 minutos)?
- [ ] Nenhuma promessa de resultado sem dado?
- [ ] Nudge para Dick sinalizado a Fabiano (leitor externo)?
