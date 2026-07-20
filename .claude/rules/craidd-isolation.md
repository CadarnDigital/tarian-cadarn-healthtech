---
paths:
  - ".craidd/**"
---
# Craidd — Isolamento Read-Only (MUST)

## Regra Principal

**`.craidd/` é read-only para toda filha Cadarn.** Nenhum agente escreve, edita ou faz merge de conteúdo filha-específico para dentro de `.craidd/`, em nenhuma circunstância. Nenhum agente copia trecho de `.craidd/` para uma pasta mutável local da própria filha.

Mudança de conteúdo em Craidd só acontece **no repositório `craidd`** (`https://github.com/CadarnDigital/craidd`), nunca a partir de uma filha consumidora (Martech, Healtech, futuras).

## Por que esta regra existe

Craidd nasceu de um incidente de contaminação real (vistoria noturna, Tarian Healtech, 2026-07-19): ao tentar corrigir um `knowledge_path` quebrado, a pasta `framework-cadarn-m2m/` — que misturava conteúdo genérico (Hexágono Moral, Método C.A.D.A.R.N.) com identidade aplicada exclusiva da Martech — foi copiada inteira da Martech para dentro da Healtech. A causa-raiz não foi um erro pontual de cópia; foi a ausência de uma barreira formal impedindo esse tipo de cópia.

`ADR-005-craidd-holding-compartilhada.md` §4.5 previu esta rule como consequência direta e obrigatória da criação do Craidd — sem ela, o mesmo incidente pode se repetir exatamente na estrutura desenhada pra evitá-lo.

## Protocolo

### O que é proibido

1. **Escrever em `.craidd/`** — nenhum agente, em nenhuma filha, cria, edita ou apaga arquivo dentro de `.craidd/`. O submodule é consumido por leitura.
2. **Copiar de `.craidd/` para fora dele** — nenhum agente copia trecho, arquivo ou pasta de `.craidd/` para qualquer local mutável da filha (`.aiox-core/knowledge/`, `docs/`, `squads/`, etc.), mesmo com boa intenção ("só pra ter uma cópia de referência local").
3. **Referenciar `.craidd/` fora do padrão de submodule** — nenhum `knowledge_path` ou script assume que o conteúdo de `.craidd/` pode ser resolvido por caminho relativo fora da estrutura de submodule padrão (`.craidd/valores/`, `.craidd/metodo/`).

### O que é permitido

- **Ler** qualquer arquivo dentro de `.craidd/` — é exatamente para isso que o submodule existe (ex: `knowledge_path` do agente `estrategista` apontando para `.craidd/valores/` e `.craidd/metodo/`)
- **Atualizar o pin do submodule** (`git submodule update --remote` seguido de commit) — ação manual e explícita, exclusiva de @devops (`agent-authority.md`), nunca automática via CI (ADR-005 §4.4)

### Se um agente precisar de mudança de conteúdo em Craidd

1. **Parar** — não editar `.craidd/` diretamente em nenhuma filha
2. **Sinalizar a Fabiano** que a mudança precisa acontecer no repositório `craidd` em si
3. A mudança é feita no repo `craidd`, versionada com nova tag
4. Cada filha que quiser a atualização roda `git submodule update --remote` e commita o novo pin, por decisão própria e independente (ADR-005 §7.2 — sem essa disciplina, filhas ficam presas em versão antiga, débito já aceito)

## Extensão futura (referência, não implementada nesta rule)

`*framework-drift-check` (mecanismo já citado em ADR-002 §4.4, nunca implementado) pode, futuramente, ser reaproveitado para checar drift de `.craidd/` entre filhas — fora de escopo desta rule.

## Relação com outras regras

| Rule | Relação |
|---|---|
| `agent-authority.md` | Atualização do pin do submodule é operação de @devops; nenhum outro agente atualiza `.craidd/` |
| `plano-tatico-cadarn-multi-cliente.md` | Mesmo padrão estrutural de isolamento (imutável vs. mutável), aplicado aqui ao eixo holding↔filha em vez de agência↔cliente |
| `anti-impersonation-fail-loud.md` | Se um agente encontrar `.craidd/` desatualizado ou incompleto, PARA e sinaliza — não copia conteúdo de outra fonte para preencher a lacuna |
| `metodo-cadarn-acronimo.md` | Fonte canônica do Método C.A.D.A.R.N. agora vive em `.craidd/metodo/acronimo-cadarn.md`, sujeita a esta regra de isolamento |

## Severidade

**MUST** — Violação recria exatamente o incidente que motivou a criação do Craidd. Toda violação detectada exige: (1) reversão imediata da escrita/cópia indevida, (2) notificação a Fabiano, (3) verificação se a mesma cópia se espalhou para outros pontos da filha.

## Aplicabilidade

Aplica-se a **todo agente**, em **toda filha Cadarn** que consome Craidd via submodule (Martech, Healtech, futuras), sem exceção de squad.

---

*Rule: craidd-isolation | Criada: 2026-07-20 | Origem: ADR-005-craidd-holding-compartilhada.md §4.5 | Autoridade: Fabiano + Aria (Architect) | Severidade: MUST*
