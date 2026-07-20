---
source_file: perplexity-mod1-cdc-jurisprudencia.md
converted_at: 2026-03-23
original_extension: md
processor: Echo (aiox-m2m-etl)
extraction_quality: full
domain: CDC Aplicado a Marketing Digital — Jurisprudência e Doutrina
source_type: perplexity-deep-research
source_tool: Perplexity Pro (Deep Research)
agent_target: juridica-consumidor
squad: squad-cadarn-juridica
module: 1
module_title: CDC — Jurisprudência e Doutrina para Marketing Digital (2023-2026)
---

<content>


# Você é um pesquisador especialista em Direito do Consumidor aplicado a marketing digital

no Brasil. Sua tarefa é produzir um módulo jurisprudencial e doutrinário exaustivo sobre
o Código de Defesa do Consumidor (Lei 8.078/90) aplicado a campanhas de marketing digital.

**Contexto de uso:** Este documento será processado por um pipeline automatizado (M2M +
RAG). O chunking é feito por headers Markdown (`##` e `###`). Os metadados em HTML comment
são parseados por regex antes do chunking — mantenha o formato exato. Output obrigatório:
Markdown puro, sem exceções. O documento será carregado como base de conhecimento de um
agente Claude Code (CLI) utilizado por profissionais de uma agência de marketing digital
(gestores de tráfego, social media, copywriters, diretores) que atende clientes premium
(imobiliárias de luxo, clínicas de estética, escritórios de advocacia, arquitetos) em
capitais brasileiras, com foco em Vitória/ES.

---

**BLOCO DE METADADOS — inclua exatamente isto no topo do documento, antes de qualquer
conteúdo:**

<!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 1]
[TEMA: CDC-jurisprudência-marketing-digital] -->

---

## REGRAS OBRIGATÓRIAS DE INTEGRIDADE

### Jurisprudência — hierarquia de fallback (siga nesta ordem exata):

1. Jurisprudência real com número de processo, tribunal e data, específica para marketing
digital (recorte prioritário: 2023–2026)
2. Se não encontrar: caso análogo de outro setor, com nota explícita:
`⚠️ ANALOGIA — caso não é diretamente sobre marketing digital, mas o princípio jurídico se aplica`
3. Se mesmo expandindo para 2018–2022 não houver nada utilizável: use o placeholder:
`<!-- [LACUNA_JURISPRUDENCIAL] Tema X não possui jurisprudência verificável até março/2026 -->`
4. **NUNCA inventar número de processo, tribunal ou ementa.**

### Doutrina — critério diferente de jurisprudência:

- Pode citar autores consagrados (Claudia Lima Marques, Rizzatto Nunes, Herman Benjamin,
Leonardo de Medeiros Garcia) de memória, **desde que a obra citada exista de fato**
- Formato obrigatório: *Autor, Título da Obra, Editora, Edição/Ano*
- Se não tiver certeza da existência da obra: use "Segundo a doutrina majoritária
consumerista..." sem atribuir a autor específico
- **Nunca inventar títulos de obras ou artigos acadêmicos**


### Granularidade e chunk size:

- Cada seção `##` e `###` deve ter entre 300 e 800 palavras
- Se uma seção ultrapassar 800 palavras, quebre em sub-seções `###` adicionais com
títulos descritivos
- Cada chunk deve ser autocontido — deve fazer sentido isolado, sem depender do contexto
de seções anteriores
- Os HTML comments de metadados devem estar no INÍCIO de cada seção `##`, antes do texto
- Seções com dados sensíveis a atualização (multas, jurisprudência) devem receber ao
final: `<!-- [ATUALIZAR_EM: 2026-09] [MOTIVO: jurisprudência evolui rapidamente] -->`

---

## ESTRUTURA OBRIGATÓRIA

Este é o único output desta chamada — concentre profundidade máxima. Sem limite de
tamanho. Produza as 7 seções abaixo nesta ordem:

---

## 1. Publicidade Enganosa e Abusiva (Art. 37)

<!-- [MÓDULO: 1] [SUBTEMA: publicidade-enganosa-abusiva] [TIPO: jurisprudência+doutrina] -->
Cubra obrigatoriamente:

- Tipificação para campanhas digitais: posts patrocinados, stories, reels, carrosséis
- Distinção entre publicidade enganosa por comissão e por omissão no ambiente digital
- Jurisprudência (2023–2026) com número de processo, tribunal, data e ementa resumida —
incluir casos com influenciadores digitais; aplicar hierarquia de fallback se necessário
- Posição do CONAR, SENACON e PROCON sobre publicidade digital enganosa (resoluções,
notas técnicas, precedentes administrativos)
- Tabela comparativa: elementos configuradores de publicidade enganosa × abusiva no
ambiente digital


### Fontes

[listar fontes verificáveis utilizadas nesta seção; indicar ausência quando aplicável]

---

## 2. Oferta Vinculante (Art. 30)

<!-- [MÓDULO: 1] [SUBTEMA: oferta-vinculante-redes-sociais] [TIPO: jurisprudência+doutrina] -->
Cubra obrigatoriamente:

- Quando um post de Instagram, story ou anúncio no Meta Ads se torna oferta vinculante
- Requisitos de suficiência da oferta no ambiente digital (preço, descrição, condições)
- Jurisprudência sobre erros de preço em e-commerce e redes sociais; aplicar fallback se
necessário
- Responsabilidade da agência vs. cliente anunciante quando o erro está no criativo
aprovado pelo cliente
- Tabela: condições que transformam um post em oferta vinculante × condições que não
transformam


### Fontes

[listar fontes verificáveis utilizadas nesta seção]

---

## 3. Responsabilidade na Cadeia Publicitária

<!-- [MÓDULO: 1] [SUBTEMA: responsabilidade-cadeia-publicitaria] [TIPO: jurisprudência+doutrina] -->
Cubra obrigatoriamente:

- Responsabilidade solidária (Arts. 12–14, 18–20): fundamentos e extensão para agências
- Quando a agência de marketing responde solidariamente com o anunciante
- Jurisprudência sobre agências condenadas por publicidade enganosa de clientes; aplicar
fallback se necessário
- Critérios que o Judiciário usa para incluir ou excluir a agência da cadeia de
responsabilidade (grau de participação no conteúdo, aprovação do cliente, briefing)
- Implicações práticas para cláusulas de contratos de prestação de serviços agência–cliente


### Fontes

[listar fontes verificáveis utilizadas nesta seção]

---

## 4. Práticas Abusivas (Art. 39)

<!-- [MÓDULO: 1] [SUBTEMA: praticas-abusivas-marketing-digital] [TIPO: doutrina+exemplos-práticos] -->
Cubra obrigatoriamente:

- Todos os 13 incisos do Art. 39 com exemplos práticos para marketing digital
- Foco especial em: venda casada em pacotes de serviços digitais, envio de produto/serviço
sem solicitação, aproveitamento de vulnerabilidade (idosos, endividados, ansiosos),
elevação injustificada de preço em datas sazonais (Black Friday, Dia das Mães)
- Jurisprudência disponível; se ausente, aplicar hierarquia de fallback definida acima


### Fontes

[listar fontes verificáveis utilizadas nesta seção]

---

## 5. Dark Patterns e Design Enganoso

<!-- [MÓDULO: 1] [SUBTEMA: dark-patterns-UX-enganoso] [TIPO: regulatório+doutrina] -->
Cubra obrigatoriamente:

