---
material: corpus-ia-saude-suplementar
anexo: A
titulo: "Perguntas Estratégicas — Fio Condutor e Backlog de Aprofundamento"
fontes: [health-estrategia-oferta-gemini, health-dossie-estrategico-ia-backoffice-es, health-dossie-mesa-gpt, health-dossie-gemini-brasil]
gerado_em: 2026-06-27
---

# Anexo — Perguntas Estratégicas

> **O que é este anexo e para que serve.** As conversas com Gemini e GPT que deram origem ao Capítulo 6 são, na sua espinha, uma **sequência de perguntas**: as que Fabiano fez para direcionar a investigação, e as que os modelos devolveram ao final de cada resposta, oferecendo-se para aprofundar um próximo ponto. Reunidas aqui, essas perguntas cumprem duas funções para a frente **treinar IA**: (1) preservam o **fio condutor** do raciocínio — como o projeto evoluiu de "vender software" para "ser um BPO Tech"; e (2) formam um **backlog de aprofundamento** — cada pergunta-isca em aberto é uma pesquisa ou decisão futura que ainda não foi tomada. Todas vêm de [fonte: health-estrategia-oferta-gemini].
>
> Cada item de backlog traz um **status**: `✅ destilada` (a resposta já foi incorporada ao material — diz onde) ou `⬜ em aberto` (segue como pergunta não respondida, candidata a próxima pesquisa/decisão).

---

## A. O fio condutor — as três intervenções de Fabiano

Três falas de Fabiano, na ordem em que aparecem, são os pontos de inflexão de toda a investigação [fonte: health-estrategia-oferta-gemini]:

1. **O prompt-mestre (método de análise).** *"Atue como um Consultor Sênior de Inovação B2B e Arquiteto de Operações em Saúde. [...] destile as informações através da lente da nossa empresa: o que serve como matéria-prima técnica ou estratégica para criarmos soluções de IA voltadas ao back-office da saúde suplementar?"* — repetido em quase todos os blocos, sempre com o mesmo formato de saída (ver Seção C). É o método que gerou toda a camada de oferta.

2. **A revelação das duas pontas.** *"Tenho acesso a uma corretora de plano de saúde e uma empresa que faz faturamento hospitalar, o que vc pode me sugerir então a partir daí tanto como insights como plano de ação."* — esta fala destravou o **Efeito Espelho** e o **Insight de Ouro** (Cap. 6, Seção 1).

3. **A correção de rumo para BPO Tech.** *"Talvez eu não tenha sido claro, mas minha intenção, como uma das possibilidades, seria ser um BPO que trabalharia com cadastros e faturamento. Vou ter acesso a dois players inicialmente. Uma dona de corretora de plano de saúde. Um dono de uma empresa de faturamento hospitalar. Baseado nisso refaça sua análise."* — esta fala redefiniu o **modelo de negócio**: de fornecedor de software para **BPO Tech** (Cap. 6, Seção 1).

> **Leitura para a frente IA.** Note o status epistêmico das duas últimas falas: ambas usam "uma das possibilidades" e "acesso a" — são **declarações de intenção e de acesso**, não de operação consolidada. O material trata o modelo BPO Tech como hipótese a validar, em fidelidade a essa formulação original.

---

## B. O backlog de aprofundamento — as perguntas-isca do Gemini

As perguntas que os modelos devolveram, agrupadas por tema. Cada uma é um gancho de aprofundamento que Fabiano pode (ou não) puxar.

### B.1 ROI, precificação e material comercial

- *"Gostaria que eu detalhasse como calcular o ROI dessa automação para apresentar aos seus clientes?"* — **✅ destilada** (Cap. 6, Seção 4: ROI 211,7%).
- *"Você gostaria que eu desenhasse um modelo de precificação sugerido para esse serviço de automação?"* — **✅ destilada parcialmente** (Cap. 6, Seção 4: Setup R$ 3.000 + R$ 1.500/mês). Um modelo de precificação por **performance / por vida gerida** foi mencionado mas não fechado — **⬜ em aberto**.
- *"Gostaria que eu estruturasse um roteiro de reunião de diagnóstico?"* — **✅ destilada** (Cap. 6, Seção 5: roteiro de 4 blocos).
- *"Gostaria que eu escrevesse um modelo de e-mail de convite para agendar essa reunião diagnóstica?"* — **⬜ em aberto** (o e-mail em si nunca foi escrito).
- *"O que você acha de criar uma 'Planilha de Diagnóstico de Processos'?"* — **✅ destilada** (Cap. 6, Seção 5: as 3 perguntas da planilha). A planilha como artefato pronto — **⬜ em aberto**.
- *"Gostaria que eu estruturasse uma proposta de apresentação comercial focada em um desses pilares (automação ou marketing consultivo)?"* — **⬜ em aberto** (a apresentação comercial nunca foi produzida).

