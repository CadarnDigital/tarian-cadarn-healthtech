# Catálogo de Especialistas por Nicho

Este diretório é reservado para agentes especialistas criados especificamente para o domínio deste produto.

## Diferença em relação ao tarian-template

No `tarian-template` (para clientes de agência), `specialists/` vem pré-populado com agentes por setor (ex: `imobiliario/especialista-juridico.md`).

No `tarian-cadarn-template` (para produtos próprios), `specialists/` parte **vazio** — os especialistas são construídos conforme o produto exige, não por antecipação.

## Quando criar um especialista aqui

Criar uma pasta `specialists/{subtema}/` quando o produto precisar de um agente com conhecimento muito específico de um subtema do domínio:

**Exemplo:**
```
specialists/
└── {subtema}/
    └── especialista-{subtema}.md
```

## Como construir

1. Identificar a necessidade (lacuna de especialidade que os agentes core não cobrem)
2. Definir o escopo do especialista (papel, comandos, knowledge_path)
3. Criar o agente em `specialists/{subtema}/especialista-{subtema}.md`
4. Registrar na squad correspondente (`squads/cadarn-{produto}/squad.yaml`)

## Estado atual

> Nenhum especialista pré-construído — adicionar no setup do Tarian conforme necessidade do produto.