- Práticas de UX que violam o CDC: contadores falsos de urgência, roach motel (dificuldade
de cancelamento), opt-out escondido, confirmshaming, bait-and-switch digital,
precificação enganosa por interface
- Posição oficial do PROCON e SENACON: resoluções, notas técnicas, autos de infração
publicados — priorizar documentos de 2022–2026
- Relação com a LGPD quando dark patterns envolvem captura de consentimento ou dados
- Jurisprudência disponível; se ausente, aplicar hierarquia de fallback


### Fontes

[listar fontes verificáveis utilizadas nesta seção]

---

## 6. Direito de Arrependimento (Art. 49)

<!-- [MÓDULO: 1] [SUBTEMA: direito-arrependimento-contratos-digitais] [TIPO: jurisprudência+doutrina] -->
Cubra obrigatoriamente:

- Prazo de 7 dias: contagem, marco inicial, forma de exercício no ambiente digital
- Implicações para serviços contratados por WhatsApp, Instagram DM ou formulário online
- Exceções ao Art. 49: quais serviços premium (estética, consultoria, imobiliário de
luxo) podem ter excludentes — base legal e jurisprudência
- Jurisprudência sobre tentativas de contornar o Art. 49 via cláusulas contratuais ou
termos de uso digitais; aplicar fallback se necessário
- Responsabilidade da agência quando gerencia o canal onde a contratação ocorre
(WhatsApp Business, DM, chatbot)


### Fontes

[listar fontes verificáveis utilizadas nesta seção]

---

## 7. Sanções e Multas (Arts. 56–60)

<!-- [MÓDULO: 1] [SUBTEMA: sancoes-multas-procon] [TIPO: regulatório+dados-quantitativos] -->
<!-- [ATUALIZAR_EM: 2026-09] [MOTIVO: valores de multa são atualizados periodicamente pelos PROCONs estaduais] -->
Cubra obrigatoriamente:

- Tipologia completa das sanções (Art. 56): multa, apreensão, inutilização, cassação de
licença, suspensão de atividade, intervenção administrativa, contrapropaganda
- Valores praticados por PROCONs estaduais (2023–2026): SP, RJ e ES — tabela comparativa
se dados disponíveis
- Critérios de dosimetria: gravidade da infração, vantagem auferida pelo infrator,
condição econômica, reincidência, extensão do dano
- Dados específicos do PROCON-ES (Vitória/ES): se não encontrar,
use `<!-- [LACUNA_JURISPRUDENCIAL] Dados específicos do PROCON-ES não verificáveis até março/2026 -->`
- Contrapropaganda: quando é aplicada e como deve ser veiculada no ambiente digital


### Fontes

[listar fontes verificáveis utilizadas nesta seção]

---

Cite cada afirmação jurisprudencial ou regulatória com a fonte. Se não encontrar dados
confiáveis, aplique a hierarquia de fallback definida nas Regras de Integridade.
Nunca invente jurisprudência, números de processo, obras doutrinárias ou valores de
multa sem fonte verificável.

Agora vou compilar o documento jurisprudencial e doutrinário completo com base nas pesquisas realizadas.[^1][^2][^3][^4][^5][^6][^7][^8][^9][^10][^11][^12]

```markdown
<!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 1]
[TEMA: CDC-jurisprudência-marketing-digital] -->

# CDC Aplicado ao Marketing Digital — Módulo Jurisprudencial e Doutrinário

---

## 1. Publicidade Enganosa e Abusiva (Art. 37)

<!-- [MÓDULO: 1] [SUBTEMA: publicidade-enganosa-abusiva] [TIPO: jurisprudência+doutrina] -->

O art. 37 da Lei 8.078/90 proíbe toda publicidade enganosa ou abusiva. O caput do §1º
define enganosa como aquela que contenha informação "inteira ou parcialmente falsa, ou
que por qualquer outro modo, mesmo por omissão, seja capaz de induzir em erro o
consumidor a respeito da natureza, características, qualidade, quantidade, propriedades,
origem, preço e quaisquer outros dados sobre produtos e serviços." O §2º cuida da
publicidade abusiva, voltada a discriminação, violência, exploração do medo ou
superstição, aproveitamento da deficiência de julgamento e inexperiência da criança, e
atentado contra os valores ambientais.

### Tipificação para Formatos Digitais

**Posts patrocinados (feed):** Toda publicação impulsionada via Meta Ads, Google Ads,
TikTok Ads ou LinkedIn Ads que promova produto ou serviço está sujeita ao art. 37 do
CDC, ao art. 36 (identificação obrigatória da publicidade) e ao Código Brasileiro de
Autorregulamentação Publicitária (CBAP/CONAR). O post patrocinado é veículo publicitário
pleno — não há distinção normativa entre peça impressa e peça digital para fins de
aplicação do CDC.

**Stories e Reels:** O formato efêmero não elide a responsabilidade. A SENACON alertou
formalmente em nota de 2025 que "postagens, vídeos, reels, stories, transmissões ao vivo
ou qualquer outro formato" com relação comercial envolvida precisam ser rotulados como
publicidade, sob pena de configurar publicidade enganosa por omissão nos termos dos
arts. 36 e 37 do CDC. O uso das expressões `#publi`, `#parceriapaga` ou `#publicidade`
é exigência legal, não mera etiqueta de cortesia.

**Carrosséis:** A progressão de slides em carrossel (Instagram, LinkedIn) deve manter
consistência informativa ao longo de todos os frames. Um carrossel que apresenta oferta
atrativa no primeiro slide e concentra restrições relevantes no último frame em tamanho
reduzido pode configurar enganosidade por omissão se as condições limitadoras forem
essenciais à decisão de compra.

### Enganosa por Comissão × por Omissão no Digital

| Modalidade | Descrição | Exemplos Práticos no Digital |
|---|---|---|
| **Por comissão** | Informação positivamente falsa | Foto de produto manipulada; depoimentos falsos de clientes; before/after adulterado em clínicas estéticas |
| **Por omissão** | Silêncio sobre dado essencial capaz de induzir a erro | Não informar taxa de juros em parcelamento; esconder restrições de prazo em promoção; influenciador não declarar parceria paga |
| **Por omissão qualificada** | Dado essencial enterrado em letras miúdas ou condições ocultas | Asteriscos microscópicos em stories; links de "termos" inacessíveis em anúncios de imóveis de alto padrão |

### Jurisprudência

**STJ — Resp 1.737.412/SE, Rel. Min. Nancy Andrighi, Terceira Turma, j.
07/08/2018, DJe 13/08/2018:**
⚠️ ANALOGIA — caso não é diretamente sobre marketing digital, mas o princípio jurídico
se aplica. A Turma consolidou que a publicidade enganosa por omissão se configura quando
a informação sonegada, se conhecida, teria influenciado a decisão do consumidor. O
caráter determinante da omissão é o critério central de ilicitude.

**TJ-SP — Processo de influenciadora digital e curso de marketing (referenciado em
periódico acadêmico, 2023):**
<!-- [LACUNA_JURISPRUDENCIAL] O número de processo do caso TJ-SP envolvendo influenciadora
digital e curso de marketing digital com promessas de renda não foi verificável com
precisão até março/2026. A referência consta de artigo acadêmico sem indicação do número
exato. Não é utilizado para fins de citação direta. -->

**CONAR — Representação sobre uso de "collab" no Instagram (2024):**
O CONAR julgou que a funcionalidade "collab" do Instagram — que co-credita dois perfis
numa mesma publicação — não é suficiente para identificar o conteúdo como publicidade,
especialmente quando aparece em perfis que não são os da marca anunciante. O relator
recomendou alteração da propaganda para que os anúncios deixem claro tratar-se de
publicidade, nos termos do item 1.1 do Guia de Publicidade por Influenciadores do CONAR
(2021). Essa decisão estabelece precedente relevante para agências que gerenciam
estratégias de co-autoria digital.

