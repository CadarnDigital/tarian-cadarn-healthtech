---
paths:
  - "docs/stories/**"
---
# Security Review Mandatory — Gate Aegis Obrigatório antes de Drafting e Implementação

## Regra Principal

**@aegis DEVE ser acionada antes de @sm draftar** qualquer story que envolva dados pessoais, autenticação, autorização, pagamentos, secrets ou infraestrutura crítica. **@aegis DEVE ser acionada antes de @pm executar epic** que contenha PRDs com processamento de PII ou mecanismos de autenticação.

Aegis não duplica Quinn (@qa). Quinn valida funcionalidade e cobertura de testes. Aegis valida ameaças e compliance antes que entrem no código.

## Gatilho da regra

A rule se ativa quando qualquer um dos critérios abaixo for verdadeiro:

### Para stories (gate pré-drafting via @sm)

| Critério | Gate obrigatório? |
|---|---|
| Story processa ou armazena PII (nome, CPF, e-mail, telefone, endereço) | ✅ SIM |
| Story implementa autenticação ou autorização | ✅ SIM |
| Story expõe endpoint que opera sobre dados de terceiros | ✅ SIM |
| Story integra com serviço externo (webhook, API de pagamento, CRM) | ✅ SIM |
| Story envolve upload/download de arquivos | ✅ SIM |
| Story toca em configuração de CI/CD ou secrets | ✅ SIM |
| Story puramente de frontend sem dados sensíveis | ❌ Opcional |
| Story de refactor interno sem mudança de fluxo de dados | ❌ Opcional |

### Para PRDs (gate pré-epic via @pm)

| Critério | Gate obrigatório? |
|---|---|
| PRD descreve sistema com armazenamento de dados pessoais | ✅ SIM |
| PRD inclui mecanismo de autenticação ou gestão de sessão | ✅ SIM |
| PRD integra com sistema externo que processa dados | ✅ SIM |
| PRD descreve módulo financeiro ou de pagamentos | ✅ SIM |
| PRD sem qualquer processamento de dados sensíveis | ❌ Opcional |

## Protocolo de execução

### Step 1 — Identificação (quem detecta)

Qualquer agente pode (e deve) sinalizar quando a story/PRD atende aos critérios acima. A sequência normal é:

```
@sm recebe pedido de draft
    ↓
@sm verifica critérios da tabela acima
    ↓
Critério positivo?
    SIM → "Esta story requer gate de segurança. Acione @aegis antes do draft."
    NÃO → draft normal (gate opcional)
```

### Step 2 — Execução do gate (Aegis)

```
Fabiano invoca @aegis
    ↓
Aegis executa *review-story {path} ou *review-prd {path}
    ↓
Veredicto emitido (APROVA / APROVA COM RESSALVAS / BLOQUEIA)
    ↓
APROVA → @sm drafta normalmente
APROVA COM RESSALVAS → @sm drafta, ressalvas viram ACs ou dívidas técnicas na story
BLOQUEIA → story aguarda correção antes do draft
```

### Step 3 — Registro

Aegis registra o veredicto em `docs/security/reviews/{YYYY-MM-DD}-{story-id}.md` com o schema padrão:
```
VEREDICTO: [APROVA|APROVA COM RESSALVAS|BLOQUEIA]
JUSTIFICATIVA: [...]
RESSALVAS: [...]
ANOMALIAS: [...]
```

## Quem pode dispensar o gate

**Apenas Fabiano** pode dispensar explicitamente: *"Aegis não precisa revisar esta story"* ou equivalente. Nenhum agente pode auto-dispensar o gate por conveniência ou urgência.

## Relação com outras regras

| Rule | Relação |
|---|---|
| `specialist-handoff-mandatory.md` | Aegis é o especialista de security — esta rule define quando acionar |
| `story-lifecycle.md` | Gate de Aegis é pré-condição para status Draft → Ready em stories com PII/auth |
| `forja-wave-close-gate.md` | Wave-close inclui verificação se alguma story entregue deveria ter passado por Aegis |
| `agent-authority.md` | Delegation matrix de Aegis — owns exclusivo de security review |

## Quando NÃO se aplica

- Stories puramente de UI sem dados sensíveis
- Refactors que não alteram fluxo de dados
- Hotfixes urgentes (mas registrar dívida: "*review-story após o fix")
- Fora do AIOX Manager / Tarian (Aegis é core do AIOX — replicação em Tarian de clientes = Wave C pós-MVP)

## Severidade

**MUST** para stories e PRDs com dados pessoais, autenticação ou integração externa.
**SHOULD** para os demais casos (gate opcional, recomendado por Aegis quando relevante).

Violação compromete LGPD compliance e postura de segurança do produto. Ameaça identificada em pré-drafting tem custo de correção ~100x menor que ameaça identificada em produção.

---

*Rule: security-review-mandatory | Criada: 2026-04-29 | Origem: Deliberação Forja + Pesquisas OWASP/STRIDE/LGPD/LLM-SHIELD | Autoridade: Fabiano + Emrys | Severidade: MUST (dados sensíveis/auth) / SHOULD (demais)*
