---

## Task Definition

```yaml
task: generateProposal()
responsavel: Caio (caio) + Camaleão (camaleao)
responsavel_type: Agentes
squad: cadarn-comercial
templates:
  - proposta-comercial-tmpl.yaml
tarian_portable: true

description: >
  Estrutura proposta comercial completa baseada no diagnóstico.
  Caio monta a proposta; Camaleão revisa e calibra pelo perfil DISC do decisor.
  Nunca gerar proposta sem diagnóstico confirmado — violação do princípio
  central do VENDE-C. A proposta espelha as palavras exatas do cliente
  (JTBD) como headline para que o cliente se reconheça imediatamente.

Entrada:
  - campo: mapa_diagnostico
    tipo: object
    origem: Task run-diagnostic.md
    obrigatório: true
    campos:
      - dor_principal
      - situacao_atual
      - resultado_esperado_90d
      - palavras_chave_jtbd
      - perfil_disc_confirmado
      - urgencia_confirmada
      - historico_tentativas_anteriores

  - campo: segmento
    tipo: enum
    valores: [imobiliaria, advocacia, estetica, outro]
    origem: Mapa diagnóstico
    obrigatório: true

  - campo: escopo_servicos
    tipo: list
    origem: Elicitação (Caio define com base no diagnóstico)
    obrigatório: true

Saída:
  - campo: proposta_comercial
    tipo: markdown
    template: proposta-comercial-tmpl.yaml
    destino: Cliente (via Caio)
    persistido: true
```

---

## Execution Modes

### 1. Proposta Completa **[DEFAULT]**
- Gera proposta do zero com base no diagnóstico
- Camaleão revisa antes de enviar
- **Trigger:** `*proposta {diagnóstico}`

### 2. Revisão de Proposta Existente
- Ajusta proposta já escrita pelo perfil DISC
- **Trigger:** `*revisar-proposta {perfil} {proposta}` → delegar ao Camaleão

---

## Workflow — Proposta Completa

### Pré-Condição

```
task: |
  GATE OBRIGATÓRIO — verificar antes de prosseguir:
  [ ] Diagnóstico foi realizado (run-diagnostic.md)?
  [ ] Dor principal confirmada pelo cliente?
  [ ] Resultado esperado em 90 dias mapeado?
  [ ] Economic Buyer identificado (EB ≠ 0 no MEDDIC)?

  SE qualquer item não preenchido → NÃO gerar proposta.
  Voltar para qualificação ou diagnóstico.

  ANTI-PATTERN ABSOLUTO:
  "NUNCA proposta antes de diagnóstico — sem exceção." (Caio Carneiro)
```

### Fase 1 — Headline com Palavras do Cliente

```
task: |
  Extrair das palavras-chave JTBD do diagnóstico o headline da proposta.

  TÉCNICA:
  Usar a frase EXATA que o cliente usou ao descrever o cenário ideal.
  Exemplo: cliente disse "queria ter agenda cheia sem depender de indicação"
  → Headline: "Agenda cheia sem depender de indicação — é exatamente isso
     que esse plano entrega."

  ADAPTAÇÃO POR PERFIL DISC:
  🔴 D: headline focado em RESULTADO e VELOCIDADE
       "X% mais leads qualificados em 90 dias."
  🟡 I: headline focado em TRANSFORMAÇÃO e RECONHECIMENTO
       "Do invisível ao referência no {nicho} — essa é a virada."
  🟢 S: headline focado em SEGURANÇA e CONTINUIDADE
       "Um plano estruturado para crescer sem depender de sorte."
  🔵 C: headline focado em METODOLOGIA e EVIDÊNCIA
       "Diagnóstico completo + plano em 5 fases — documentação disponível."
```

### Fase 2 — Estrutura da Proposta