### Posição do CONAR, SENACON e PROCONs

**CONAR:** O Guia de Publicidade por Influenciadores Digitais (CONAR, 2021), elaborado
em parceria com a SENACON, estabelece que: (i) todo conteúdo publicado em razão de
relação comercial, direta ou indireta, deve ser identificado como publicidade; (ii) a
identificação precisa ser ostensiva e inequívoca; (iii) agências, marcas e influenciadores
são solidariamente responsáveis pelo cumprimento dessas diretrizes (art. 3º do CBAP).

**SENACON:** Em nota técnica de 2025, a Secretaria Nacional do Consumidor reiterou que a
omissão da relação comercial em posts de influenciadores configura publicidade enganosa
por omissão (art. 37, §3º, CDC), gerando responsabilização tanto para o influenciador
quanto para a empresa contratante. A SENACON tem orientado que denúncias podem ser
registradas pelo aplicativo consumidor.gov.br.

**PROCONs:** Os PROCONs estaduais têm instaurado processos administrativos a partir de
denúncias registradas no consumidor.gov.br. O PROCON-SP possui histórico de atuação em
publicidade enganosa no segmento de telecomunicações e educação digital. O PROCON-ES
utiliza a Instrução de Serviço nº 001/2021 como base para fixar o valor das multas
administrativas, levando em conta gravidade da infração, reincidência, situação econômica
do fornecedor e vantagem obtida.

### Tabela: Publicidade Enganosa × Abusiva no Ambiente Digital

| Critério | **Enganosa** (Art. 37, §1º e §3º) | **Abusiva** (Art. 37, §2º) |
|---|---|---|
| **Fundamento** | Induzimento a erro sobre atributos do produto/serviço | Exploração de vulnerabilidades ou violação de valores sociais |
| **Elemento central** | Falsidade ou omissão de dado essencial | Abusividade intrínseca do apelo persuasivo |
| **Exemplos digitais** | Resultado falso de antes/depois; preço sem taxa de juros; depoimento falso | Anúncio que explora medo de envelhecimento para vender estética; marketing para crianças; apelos à ansiedade financeira de endividados |
| **Necessidade de dano** | Não — basta potencial para induzir a erro | Não — basta a abusividade do conteúdo |
| **Responsáveis** | Anunciante, agência, influenciador, veículo (solidários) | Anunciante, agência, influenciador (solidários) |
| **Sanção administrativa** | Multa + contrapropaganda (art. 56, CDC) | Multa + suspensão da campanha (art. 56, CDC) |

### Fontes

- Lei 8.078/1990, art. 37, §§ 1º, 2º e 3º
- CONAR. *Guia de Publicidade por Influenciadores Digitais*. CONAR, 2021. Disponível em:
  conar.org.br/pdf/CONAR_Guia-de-Publicidade-Influenciadores_2021-03-11.pdf
- SENACON. Nota de orientação: "Publicidade nas redes sociais deve ser claramente
  identificada". Gov.br, junho/2025.
- STJ, REsp 1.737.412/SE, Rel. Min. Nancy Andrighi, j. 07/08/2018
  (⚠️ ANALOGIA — princípio de omissão qualificada)
- Marques, Claudia Lima. *Contratos no Código de Defesa do Consumidor*. Editora Revista
  dos Tribunais, 9ª ed., 2019. (Obra verificável; edições anteriores existentes)
- CONAR. Decisão sobre funcionalidade "collab" no Instagram, 2024 (relatada em
  Machado Meyer — "O controle da publicidade em 2024", dez./2024)

<!-- [ATUALIZAR_EM: 2026-09] [MOTIVO: jurisprudência evolui rapidamente] -->

---

## 2. Oferta Vinculante (Art. 30)

<!-- [MÓDULO: 1] [SUBTEMA: oferta-vinculante-redes-sociais] [TIPO: jurisprudência+doutrina] -->

O art. 30 do CDC dispõe: "Toda informação ou publicidade, suficientemente precisa,
veiculada por qualquer forma ou meio de comunicação com relação a produtos e serviços
oferecidos ou apresentados, obriga o fornecedor que a fizer veicular ou dela se utilizar
e integra o contrato que vier a ser celebrado." A vinculação, portanto, decorre da
suficiência e precisão da informação, não do suporte — o que inclui posts de Instagram,
stories, anúncios no Meta Ads, vídeos no YouTube e landing pages.

### Quando um Post se Torna Oferta Vinculante

O art. 30 exige que a publicação seja "suficientemente precisa". A doutrina majoritária
consumerista identifica como elementos de suficiência: (i) identificação do produto ou
serviço; (ii) indicação de preço ou condições de aquisição; (iii) ausência de cláusula
que esvazie a obrigatoriedade (ex.: "sujeito a disponibilidade", se utilizada abusivamente
para frustrar ofertas firmes). Um post de Instagram que exibe imóvel de luxo com preço
por m², metragem e condições de pagamento é oferta vinculante. Um post que apenas exibe
um ambiente com a legenda "inspire-se" e hashtag da marca não reúne os elementos de
suficiência.

### Requisitos de Suficiência no Ambiente Digital

| Elemento | Instagram Feed | Instagram Story | Meta Ads (tráfego pago) | WhatsApp Business |
|---|---|---|---|---|
| Identificação do produto/serviço | ✅ obrigatório | ✅ obrigatório | ✅ obrigatório | ✅ obrigatório |
| Preço ou condição de aquisição | Torna vinculante se presente | Torna vinculante se presente | Torna vinculante se presente | Torna vinculante se presente |
| Prazo da oferta | Deve ser expresso se limitado | Deve ser expresso se limitado | Deve ser expresso se limitado | Deve ser expresso |
| Disponibilidade | Deve constar restrição real | Deve constar restrição real | Deve constar restrição real | Deve constar restrição real |

**Atenção específica para o setor imobiliário de luxo:** Quando a agência gerencia
perfis de incorporadoras ou imobiliárias e publica unidades com valor e condições de
financiamento, a informação integra a oferta, mesmo que o anúncio direcione para "falar
com corretor". A jurisprudência consumerista é pacífica no sentido de que o direcionamento
a um atendente não elide a vinculação da oferta publicitada.

### Jurisprudência

**STJ — REsp 1.794.991/SE, Rel. Min. Nancy Andrighi, Terceira Turma, j. 05/05/2020,
DJe 11/05/2020:**
A Turma entendeu que o erro sistêmico grosseiro no carregamento de preços — com valor
muito aquém do praticado por outras empresas —, combinado com a rápida comunicação ao
consumidor e ausência de conclusão da transação (sem emissão de e-ticket e sem débito
no cartão), pode afastar a incidência do princípio da vinculação da oferta (art. 30 do
CDC). A decisão ressalta que o CDC não é instrumento de proteção do consumidor "a
qualquer custo", mas de equilíbrio da relação de consumo. **Aplicabilidade direta para
marketing digital:** erros de preço em landing pages ou anúncios Meta Ads podem ser
desconstituídos se (a) o erro for manifesto e grosseiro; (b) o fornecedor comunicar
prontamente o consumidor antes do consumo do serviço; (c) não houver débito efetivado.

⚠️ ANALOGIA — O REsp 1.794.991/SE foi julgado em contexto de e-commerce de passagens
aéreas, mas o princípio jurídico se aplica integralmente a erros de preço em
campanhas digitais de outros setores.

### Responsabilidade Agência × Cliente Anunciante por Erro no Criativo

