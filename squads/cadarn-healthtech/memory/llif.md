---
agente: Llif
squad: cadarn-healthtech
versao: 0.1.0 (semente)
criado_em: 2026-06-28
status: ativo
---

# Memória Persistente — Llif 🎋

## Decisão de Entrada PENDENTE

```yaml
status: PENDENTE — martelo de Fabiano
opcoes:
  trilha_a:
    label: "Alexandre / faturamento hospitalar"
    entrada: "Raio-X de glosas 30-60 dias"
    perfil: "Âncora: volume de guias, equipe de faturamento, TISS"
  trilha_b:
    label: "Delma / corretora"
    entrada: "Conciliação de comissões / diagnóstico cadastral"
    perfil: "Âncora: cadastro, movimentações, carteira de beneficiários"
nota: "Llif não decide sozinho — propõe, aguarda martelo de Fabiano."
```

## Status Epistêmico

```yaml
tier_fato: "Caps 1-5 + Glossário do Corpus IA — citar [fonte: cap-0X]"
tier_hipotese: "Cap 6 + Anexo A (itens 🜂) — prefixar [HIPÓTESE CADARN — a validar]"
armadilha_roi:
  valor: "211,7%"
  natureza: "Projeção Cadarn (Cap. 6) — NÃO é benchmark de mercado"
  uso_correto: "Só em *planilha-roi como referência marcada; recalcular com dado real do cliente"
  violacao: "Apresentar como resultado esperado = Art. IV violation"
```

## Backlog Vivo (Anexo A)

Lista de entregáveis priorizados para a fase de validação:

- [ ] E-mail de convite para piloto (`*email-convite`)
- [ ] Apresentação comercial (`*apresentacao-comercial`)
- [ ] Planilha de ROI com dado real do primeiro cliente (`*planilha-roi`)
- [ ] Roteiro de validação clínica (`*roadmap-validacao`)
- [ ] Obter XML TISS anonimizado (pré-requisito para treino operacional — depende do cliente)

## Relação com a Squad Comercial (atualizado 2026-07-16)

```yaml
status: "Squad cadarn-comercial já existe (Caio, Camaleão, GestorFunil) — substitui o plano antigo de cisão futura de 1 SDR"
papel_llif: "Orquestrador consultivo — estratégia, diagnóstico, munição comercial (Caps 3-4-5)"
papel_squad_comercial: "Execução tática — prospecção, qualificação, follow-up, fechamento"
fluxo: "Llif diagnostica e prepara munição → squad-comercial executa a operação de vendas"
nota: "Substitui a seção antiga 'Cisão Futura — 2º Agente Comercial/SDR'. Decisão: Fabiano, 2026-07-16."
```

## Papel Expandido — Porta de Entrada do Tarian (decisão 2026-07-16)

```yaml
decisao: "Llif deixa de ser só o agente da squad cadarn-healthtech e vira o braço direito
  de Fabiano neste Tarian — secretário + conselheiro + consultor, com autonomia para
  ser brutalmente honesto."
o_que_muda:
  - "Llif é quem recebe Fabiano ao abrir o Claude Code neste Tarian (porta de entrada)"
  - "Llif vira transversal nas squads Forja, MKT, Comercial e Conselho (mesmo padrão de
     Grafia/Dick/Coel) — participa de todas, mantém a casa em cadarn-healthtech"
  - "Memória do Llif absorve dado real de cliente ao longo do tempo (personas: Delma,
     Alexandre, futuros clientes reais)"
o_que_nao_muda:
  - "Emrys continua existindo — é o especialista de bastidor para mecânica de framework
     (delegation matrix, git push, gates de segurança, protocolo entre squads)"
  - "Llif NÃO absorve a governança de framework do Emrys — aciona o Emrys quando a
     tarefa é mecânica, do mesmo jeito que aciona @devops pra dar push"
justificativa: |
  Emrys carrega conhecimento de framework (reutilizável entre Tarians — Alex, Samira,
  Martech, aqui). Llif carrega conhecimento de domínio + cliente real (específico deste
  produto). Fundir os dois recriaria a mistura de responsabilidades que o projeto vem
  corrigindo a sessão inteira. Separar preserva os dois, mas muda quem é "a cara" do
  projeto no dia a dia.
nota: "Decisão: Fabiano, 2026-07-16."
```

## Contexto Operacional

```yaml
socia: Delma
  papel: "Corretora (cadastro + faturamento). Parceira operacional."
ancora: Alexandre
  papel: "Faturamento hospitalar. Cliente embutido na relação Delma."
laboratorio: "Efeito Espelho — duas pontas espelhando a mesma Demora [HIPÓTESE 🜂]"
recorte_regional: "ES / Grande Vitória — confiança lidera, preço cai ao 5º lugar"
tarian_health: "Reservado para Fase de operação — este squad É a semente migrável"
```

## Histórico de Decisões

| Data | Decisão | Autoridade |
|---|---|---|
| 2026-06-28 | Squad `cadarn-healthtech` (não standalone) | Fabiano (A) |
| 2026-06-28 | Via 3 híbrido do cânone | Fabiano (B) |
| 2026-06-28 | Skill `cadarn-healthtech:llif` (namespaced) | Fabiano (C) |
| 2026-06-28 | Athena `*mine` → DNA-EXTRACT.md (88%) | Athena |
| 2026-06-28 | Craft `*design-squad` → blueprint aprovado | Craft + Fabiano |
| 2026-06-28 | Forja executada em Sonnet | Emrys |

---
*Llif memory-semente | v0.1.0 | 2026-06-28 | Squad Cadarn Healtech*
