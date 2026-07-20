---
source_file: perplexity-mod3-promocoes-sorteios.md
converted_at: 2026-03-23
original_extension: md
processor: Echo (aiox-m2m-etl)
extraction_quality: full
domain: Promoções, Sorteios e Concursos em Marketing Digital
source_type: perplexity-deep-research
source_tool: Perplexity Pro (Deep Research)
agent_target: juridica-consumidor
squad: squad-cadarn-juridica
module: 3
module_title: Promoções, Sorteios e Concursos — Regulação para Marketing Digital
---

<content>


# Você é um pesquisador especialista em Direito Promocional e regulação de promoções comerciais no Brasil. Sua tarefa é

produzir um módulo exaustivo e atualizado (base: março de 2026) sobre promoções, sorteios, concursos e operações
assemelhadas aplicados a marketing digital. Este documento será inserido em um pipeline RAG para alimentar um agente
de IA jurídico que assessora agências de marketing digital.

Contexto de uso: Este documento será processado por um pipeline automatizado (M2M + RAG). O chunking é feito por
headers Markdown (\#\# e \#\#\#). Os metadados em HTML comment são parseados por regex antes do chunking e funcionam como
tags de classificação semântica — mantenha o formato exato. Output obrigatório: Markdown puro, sem exceções. O
documento será carregado como base de conhecimento de um agente Claude Code (CLI) utilizado por profissionais de uma
agência de marketing digital que atende prestadores de serviços premium (imobiliárias de luxo, clínicas de estética,
escritórios de advocacia) em capitais brasileiras.

  <!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 3] [TEMA:
  promocoes-sorteios-concursos-marketing-digital] -->
Cubra obrigatoriamente:

1. **Marco legal — Lei 5.768/71 e Decreto 70.951/72** — Quais operações exigem autorização prévia (sorteios,
vale-brinde, concursos com premiação). O que mudou com a migração da SEAE/CAIXA para SECAP/SCPC. Processo de
autorização: prazos, custos, documentos, requisitos. Status atual (março 2026) do órgão autorizador.
2. **Concurso cultural — A exceção que não precisa de autorização** — Requisitos cumulativos para que um concurso seja
considerado "cultural" e dispensado de autorização: (a) premiação exclusivamente por mérito/habilidade, (b) sem
vinculação a compra de produto/serviço, (c) sem elemento de sorte/azar. Exemplos práticos para redes sociais: "melhor
foto", "melhor legenda", "desafio criativo". Quando um concurso cultural PERDE a isenção (ex: votação popular =
elemento de sorte?).
3. **Sorteios em redes sociais (Instagram, TikTok, YouTube)** — Como fazer sorteio legal no Instagram: processo
completo de autorização, regras obrigatórias no regulamento, termos de uso da plataforma (Instagram proíbe "curta para
concorrer"?), prazo de validade, prestação de contas. Riscos de sorteios ilegais (sem autorização). Multas e
consequências.
4. **Modalidades promocionais detalhadas** — Para cada tipo, explicar: conceito, se precisa de autorização, requisitos
legais, riscos:
    - Sorteio (vinculado a compra)
    - Vale-brinde
    - Concurso (com premiação)
    - Concurso cultural (sem autorização)
    - "Compre e ganhe" / brinde no ato
    - "Indique um amigo" / programa de referral
    - Cashback e programas de fidelidade
    - Cupom de desconto
    - "Compre X e concorra a Y"
    - Ação de sampling (distribuição de amostras)
5. **Regulamento de promoção — checklist obrigatório** — O que deve conter: período, mecânica, premiação, critérios de
elegibilidade, forma de apuração, data de divulgação de resultados, autorização SECAP (número/série), termo de cessão
de imagem dos ganhadores, legislação aplicável, foro. Template de estrutura.
6. **Promoções em plataformas específicas** — Regras próprias de cada plataforma que devem ser cumpridas ALÉM da
legislação:
    - Instagram/Facebook (Meta) — Promotion Guidelines
    - TikTok — regras de promoções
    - YouTube — políticas de concursos
    - WhatsApp — limitações (promoções via broadcast/grupos)
    - LinkedIn — políticas promocionais
7. **Fiscalização e sanções** — Quem fiscaliza (SECAP, PROCON, Ministério Público). Multas por promoção sem
autorização. Casos recentes de autuação (2023-2026) se verificáveis. Consequências criminais (Art. 45 do Decreto-Lei
6.259/44 — contravenção penal).
8. **Tabela de decisão rápida** — Para uso operacional: tipo de ação → precisa autorização? → órgão → prazo → custo
estimado → risco se fizer sem.

Regras de integridade:

- Cite lei, artigo e URL para cada afirmação legal
- Se a legislação mudou recentemente (SEAE→SECAP→SCPC), documente a transição com datas
- Se não encontrar fonte verificável: "não encontrado com fonte confiável"
- Use HTML comments para metadados: <!-- [MÓDULO: 3] [SUBTEMA: nome] [TIPO: tipo] -->
- Chunks entre 300-800 palavras por seção \#\#/\#\#\#
- Formato: Markdown puro, headers \#\# e \#\#\#, tabelas onde aplicável

Tenho todos os dados necessários. Vou gerar o documento completo agora.

***

<!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 3] [TEMA: promocoes-sorteios-concursos-marketing-digital] -->

# Módulo 3 — Promoções, Sorteios, Concursos e Operações Assemelhadas no Marketing Digital

> **Aviso de validade:** Este módulo foi gerado em março de 2026 com base em legislação e normas vigentes até essa data. Validade estimada: setembro de 2026. Em razão do Grupo de Trabalho instituído pela Portaria SPA/MF nº 230/2026, revisões normativas são esperadas no segundo semestre de 2026. Revisar antes de reutilizar.

***

<!-- [MÓDULO: 3] [SUBTEMA: marco-legal] [TIPO: legislacao-base] -->

## 1. Marco Legal — Lei 5.768/71 e Decreto 70.951/72

### 1.1 Fundamentos Legislativos