### B.2 Detalhamento técnico das automações

- *"Gostaria que eu explorasse alguma das automações (conciliação de faturas ou análise de sinistralidade) com mais detalhes técnicos?"* — **✅ destilada em parte** (Cap. 6, Seção 3: catálogo de soluções). Detalhamento técnico de implementação (esquema de dados, prompts, fluxos) — **⬜ em aberto**.
- *"Qual dessas arquiteturas de IA se alinha melhor com a capacidade atual de desenvolvimento do seu time para iniciarmos o escopo técnico do MVP?"* (perguntada duas vezes, com variações) — **⬜ em aberto** (decisão de Fabiano sobre qual arquitetura priorizar).
- *"Você já possui ou consegue viabilizar o acesso a um lote de arquivos XML no padrão TISS (anonimizados) para estruturarmos a primeira Prova de Conceito?"* — **⬜ em aberto** (pré-requisito técnico do MVP anti-glosa).

### B.3 Escopo de produto e validação

- *"Deseja que eu ajude a estruturar um modelo de proposta de valor baseada na lacuna de transparência do mercado?"* — **⬜ em aberto**.
- *"Quer ajuda para definir um escopo de MVP de IA que resolva uma dor específica (ex.: gestão de glosas para pequenos)?"* — **⬜ em aberto** (escopo de MVP a fechar).
- *"Prefere que eu elabore uma lista de perguntas para fazer a potenciais clientes (médicos/donos de clínica) para validar essas ideias?"* — **⬜ em aberto** (roteiro de validação para a ponta clínica/hospitalar).

### B.4 Priorização entre as duas pontas — a decisão recorrente

Os modelos voltaram **quatro vezes**, com formulações diferentes, à mesma decisão de priorização — sinal de que é a pergunta mais importante ainda sem resposta [fonte: health-estrategia-oferta-gemini]:

- *"Qual das duas pontas (a corretora ou a empresa de faturamento hospitalar) tem mais abertura política e facilidade técnica para extrair os primeiros dados de teste hoje?"*
- *"Qual desses dois parceiros possui o gargalo operacional mais urgente e estaria mais disposto a compartilhar a base histórica de dados para a validação?"*
- *"Qual dessas quatro arquiteturas propostas se alinha melhor com a infraestrutura e os talentos que vocês já têm internamente hoje?"*
- *"Qual destas frentes operacionais (auditoria de faturas ou movimentação cadastral) reflete de forma mais urgente as conversas que você tem tido com seus parceiros comerciais na região?"*

**Status: ⬜ em aberto.** Esta é a decisão de entrada do projeto — por qual ponta e por qual processo começar a validação. O material descreveu as duas opções de "cavalo de Troia" (conciliação de comissões na corretora; raio-X de glosas no hospital), mas **a escolha é de Fabiano** e ainda não foi feita.

---

## C. Nota de método — o prompt-template usado

Toda a camada de oferta foi gerada com um único molde de prompt, repetido a cada material analisado. Ele tem valor de **referência reutilizável** e segue, em espírito, a mesma lógica do Método CADARN (diagnóstico → arquitetura → ação) [fonte: health-estrategia-oferta-gemini]:

> **Persona:** "Atue como um Consultor Sênior de Inovação B2B e Arquiteto de Operações em Saúde."
> **Contexto:** pequena empresa desenvolvendo soluções táticas de IA para o back-office da saúde suplementar — eficiência operacional, organização de dados, proteção de margem (glosas, auditoria, TISS/TUSS, compliance).
> **Tarefa:** destilar o material pela lente da empresa, não um resumo acadêmico.
> **Formato de saída exigido (três fases):**
> 1. **Clareza (O Essencial)** — resumo executivo de no máximo 3 parágrafos, só o que impacta operações, dados, auditoria ou regulação.
> 2. **Arquitetura (Oportunidades de IA)** — 3 a 5 ideias práticas de solução (agentes, automação, RAG) vendáveis a prestadores/operadoras.
> 3. **Dados e Ação (Próximo Passo)** — o primeiro passo técnico ou de negócio para validar a ideia mais promissora.

---

## D. Nota de proveniência — material fora de escopo preservado na fonte

O arquivo-fonte [fonte: health-estrategia-oferta-gemini] contém **dois blocos sobre suplementos alimentares** (nutrição/varejo) — "NL 001 GPT IA para Eficiência em Suplementos" e "NL 003 Gemini IA para Eficiência em Suplementos". Eles tratam de ANVISA/RDCs, SKUs, *shelf life*, NF-e, marketplaces e farmácias de manipulação — **outro domínio**, que entrou no arquivo por ambiguidade do termo "suplementos" (alimentar ≠ saúde suplementar).