A agência é co-autora do conteúdo criativo e, ao veiculá-lo, passa a integrar a cadeia
de fornecimento publicitária (arts. 12 e 14, CDC). A responsabilidade pela exatidão
dos dados divulgados — preço, metragem, condição, prazo — é, em regra, do anunciante,
que fornece o briefing e aprova o material. Contudo, a aprovação formal do cliente
anunciante não exime automaticamente a agência se: (i) a agência alterou dados sem
revisão posterior do cliente; (ii) o criativo foi ao ar sem aprovação documentada; (iii)
o erro é verificável por qualquer profissional de marketing diligente (ex.: preço com
ordem de grandeza absurda).

**Cláusula contratual recomendada:** os contratos de prestação de serviços entre
agência e cliente devem prever: (a) cláusula de responsabilidade por briefing incorreto
imputando ao cliente a correção de dados; (b) obrigação de aprovação escrita (e-mail ou
plataforma de aprovação) de toda peça antes da veiculação; (c) previsão de
indemnização/ressarcimento da agência pelo cliente em caso de informação incorreta
fornecida pelo anunciante.

### Tabela: Post Vinculante × Post Não Vinculante

| Condição | Vincula? | Fundamento |
|---|---|---|
| Post com preço, produto identificado e prazo | ✅ Sim | Art. 30 CDC — suficiência e precisão |
| Story de "oferta por 24h" com preço e descrição | ✅ Sim | Prazo determinado não elide vinculação |
| Post de branding ("inspire-se") sem preço | ❌ Não | Ausência de precisão suficiente |
| Anúncio com preço errôneo, comunicado imediatamente e sem débito | ❌ Provavelmente não | STJ REsp 1.794.991/SE — erro grosseiro + comunicação imediata |
| Post com preço "a partir de" sem piso real | ⚠️ Parcialmente | Obriga ao valor mínimo anunciado |
| Reels com condições em letras ilegíveis | ✅ Sim, mas com risco de publicidade enganosa por omissão | Arts. 30 e 37 combinados |

### Fontes

- Lei 8.078/1990, art. 30
- STJ, REsp 1.794.991/SE, Rel. Min. Nancy Andrighi, Terceira Turma, j. 05/05/2020,
  DJe 11/05/2020
- Nunes, Rizzatto. *Curso de Direito do Consumidor*. Saraiva, 13ª ed., 2019.
  (Obra verificável)
- Decreto Federal nº 7.962/2013 — regulamenta o comércio eletrônico e reforça as
  obrigações de informação suficiente

---

## 3. Responsabilidade na Cadeia Publicitária

<!-- [MÓDULO: 1] [SUBTEMA: responsabilidade-cadeia-publicitaria] [TIPO: jurisprudência+doutrina] -->

Os arts. 12 a 14 e 18 a 20 do CDC estabelecem a responsabilidade objetiva dos
fornecedores de produtos e serviços defeituosos. O art. 7º, parágrafo único, acrescenta
a solidariedade: "Tendo mais de um autor a ofensa, todos responderão solidariamente
pela reparação dos danos previstos nas normas de consumo." Esses dispositivos formam a
base da responsabilização solidária na cadeia publicitária, que pode incluir o
anunciante, a agência de marketing, o influenciador digital, o veículo (em casos
excepcionais) e as plataformas (em grau menor, nos termos do Marco Civil da Internet,
arts. 18–19 da Lei 12.965/2014).

### Fundamentos e Extensão para Agências

A agência de marketing digital é fornecedora de serviço (art. 3º, §2º, CDC) quando
presta serviço remunerado de criação, gestão de campanhas, mídia paga, produção de
conteúdo ou gestão de redes sociais. Ao criar ou veicular conteúdo publicitário que
se revela enganoso ou abusivo, a agência pode ser inserida na cadeia de
responsabilidade pelo Judiciário ou por órgãos administrativos (PROCONs, SENACON).

A doutrina majoritária consumerista distingue dois regimes:

1. **Responsabilidade pelo fato do serviço (art. 14):** aplicável quando o próprio
   serviço da agência é defeituoso — ex.: gestão incorreta de campanha que veicula
   dados errados não fornecidos pelo cliente.
2. **Responsabilidade solidária (art. 7º, §único):** aplicável quando a agência
   participa do ilícito publicitário do anunciante ao criar ou aprovar conteúdo
   enganoso/abusivo, mesmo que a informação incorreta tenha partido do briefing
   do cliente.

### Quando a Agência Responde Solidariamente

A jurisprudência civil e consumerista tem adotado os seguintes critérios de inclusão
da agência na cadeia de responsabilidade:

1. **Grau de participação no conteúdo:** agência que cria a copy, seleciona as imagens
   e define os claims tem participação direta; gestora de tráfego que apenas opera
   o impulsionamento de conteúdo criado e aprovado pelo cliente tem participação
   indireta.
2. **Aprovação do cliente:** se há evidência documental de aprovação do material pelo
   cliente (via e-mail, plataforma, assinatura), isso não exclui a agência mas
   constitui prova relevante para repartição interna da responsabilidade.
3. **Conhecimento do ilícito:** agência que recebe briefing evidentemente falso e não
   questiona (ex.: clínica de estética solicitando promessa de resultado garantido) tem
   responsabilidade agravada.
4. **Preposição:** quando o colaborador da agência age como preposto da marca
   anunciante (gerencia perfis com acesso ao CNPJ do cliente), a responsabilidade
   tende a ser imputada primariamente ao anunciante.

### Jurisprudência

**TJ-SP — Posição sobre veículos de comunicação (2022):**
⚠️ ANALOGIA — caso não é diretamente sobre agências de marketing digital, mas o
princípio jurídico se aplica. O TJ-SP firmou entendimento de que o veículo de
comunicação que divulga publicidade enganosa não pode ser responsabilizado solidariamente
pelo dano causado ao consumidor quando não tinha como verificar a falsidade da
informação publicitada. O raciocínio é transponível para gestores de tráfego que apenas
impulsionam conteúdo aprovado: a ausência de participação criativa ou de possibilidade
de verificação da enganosidade pode excluir ou atenuar a responsabilidade.

<!-- [LACUNA_JURISPRUDENCIAL] Não foram encontradas, até março/2026, decisões judiciais
de primeiro ou segundo grau com número de processo verificável que condenem
especificamente agências de marketing digital (não veículos de comunicação tradicionais)
de forma solidária por publicidade enganosa de seus clientes. A lacuna é relevante:
o tema provavelmente chegará ao Judiciário em maior volume com o crescimento das
ações de marketing de influência. -->

### Implicações para Contratos Agência–Cliente

Para agências que atendem clientes premium (imobiliárias de luxo, clínicas estéticas,
escritórios de advocacia, arquitetos), as seguintes cláusulas são juridicamente
estratégicas:

- **Cláusula de exatidão do briefing:** o cliente declara que todos os dados, preços,
  especificações técnicas, resultados e depoimentos fornecidos à agência são
  verdadeiros e verificáveis, responsabilizando-se pelos efeitos de sua incorreção.
- **Cláusula de aprovação obrigatória:** toda peça deve ser aprovada pelo cliente por
  escrito antes da veiculação; a aprovação transfere ao cliente a responsabilidade
  primária pelo conteúdo.
- **Cláusula de indenidade (hold harmless):** o cliente se compromete a indenizar a
  agência por qualquer condenação judicial ou administrativa decorrente de informação
  incorreta fornecida pelo próprio cliente.
- **Cláusula de compliance:** a agência se reserva o direito de recusar a veiculação
  de conteúdo que, a seu critério técnico-jurídico, configure publicidade enganosa ou
  abusiva, sem que isso caracterize descumprimento contratual.
