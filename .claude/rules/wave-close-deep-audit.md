---
paths:
  - "docs/stories/**"
  - "docs/projeto-camara/**"
---
# Wave Close Deep Audit — Auditoria Profunda Obrigatória Antes de Fechar Wave

## Regra Principal

**Nenhuma wave da Forja pode ser declarada PASS sem auditoria profunda baseada em EVIDÊNCIA EMPÍRICA.** Declaração não é evidência. Quem afirma "ajv 47/47 OK" abre o terminal e roda. Quem afirma "rotation-log atualizado" abre o arquivo e lê. Quem afirma "39 agentes assinados com chave produção" pega 1 agente aleatório e verifica os campos `dna.sig`, `dna.alg`, `dna.pubkey_id`, `dna.signed_at`.

Esta rule **estende** `forja-wave-close-gate.md` — não substitui. O gate Morgan + Cosmo continua, mas com critério de profundidade explicitado.

## Por que esta regra existe

Em 2026-05-02, auditoria 5-lentes (Cosmo + Morgan + Aegis + Dex + Aria) sobre Wave 0-3 do Projeto Câmara achou **145 problemas** (29 CRITICAL) que os gates anteriores haviam declarado PASS. Causa raiz documentada:

> Declarações foram tratadas como verdade. Ninguém abriu os arquivos pra ver se as declarações eram verdade.

O caso mais grave: o `aiox-core/` (sem ponto) — diretório paralelo com loader/signing/audit/chave Ed25519 distinta da canônica — nasceu no MESMO commit que fechou a Wave 3. O gate Wave 3 declarou PASS sem que ninguém auditasse paths. PRD V1.6 §9 marcou ✅ em 8/8 critérios; 4-5 eram empiricamente falsos.

Wave 4 estava prestes a abrir em cima de fundação podre. Foi interceptado pelo Fabiano por desconfiança, **não pelo framework**. Esta rule existe pra que o framework intercepte sozinho da próxima vez.

## Os 5 princípios da auditoria profunda

### Princípio 1 — Cross-check declaração-realidade obrigatório

Para cada item de checklist do gate, o auditor (Morgan, Cosmo, ou quem mais participar) DEVE registrar:

- **Declarado** — o que story / wave-close anterior / PRD afirma
- **Comando que reproduz** — bash exato pra confirmar empiricamente
- **Output observado** — trecho real do que viu

Sem essas 3 colunas em cada item, o item NÃO conta como verificado. Marcar ✅ por confiança em outro agente é violação.

**Anti-pattern (visto em Wave 3 close):**
> "✅ ajv OK 11/11 (verificado por Story 3.2)"

**Pattern correto:**
> "✅ ajv OK 11/11 — `node validate-spec.js squads/cadarn-marketing/agents/*.md` retorna `0 errors, 11 valid`"

### Princípio 2 — Aegis convocada AUTOMATICAMENTE em waves cripto/security/PII

Não é opcional. Não depende de "alguma story tinha PII?". Wave-close gate dispara convocação automática se a wave tocou:

- Signing, signing key, key rotation, secrets management
- Autenticação ou autorização
- Audit logs
- PII (dados pessoais)
- Schema canônico de agente (load-bearing)
- CI/CD security
- Skill incorporation policy
- Deny rules / settings.json

Se Aegis foi convocada e emitiu RESSALVA → wave **NÃO PODE** fechar PASS, fecha **PASS COM RESSALVAS** e a próxima wave **NÃO PODE** abrir até ressalvas estarem fechadas. Precedente Wave 1 → Wave 2 (ressalvas Gap A/B abertas, Wave 2 abriu mesmo assim) é proibido a partir desta rule.

### Princípio 3 — @qa (Quinn) convocada em TODA wave

Story-lifecycle.md já obriga InReview entre InProgress e Done. Wave-close gate confirma: cada story Done passou por Quinn? Se não, gate falha o item 1 do checklist Morgan ("ACs cumpridas?").

Se a Forja decidir formalmente que QA é dispensável pra um tipo específico de story (ex: stories puramente de migração mecânica via script testado), isso vira decision-doc registrado em `docs/projeto-camara/decisions/` (ou equivalente do projeto), não convenção tribal.

### Princípio 4 — Diff entre PRD e estado real do repo

Para cada item de critério de sucesso do projeto (PRD §9 ou equivalente) marcado ✅:

- Abrir o arquivo citado e confirmar conteúdo
- Rodar a ferramenta citada e capturar exit code
- Contar os itens citados (testes, arquivos, agentes) e bater com declaração

Marcar ✅ sem evidência verificável é **fraude documental** — não retórica forte, é o que aconteceu em §9.5 ("skill-registry.yaml machine-readable") quando o arquivo nem existia.

### Princípio 5 — Se gate descobre falha em wave anterior, RE-AUDITAR antes de prosseguir

Se a Wave N descobre que a Wave N-1 declarou algo que não é verdade, a próxima wave (N+1) **NÃO ABRE** até a Wave N-1 ser re-auditada e fechada de fato. Não importa se o veredicto anterior dizia PASS — falha não detectada não vira "sucesso histórico" só porque foi declarada.

## Checklist Wave-Close Profundo (estende forja-wave-close-gate.md)

### Checklist Morgan (produto) — agora com evidência empírica obrigatória