**Decisão (zero perda + zero contaminação):** esses dois blocos **não foram destilados no Capítulo 6**, por não pertencerem ao escopo da saúde suplementar — incorporá-los contaminaria o material. Mas **não foram descartados**: permanecem preservados na íntegra no arquivo-fonte bruto (`docs/biblioteca/pesquisas/2026-06-27_health-estrategia-oferta-gemini.md`). Curiosidade reaproveitável: eles aplicam a **mesma lógica de back-office** (pré-auditoria profilática, RAG de compliance regulatório, OCR de pedidos B2B, auditoria de marketplace) a outro setor — uma evidência de que o método é transferível, caso a Cadarn um dia atue no nicho de suplementos alimentares.

---

## E. Banco de perguntas de diagnóstico de campo (dossiês de 2026-06-27)

Três dossiês posteriores — registrados na biblioteca como [fonte: health-dossie-estrategico-ia-backoffice-es], [fonte: health-dossie-mesa-gpt] e [fonte: health-dossie-gemini-brasil] — trouxeram um conjunto de **perguntas de quebra-gelo** desenhadas para a reunião de diagnóstico, organizadas por cadeira. Elas diferem das do bloco B: aquelas eram perguntas que a IA devolvia para aprofundar a pesquisa; estas são **perguntas para o cliente**, calibradas para abrir o desabafo sobre dinheiro parado sem soar como "vendedor de tecnologia". Servem de matéria-prima direta para o roteiro de diagnóstico do Capítulo 6.

### E.1 Diagnóstico de "sangramento de caixa" (foco no custo oculto)

- *"Você sabia que um único auxiliar de faturamento no Lucro Presumido custa quase R$ 5 mil por mês só para navegar em portais e redigitar dados de sistemas como iClinic ou Doctoralia?"* [fonte: health-dossie-estrategico-ia-backoffice-es]
- *"Qual foi o montante de glosas que sua operação 'aceitou' perder no último trimestre por ser administrativamente inviável recorrer de todas?"* [fonte: health-dossie-estrategico-ia-backoffice-es]
- *"Como você identifica hoje, em tempo real, quais vidas na sua fatura já deveriam ter sido excluídas e estão gerando cobrança indevida há meses?"* [fonte: health-dossie-estrategico-ia-backoffice-es]
- *"Sua equipe consegue aplicar a 'Regra 5/50' para prever qual conta PME vai estourar a sinistralidade antes que a operadora envie o boleto com 20% de reajuste?"* [fonte: health-dossie-estrategico-ia-backoffice-es]

### E.2 Para a clínica e o faturista (foco no ciclo e no estrangulamento de capital)

- *"Se eu acompanhasse um ciclo inteiro de vocês — da venda ou elegibilidade até a autorização, o faturamento, o demonstrativo e o recurso de glosa —, em que etapa eu veria mais retrabalho e mais dinheiro parado?"* [fonte: health-dossie-mesa-gpt]
- *"Quando uma conta entra em glosa, o que pesa mais na prática: a perda definitiva do valor, o atraso do valor incontroverso, ou o custo interno de mobilizar equipe para contestar e acompanhar a resposta?"* [fonte: health-dossie-mesa-gpt]
- *"Olhando o ciclo interno de vocês — da elegibilidade na recepção até o envio do lote TISS —, onde estão as maiores goteiras processuais que inflam a glosa administrativa e penalizam o resgate do caixa?"* [fonte: health-dossie-gemini-brasil]

### E.3 Para o corretor (foco na gestão de carteira e sinistralidade)

- *"Para quem vive de PME e contratos com menos de 30 vidas, o que desgasta mais hoje: explicar reajuste, segurar o pós-venda por rede e cobertura, ou administrar inadimplência e cancelamento sem perder a relação com o cliente?"* [fonte: health-dossie-mesa-gpt]
- *"O quanto a falta de previsibilidade sobre a sinistralidade — acesso aos fluxos, detecção de abusos ao longo do tempo — impede que vocês intervenham no uso antes da explosão de custo que leva a um cancelamento pelo RH na renovação?"* [fonte: health-dossie-gemini-brasil]

### E.4 Unificadora de ecossistema (foco sistêmico)

- *"Se estruturássemos uma auditoria prévia e inteligente que fechasse a torneira das inconformidades na origem — tanto o excesso assistencial que colapsa a sinistralidade do cliente quanto o erro de prontuário que gera a glosa —, qual etapa funcional invisível daria o maior respiro operacional e financeiro imediato a todos vocês?"* [fonte: health-dossie-gemini-brasil]

> **Nota de estilo (treinar IA).** As perguntas do dossiê Gemini foram **destiladas** de uma redação original muito rebuscada; aqui estão reescritas em linguagem limpa, preservando a intenção e os jargões-âncora (PMR, glosa administrativa, sinistralidade, lote TISS) e descartando o excesso retórico da fonte. O conteúdo é fiel; a forma foi saneada — coerente com o princípio "tirar repetições/ruído sem perder dado".
