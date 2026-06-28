# Spawn Briefing — Cláusula No Invention Obrigatória

## Regra Principal

**Todo spawn briefing de agente que recebe dados de cliente ou opera em deliberação estratégica DEVE incluir explicitamente a cláusula No Invention.** A ausência da cláusula torna o spawn não-conforme com Art. IV da Constitution.

O agente spawned DEVE sinalizar inferências com a tag `[INFERÊNCIA — não verificada]` imediatamente após a afirmação. Fatos não sinalizados são tratados como verdades do briefing — omitir a sinalização é equivalente a inventar.

## Cláusula Obrigatória (texto canônico)

Incluir verbatim em todo spawn briefing elegível:

```
REGRA DE INVENÇÃO: Todo fato que você afirmar sobre o cliente deve
vir do briefing que você recebeu. Se for inferência, sinalize como
[INFERÊNCIA — não verificada]. Não é permitido derivar fatos de
contexto geral sem sinalização explícita. Art. IV Constitution.
```

## Quando esta regra se aplica

Qualquer chamada via Agent tool ou spawn de subagente onde o briefing contém:

| Situação | Cláusula obrigatória? |
|---|---|
| Dados de cliente (nome, segmento, ticket, histórico, oferta) | ✅ SIM |
| Deliberação estratégica sobre cliente específico | ✅ SIM |
| Análise de cap. do Método CADARN para cliente | ✅ SIM |
| Agente de Távola recebendo contexto de cliente | ✅ SIM |
| Spawn para pesquisa genérica sem dados de cliente | ❌ Não obrigatório |
| Spawn técnico (código, infra, CI/CD) | ❌ Não obrigatório |

## Protocolo de sinalização para o agente spawned

### Tag de inferência

```
[INFERÊNCIA — não verificada]
```

Usar imediatamente após qualquer afirmação que não cite campo do briefing como fonte.

**Exemplos:**

```
❌  ERRADO — fato apresentado como verdade:
    "Vinícius tem 21 anos de experiência exclusiva em tickets acima de R$ 800k."

✅  CORRETO — fato com fonte do briefing:
    "Vinícius atua há 20+ anos no mercado imobiliário." (briefing: campo 'tempo_mercado')

✅  CORRETO — inferência sinalizada:
    "Vinícius parece ter foco predominante em alto ticket [INFERÊNCIA — não verificada].
     O briefing informa 'foco em tickets acima de R$ 800k' mas não afirma exclusividade."
```

### Derivação quantificada

Quando o briefing usa termos vagos ("foco em", "principalmente", "geralmente") e o agente precisa operar com esses dados:

- **Não quantificar** sem base explícita no briefing
- **Não ampliar** escopo: "foco em" ≠ "exclusivo em", "20+ anos" ≠ "21 anos exatos"
- Se a deliberação exige precisão e o briefing não fornece: sinalizar a lacuna e aguardar martelo de Fabiano

## Por que esta regra existe

Art. IV da Constitution (No Invention) define que specs não inventam — mas seu gate (`spec-write-spec.md`) cobre documentos de especificação técnica, não briefings inline de spawn.

Agentes spawned via Agent tool operam em contexto isolado, recebendo o mundo inteiro pelo briefing. Sem cláusula explícita, o comportamento default do modelo é preencher lacunas com inferências plausíveis — e apresentá-las como fatos. A inferência é silenciosa; o dano é real.

**Incidente de origem (2026-05-21):** Cascata de deliberação sobre planejamento de cliente. O briefing informava "foco em tickets acima de R$ 800k". O agente spawned extrapolou para "exclusivo em" e quantificou como "21 anos de experiência exclusiva" — fato falso apresentado sem sinalização. Art. IV violado em runtime de spawn, não coberto por gate existente.

## Anti-patterns

```
❌ Expandir escopo silenciosamente: "foco em X" → "exclusivo em X"
❌ Quantificar imprecisamente: "20+ anos" → "21 anos exatos"
❌ Usar contexto geral como dado do cliente:
   "Corretores de alto ticket geralmente têm carteira exclusiva —
    portanto Vinícius tem carteira exclusiva." (sem sinalização)
❌ Omitir cláusula No Invention no briefing por pressa ou por assumir
   que o agente "já sabe" o Art. IV
❌ Cláusula genérica sem o texto canônico:
   "seja honesto" ou "não invente" sem formato [INFERÊNCIA] explícito
```

## Responsabilidade do orquestrador

Emrys (e qualquer agente condutor de Távola) é responsável por incluir a cláusula no briefing antes de spawnar. A checagem é feita pelo próprio orquestrador — não há gate automático externo.

**Fluxo de verificação antes do spawn:**

```
Orquestrador monta briefing
    ↓
O briefing contém dados de cliente ou deliberação estratégica?
    ├─ SIM → incluir cláusula canônica No Invention antes de spawnar
    └─ NÃO → spawn sem cláusula é permitido
```

## Relação com outras regras

| Rule | Relação |
|---|---|
| `anti-impersonation-fail-loud.md` Rule 3 | Fail Loud cobre bloqueio de recurso; esta rule cobre inferência silenciosa — mesma categoria de falha (agente improvisa sem reportar), vetor diferente |
| Constitution Art. IV | Esta rule é o mecanismo de enforcement de Art. IV em runtime de spawn, cobrindo o gap do gate `spec-write-spec.md` |
| `plano-tatico-cadarn-multi-cliente.md` | Isolamento garante que dados de clientes não se cruzam; esta rule garante que o agente não completa dados do cliente com inferências dentro do contexto correto |
| `one-question-per-turn.md` | Quando dado está faltando no briefing e o agente precisa de precisão, uma pergunta de clarificação é preferível a inferir — complementar |
| `no-promessa-sem-lastro.md` | Promessa client-facing sem lastro é o resultado downstream de uma inferência não sinalizada — esta rule intercepta na origem |

## Severidade

**MUST** — Art. IV Constitution. Fato inventado sobre cliente entregue como verdade compromete a credibilidade da Cadarn e pode gerar decisão estratégica errada.

---

*Rule: spawn-briefing-no-invention | Criada: 2026-05-21 | Origem: Incidente real — inferência silenciosa "foco em" → "exclusivo em" | Autoridade: Fabiano + Emrys | Severidade: MUST*