```
task: |
  Usar template proposta-comercial-tmpl.yaml.

  ESTRUTURA BASE:
  [1] SITUAÇÃO ATUAL: espelhar o que o cliente disse no diagnóstico
      → "Hoje você {situação exata}. Isso significa que {custo/impacto}."
      → NÃO inventar. Usar apenas o que foi dito no diagnóstico.

  [2] PROBLEMA (custo da inação): o que acontece se não resolver
      → "Se continuar assim por mais 12 meses: {impacto concreto em números}"
      → Usar métricas do MEDDIC quando disponíveis.

  [3] SOLUÇÃO: o que a Cadarn entrega
      → Listar serviços contratados com resultado esperado por serviço
      → Nunca features — sempre resultados.
      → Adaptado ao segmento (ver template por segmento)

  [4] METODOLOGIA (opcional para C): como vai ser feito
      → Incluir para perfil C e S. Omitir ou resumir para D e I.

  [5] CRONOGRAMA: timeline dos primeiros 90 dias
      → Marcos mensais: mês 1, mês 2, mês 3
      → Inclui KPIs esperados por marco

  [6] INVESTIMENTO: valor + forma de pagamento
      → Apresentar FALAR PREÇO DE BOCA CHEIA (VENDE-C)
      → Nunca hesitar no preço. Nunca pedir desculpa pelo valor.
      → Depois do valor: silêncio — deixar o cliente processar

  [7] PROVA SOCIAL (calibrada por perfil):
      D: dado quantitativo de cliente similar
      I: depoimento + antes/depois visual
      S: case de parceria de longo prazo + garantia
      C: benchmark do mercado + metodologia documentada

  [8] PRÓXIMOS PASSOS (CTA claro):
      → "Para começar: {ação específica} até {data}"
      → NÃO: "Qualquer dúvida me avisa"
      → SEMPRE: próximo passo com data

  ADAPTAÇÕES POR SEGMENTO (template proposta-comercial-tmpl.yaml):
  Imobiliária: incluir conformidade COFECI. Prova: resultado em agenda/lead digital.
  Advocacia: NUNCA chamar de "proposta de marketing" → "Plano de Posicionamento".
             Incluir seção específica de conformidade OAB.
  Estética: incluir seção de posicionamento de autoridade médica.
            Prova: antes/depois de agenda + posicionamento no Instagram.
```

### Fase 3 — Calibração pelo Camaleão

```
task: |
  Antes de enviar ao cliente, passar proposta para Camaleão:

  Input para Camaleão:
  - Perfil DISC confirmado na reunião de diagnóstico
  - Proposta rascunho completa
  - Segmento

  Camaleão retorna recomendações em 4 dimensões:
  1. Estrutura (o que mover)
  2. Extensão e densidade
  3. Tipo de prova a enfatizar
  4. Ajustes de tom + frase de fechamento calibrada

  Caio aplica ajustes e envia ao cliente.
```

### Fase 4 — Envio e Follow-up

```
task: |
  ENVIO DA PROPOSTA:
  - Enviar por escrito (PDF ou Google Docs com link)
  - Sempre acompanhar com mensagem personalizada (não genérica)
  - Mensagem de envio: 4 linhas máx. + link + próximo passo confirmado

  MENSAGEM DE ENVIO PADRÃO:
  "{Nome}, conforme conversamos — a proposta está aqui: [link]
  Ela já reflete {dor principal que você descreveu}.
  Agendei nossa conversa para {dia/hora} para percorrer juntos.
  Qualquer ponto antes disso, estou disponível."

  PRÓXIMO PASSO OBRIGATÓRIO:
  Reunião de revisão da proposta agendada ANTES de enviar.
  Caio define: *followup para cadência se lead não responder.

output: proposta-{cliente}-{YYYY-MM-DD}.md
```

---

## Integração com Outros Agentes

- **Camaleão:** Obrigatório — revisa proposta antes de enviar (calibração DISC)
- **GestorFunil:** Score MEDDIC alimenta métricas e custo da inação na proposta
- **Caio (client-intake-handoff):** Após aceite, dispara task close-deal.md

---

*Squad Cadarn Comercial — Task v1.0*
*Framework: VENDE-C (Caio Carneiro) + Challenger Sale (Dixon & Adamson)*
*"Proposta sem diagnóstico é spam." — GestorFunil*