A Lei nº 5.768, de 20 de dezembro de 1971 ([https://www.planalto.gov.br/ccivil_03/leis/l5768.htm](https://www.planalto.gov.br/ccivil_03/leis/l5768.htm)), é o diploma central que regula a **distribuição gratuita de prêmios a título de propaganda** no Brasil, abrangendo sorteios, vale-brindes e concursos. O Decreto nº 70.951, de 9 de agosto de 1972 ([https://www.planalto.gov.br/ccivil_03/decreto/antigos/d70951.htm](https://www.planalto.gov.br/ccivil_03/decreto/antigos/d70951.htm)), regulamenta essa lei e detalha os procedimentos operacionais para cada modalidade. Toda promoção que envolva distribuição gratuita de prêmios vinculada à propaganda de produto ou serviço está sujeita a autorização prévia, independentemente do canal — inclusive digital e redes sociais.[^1]

A Lei 14.790/2023 (Lei das Apostas de Quota Fixa) alterou dispositivos da Lei 5.768/71 e transferiu definitivamente as competências de promoção comercial para a estrutura atual do Ministério da Fazenda.[^2]

### 1.2 Transição Institucional: SEAE → SECAP → SPA

A linha histórica do órgão autorizador é:


| Período | Órgão | Estrutura |
| :-- | :-- | :-- |
| Até ~2019 | SEAE (Secretaria de Acompanhamento Econômico) + Caixa Econômica Federal | Ministério da Fazenda |
| 2019–2023 | SECAP (Secretaria de Avaliação, Planejamento, Energia e Loteria) | Ministério da Economia |
| A partir de 2023 | **SPA — Secretaria de Prêmios e Apostas** | **Ministério da Fazenda** |

A **SPA** é atualmente o órgão exclusivo responsável por autorizar, regulamentar, fiscalizar e sancionar promoções comerciais em todo o território nacional.  A Portaria SEAE/ME nº 7.638, de 18 de outubro de 2022, instituiu o **SCPC — Sistema de Controle de Promoções Comerciais** ([https://scpc.seae.fazenda.gov.br](https://scpc.seae.fazenda.gov.br)), plataforma digital que centraliza pedidos de autorização, emissão de certificados e prestação de contas.  A Portaria SPA/MF nº 817, de 15 de abril de 2025, instituiu a Agenda Regulatória para o biênio 2025/2026 da SPA.[^3][^4][^5]

**Atenção (março 2026):** A Portaria SPA/MF nº 230, de 28 de janeiro de 2026, instituiu o **Grupo de Trabalho Promoções Comerciais** para revisar normas sobre distribuição gratuita de prêmios com base nas conclusões do Relatório nº 5/2025 de Análise de Impacto Regulatório.  O grupo tem prazo de 75 dias (conta a partir de 28/01/2026) para apresentar propostas de revisão, tornando possível que novas normas sejam publicadas até meados de 2026. Monitorar o DOU e o portal da SPA.[^6][^7]

### 1.3 Operações que Exigem Autorização Prévia

Conforme Art. 1º da Lei 5.768/71 e Arts. 1º–3º do Decreto 70.951/72, **exigem autorização prévia da SPA**:

- Sorteio vinculado à compra de produto ou serviço
- Vale-brinde (prêmio na embalagem ou acoplado ao produto)
- Concurso com premiação vinculado a propaganda (exceto o concurso cultural — ver Seção 2)
- Operações assemelhadas a sorteio, vale-brinde e concurso (ex: "compre X e concorra a Y")
- Captação antecipada de poupança popular

**Não exigem autorização prévia** (Art. 3º, II, Lei 5.768/71; Art. 30, Decreto 70.951/72):

- Concurso exclusivamente artístico, cultural, desportivo ou recreativo (ver requisitos cumulativos na Seção 2)
- Brindes no ato da compra sem sorteio ("compre e ganhe" sem elemento aleatório)
- Cupons de desconto sem prêmio associado
- Programas de fidelidade sem sorteio
- Cashback puro (devolução de valor ao próprio comprador)


### 1.4 Processo de Autorização: Prazos, Documentos e Custos

**Prazos:**

- Protocolo mínimo: **40 dias** antes do início da promoção[^8][^9]
- Protocolo máximo: **120 dias** antes do início da promoção[^9]
- Prazo de vigência máximo da promoção: 12 meses, prorrogável mediante aditamento

**Documentos obrigatórios (via SCPC):**[^10][^3]

- Regulamento completo da promoção
- Demonstrativo consolidado da receita operacional do promotor (assinado digitalmente — ICP-Brasil PAdES ou gov.br prata/ouro, a partir de 02/01/2025)
- Comprovante de pagamento da GRU (taxa de fiscalização)
- Procuração outorgada pela pessoa jurídica (assinatura digital ICP-Brasil ou gov.br prata/ouro)
- Atas de apuração devem ser assinadas digitalmente (a partir de 02/12/2024)

**Taxas de autorização (vigentes desde 01/01/2025 — Decreto nº 12.307/2024):**[^10]


| Valor total dos prêmios | Taxa GRU (a partir de 01/01/2025) |
| :-- | :-- |
| Até R\$ 1.000,00 | R\$ 34,00 |
| R\$ 1.000,01 a R\$ 5.000,00 | R\$ 166,00 |
| R\$ 5.000,01 a R\$ 10.000,00 | R\$ 334,00 |
| R\$ 10.000,01 a R\$ 50.000,00 | R\$ 1.666,00 |
| R\$ 50.000,01 a R\$ 100.000,00 | R\$ 4.166,00 |
| R\$ 100.000,01 a R\$ 500.000,00 | R\$ 13.334,00 |
| R\$ 500.000,01 a R\$ 1.667.000,00 | R\$ 41.666,00 |
| ≥ R\$ 1.667.000,01 | R\$ 83.334,00 |

*GRU emitida em: [https://pagtesouro.tesouro.gov.br/portal-gru/\#/emissao-gru](https://pagtesouro.tesouro.gov.br/portal-gru/#/emissao-gru)*[^11]

***

<!-- [MÓDULO: 3] [SUBTEMA: concurso-cultural] [TIPO: excecao-autorizacao] -->

## 2. Concurso Cultural — A Exceção sem Autorização

### 2.1 Base Legal e Requisitos Cumulativos

O concurso cultural é a **única modalidade de promoção** isenta de autorização prévia da SPA, nos termos do Art. 3º, II, da Lei 5.768/71 e do Art. 30 do Decreto 70.951/72, reafirmados pela Portaria MF nº 422, de 18 de julho de 2013 ([https://www.gov.br/fazenda/pt-br/acesso-a-informacao/institucional/legislacao/portarias-ministeriais/2013/portaria-no.-422-de-18-de-julho-de-2013](https://www.gov.br/fazenda/pt-br/acesso-a-informacao/institucional/legislacao/portarias-ministeriais/2013/portaria-no.-422-de-18-de-julho-de-2013)).[^12]

Para ser considerado concurso cultural e usufruir da isenção, **todos** os requisitos abaixo devem ser cumpridos cumulativamente:[^13][^14]

1. **Caráter exclusivo:** Ser exclusivamente artístico, cultural, desportivo ou recreativo — não pode ter finalidade promocional de vendas como objetivo primário
2. **Sem subordinação à sorte:** A escolha do vencedor deve ser integralmente por mérito, habilidade ou criatividade avaliados por comissão julgadora — nenhum elemento aleatório pode existir
3. **Gratuidade total:** Participação completamente gratuita, sem custo direto ou indireto
4. **Sem vínculo de compra:** O participante não pode precisar adquirir produto ou serviço da promotora (nem de terceiros) para participar
5. **Prêmio adequado:** O prêmio não pode ser dinheiro, nem produto ou serviço da própria empresa promotora[^14]
6. **Sem vínculo a datas comemorativas:** Não pode ser vinculado a datas comemorativas (Natal, Dia das Mães etc.)[^15]
7. **Sem banco de dados de marketing:** Os dados dos participantes só podem ser usados para identificar e localizar o vencedor — proibido solicitar aceite de comunicações de marketing[^15]

### 2.2 O Concurso Cultural nas Redes Sociais

**Atenção crítica:** A Portaria 422/2013 **proibiu o uso de redes sociais como mecanismo/plataforma para a realização do concurso cultural.**  As redes sociais (Instagram, TikTok, YouTube, Facebook, LinkedIn etc.) só podem ser usadas para **divulgar** a existência do concurso e direcionar os participantes para a plataforma oficial (site próprio da empresa, landing page externa, formulário hospedado no domínio do promotor etc.).[^16][^14][^15]

**O que isso significa na prática:**


| Situação | Permitido? |
| :-- | :-- |
| "Envie sua melhor foto pelo nosso site para concorrer, divulgamos no Instagram" | ✅ Permitido |
| "Comente aqui no Instagram sua melhor legenda para ganhar" | ❌ Proibido como concurso cultural |
| "Clique no link da bio e acesse o formulário para participar do concurso" | ✅ Permitido |
| "Marque 3 amigos e concorra" | ❌ Elemento aleatório + redes sociais como plataforma |
| "Votação popular via Instagram Stories" | ❌ Elemento de sorte (votação popular = aleatório) |

### 2.3 Quando o Concurso Cultural Perde a Isenção

O concurso perde a isenção e passa a exigir autorização quando:[^17][^13][^14]

- Introduz **votação popular** (elemento de sorte/aleatoriedade — a popularidade não reflete mérito técnico)
- Exige compra de produto para participar (ainda que de modo indireto, como "compradores têm pontos extras")
- O prêmio é produto, serviço ou dinheiro da empresa promotora
- É vinculado a datas comemorativas (ex: "Concurso de Fotos Natalinas")
- A participação ocorre diretamente nas funcionalidades da rede social (curtir, comentar, compartilhar como condição de participação)
- Exige preenchimento de cadastro detalhado com fins de marketing
- É divulgado na embalagem de produto da promotora

**Atenção para agências:** "Melhor foto", "melhor legenda" e "desafio criativo" **podem** ser concursos culturais, mas somente se a inscrição for feita em plataforma externa, a avaliação for feita por júri técnico (não votação popular), e não houver nenhum dos vínculos proibidos acima. Se o cliente quiser usar o Instagram como plataforma de participação, deve obter autorização da SPA como concurso ou operação assemelhada.[^1][^15]

***

<!-- [MÓDULO: 3] [SUBTEMA: sorteios-redes-sociais] [TIPO: operacional] -->

## 3. Sorteios em Redes Sociais — Processo Legal Completo

### 3.1 Fundamento: Não Há Distinção de Canal

A legislação brasileira não distingue promoções físicas de digitais. Sorteios realizados no Instagram, TikTok, YouTube ou qualquer outra rede social estão sujeitos às **mesmas regras** da Lei 5.768/71 e do Decreto 70.951/72.  O meio de divulgação é irrelevante para fins de exigência de autorização — o que determina a necessidade é a **natureza da atividade** (distribuição gratuita de prêmios vinculada à propaganda).[^1]

### 3.2 Como Fazer um Sorteio Legal no Instagram: Passo a Passo

**Pré-lançamento (mínimo 40 dias antes):**

1. **Elaborar o regulamento completo** (ver Seção 5 — Checklist)
2. **Calcular o valor total dos prêmios** para determinar a taxa GRU
3. **Emitir e pagar a GRU** via [https://pagtesouro.tesouro.gov.br/portal-gru/\#/emissao-gru](https://pagtesouro.tesouro.gov.br/portal-gru/#/emissao-gru)[^11]
4. **Protocolar pedido no SCPC** em [https://scpc.seae.fazenda.gov.br](https://scpc.seae.fazenda.gov.br) com todos os documentos assinados digitalmente (ICP-Brasil PAdES ou gov.br prata/ouro)[^10]
5. **Aguardar autorização** e receber o **Certificado de Autorização** com número e série
6. **Publicar o número do certificado** em todas as peças de divulgação

**Durante a promoção:**

- Divulgar amplamente o regulamento e o número do certificado SPA
- Toda comunicação deve informar: "Promoção autorizada pela SPA/MF sob o Certificado nº [X]/Série [Y]"
- Manter registro das participações para prestação de contas

**Apuração:**

- A apuração deve ser feita mediante sorteio ligado à Loteria Federal (prática padrão) ou mediante sistema informatizado previamente aprovado
- Ata de apuração deve ser assinada digitalmente (ICP-Brasil PAdES ou gov.br prata/ouro)[^10]

**Pós-promoção:**

- Divulgar o resultado conforme data prevista no regulamento
- Entregar o prêmio ao ganhador e obter comprovante
- **Prestar contas à SPA** via SCPC no prazo de 30 dias após o encerramento da promoção
- Guardar toda documentação por 5 anos


### 3.3 Regras do Instagram para Promoções

As Promotion Guidelines da Meta (Instagram/Facebook) estabelecem:[^18]

- **Isenção obrigatória:** Todo post de sorteio deve conter declaração explícita de que "Instagram não é patrocinador, endossante ou administrador desta promoção"
- **Vedação de marcação inorgânica:** Proibido pedir que participantes marquem pessoas que não aparecem no conteúdo (prática comum em sorteios improvisados)
- **Vedação de compartilhamento obrigatório:** A plataforma não permite exigir compartilhamento de conteúdo no feed ou stories como requisito de participação
- **Vedado "curta para concorrer" como ÚNICO critério:** O Instagram admite curtidas como sinal de engajamento, mas não como única condição de participação — e do ponto de vista da legislação brasileira, curtir não garante identificação do participante


### 3.4 Riscos de Sorteios sem Autorização

**Consequências administrativas e civis:**[^19]

- Multa de **até 100% do valor total dos prêmios** oferecidos
- **Proibição de realizar promoções comerciais por até 2 anos**
- Obrigação de restituição dos prêmios não entregues
- Processo administrativo na SPA

**Consequências criminais:**

- O Decreto-Lei nº 6.259/44 (em seu Art. 45) tipifica como **contravenção penal** a realização de distribuição de prêmios sem autorização do órgão competente — não encontrado acórdão recente específico com fonte verificável, mas a previsão legal permanece vigente

**Consequências reputacionais e de plataforma:**

- Denúncia ao PROCON pelo consumidor prejudicado
- Remoção de conteúdo pelas plataformas
- Ação civil pública pelo Ministério Público

***

<!-- [MÓDULO: 3] [SUBTEMA: modalidades-promocionais] [TIPO: referencia-tecnica] -->

## 4. Modalidades Promocionais — Guia Detalhado

### 4.1 Sorteio (Vinculado a Compra)

**Conceito:** O participante realiza uma compra e obtém número(s) da sorte para concorrer a prêmio mediante sorteio ligado à Loteria Federal ou sistema informatizado aprovado.[^20]

**Autorização:** Obrigatória — SPA/MF via SCPC.[^21][^3]

**Requisitos legais:**

- Regulamento aprovado pela SPA
- Certificado de autorização publicado em todas as peças
- Sorteio atrelado à Loteria Federal ou sistema aprovado
- Valor dos prêmios não pode exceder percentual da receita operacional do promotor (Art. 2º, § 2º, Lei 5.768/71)
- **Proibida a conversão de prêmios em dinheiro** (Art. 2º, § 3º, Lei 5.768/71)[^22]
- Prestação de contas pós-promoção

**Riscos sem autorização:** Multa de até 100% dos prêmios + suspensão de 2 anos + contravenção penal.[^19]

***

### 4.2 Vale-Brinde

**Conceito:** Prêmio inserido ou acoplado ao produto (na embalagem, cápsula, lacre) — o consumidor descobre se ganhou no momento da abertura.[^20]

**Autorização:** Obrigatória — SPA/MF via SCPC.[^3]

**Requisitos legais:**

- Distribuição proporcional de vales-brindes premiados
- Regulamento aprovado
- Prazo de validade obrigatório no próprio produto
- Proibida a conversão em dinheiro

**Aplicação no digital:** Pouco comum no marketing digital puro, mas relevante para e-commerce que envia embalagens físicas com códigos de prêmio.

**Riscos:** Idem ao sorteio.

***

### 4.3 Concurso com Premiação (Modalidade Regulamentada)

**Conceito:** Participante responde a perguntas ou realiza tarefas e concorre por critério misto (resposta correta + sorteio entre os acertantes). Difere do concurso cultural pela presença do elemento aleatório.[^20]

**Autorização:** Obrigatória — SPA/MF via SCPC.[^3]

**Requisitos legais:**

- Pergunta de resposta objetiva (não pode ser obviamente induzida)
- Regulamento aprovado
- Certificado publicado em todas as peças
- Apuração vinculada à Loteria Federal

**Exemplo digital:** "Responda qual o principal benefício do nosso produto e concorra a um voucher de R\$ 2.000" com sorteio entre os acertantes.

***

### 4.4 Concurso Cultural (Sem Autorização)

**Conceito:** Promoção por mérito artístico, cultural, esportivo ou recreativo, sem sorteio, sem vínculo de compra e sem uso das redes sociais como plataforma de participação.[^13][^14]

**Autorização:** **Dispensada** — Art. 3º, II, Lei 5.768/71 e Art. 30, Decreto 70.951/72.[^12]

**Requisitos cumulativos:** Ver Seção 2.1 completa.

**Exemplo digital legítimo:** Concurso de redação promovido via formulário no site da empresa, com julgamento por comissão de especialistas, prêmio em espécie não relacionado à marca, divulgado nas redes sociais apenas como convite a acessar o site.

**Risco principal:** Descaracterização para promoção sujeita a autorização, com todas as sanções cabíveis.

***

### 4.5 "Compre e Ganhe" / Brinde no Ato

**Conceito:** A cada compra (ou compra acima de determinado valor), o cliente recebe um brinde imediatamente, sem elemento aleatório.[^20]

**Autorização:** **Não exigida** — não há sorteio, concurso ou elemento de sorte. Trata-se de desconto na forma de produto adicional.

**Requisitos:** Respeitar o CDC (Código de Defesa do Consumidor — Lei 8.078/90), especialmente quanto à informação clara sobre o brinde (valor, condições, disponibilidade de estoque). Atenção: se o brinde for de valor muito elevado e houver qualquer elemento de sorteio entre compradores, migra para modalidade sujeita a autorização.

**Riscos:** Publicidade enganosa (CONAR/PROCON) se as condições do brinde não forem claras; sem risco de autuação pela SPA.

***

### 4.6 "Indique um Amigo" / Programa de Referral

**Conceito:** O cliente recebe benefício (desconto, crédito, brinde) ao indicar novos clientes que efetivamente realizem uma compra ou cadastro.[^23]

**Autorização:** **Não exigida** — não há sorteio, vale-brinde ou concurso. O benefício é determinístico (se o amigo comprar, o indicador ganha).

**Requisitos legais:**

- Regulamento claro publicado e acessível
- Conformidade com a LGPD (Lei 13.709/2018) para tratamento de dados dos indicados
- Conformidade com o CDC quanto à transparência das condições
- Atenção: se houver sorteio entre os indicadores (ex: "indique e concorra a um iPhone"), passa a exigir autorização SPA

**Riscos sem regulamento:** Práticas abusivas podem atrair PROCON; violações LGPD implicam sanções da ANPD.

***

### 4.7 Cashback e Programas de Fidelidade

**Conceito:** O cliente acumula pontos ou recebe percentual do valor pago de volta, resgatáveis em compras futuras ou em dinheiro.[^24]

**Autorização:** **Não exigida** — não há distribuição gratuita de prêmios; trata-se de desconto condicional ou remuneração diferida.

**Requisitos legais:**

- Regulamento detalhado (prazo de validade dos pontos, condições de resgate, política de cancelamento)
- CDC: transparência total sobre condições
- LGPD: tratamento de dados pessoais conforme base legal adequada
- Resolução BCB nº 96/2021 (arranjos de pagamento): cashback em dinheiro pode envolver regulação do Banco Central se operado por instituição de pagamento não autorizada

**Riscos:** Programa sem regulamento claro gera passivo de reclamações no Procon e Reclame Aqui; operação de cashback com movimentação financeira relevante pode requerer autorização do Banco Central como arranjo de pagamento.

***

### 4.8 Cupom de Desconto

**Conceito:** Código que garante desconto determinado em compra futura — benefício certo, sem aleatoriedade.

**Autorização:** **Não exigida.**

**Requisitos:**

- Informação clara sobre condições de uso (validade, produtos aplicáveis, cumulatividade)
- Conformidade com CDC
- Se o cupom for obtido por sorteio (ex: "sorteamos 10 cupons de 50% entre os seguidores"), a ação de sorteio exige autorização SPA, ainda que o cupom em si seja apenas desconto

***

### 4.9 "Compre X e Concorra a Y"

**Conceito:** Modalidade assemelhada a sorteio — o consumidor que compra determinado produto/serviço ou valor mínimo ganha cupons para concorrer em sorteio posterior. É a modalidade mais utilizada em promoções de varejo e a mais fiscalizada.[^20]

**Autorização:** **Obrigatória** — SPA/MF via SCPC. Classificada como operação assemelhada a sorteio.

**Requisitos:** Idem ao sorteio (Seção 4.1). Regulamento com mecânica de cupons, período, apuração por Loteria Federal, certificado publicado.

**Riscos:** Altíssimo. É a modalidade mais comum em autuações da SPA e denúncias ao PROCON.

***

### 4.10 Ação de Sampling (Distribuição de Amostras)

**Conceito:** Distribuição gratuita de amostras de produto a consumidores, sem sorteio.

**Autorização:** **Não exigida** para distribuição universal (todos recebem). **Exigida** se houver sorteio para definir quem recebe as amostras.

**Requisitos:**

- Conformidade com ANVISA (amostras de cosméticos, alimentos, medicamentos têm regras específicas)
- CDC: transparência sobre a natureza da amostra
- Regras de plataformas: Meta/Instagram proíbe anúncios que oferecem produtos gratuitos como isca para coleta de dados

***

<!-- [MÓDULO: 3] [SUBTEMA: regulamento-checklist] [TIPO: operacional] -->

## 5. Regulamento de Promoção — Checklist Obrigatório

### 5.1 Elementos Obrigatórios por Lei e Regulamento

Todo regulamento de promoção sujeita a autorização deve conter os seguintes elementos:[^21][^3]

**Identificação:**

- [ ] Razão social, CNPJ e endereço completo da empresa promotora
- [ ] Razão social e CNPJ da empresa mandatária (se houver agência gestora)
- [ ] Número e série do Certificado de Autorização SPA/MF

**Período e Abrangência:**

- [ ] Data de início e encerramento da promoção (período de participação)
- [ ] Área geográfica de abrangência (ex: "todo o território nacional")
- [ ] Modalidade (sorteio / vale-brinde / concurso / assemelhado)

**Mecânica e Participação:**

- [ ] Descrição detalhada de como participar (passo a passo)
- [ ] Critérios de elegibilidade (idade mínima — recomenda-se 18 anos; proibição a funcionários e parentes do promotor; outros requisitos)
- [ ] Quantidade máxima de participações por CPF
- [ ] Forma de obtenção dos números da sorte / cupons / inscrições

**Premiação:**

- [ ] Descrição completa de cada prêmio (especificações, marca, modelo quando aplicável)
- [ ] Valor de mercado de cada prêmio (obrigatório para fins da taxa GRU)
- [ ] Quantidade total de prêmios
- [ ] Proibição explícita de conversão em dinheiro (Art. 2º, § 3º, Lei 5.768/71)
- [ ] Procedimento em caso de prêmio não reclamado

**Apuração e Resultado:**

- [ ] Data, local e horário da apuração
- [ ] Método de apuração (Loteria Federal — indicar a extração; sistema informatizado aprovado)
- [ ] Data de divulgação do resultado
- [ ] Canal de divulgação do resultado
- [ ] Prazo para o ganhador se manifestar (mínimo 30 dias)

**Entrega do Prêmio:**

- [ ] Documentos exigidos do ganhador para recebimento
- [ ] **Termo de cessão de uso de imagem e depoimento** (para uso em peças publicitárias — base legal: Art. 5º, X, CF/88 + Art. 20, CC)
- [ ] Prazo de entrega do prêmio após identificação do ganhador
- [ ] Responsabilidade por impostos incidentes sobre o prêmio (IRPF — o prêmio é rendimento tributável para o ganhador; o promotor é responsável pelo recolhimento do IR na fonte à alíquota de 20% sobre o valor excedente à isenção)

**Disposições Gerais:**

- [ ] Legislação aplicável (Lei 5.768/71, Decreto 70.951/72, Portaria SEAE/ME 7.638/2022)
- [ ] Foro de eleição para dirimir controvérsias
- [ ] Isenção de responsabilidade da plataforma de redes sociais (obrigatória pelo Instagram/Meta e demais plataformas)
- [ ] Política de privacidade e uso de dados (LGPD — Lei 13.709/2018)
- [ ] Referência à página de consulta pública no SCPC


### 5.2 Template de Estrutura de Regulamento

```
REGULAMENTO DA PROMOÇÃO "[NOME DA PROMOÇÃO]"

1. EMPRESA PROMOTORA
2. EMPRESA MANDATÁRIA (se houver)
3. CERTIFICADO DE AUTORIZAÇÃO SPA/MF nº [X]/[SÉRIE]
4. PERÍODO DE PARTICIPAÇÃO
5. ÁREA DE ABRANGÊNCIA
6. MODALIDADE
7. COMO PARTICIPAR
8. CRITÉRIOS DE ELEGIBILIDADE
9. PRÊMIOS
   9.1 Descrição dos Prêmios
   9.2 Valor dos Prêmios
   9.3 Vedação de Conversão em Dinheiro
10. APURAÇÃO
    10.1 Data, Local e Horário
    10.2 Método (Loteria Federal — Extração nº [X])
11. DIVULGAÇÃO DO RESULTADO
12. ENTREGA DO PRÊMIO
    12.1 Documentação Necessária
    12.2 Cessão de Imagem
    12.3 Tributação (IR Fonte)
13. DISPOSIÇÕES GERAIS
    13.1 Esta promoção não tem qualquer vínculo com [Plataforma]. [Nome da Plataforma]
         não é patrocinadora, endossante ou administradora desta promoção.
    13.2 Tratamento de Dados Pessoais (LGPD)
    13.3 Legislação Aplicável
    13.4 Foro: [Comarca], com renúncia a qualquer outro.
```


***

<!-- [MÓDULO: 3] [SUBTEMA: plataformas-digitais] [TIPO: operacional] -->

## 6. Promoções em Plataformas Específicas

### 6.1 Instagram e Facebook (Meta)

As Meta Promotion Guidelines (disponíveis em [https://www.facebook.com/policies/pages/promotions](https://www.facebook.com/policies/pages/promotions)) estabelecem:[^18]

**Obrigações:**

- Declaração explícita de que a promoção não é patrocinada, endossada ou administrada pelo Instagram/Facebook, nem a eles associada
- As regras e condições da promoção devem ser claramente comunicadas
- Conformidade com todas as leis locais aplicáveis (incluindo a Lei 5.768/71)

**Vedações (Promotion Guidelines + política de conteúdo):**

- Proibido solicitar marcação de pessoas que **não aparecem** no conteúdo (violação das Community Guidelines do Instagram)
- Proibido exigir compartilhamento no feed ou stories como condição obrigatória de participação
- Proibido incentivar marcações inorgânicas ou artificiais
- Publicidade impulsionada (anúncios) com oferta de prêmios exige conformidade com as Políticas de Publicidade da Meta — alguns tipos de promoção requerem aprovação prévia da Meta para veicular como anúncio

**Boas práticas legais (Brasil + Meta):**

- Publicar o regulamento completo em link externo (site ou landing page do promotor)
- Mencionar o número do certificado SPA em todos os posts
- Usar a declaração de isenção em todo post de sorteio
- Não usar "curta para participar" como único critério (elemento aleatório não mensurável + vedação SEAE)

***

### 6.2 TikTok

**Regras da plataforma (TikTok Promotion Guidelines):**[^18]

- Participantes devem ter no mínimo 18 anos (ou a idade legal na jurisdição)
- Proibida a solicitação de interações artificiais ou enganosas
- As regras do sorteio/concurso devem estar em link externo facilmente acessível
- Proibidas promoções envolvendo produtos controlados (álcool, tabaco, armas, medicamentos sujeitos a prescrição)
- A plataforma exige que o conteúdo promocional seja claramente identificado como tal (\#publi ou equivalente em conformidade com o CONAR — Resolução CONAR nº 174/2022 sobre marketing de influência)

**Atenção legislativa:** O TikTok proibiu campanhas de "siga e ganhe" que geram seguidores artificiais — o que coincide com o entendimento da SPA de que qualquer distribuição de prêmio por critério aleatório vinculado a ação na plataforma exige autorização.

***

### 6.3 YouTube

**Políticas de Concursos do YouTube (disponíveis em [https://support.google.com/youtube/answer/1620498](https://support.google.com/youtube/answer/1620498)):**

- O administrador da promoção é inteiramente responsável pela conformidade com leis locais aplicáveis
- Declaração obrigatória de que o YouTube não é patrocinador da promoção
- Proibido exigir que espectadores votem várias vezes, criem contas múltiplas ou tomem ações que violem os Termos de Serviço do YouTube
- Proibido prometer mais visualizações, curtidas ou inscritos como resultado de participação

**Legislação brasileira aplicada ao YouTube:**

- Sorteios em lives do YouTube seguem integralmente a Lei 5.768/71
- Comentar no vídeo como mecânica de participação + sorteio = operação assemelhada a sorteio exigindo autorização SPA

***

### 6.4 WhatsApp

**Limitações críticas para promoções:**[^18]

- Os **Termos de Serviço do WhatsApp** proíbem o envio de mensagens em massa não solicitadas (spam) — lists de transmissão para usuários que não adicionaram o número como contato violam os termos
- WhatsApp Business API (oficial) permite envio a usuários que optaram por receber comunicações da empresa
- **Proibido no WhatsApp:** Usar grupos para distribuir números da sorte em sorteio sem autorização; usar broadcast para comunicar promoções a listas não optantes

**Legislação LGPD:** O uso de dados pessoais (número de telefone) para fins promocionais exige consentimento específico — base legal de consentimento (Art. 7º, I, LGPD) ou legítimo interesse (Art. 7º, IX, LGPD com análise de necessidade e proporcionalidade).

**Prática recomendada:** WhatsApp como canal de atendimento para esclarecimento de dúvidas sobre promoções, nunca como mecanismo de participação no sorteio.

***

### 6.5 LinkedIn

**Políticas Promocionais do LinkedIn:**

- O LinkedIn permite concursos e promoções, mas exige declaração de que a promoção "não é patrocinada, endossada ou administrada pelo LinkedIn, nem a ele associada"
- Vedado solicitar que usuários "compartilhem para ganhar" de forma que o compartilhamento force exposição indesejada nos feeds de conexões
- Promoções voltadas para B2B (perfil do público do LinkedIn) com prêmios acima de R\$ 10.000 exigem atenção especial ao regulamento LGPD para dados de leads coletados
- Legislação brasileira: se há sorteio entre participantes com critério aleatório, exige autorização SPA independente da plataforma

***

<!-- [MÓDULO: 3] [SUBTEMA: fiscalizacao-sancoes] [TIPO: risco-legal] -->

## 7. Fiscalização e Sanções

### 7.1 Quem Fiscaliza

**SPA — Secretaria de Prêmios e Apostas (órgão primário):**[^4]

- Competência exclusiva para autorizar, fiscalizar e sancionar promoções comerciais
- Fiscalização ativa: monitoramento de promoções divulgadas em redes sociais, e-commerce e mídia
- Canal de denúncia: [promocaocomercial@economia.gov.br](mailto:promocaocomercial@economia.gov.br)[^25]
- Consulta pública de promoções autorizadas: [https://scpc.seae.fazenda.gov.br](https://scpc.seae.fazenda.gov.br)[^25]

**PROCON (estaduais e municipal):**

- Fiscaliza o cumprimento do CDC (Lei 8.078/90)
- Atua em casos de promoção enganosa, não entrega de prêmios, descumprimento do regulamento
- Pode aplicar multas administrativas independentes das sanções da SPA

**Ministério Público:**

- Pode instaurar inquérito civil ou propor Ação Civil Pública por práticas abusivas
- Pode acionar a esfera penal (contravenção) em casos de promoção ilegal sistemática

**Polícia Civil / Federal:**

- Por requisição em inquérito policial, pode investigar promoções fraudulentas (estelionato — Art. 171, CP; contravenção penal — Decreto-Lei 6.259/44)[^25]


### 7.2 Sanções Administrativas

**Multas (Art. 12 e seguintes da Lei 5.768/71 e regulamentação da SPA):**[^19]

- Multa de **até 100% do valor total dos prêmios** oferecidos na promoção irregular
- **Proibição de realizar promoções comerciais por até 2 anos**
- Obrigação de recolher os prêmios não entregues ao Fundo de Defesa de Direitos Difusos (FDD)
- Cancelamento da autorização em caso de irregularidade durante promoção em andamento

**Processo administrativo:**

- Autuação pela SPA
- Prazo para defesa (contraditório e ampla defesa)
- Recurso administrativo cabível
- Inscrição em dívida ativa e execução fiscal em caso de multa não paga


### 7.3 Sanções Criminais

O Decreto-Lei nº 6.259, de 10 de fevereiro de 1944, tipifica como **contravenção penal** (Art. 45) a exploração de jogos de azar e práticas promocionais não autorizadas. A previsão de contravenção permanece vigente e é aplicável a promoções sem autorização que se assimilem a jogos de azar ou exploração ilegal de sorteios.

*Nota de integridade: Não foram encontrados com fonte verificável (março 2026) acórdãos ou condenações criminais recentes (2023–2026) especificamente por promoções comerciais sem autorização SPA. O risco criminal existe normativamente, mas a via administrativa (SPA + PROCON) é a mais frequentemente utilizada para autuação.*

### 7.4 Casos e Tendências de Autuação (2023–2026)

A SPA intensificou o monitoramento de redes sociais desde 2023, com foco em:[^21][^1]

- Sorteios de influenciadores digitais sem certificado SPA
- Promoções de imobiliárias, clínicas e escritórios que realizam "sorteios" de serviços premium sem autorização
- Campanhas "siga e ganhe" de contas comerciais no Instagram e TikTok

*Nota de integridade: Números específicos de autuações para 2024–2026 não foram encontrados com fonte oficial verificável até março de 2026. Monitorar o portal da SPA ([https://www.gov.br/fazenda/pt-br/composicao/orgaos/secretaria-de-premios-e-apostas](https://www.gov.br/fazenda/pt-br/composicao/orgaos/secretaria-de-premios-e-apostas)) para relatórios de fiscalização.*

***

<!-- [MÓDULO: 3] [SUBTEMA: tabela-decisao] [TIPO: referencia-rapida] -->

## 8. Tabela de Decisão Rápida — Uso Operacional

### 8.1 Matriz de Autorização por Tipo de Ação

| Tipo de Ação | Autorização SPA? | Órgão | Prazo para Protocolar | Custo Mínimo (prêmio até R\$ 5k) | Risco sem Autorização |
| :-- | :-- | :-- | :-- | :-- | :-- |
| Sorteio vinculado a compra | **SIM** | SPA/MF via SCPC | 40–120 dias antes | R\$ 166,00 (GRU) | Multa até 100% dos prêmios + suspensão 2 anos |
| Vale-brinde | **SIM** | SPA/MF via SCPC | 40–120 dias antes | R\$ 166,00 (GRU) | Multa até 100% dos prêmios + suspensão 2 anos |
| Concurso com premiação (com sorteio) | **SIM** | SPA/MF via SCPC | 40–120 dias antes | R\$ 166,00 (GRU) | Multa até 100% dos prêmios + suspensão 2 anos |
| "Compre X e concorra a Y" | **SIM** | SPA/MF via SCPC | 40–120 dias antes | R\$ 166,00 (GRU) | Multa até 100% dos prêmios + suspensão 2 anos |
| Concurso cultural (mérito, sem redes sociais como plataforma) | **NÃO** | — | — | — | Risco de requalificação se requisitos não cumpridos |
| "Compre e ganhe" (brinde certo, sem sorteio) | **NÃO** | — | — | — | PROCON (CDC) se condições não forem claras |
| Cupom de desconto | **NÃO** | — | — | — | PROCON/CONAR se enganoso |
| Indique um amigo (benefício certo) | **NÃO** | — | — | — | LGPD/PROCON se sem regulamento |
| Indique um amigo + sorteio entre indicadores | **SIM** | SPA/MF via SCPC | 40–120 dias antes | R\$ 166,00 (GRU) | Multa até 100% dos prêmios |
| Cashback puro | **NÃO** | — | — | — | BCB se movimentação financeira relevante |
| Programa de fidelidade (pontos) | **NÃO** | — | — | — | PROCON se condições opacas |
| Sampling universal (todos recebem) | **NÃO** | — | — | — | ANVISA (produtos regulados) |
| Sampling por sorteio | **SIM** | SPA/MF via SCPC | 40–120 dias antes | R\$ 166,00 (GRU) | Multa até 100% dos prêmios |
| Concurso cultural realizado via Instagram | **NÃO autorizado** pela SPA — mas a ação nas redes é vedada pela Portaria 422/2013 | — | — | Pedir autorização como concurso assemelhado | Requalificação + sanções SPA |

### 8.2 Fluxo de Decisão Simplificado

```
A ação distribui prêmio gratuitamente vinculada à propaganda?
│
├─ NÃO → Sem autorização SPA (verificar CDC, LGPD, CONAR)
│
└─ SIM → Há elemento aleatório (sorteio, azar)?
         │
         ├─ NÃO → É concurso por mérito?
         │        │
         │        ├─ SIM → Cumpre TODOS os requisitos cumulativos do concurso cultural?
         │        │        │
         │        │        ├─ SIM → Concurso Cultural — sem autorização SPA
         │        │        │        (mas NUNCA use redes sociais como plataforma de participação)
         │        │        │
         │        │        └─ NÃO → Concurso sujeito a autorização SPA
         │        │
         │        └─ NÃO → Verificar natureza da ação
         │
         └─ SIM → AUTORIZAÇÃO SPA OBRIGATÓRIA
                  Protocolar no SCPC com 40–120 dias de antecedência
                  Pagar GRU proporcional ao valor dos prêmios
```


***

<!-- [MÓDULO: 3] [SUBTEMA: referencias-legais] [TIPO: indice-normativo] -->

## 9. Índice Normativo — Referências Consolidadas

| Norma | Descrição | URL |
| :-- | :-- | :-- |
| Lei nº 5.768/1971 | Marco legal de promoções comerciais | https://www.planalto.gov.br/ccivil_03/leis/l5768.htm |
| Decreto nº 70.951/1972 | Regulamentação da Lei 5.768/71 | https://www.planalto.gov.br/ccivil_03/decreto/antigos/d70951.htm |
| Portaria MF nº 422/2013 | Concursos culturais — requisitos e vedações | https://www.gov.br/fazenda/pt-br/acesso-a-informacao/institucional/legislacao/portarias-ministeriais/2013/portaria-no.-422-de-18-de-julho-de-2013 |
| Portaria SEAE/ME nº 7.638/2022 | Institui o SCPC e normatiza o processo digital de autorização | https://scpc.seae.fazenda.gov.br |
| Decreto nº 12.307/2024 | Atualiza taxas GRU a partir de 01/01/2025 | — (publicado no DOU em 11/12/2024) |
| Portaria SPA/MF nº 817/2025 | Agenda Regulatória SPA 2025/2026 | https://www.editoraroncarati.com.br/v2/Diario-Oficial/Diario-Oficial/PORTARIA-SPA-MF-Nº-817-DE-15-04-2025.html |
| Portaria SPA/MF nº 230/2026 | GT Promoções Comerciais — revisão normativa em curso | https://legismap.com.br/leis-e-normas/portaria-spa-mf-n-230-de-28-01-2026 |
| Lei nº 14.790/2023 | Apostas de quota fixa — altera Lei 5.768/71 | — |
| MP nº 2.158-35/2001 | Base para taxas de fiscalização | — |
| Lei nº 13.709/2018 (LGPD) | Proteção de dados pessoais aplicável a promoções | https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm |
| CDC — Lei nº 8.078/1990 | Proteção do consumidor | https://www.planalto.gov.br/ccivil_03/leis/l8078compilado.htm |
| SCPC (portal) | Sistema de autorização online | https://scpc.seae.fazenda.gov.br |
| Portal SPA/MF | Página oficial da Secretaria de Prêmios e Apostas | https://www.gov.br/fazenda/pt-br/composicao/orgaos/secretaria-de-premios-e-apostas |


***

*Documento gerado em março de 2026. Validade estimada: setembro de 2026. Monitorar Diário Oficial da União e portal SPA/MF para eventuais revisões decorrentes do Grupo de Trabalho instituído pela Portaria SPA/MF nº 230/2026.*

***

O documento acima é o Módulo 3 completo, em Markdown puro, pronto para ingestão em pipeline RAG. Abaixo seguem os detalhes das fontes que embasam cada seção:[^26][^7][^5][^27][^22][^8][^4][^6][^14][^15][^11][^13][^12][^21][^3][^19][^1][^18][^10]

**Destaques críticos para a agência:**

- O órgão autorizador é atualmente a **SPA (Secretaria de Prêmios e Apostas)**, não mais SEAE nem SECAP — comunicações oficiais e GRU devem referenciar a SPA[^4]
- Desde **01/01/2025**, os valores da GRU foram atualizados pelo Decreto 12.307/2024, e desde **02/01/2025** toda a documentação protocolada no SCPC exige **assinatura digital ICP-Brasil**[^10]
- Uma **revisão normativa está em andamento** (GT instituído em jan/2026 com prazo de 75 dias) — possíveis mudanças nas regras até meados de 2026[^7][^6]
- Concurso cultural **não pode ser realizado via Instagram** como plataforma de participação — somente como canal de divulgação[^14][^15]
- Sorteios de influenciadores e clínicas de estética estão sob monitoramento intensificado pela SPA desde 2023[^1]
<span style="display:none">[^28][^29][^30][^31][^32][^33][^34][^35][^36][^37][^38][^39][^40]</span>

<div align="center">⁂</div>

[^1]: https://webcompany.com.br/blog/regulamentacao-de-sorteios-nas-redes-sociais-no-brasil/

[^2]: https://www.legisweb.com.br/legislacao/?id=475328

[^3]: https://www.gov.br/fazenda/pt-br/composicao/orgaos/secretaria-de-premios-e-apostas/promocao-comercial/scpc

[^4]: https://www.gov.br/fazenda/pt-br/composicao/orgaos/secretaria-de-premios-e-apostas

[^5]: https://www.editoraroncarati.com.br/v2/Diario-Oficial/Diario-Oficial/PORTARIA-SPA-MF-Nº-817-DE-15-04-2025.html

[^6]: https://legismap.com.br/leis-e-normas/portaria-spa-mf-n-230-de-28-01-2026

[^7]: https://bnldata.com.br/ministerio-da-fazenda-cria-grupo-para-modernizar-regras-de-promocoes-comerciais-no-brasil/

[^8]: https://sccsa.com.br/impulso-de-vendas-entenda-os-requisitos-legais/

[^9]: https://incentive.me/blog/secap-sorteios

[^10]: https://fasadv.com.br/pt/bra/publication/atualizacao-dos-valores-da-taxa-de-autorizacao-para-as-promocoes-comerciais

[^11]: https://vilaricapromocaocomercial.com.br/quanto-custa-autorizar-um-sorteio/

[^12]: https://www.gov.br/fazenda/pt-br/acesso-a-informacao/institucional/legislacao/portarias-ministeriais/2013/portaria-no.-422-de-18-de-julho-de-2013

[^13]: https://www.diasteixeira.com.br/post/2015/08/04/os-concursos-culturais-e-a-portaria-4222013-do-ministério-do-estado-da-fazenda-o-que-real

[^14]: https://inovahouse.com.br/blog/concurso-cultural-regras-realizacao/

[^15]: https://www.oconhecimento.com.br/a-realizacao-de-concurso-cultural-e-proibida-nas-redes-sociais/

[^16]: https://g1.globo.com/tecnologia/noticia/2013/07/governo-proibe-concursos-culturais-em-redes-sociais-no-brasil.html

[^17]: https://fflaw.com.br/regras-para-realizacao-de-concursos-culturais-estao-mais-rigidas/

[^18]: https://webcompany.com.br/blog/quais-as-regras-para-sorteios-nas-redes-sociais/

[^19]: https://www.mmdadvogados.com.br/vai-realizar-uma-promocao-comercial-atencao-para-as-regras/

[^20]: https://lrilaw.com.br/2024/06/13/promocoes-comerciais-conceito-geral-e-modalidades/

[^21]: https://blog.autorizacaodesorteios.com.br/promocoes-comerciais-como-funcionam-e-quais-sao-as-regras/

[^22]: https://www.planalto.gov.br/ccivil_03/leis/l5768.htm

[^23]: https://www.fidelimax.com.br/recursos/indicacao-de-amigos/

[^24]: https://www.cashback.pt/referral

[^25]: https://evolutionmarketing.com.br/como-denunciar-sorteios-sem-autorizacao/

[^26]: https://www.planalto.gov.br/ccivil_03/decreto/antigos/d70951.htm

[^27]: https://www.gov.br/fazenda/pt-br/composicao/orgaos/secretaria-de-premios-e-apostas/promocao-comercial

[^28]: https://www2.camara.leg.br/legin/fed/lei/1970-1979/lei-5768-20-dezembro-1971-357812-publicacaooriginal-1-pl.html

[^29]: https://www.administradores.com.br/artigos/sorteio-de-premios-e-promocoes-comerciais-tem-que-seguir-a-lei

[^30]: https://www.gov.br/fazenda/pt-br/composicao/orgaos/secretaria-de-premios-e-apostas/agenda-regulatoria/2025/RelatriodeAnlisedeImpactoRegulatrioPromooComercial.pdf

[^31]: https://premmiar.com.br/blog/legislacao-promocional/

[^32]: https://www2.camara.leg.br/legin/fed/lei/1970-1979/lei-5768-20-dezembro-1971-357812-norma-pl.html

[^33]: https://exame.com/marketing/concursos-culturais-nas-redes-sociais/

[^34]: https://www.youtube.com/watch?v=LXtmW9mtxVo

[^35]: https://www2.camara.leg.br/atividade-legislativa/comissoes/comissoes-permanentes/cespo/apresentacoes-em-eventos/apresentacoes-de-convidados-em-eventos-de-2025/manual-de-instrucoes-para-calculo

[^36]: https://bvalaw.com.br/wp-content/uploads/2021/01/BVA-Promocoes-Comerciais-1.pdf

[^37]: https://scpc.seae.fazenda.gov.br

[^38]: https://blog.polgo.com.br/tudo-o-que-voce-precisa-saber-sobre-distribuicao-gratuita-de-premios-ou-promocao-comercial/

[^39]: https://www.legisweb.com.br/legislacao/?id=473237

[^40]: https://www.mycashback.com.br/referral


</content>