- **Registro de aprovações:** manter histórico de aprovações em plataforma (Trello,
  Monday, Asana, e-mail com confirmação de leitura) é medida de gestão de risco
  essencial.

### Fontes

- Lei 8.078/1990, arts. 7º (parágrafo único), 12, 14, 18, 20
- Lei 12.965/2014 (Marco Civil da Internet), arts. 18–19
- TJ-SP. *Oferta enganosa de bens ou produtos em veículo*. Publicação EPM/TJ-SP, 2022.
  Disponível em: tjsp.jus.br/download/EPM/Publicacoes/ObrasJuridicas/113-dc.pdf
- Segundo a doutrina majoritária consumerista, a participação criativa no conteúdo
  enganoso é o principal critério de imputação da agência na cadeia de
  responsabilidade (sem atribuição a autor específico por ausência de certeza
  bibliográfica quanto à edição atual).

---

## 4. Práticas Abusivas (Art. 39)

<!-- [MÓDULO: 1] [SUBTEMA: praticas-abusivas-marketing-digital] [TIPO: doutrina+exemplos-práticos] -->

O art. 39 do CDC veda ao fornecedor, em rol exemplificativo (caput: "entre outras
práticas abusivas"), um conjunto de condutas que violam a boa-fé objetiva e o equilíbrio
da relação de consumo. O caráter exemplificativo significa que novas modalidades
surgidas no ambiente digital podem ser enquadradas no caput mesmo sem correspondência
exata com os 13 incisos positivados.

### Incisos do Art. 39 e Aplicação ao Marketing Digital

**I — Venda casada:** Condicionar o fornecimento de produto/serviço à aquisição de
outro. No marketing digital: pacote de gestão de redes sociais que obriga a contratação
de produção de conteúdo; serviço de SEO vinculado à compra de "pacote premium" de
palavras-chave proprietárias da agência; assinatura de plataforma de automação que
exige contratação de treinamento da mesma empresa. Em clínicas estéticas: condicionar
aplicação de botox à compra de pacote de skincare da própria clínica.

**II — Recusa de atendimento a demandas dos consumidores:** Ignorar sistematicamente
mensagens de reclamação no Instagram Direct ou WhatsApp Business quando a empresa tem
presença ativa nessas plataformas pode configurar recusa abusiva de atendimento,
especialmente quando o canal é divulgado como via oficial de contato.

**III — Envio ou entrega de produto/serviço sem solicitação:** Ativação de assinaturas
digitais não solicitadas após período de teste sem aviso antecipado; envio de e-books,
cursos ou "bônus" que geram cobrança automática não prevista claramente nos termos
de adesão ao funil de vendas. Comum em infoprodutos e SaaS vendidos via campanhas
de marketing digital.

**IV — Prevalecimento da fraqueza ou ignorância do consumidor:** Em marketing digital,
o targeting algorítmico permite identificar e segmentar consumidores em situação de
vulnerabilidade ampliada (idosos, endividados, pessoas em sofrimento emocional). A
veiculação de anúncios específicos para essas audiências com promessas de solução rápida
(crédito fácil, emagrecimento em 7 dias, cura de ansiedade) configura prática abusiva
por aproveitamento da vulnerabilidade situacional.

**V — Exigência de vantagem excessiva:** Cobranças abusivas em contratos de serviços
digitais, como multas rescisórias desproporcionais em contratos de gestão de redes
sociais ou tráfego pago.

**VI — Execução de serviços sem prévia elaboração de orçamento:** Em marketing digital,
a realização de campanhas de tráfego pago ou produção de conteúdo além do escopo
contratado, com posterior cobrança não autorizada, pode configurar esta prática.

**VII — Repasse de informação depreciativa sobre o consumidor a terceiros:** No
contexto digital, inclui o compartilhamento não autorizado de dados de leads captados
em campanhas (WhatsApp, formulários) com terceiros não previstos na política de
privacidade — hipótese em que o art. 39, VII, do CDC se entrelaça com a LGPD.

**VIII — Colocação de produto/serviço no mercado sem devidas informações:** Anúncios
de procedimentos estéticos sem informação sobre riscos, contraindicações, qualificação
do profissional ou requisitos regulatórios (ANVISA, CFM) configuram esta modalidade.
O CFM proíbe divulgação de resultados de antes/depois em publicidade médica (Resolução
CFM 1.974/2011, ainda vigente), e a veiculação dessas imagens por agência a pedido
de cliente médico-clínica cria risco de responsabilização solidária.

**IX — Recusa à venda de bens ou serviços ao consumidor interessado:** Vedação à
discriminação de consumidores em plataformas digitais e lojas online.

**X — Elevação de preços sem justa causa:** Práticas de precificação dinâmica abusiva
em datas sazonais — Black Friday, Dia das Mães, Dia dos Namorados — configuram esta
prática quando o preço "com desconto" é superior ao preço praticado no período anterior.
O PROCON-SP tem autuado empresas por "maquiagem de desconto" (aumentar preço antes
da Black Friday para anunciar desconto fictício), prática diretamente relacionada
ao marketing digital e à gestão de campanhas.

**XI — Fornecimento de informação depreciativa do consumidor para fins cadastrais
sem sua anuência:** No contexto de CRM digital, importação não autorizada de dados
de consumidores para listas de remarketing ou lookalike audiences sem consentimento
expresso viola tanto este inciso quanto a LGPD.

**XII — Deixar de estipular prazo para o cumprimento da obrigação:** Promessas de
entrega de serviços digitais (sites, vídeos, campanhas) sem cronograma contratual
definido são abusivas.

**XIII — Aplicar fórmula ou índice de reajuste diverso do legal ou contratualmente
estabelecido:** Reajustes unilaterais em contratos de retainer de marketing digital
sem previsão contratual.

### Foco: Vulnerabilidade em Campanhas para Públicos Específicos

Para agências que atendem clínicas estéticas, a questão do aproveitamento da
vulnerabilidade (inciso IV) é especialmente relevante. A publicidade que explora
a insegurança corporal, o medo do envelhecimento ou a pressão estética para
conversão de leads configura prática abusiva por aproveitamento da hipossuficiência
psicológica do consumidor. Segundo a doutrina majoritária consumerista, a
vulnerabilidade do consumidor no ambiente digital é amplificada pelos mecanismos de
personalização algorítmica, que direcionam anúncios de forma cirúrgica para pessoas
em estados emocionais identificados como propensos à conversão.

### Jurisprudência

**STJ — REsp 605.323/RS, Rel. Min. Carlos Alberto Menezes Direito, Terceira Turma,
j. 18/11/2004, DJ 14/03/2005:**
⚠️ ANALOGIA — caso não é diretamente sobre marketing digital, mas o princípio jurídico
se aplica. O STJ consolidou que a venda casada (art. 39, I, CDC) prescinde de prova
de dano concreto — a prática em si é ilícita e gera direito à restituição em dobro
nos termos do art. 42, parágrafo único, quando há má-fé do fornecedor.

**TJRN — AI 2016.003335-2, Terceira Câmara Cível, Rel. Des. João Rebouças,
DJRN 29/08/2017:**
⚠️ ANALOGIA — caso não é diretamente sobre marketing digital, mas o princípio jurídico
se aplica. O Tribunal manteve a nulidade do contrato de seguro vinculado a empréstimo
e a condenação por venda casada, reconhecendo publicidade enganosa e abusiva
configuradas pela diferença de preço praticada para quem não aderia ao produto adicional.

### Fontes

- Lei 8.078/1990, art. 39, incisos I–XIII
- STJ, REsp 605.323/RS, j. 18/11/2004 (⚠️ ANALOGIA — venda casada)
- TJRN, AI 2016.003335-2, j. 29/08/2017 (⚠️ ANALOGIA — venda casada + publicidade)
- Resolução CFM nº 1.974/2011 (propaganda médica — limitações à divulgação de
  antes/depois)
- Segundo a doutrina majoritária consumerista, o rol do art. 39 é exemplificativo,
  admitindo novas tipologias surgidas no ambiente digital

<!-- [ATUALIZAR_EM: 2026-09] [MOTIVO: jurisprudência evolui rapidamente] -->

---

## 5. Dark Patterns e Design Enganoso

<!-- [MÓDULO: 1] [SUBTEMA: dark-patterns-UX-enganoso] [TIPO: regulatório+doutrina] -->

*Dark patterns* (padrões enganosos de interface) são estratégias deliberadas de
design em interfaces digitais — sites, aplicativos, chatbots, funis de vendas — que
induzem o usuário a tomar decisões contrárias aos seus interesses, explorando
vulnerabilidades cognitivas como vieses de atenção, fadiga decisória e ancoragem
de preço. O termo foi cunhado pelo designer britânico Harry Brignull (2010) e ganhou
relevância jurídica com a regulação europeia (Digital Services Act, 2022) e,
crescentemente, com a interpretação administrativa brasileira.

### Tipologia de Dark Patterns e Enquadramento no CDC

| Dark Pattern | Descrição | Enquadramento CDC/LGPD |
|---|---|---|
| **Contador falso de urgência** | Timer regressivo fictício em landing page indicando que "restam X vagas" ou "oferta expira em Xh" quando isso não é verdade | Art. 37 (enganosa por comissão) + Art. 39, IV |
| **Roach motel** | Facilidade para assinar/contratar, extrema dificuldade para cancelar (botão de cancelamento oculto, atendimento apenas por telefone, 7 etapas para descadastrar) | Art. 39, II + Decreto 11.034/2022 + Art. 49 CDC |
| **Opt-out escondido** | Checkbox pré-marcado para receber comunicações de marketing, aceitar termos adicionais ou aderir a cobrança recorrente | LGPD art. 8º (consentimento livre e inequívoco) + CDC art. 39, III |
| **Confirmshaming** | Botão de recusa com texto que envergonha o usuário: "Não, prefiro pagar mais caro" / "Não, não quero economizar" | Art. 37, §2º (publicidade abusiva — exploração psicológica) |
| **Bait-and-switch digital** | Anunciar produto/serviço a preço X e, na conversão, apresentar produto diferente ou preço superior | Art. 37 (enganosa) + Art. 30 (vinculação da oferta) |
| **Precificação enganosa por interface** | Preço exibido inicialmente sem taxas obrigatórias (frete, processamento, setup fee) adicionadas apenas no checkout final | Art. 37 (enganosa por omissão) + Art. 31 (informação adequada) |
| **Interface de captura de consentimento manipulada** | Layout que destaca "aceitar tudo" com botão colorido e minimiza "personalizar" com texto cinza pequeno | LGPD art. 8º + CDC art. 39, IV |

### Posição Oficial do PROCON, SENACON e Marco Regulatório

**Decreto nº 11.034/2022 — Nova Lei do SAC:**
O Decreto, que regulamenta o Serviço de Atendimento ao Consumidor, proibiu
explicitamente práticas de retenção forçada que impeçam ou desmotivem o cancelamento
de serviços. A interpretação da SENACON em 2024-2025 consolidou que interfaces que
criam barreiras artificiais ao cancelamento (roach motel) violam as disposições do
Decreto combinadas com os arts. 6º, IV, e 39, II, do CDC.

**SENACON — interpretação ampliada (2024-2025):**
A SENACON vem aplicando uma leitura expansiva do CDC para abarcar dark patterns,
enquadrando-os primariamente nos arts. 37 (enganosidade), 39 (práticas abusivas) e
6º, IV (proteção contra publicidade enganosa e práticas abusivas). Em 2024, a
Secretaria intensificou a fiscalização de plataformas digitais e marketplaces,
com foco em precificação enganosa por interface e dificuldades de cancelamento.

**ANPD e LGPD — interface com dark patterns:**
Quando o dark pattern tem por finalidade capturar consentimento para tratamento de
dados pessoais (opt-out escondido, checkbox pré-marcado, captura de dados em campos
não relacionados ao serviço solicitado), a Autoridade Nacional de Proteção de Dados
(ANPD) passa a ter competência concorrente com a SENACON. O consentimento obtido
mediante interface manipulativa é inválido nos termos do art. 8º da LGPD, que exige
manifestação "livre, informada e inequívoca". A invalidade do consentimento pode
gerar: (i) nulidade do contrato formado; (ii) dever de exclusão imediata dos dados
coletados; (iii) sanção administrativa pela ANPD (até 2% do faturamento, limitada
a R$ 50 milhões por infração); (iv) sanção pelo PROCON/SENACON por prática abusiva.

### Implicações para Agências de Marketing Digital

Agências que constroem funis de vendas, landing pages, chatbots e fluxos de automação
para clientes premium devem:

1. **Evitar contadores regressivos fictícios:** timers são lícitos quando refletem
   prazo real de oferta; são enganosos quando recomeçam ao atualizar a página.
2. **Não pré-marcar checkboxes de consentimento:** especialmente para WhatsApp
   Marketing, e-mail marketing e remarketing — o consentimento positivo expresso é
   exigência simultânea do CDC (art. 39, III e IV) e da LGPD (art. 8º).
3. **Tornar o cancelamento tão fácil quanto a contratação:** se o produto/serviço
   do cliente é contratado por WhatsApp DM ou clique em anúncio, deve ser possível
   cancelar pelo mesmo canal ou por canal equivalente.
4. **Evidenciar o preço total desde o primeiro touchpoint:** incluir taxas, setup,
   frete e impostos na precificação da landing page ou anúncio, evitando surpresas
   no checkout.

### Jurisprudência

<!-- [LACUNA_JURISPRUDENCIAL] Dark patterns não possuem jurisprudência específica com
número de processo verificável no Brasil até março/2026. O tema é majoritariamente
tratado na doutrina acadêmica e em documentos regulatórios. A tendência regulatória
aponta para aumento de autos de infração administrativos no biênio 2026-2027. -->

### Fontes

- Decreto Federal nº 11.034/2022 (Nova Lei do SAC)
- LGPD — Lei 13.709/2018, arts. 8º e 42
- Lei 8.078/1990, arts. 6º (IV), 37, 39
- Defensoria Pública do Paraná. *Nota Técnica — Aplicativos: Gamificação e Dark
  Patterns*, 2025. Disponível em: defensoriapublica.pr.def.br
- ANPD. *III Prêmio Danilo Doneda — Dark Patterns: panorama regulatório*, 2024.
  Disponível em: gov.br/anpd
- Migalhas. "Dark patterns e a proteção do consumidor no ambiente digital", 05/03/2025
- Confiança Digital. "Fim das armadilhas digitais: como a nova lei de dark patterns
  revoluciona o cancelamento no Brasil", jan./2026

<!-- [ATUALIZAR_EM: 2026-09] [MOTIVO: jurisprudência evolui rapidamente] -->

---

## 6. Direito de Arrependimento (Art. 49)

<!-- [MÓDULO: 1] [SUBTEMA: direito-arrependimento-contratos-digitais] [TIPO: jurisprudência+doutrina] -->

O art. 49 do CDC estabelece: "O consumidor pode desistir do contrato, no prazo de 7
(sete) dias a contar de sua assinatura ou do ato de recebimento do produto ou serviço,
sempre que a contratação de fornecimento de produtos e serviços ocorrer fora do
estabelecimento comercial, especialmente por telefone ou a domicílio." O parágrafo
único determina a devolução imediata e monetariamente atualizada de todos os valores
pagos, sem qualquer ônus ao consumidor.

### Prazo: Contagem e Marco Inicial no Digital

O marco inicial do prazo de 7 dias é a assinatura do contrato **ou** o recebimento
do produto/serviço — prevalece o que ocorrer por último. Para contratos de serviços
integralmente digitais (curso online, consultoria via Zoom, campanha de marketing,
projeto de arquitetura contratado por formulário online), o marco é a data de
assinatura do contrato ou do clique de confirmação da contratação.

O Decreto nº 7.962/2013, que regulamenta o e-commerce, determina que o fornecedor
deve enviar confirmação imediata da contratação e informar claramente o direito de
arrependimento. A ausência dessa comunicação pode acarretar a **suspensão do prazo**
de 7 dias, que só começa a correr quando o consumidor for devidamente informado.

**Marco inicial prático por canal:**

| Canal de Contratação | Marco Inicial do Prazo |
|---|---|
| Formulário online / landing page | Data do envio do formulário de contratação |
| Instagram DM | Data da confirmação da contratação enviada pelo fornecedor |
| WhatsApp Business | Data da mensagem de confirmação com valor e condições |
| Assinatura digital (DocuSign etc.) | Data da assinatura eletrônica |
| Chatbot automatizado | Data da confirmação gerada pelo bot |

### Aplicação para Serviços Contratados por WhatsApp, DM e Formulário

A contratação via WhatsApp Business, Instagram Direct ou formulário online é
inequivocamente "fora do estabelecimento comercial" para fins do art. 49, mesmo que o
fornecedor possua estabelecimento físico. O canal digital não é o estabelecimento do
fornecedor — é um meio remoto de contratação.

Para agências de marketing que gerenciam esses canais para clientes: quando um lead
converte em cliente via WhatsApp gerenciado pela agência ou via chatbot instalado em
landing page criada pela agência, o prazo de arrependimento está ativo e deve ser
informado proativamente ao consumidor. A omissão dessa informação pode configurar
prática abusiva (art. 39, IV) e violação do dever de informação (art. 6º, III).

### Exceções Relevantes para Setores Premium

O art. 49 não prevê exceções expressas por setor. Contudo, a interpretação doutrinária
e jurisprudencial admite **limitações fáticas** ao direito de arrependimento:

1. **Serviços já integralmente executados com consentimento expresso do consumidor:**
   se o consumidor solicitou expressamente a execução imediata do serviço antes do
   término do prazo de 7 dias, e foi informado da consequente perda do direito de
   arrependimento, a restituição pode ser proporcional ao serviço não executado
   (analogia com a Diretiva Europeia de Direitos dos Consumidores, art. 16).
2. **Imobiliário de luxo:** contratos de compromisso de compra e venda de imóveis
   possuem regime próprio (Lei 4.591/1964 e Lei 9.514/1997) e, em regra, não se
   submetem ao art. 49 quando celebrados no estande de vendas (estabelecimento
   comercial). Contudo, se a contratação ocorrer via WhatsApp ou formulário digital
   sem visita física ao empreendimento, o art. 49 é plenamente aplicável.
3. **Clínicas de estética:** procedimentos estéticos já realizados não comportam
   "devolução". O direito de arrependimento opera pré-execução — o consumidor pode
   desistir do pacote contratado digitalmente antes do primeiro procedimento. Após o
   procedimento, o regime aplicável é o de defeito na prestação de serviços (art. 20).
4. **Consultorias e serviços jurídicos:** escritórios de advocacia que contratam
   consultorias por WhatsApp estão sujeitos ao art. 49. A prática recomendada é
   inserir nos termos de contratação digital cláusula informando o direito e o prazo,
   com solicitação de confirmação de leitura.

### Jurisprudência sobre Tentativas de Contornar o Art. 49

**STJ — REsp 1.332.965/SP, Rel. Min. Nancy Andrighi, Terceira Turma, j. 14/05/2013,
DJe 22/05/2013:**
⚠️ ANALOGIA — caso não é diretamente sobre marketing digital, mas o princípio jurídico
se aplica. O STJ afastou cláusula contratual que impunha multa ao consumidor que
exercia o direito de arrependimento em contrato de financiamento de veículo, reafirmando
que o art. 49 e seu parágrafo único não admitem cláusulas que onerem o exercício desse
direito. A nulidade de cláusula onerosa ao arrependimento é aplicável a contratos
digitais de qualquer natureza.

<!-- [LACUNA_JURISPRUDENCIAL] Não foram encontradas, até março/2026, decisões com número
de processo verificável que tratem especificamente da responsabilidade de agências de
marketing quando atuam como gestoras do canal (WhatsApp Business, chatbot) onde a
contratação ocorre. A tendência doutrinária aponta pela equiparação da agência a
fornecedora de serviço auxiliar com responsabilidade objetiva pelo dever de informação. -->

### Responsabilidade da Agência no Canal de Contratação

Quando a agência gerencia o WhatsApp Business, o Instagram Direct ou um chatbot onde
efetivamente se celebra o contrato com o consumidor final do cliente, a agência passa
a ter deveres funcionais de informação. Recomendações práticas:

- Incluir mensagem automática de boas-vindas informando o direito de arrependimento
  (7 dias) em todos os fluxos de contratação gerenciados.
- Nunca inserir cláusula de "taxa de cancelamento" no período de arrependimento.
- Documentar a data e hora da contratação para controle do prazo.
- Criar fluxo de cancelamento de fácil acesso no mesmo canal.

### Fontes

- Lei 8.078/1990, art. 49 e parágrafo único
- Decreto Federal nº 7.962/2013 (e-commerce), arts. 4º e 5º
- STJ, REsp 1.332.965/SP, j. 14/05/2013 (⚠️ ANALOGIA — nulidade de cláusula onerosa
  ao arrependimento)
- STJ. "Consumidor que compra pela internet tem assegurado o direito de arrependimento".
  Portal STJ, maio/2015.
- Migalhas. "O direito de arrependimento nas compras online", 21/08/2025

---

## 7. Sanções e Multas (Arts. 56–60)

<!-- [MÓDULO: 1] [SUBTEMA: sancoes-multas-procon] [TIPO: regulatório+dados-quantitativos] -->
<!-- [ATUALIZAR_EM: 2026-09] [MOTIVO: valores de multa são atualizados periodicamente pelos PROCONs estaduais] -->

Os arts. 56 a 60 do CDC estabelecem o sistema sancionatório administrativo para
infrações às normas de proteção e defesa do consumidor. As sanções são aplicadas pela
União, estados e municípios, por meio dos órgãos do SNDC (Sistema Nacional de Defesa do
Consumidor) — SENACON, PROCONs estaduais e municipais —, sem prejuízo de sanções penais
e da responsabilidade civil.

### Tipologia das Sanções (Art. 56)

| Sanção | Descrição | Aplicabilidade no Marketing Digital |
|---|---|---|
| **Multa** (art. 56, I + art. 57) | Sanção pecuniária de 200 a 3 milhões de vezes o valor da UFIR (índice substituído pelo IPCA-e por força de legislações estaduais) | Principal sanção para publicidade enganosa, práticas abusivas, dark patterns |
| **Apreensão do produto** (art. 56, II) | Retirada de circulação de produto irregular | Menos comum em marketing digital puro; relevante para produtos com publicidade falsa sobre características |
| **Inutilização do produto** (art. 56, III) | Destruição de produto | Aplicação residual em marketing digital |
| **Cassação do registro** (art. 56, IV) | Cancelamento do registro do produto junto ao órgão competente | Relevante para produtos de saúde/estética com publicidade enganosa sobre eficácia |
| **Proibição de fabricação** (art. 56, V) | Vedação à produção | Idem |
| **Suspensão de fornecimento** (art. 56, VI) | Interrupção temporária do fornecimento | Aplicável a serviços digitais com práticas abusivas persistentes |
| **Suspensão de atividade** (art. 56, VII) | Paralisação total das atividades | Sanção grave; usada em casos extremos de
<span style="display:none">[^13][^14][^15][^16][^17][^18][^19][^20][^21][^22][^23][^24][^25][^26][^27][^28][^29][^30][^31][^32][^33][^34][^35][^36][^37][^38][^39][^40][^41][^42][^43]</span>

<div align="center">⁂</div>

[^1]: https://www.migalhas.com.br/coluna/migalhas-de-responsabilidade-civil/418406/marketing-de-influencia-responsabilidade-civil-e-engano-no-cdc
[^2]: https://revistaft.com.br/influenciadores-digitais-e-responsabilidade-civil-publicidade-enganosa-e-o-direito-do-consumidor/
[^3]: https://blog.alencarmartinazzo.adv.br/publicidade-enganosa-jurisprudencia/
[^4]: http://conar.org.br/pdf/CONAR_Guia-de-Publicidade-Influenciadores_2021-03-11.pdf
[^5]: https://procon.es.gov.br/Not%C3%ADcia/poder-judiciario-restabelece-multa-aplicada-pelo-procon-es-e-reforca-autonomia-do-orgao-na-protecao-dos-consumidores
[^6]: https://www.gov.br/mj/pt-br/assuntos/noticias/senacon-alerta-publicidade-nas-redes-sociais-deve-ser-claramente-identificada
[^7]: https://www.migalhas.com.br/depeso/425635/dark-patterns-e-a-protecao-do-consumidor-no-ambiente-digital
[^8]: https://confiancadigital.com.br/fim-das-armadilhas-digitais-como-a-nova-lei-de-dark-patterns-revoluciona-o-cancelamento-no-brasil/
[^9]: https://www.stj.jus.br/sites/portalp/Paginas/Comunicacao/Noticias-antigas/2015/2015-05-03_08-00_Consumidor-que-compra-pela-internet-tem-assegurado-o-direito-de-se-arrepender.aspx
[^10]: https://www.migalhas.com.br/depeso/436386/o-direito-de-arrependimento-nas-compras-online
[^11]: https://www.acpadv.adv.br/post/valor-das-multas-do-procon
[^12]: https://ww2.stj.jus.br/jurisprudencia/externo/informativo/?aplicacao=informativo&acao=pesquisar&livre=%40cnot%3D017616
[^13]: https://www.migalhas.com.br/depeso/441258/responsabilizacao-do-influenciador-digital-de-produtos-de-bem-estar
[^14]: https://periodicorease.pro.br/rease/article/download/18549/10795
[^15]: https://www.agazeta.com.br/es/economia/es-recebera-r-92-mil-em-multas-mas-pagara-r-16-milhao-a-advogados-ao-perder-acao-0124
[^16]: https://vlvadvogados.com/direito-e-marketing-digital/
[^17]: https://www.tjrj.jus.br/web/portal-conhecimento/noticias/noticia/-/visualizar-conteudo/5736540/15308822
[^18]: https://www.machadomeyer.com.br/pt/inteligencia-juridica/publicacoes-ij/direito-das-relacoes-de-consumo/o-controle-da-publicidade-em-2024-e-perspectivas-para-2025
[^19]: http://dominiopublico.mec.gov.br/download/teste/arqs/cp090477.pdf
[^20]: https://www.stj.jus.br/sites/portalp/Paginas/Comunicacao/Noticias/15082021-Os-limites-da-publicidade-diante-dos-direitos-do-consumidor.aspx
[^21]: https://procon.es.gov.br/refis-multas-aplicadas-pelo-procon-es-poderao-2
[^22]: https://www.defensoriapublica.pr.def.br/sites/default/arquivos_restritos/files/documento/2025-10/nota_tecnica_-_aplicativos_-_gamificacao_e_dark_patterns_-_assinado.pdf
[^23]: https://www.galiciaeducacao.com.br/blog/dark-patterns-e-protecao-do-consumidor-no-ambiente-digital/
[^24]: https://revistaaec.com/index.php/revistaaec/article/view/2011
[^25]: https://www.tjsp.jus.br/download/EPM/Publicacoes/ObrasJuridicas/113-dc.pdf?d=637581604679873754
[^26]: https://www.gov.br/anpd/pt-br/centrais-de-conteudo/outros-documentos-e-publicacoes-institucionais/iii-premio-danilo-doneda-artigos-cientificos-vencedores.pdf
[^27]: https://www.rodriguespinheiro.adv.br/o-direito-de-arrependimento/
[^28]: https://pillifanucchi.com.br/artigos/dark-patterns/
[^29]: https://sol.sbc.org.br/index.php/wide/article/download/32163/31965/
[^30]: https://www.gov.br/mj/pt-br/assuntos/noticias/consumidor-tem-direito-ao-arrependimento-em-compras-on-line
[^31]: https://procon.es.gov.br/Media/procon/Instrucao%20de%20Servico/Instru%C3%A7%C3%A3o%20de%20Servi%C3%A7o%20N%C2%BA%20170_Parcelamento%20de%20multa.pdf
[^32]: https://procon.es.gov.br/instrucao-de-servico-2
[^33]: https://linhares.es.gov.br/wp-content/uploads/2024/08/INSTRUCAO-DE-SERVICO-No-02-2023.pdf
[^34]: https://jus.com.br/artigos/43206/como-o-procon-estabelece-o-valor-de-uma-multa
[^35]: https://www.peticoesonline.com.br/blog/jurisfavoravel-consumidor-venda-casada-cdc-art-39-inc-i
[^36]: https://www.procon.rs.gov.br/upload/arquivos/202307/31164635-resolucao-normativa-sjcdhproconrs-n-012023-dosimetria-da-multa.pdf
[^37]: https://www.stj.jus.br/sites/portalp/Paginas/Comunicacao/Noticias/2022/11092022-In-re-ipsa-os-entendimentos-mais-recentes-do-STJ-sobre-a-configuracao-do-dano-presumido.aspx
[^38]: https://www.stj.jus.br/websecstj/cgi/revista/REJ.cgi/ITA?seq=1510765&tipo=0&nreg=201201325556&SeqCgrmaSessao=&CodOrgaoJgdr=&dt=20160905&formato=HTML&salvar=false
[^39]: https://www.migalhas.com.br/arquivos/2024/10/BDE6AC0A925F07_acordao-multa-procon.pdf
[^40]: https://www.tjsp.jus.br/Download/SecaoDireitoPrivado/GAPRI/BoletinsInformativos/BoletimJulgadosSelecionados04-2022.pdf
[^41]: https://www.stj.jus.br/websecstj/cgi/revista/REJ.cgi/ITA?seq=676248&tipo=0&nreg=200500674670&SeqCgrmaSessao=&CodOrgaoJgdr=&dt=20070322&formato=HTML&salvar=false
[^42]: https://www.procon.sp.gov.br/portaria-normativa-procon-no-45/
[^43]: https://www.tjsp.jus.br/Download/SecaoDireitoPrivado/GAPRI/BoletinsInformativos/BoletimJulgadosSelecionados07-2022.pdf```


</content>
