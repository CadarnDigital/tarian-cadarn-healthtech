---
agente: Emrys
squad: cadarn-healthtech
versao: 0.1.0
criado_em: 2026-07-15
status: ativo
---

# Memória Persistente — Emrys (Regência) · Cadarn Healtech

## Fonte de Verdade

Contexto completo da sessão de design do produto (21–28 jun 2026) está consolidado em:
`docs/cadarn-healthtech/checkpoint-sessao-llif-2026-06-21-28.md`

Este arquivo é resumo estável — não duplica o checkpoint. Para detalhes de tom de
voz, marca, corpus e artefatos originais, sempre ler o checkpoint e os arquivos
que ele linka.

## O Produto

```yaml
nome: Cadarn Healtech
tipo: "2ª unidade de negócio da Cadarn (NÃO é vertical da Martech — cânone próprio)"
dominio: Saúde Suplementar
posicionamento: "Engenharia de Fluxo"
frase_sintese: "Onde a saúde emperra, nós fazemos fluir."
antagonista: "A Demora"
simbolo: "Bambu — firme porque flui"
marca_status: "v0.1 — em construção (aprovada por Samira, 2026-06-22)"
```

## O Agente do Squad

```yaml
nome: Llif
etimologia: "galês: fluxo/corrente"
vocacao: "Estrategista-Consultor + Arquiteto de Operações em Saúde"
skill: cadarn-healthtech:llif
memoria: squads/cadarn-healthtech/memory/llif.md
```

## Decisões Marteladas (Blueprint Squad, 2026-06-28)

| # | Decisão | Martelo |
|---|---------|---------|
| A | Nasce como squad `cadarn-healthtech` com 1 agente (Llif), não standalone | Fabiano |
| B | Via 3 híbrido — DNA-EXTRACT + Tom de Voz + Dossiê no squad; Corpus IA bruto fica na HQ como lastro | Fabiano |
| C | Namespacing `cadarn-healthtech:llif` (prepara cisão comercial futura) | Fabiano |

## Automações da Oferta — Trio da Eficiência

1. **Onboarding (Entrada)** — OCR + RPA no cadastro de vidas (foto → JSON → portal)
2. **Conciliação (Manutenção)** — cruza vidas ativas × faturadas pela operadora
3. **Sinistralidade (Retenção)** — dashboards preditivos + alertas de renovação

## Papel do Emrys neste Tarian

Mesma persona e autoridade de Regência da HQ (AIOX Manager). A diferença é o
domínio de produto: aqui a Regência orquestra sobre o squad `cadarn-healthtech`
e o agente `Llif` — não sobre as squads da Martech.

Antes de delegar a `@squad-creator`, `@architect` ou qualquer especialista sobre
este produto, ler `squads/cadarn-healthtech/memory/llif.md` para o estado vivo
(decisão de entrada pendente, backlog, status epistêmico do Corpus IA).

## Histórico

| Data | Evento |
|---|---|
| 2026-06-22 | Marca Cadarn Healtech aprovada (Samira) |
| 2026-06-23 | Tom de Voz v1.0 fechado |
| 2026-06-28 | Squad forjada — decisões A/B/C marteladas |
| 2026-07-15 | Memória de projeto criada para o Emrys deste Tarian |

---
*Emrys memory-produto | v0.1.0 | 2026-07-15 | Squad Cadarn Healtech*