```
[ ] 1. Todas as ACs cumpridas? — para cada story, abrir e listar ACs +
       comando que reproduz cada AC + output observado
[ ] 2. Story Change Log: status final = Done? Se ainda InProgress/InReview,
       gate FALHA imediato (Wave 0 do Projeto Câmara: 8/8 stories ainda em
       InProgress/InReview com gate "PASS" — antipattern)
[ ] 3. Lifecycle Draft→Ready→IP→InReview→Done seguido? Se InReview pulado em
       qualquer story, gate FALHA ou registra desvio formal com decision-doc
[ ] 4. Quinn (@qa) convocada em cada story? Reviews em docs/qa/ (ou
       equivalente) confirmados?
[ ] 5. EXECUTION-PLAN coerente com entrega real? Item por item, com diff de
       arquivos criados/modificados
[ ] 6. Decisão da wave invalidou premissa do PRD? Se sim, PRD precisa ser
       atualizado ANTES da próxima wave abrir
[ ] 7. Critério de sucesso §9 do PRD (ou equivalente) afetado pela wave?
       Re-verificar empiricamente os critérios afetados
```

### Checklist Cosmo (DS / framework health) — estendido

```
[ ] 1. Algum diretório novo criado pela wave? Listar com `git diff --stat
       HEAD~N` e justificar cada um
[ ] 2. Algum arquivo em path canônico? Em path shadow? Cross-check com
       Constitution L1-L4
[ ] 3. Tokens declarados em frontmatters da wave existem no catálogo?
[ ] 4. Schema (se afetado) bumpou versão coerentemente? Mudança breaking →
       SchemaVer MAJOR; mudança rename → MINOR; ADD-ONLY → PATCH
[ ] 5. Decision docs criados pra TODAS as decisões arquiteturais da wave
       (não só pra subset)
[ ] 6. ADR retroativo necessário? Se a wave introduziu mudança não prevista
       no PRD, ADR é mandatório
```

### Convocações automáticas adicionais

- **Aegis** — se wave tocou signing/security/PII/audit/secrets/CI security/schema (gatilhos do Princípio 2)
- **Aria** — se wave criou diretório novo OU modificou L1-L2 OU introduziu padrão arquitetural novo
- **Dex** — se wave entregou implementação (não só docs); para validar que testes declarados ROdam
- **Quinn** — sempre (Princípio 3)

### Veredicto

| Status | Critério |
|---|---|
| ✅ **PASS** | Todos os checklists com 100% verificação empírica + zero ressalva crítica + zero declaração não verificável |
| ⚠️ **PASS COM RESSALVAS** | Verificação empírica completa + ressalvas documentadas com Wave de fechamento explícita |
| 🔴 **BLOCKED** | Qualquer item sem verificação empírica OU dívida crítica OU invalidação de premissa OU ressalva Aegis aberta |

**Importante:** PASS COM RESSALVAS NÃO autoriza próxima wave a abrir. A próxima wave só abre quando ressalvas dessa wave estiverem fechadas formalmente. Wave 1→2 do Projeto Câmara violou isso, virou precedente perigoso, encerrado por esta rule.

## Auditoria 5-lentes — quando convocar

Em situações onde múltiplas lentes precisam convergir (final de marco grande, antes de major bump de PRD, suspeita de gate raso anterior), convocar:

1. **Cosmo** — DS / framework health / atomic / machine-readability
2. **Morgan** — PM / produto / processo / story integrity / PRD coerência
3. **Aegis** — security / threat model / cripto / compliance
4. **Dex** — implementação real / código / runtime / testes
5. **Aria** — arquitetura / Constitution L1-L4 / decisões estruturais / ADRs

Cada lente trabalha em paralelo (não-deliberativo — cada um audita sob sua lente, sem dependência cruzada). Saídas consolidadas pelo condutor (Emrys ou Morgan). Convergências entre lentes = achados confirmados; divergências = decisão arquitetural pendente.

Esta foi a metodologia que pegou os 145 achados em 2026-05-02. Documentada como template oficial pra auditoria profunda.

## Relação com outras rules

| Rule | Relação |
|---|---|
| `forja-wave-close-gate.md` | Esta rule estende — não substitui. Gate Morgan+Cosmo continua, agora com evidência empírica obrigatória |
| `story-lifecycle.md` | Esta rule reforça o Princípio 3 — Quinn obrigatória em InReview |
| `security-review-mandatory.md` | Esta rule reforça o Princípio 2 — Aegis automática em wave-close cripto/security |
| `forja-split-decisions.md` (memory) | Decisões técnicas de fundação são autônomas — esta rule garante que sejam BEM tomadas |
| `anti-impersonation-fail-loud.md` | Marcar ✅ sem evidência = "Fail Loud" violado — agente declarou sem ter |

## Severidade

**MUST** — Wave-close gate sem auditoria profunda nesses 5 princípios é gate inválido. A próxima wave **não abre** mesmo se gate declarou PASS.

Aplicação imediata. Wave 4 do Projeto Câmara só abre depois de Wave 0-3 ser re-auditada conforme esta rule e fechada de fato.

## Origem

Auditoria 5-lentes 2026-05-02, Projeto Câmara. Cosmo + Morgan + Aegis + Dex + Aria. 145 achados em Wave 0-3 que os gates anteriores não pegaram. Causa raiz: gate por declaração, não por evidência. Fabiano interceptou por desconfiança — framework não interceptou sozinho. Esta rule existe pra que o framework intercepte da próxima vez.

---

*Rule: wave-close-deep-audit | Criada: 2026-05-02 | Origem: Auditoria 5-lentes Wave 0-3 Projeto Câmara | Autoridade: Fabiano + Forja (Morgan, Cosmo, Aegis, Dex, Aria) | Severidade: MUST | Estende: forja-wave-close-gate.md*
