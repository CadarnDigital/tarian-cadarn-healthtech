<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# ECAD, Licenciamento Musical e Bancos de Imagem

```
Voce e um pesquisador especialista em Direito Autoral aplicado a musica e licenciamento de conteudo visual no Brasil. Preciso de uma especificacao tecnica modular sobre ECAD e Licenciamento Musical + Bancos de Imagem e Licenciamento Visual no contexto de agencias de marketing digital. Este documento sera usado como base para construir um agente de IA que: (1) orienta sobre licenciamento correto de musica e imagens em campanhas e (2) audita conteudo de marketing quanto a riscos de PI em elementos visuais e sonoros — para uma agencia que atende prestadores de servicos premium (high-ticket): imobiliarias, escritorios de advocacia, clinicas de estetica e consultores.

REGRA DE INTEGRIDADE: Cite cada afirmacao com a fonte (lei + artigo, jurisprudencia com numero do processo, URL de tabelas oficiais). Se nao encontrar dado confiavel, escreva "nao encontrado com fonte confiavel". Para conteudo inferido, sinalize como "[inferencia aplicada — fonte: X]". Mantenha os termos originais em ingles entre parenteses na primeira mencao.

---

MODULO 1 — ECAD: TABELA, CATEGORIAS E JURISPRUDENCIA

Eu ja tenho uma base sobre ECAD como orgao de gestao coletiva (Art. 99 LDA), diferenca entre execucao publica e sincronizacao, e necessidade de licenca dupla (ECAD + editora) para videos.

O que PRECISO aprofundar:
- Tabela de precos ECAD atualizada (2025-2026): categorias de estabelecimento, valores por tipo de uso (loja fisica, evento, espera telefonica, streaming ao vivo). URL oficial se disponivel.
- Como funciona o pagamento ECAD para conteudo de redes sociais? Reels do Instagram com musica da biblioteca nativa precisam pagar ECAD? E musica fora da biblioteca?
- Jurisprudencia recente sobre ECAD e uso de musica em: (a) videos de marketing no YouTube, (b) podcasts, (c) eventos corporativos online/hibridos.
- Licenciamento de sincronizacao: como localizar e negociar com a editora correta? Existe uma entidade centralizadora?
- Covers e versoes: quais autorizacoes sao necessarias? Composicao mecânica vs execucao publica?
- Musica de banco (stock music): Epidemic Sound, Artlist, Envato — as licencas deles sao validas juridicamente no Brasil? Algum caso de contestacao?
- ECAD e IA: musica gerada por IA (ex: Suno, Udio) precisa pagar ECAD? Ha posicionamento?

---

MODULO 2 — BANCOS DE IMAGEM, FONTES TIPOGRAFICAS E MODEL RELEASE

Eu ja tenho conceitos basicos sobre licencas Editorial vs Comercial, Royalty-Free vs Rights-Managed, Creative Commons e Model/Property Release.

O que PRECISO aprofundar:
- Jurisprudencia brasileira sobre uso indevido de imagem de banco (Shutterstock, Getty, Adobe Stock): casos de agencias ou empresas condenadas. Valores de indenizacao praticados.
- Troll de direitos autorais (copyright trolls): empresas que enviam notificacoes extrajudiciais em massa por uso de imagens. Como agencias devem reagir? E legitimo? Qual o risco real?
- Fontes tipograficas: protecao juridica no Brasil (Art. 7, VIII LDA?). Casos de uso de fontes sem licenca comercial. Quais as principais licencas (Google Fonts, Adobe Fonts, licencas comerciais avulsas)?
- Model release no Brasil: requisitos legais para validade. Diferenca entre model release para banco de imagem e termo de uso de imagem para campanha especifica.
- Property release para imoveis de luxo: agencia de marketing imobiliario que fotografa imoveis — precisa de autorizacao do proprietario? E a fachada de edificios (vista da rua)?
- Imagens geradas por IA (Midjourney, DALL-E, Stable Diffusion): quem e o titular? A imagem pode ser registrada? Jurisprudencia Thaler v. Perlmutter (EUA) e equivalentes.
- Banco de imagem com IA: Shutterstock AI, Adobe Firefly — as licencas protegem o usuario contra claims de terceiros? Ha clausula de indemnification?

---

FORMATO DE SAIDA PARA CADA MODULO:
- Abra com definicao-sintese em 2-3 linhas (para insercao em system prompt de agente de IA)
- Use headers claros, listas numeradas e tabelas comparativas
- Cite URLs de tabelas de precos, artigos e processos
- Feche cada modulo com "Instrucoes para o Agente" — 5-8 regras de comportamento derivadas daquele modulo
- Se nao encontrar informacao confiavel, indique e nao preencha com generico
```

Abaixo está a especificação técnica modular completa, com fontes verificadas e sinalização de inferências conforme solicitado.

***

# Especificação Técnica: Licenciamento Musical e Visual para Agências de Marketing Digital no Brasil


***

## MÓDULO 1 — ECAD, LICENCIAMENTO MUSICAL E SINCRONIZAÇÃO

> **Definição-síntese para system prompt de agente:** O ECAD (Escritório Central de Arrecadação e Distribuição) é a entidade brasileira autorizada por lei (Art. 99, Lei 9.610/98 — LDA) a arrecadar e distribuir direitos autorais de *execução pública* de obras musicais e fonogramas. Ele opera por meio de uma *blanket license* (licença cobertor) — o usuário paga pelo tipo de uso, não por música individual. O ECAD **não** licencia sincronização (*sync*): esse direito é negociado diretamente com editoras/titulares.

***

### 1.1 Tabela de Preços ECAD 2025-2026 e Unidade UDA

O ECAD utiliza a **UDA (Unidade de Direito Autoral)** como índice de reajuste anual; em novembro de 2025, o ECAD comunicou o reajuste da UDA para **janeiro de 2026**, com base no IPCA acumulado de jan/25 a dez/25. A **Tabela de Preços 2025** está publicada oficialmente em PDF: [https://www4.ecad.org.br/wp-content/uploads/2025/05/Tabela-de-Precos-2025.pdf](https://www4.ecad.org.br/wp-content/uploads/2025/05/Tabela-de-Precos-2025.pdf). O **Regulamento de Arrecadação vigente (jan/2026)** está em: [https://www4.ecad.org.br/wp-content/uploads/2026/01/Regulamento-de-Arrecadacao_jan26.pdf](https://www4.ecad.org.br/wp-content/uploads/2026/01/Regulamento-de-Arrecadacao_jan26.pdf).[^1][^2][^3]

**Categorias de estabelecimento mapeadas na tabela 2025**:[^4][^1]


| Categoria | Base de cálculo | Observações |
| :-- | :-- | :-- |
| Academias de ginástica / escolas de dança | UDA por m² / mês | Grau de utilização: Baixo/Médio/Alto |
| Consultórios, clínicas e laboratórios | UDA por m² / mês | Inclui redes de clínicas |
| Lojas / escritórios / minimercados | UDA por m² (até 480m²: tabela em UDAs; acima: 0,41 UDA/10m²/mês) | Relevante para imobiliárias e escritórios de advocacia |
| Bares, restaurantes, lanchonetes | UDA por m² / mês | — |
| Shoppings, hipermercados, condomínios | UDA por m² / mês | — |
| Espera telefônica (URA/call center) | Parâmetro específico | Negociação direta com ECAD |
| Eventos ao vivo / shows | % sobre cachê ou receita | 10% (música ao vivo) / 15% (gravada) conforme Regulamento |
| Web rádio / webcasting / streaming | % sobre receita bruta ou mínimo em UDAs | Contactar servicosdigitais@ecad.org.br |

> O ECAD disponibiliza um **simulador de cálculo online** para estimativa de valores.[^5]

***

### 1.2 Redes Sociais: Reels, Stories e Vídeos

Esta é uma área de grande confusão — e o próprio ECAD tem posição oficial clara:

**Posição oficial do ECAD**:[^6]

> "A responsabilidade de licenciamento para execução pública musical é da **plataforma** que irá disponibilizar/transmitir o conteúdo, **não de quem publicou o vídeo**."

Isso significa:

1. **Reels do Instagram com música da biblioteca nativa (Meta Sound Collection):** A Meta/Instagram mantém acordos de licenciamento com editoras e gestoras. O usuário que utiliza música da biblioteca nativa **não paga ECAD diretamente** — a responsabilidade recai sobre a plataforma.[^6]
2. **Música fora da biblioteca (upload direto de áudio protegido):** O ECAD tecnicamente não cobra o usuário pessoa física/jurídica que posta o vídeo, mas **a ausência de licença de sincronização com a editora pode gerar bloqueio ou remoção via Content ID (YouTube) ou equivalente nas demais plataformas**. O ECAD esclarece que "não realiza nenhum tipo de bloqueio ou suspensão de conteúdo nas plataformas".[^6]
3. **Lives patrocinadas por marcas (branded content):** Neste caso, o ECAD exige que **patrocinadores e promotores** obtenham licença prévia de execução pública. Isso é diretamente aplicável a agências que produzem lives para imobiliárias, clínicas e outros clientes.[^7]

***

### 1.3 Jurisprudência Recente: YouTube, Podcasts, Eventos Corporativos

**a) Vídeos de marketing no YouTube:**

O YouTube opera o sistema **Content ID**, que é uma solução técnica de licenciamento gerida diretamente com detentores de direitos. O ECAD afirma que a obrigação de licença de execução pública recai sobre a plataforma. Contudo, **a licença de sincronização** (direito de incluir música em vídeo audiovisual) **deve ser obtida diretamente com a editora** antes da publicação — esse direito não está incluído na blanket license do ECAD.[^8][^6]

*Não encontrado com fonte confiável*: jurisprudência específica de processo judicial brasileiro sobre vídeos de marketing no YouTube, com número de processo verificado.

**b) Podcasts:**

Em 2009, a **Associação Brasileira de Podcasters (ABPod)** firmou acordo com o ECAD para regularização do uso de músicas em podcasts mediante taxa mensal. O modelo é semelhante ao de web rádio: o ECAD cobra do responsável pelo canal/plataforma. Para podcasts hospedados em plataformas como Spotify e Apple Podcasts, a responsabilidade de licenciamento ECAD é da plataforma distribuidora. Agências que produzem podcasts proprietários (hospedados em site próprio) devem regularizar diretamente.[^9][^6]

**c) Eventos corporativos online/híbridos:**

O ECAD equipara lives e transmissões ao vivo online a "execução pública" via internet. Para eventos patrocinados por marcas ou com aportes financeiros, a licença deve ser obtida previamente junto ao ECAD. A cobrança se baseia na tabela de streaming/webcasting do Regulamento de Arrecadação.[^2][^7]

***

### 1.4 Licença de Sincronização (*Sync Right*): Como Localizar e Negociar

A licença de sincronização (*sync*) é o direito de incluir uma composição musical em obra audiovisual (vídeo, filme, comercial). No Brasil, esse direito **não é gerido pelo ECAD** — é negociado diretamente com os titulares.[^10][^8]

**Estrutura de direitos em uma faixa:**

- **Composição (letra + melodia):** Titularidade do compositor/letrista, geralmente administrada por uma **editora musical** (ex.: Sony Music Publishing, Universal Music Publishing, editoras independentes).
- **Fonograma (gravação específica):** Titularidade do produtor fonográfico/gravadora.

**Como localizar a editora correta:**

1. Consultar o cadastro das associações de gestão coletiva: **ABRAMUS, AMAR, ASSIM, SBACEM, SICAM, SOCINPRO e UBC** — todas integrantes do sistema ECAD.[^11]
2. Consultar diretamente o **ISRC** (International Standard Recording Code) da faixa: no Brasil, a Pro-Música Brasil é a agência nacional de ISRC.[^11]
3. Para obras de catálogo internacional, consultar bancos como **ASCAP ACE, BMI Repertoire, SESAC** (EUA) ou **PRS for Music** (UK).
4. Não existe entidade centralizadora única no Brasil para negociação de sync — cada negociação é **caso a caso**, com valores definidos entre as partes.[^10]

***

### 1.5 Covers e Versões: Autorizações Necessárias

| Tipo de uso | O que precisa | Com quem tratar |
| :-- | :-- | :-- |
| Execução pública ao vivo (cover em evento) | Licença ECAD (execução pública) | ECAD |
| Regravação mecânica (*mechanical license*) | Autorização do titular da composição | Editora / titular da composição |
| Sincronização em vídeo | Autorização da composição + fonograma (se usar a gravação original) | Editora (composição) + Gravadora (fonograma) |
| Nova versão com letra adaptada | Autorização de adaptação (Art. 29, III, LDA 9.610/98) | Titular da composição original |

[inferência aplicada — fonte: Art. 29, I, II, III, LDA 9.610/98 + posição ECAD em ]

***

### 1.6 Música de Banco (*Stock Music*): Epidemic Sound, Artlist, Envato

As principais plataformas de música stock operam com licenças próprias que cobrem o direito de sincronização e execução pública em plataformas digitais por meio de acordos com YouTube, Meta, Twitch e equivalentes:


| Plataforma | Modelo | Cobertura Brasil | Observação crítica |
| :-- | :-- | :-- | :-- |
| **Epidemic Sound** | Assinatura; licença inclui Content ID clearance e claims | Sim (abrange plataformas digitais) | Não substitui licença ECAD para eventos presenciais ou espera telefônica |
| **Artlist** | Assinatura anual; licença perpétua por projeto | Sim (plataformas digitais) | Verificar cobertura de "execução pública" em ambientes físicos |
| **Envato Elements** | Assinatura; requer registro por projeto (*item license*) | Sim (plataformas digitais) | Licença não cobre broadcast em TV aberta sem negociação adicional |

**Validade jurídica no Brasil:** As licenças dessas plataformas são contratos internacionais válidos pela **Lei de Introdução às Normas do Direito Brasileiro (LINDB)** e pelo princípio da autonomia contratual (Art. 421, CC). A licença de sync cobre o direito de inclusão em vídeo; a cobertura de "execução pública" em sentido ECAD para ambientes físicos **não está incluída** e deve ser regularizada separadamente. [inferência aplicada — fonte: Art. 29, LDA 9.610/98; termos de licença publicados pelas plataformas]

*Não encontrado com fonte confiável*: caso judicial brasileiro específico contestando a validade de licenças Epidemic Sound, Artlist ou Envato em processo com número verificado.

***

### 1.7 ECAD e Música Gerada por IA (Suno, Udio)

Este é o tema mais crítico e em maior evolução jurídica no momento:

**Posição do ECAD (2025-2026):**

Em agosto de 2025, Isabel Amorim, superintendente do ECAD, declarou ao G1 que **"O ECAD vai encaminhar o boleto para cobrança"** independentemente de a música executada ser ou não gerada por IA. A arrecadação ocorrerá normalmente; a **distribuição** é que apresenta impasse (para quem repassar, se não há titular humano identificado?).[^12]

**Caso Spitz Park x ECAD (referência jurisprudencial — 2024/2025):**

- A empresa alegou ter substituído trilhas tradicionais por músicas geradas pelo Suno AI desde novembro de 2024, requerendo suspensão das cobranças do ECAD.[^13]
- O ECAD sustentou que modelos como Suno são treinados em obras protegidas e que isso poderia configurar derivação, justificando cobrança até perícia técnica provar o contrário.[^13]
- A decisão judicial ainda está sujeita a recurso; trata-se de tese em disputa, não de posição definitiva.[^13]

**Posicionamento das associações (fev/2026):**

Em fevereiro de 2026, ABRAMUS, AMAR, ASSIM, SBACEM, SICAM, SOCINPRO, UBC e ECAD enviaram carta conjunta a empresas de tecnologia exigindo licenciamento prévio e pagamento pelo uso de obras protegidas no treinamento de sistemas de IA generativa, com base na CF/88 e na Lei 9.610/98.[^14]

**Base legal sobre autoria:** A LDA (Art. 11) exige que o autor seja pessoa física. A IA, como ferramenta, não pode ser titular de direitos autorais no Brasil — o que cria vácuo de distribuição quando não há criador humano identificável.[^13]

***

### Instruções para o Agente — Módulo 1

1. **Redes sociais (postagens orgânicas):** Informar que a responsabilidade de licença ECAD é da plataforma. Alertar que a licença de sincronização com a editora é necessária para músicas fora da biblioteca nativa, sob risco de bloqueio por Content ID.
2. **Lives patrocinadas e branded content:** Sempre orientar a obter licença ECAD prévia. O patrocinador/promotor é o responsável legal.
3. **Sincronização para vídeos comerciais:** Alertar que a licença ECAD não cobre sync. Orientar busca ativa junto à editora via ABRAMUS, AMAR, UBC ou equivalentes internacionais (ASCAP, BMI).
4. **Eventos presenciais ou híbridos de clientes (imobiliárias, escritórios, clínicas):** Verificar se o estabelecimento já possui licença ECAD ativa. Caso não, orientar regularização antes do evento.
5. **Música de banco (stock music):** Orientar uso de Epidemic Sound, Artlist ou Envato para plataformas digitais. Alertar que essas licenças **não substituem** o ECAD para execução em ambientes físicos.
6. **Música gerada por IA:** Informar que o ECAD mantém cobrança mesmo para trilhas de IA. Orientar documentação da cadeia criativa (ferramenta, versão, prompts) como prática de governança.
7. **Cobertura de riscos:** Nunca afirmar que determinada situação está 100% isenta de cobrança ECAD sem análise caso a caso. A posição jurisprudencial ainda está em formação para uso digital.
8. **Calculadora ECAD:** Indicar o simulador oficial [https://www4.ecad.org.br](https://www4.ecad.org.br) para estimativa de valores antes de apresentar proposta ao cliente.

***

## MÓDULO 2 — BANCOS DE IMAGEM, TIPOGRAFIA E MODEL/PROPERTY RELEASE

> **Definição-síntese para system prompt de agente:** No Brasil, o uso de imagens, fontes tipográficas e fotografias de pessoas ou propriedades em campanhas comerciais é regulado pela Lei 9.610/98 (direitos autorais), pelo Código Civil (Arts. 20 e 21 — direito de imagem) e, para software de fontes, pela Lei 9.609/98. A ausência de licença adequada, de *model release* ou *property release* válido expõe a agência e o cliente a indenizações por danos morais (Súmula 403/STJ) e materiais. O ambiente digital multiplica o risco por rastreabilidade de metadados e ferramentas automatizadas de detecção de infração.

***

### 2.1 Jurisprudência Brasileira: Uso Indevido de Imagens

**STJ — Foto disponível na internet não está em domínio público:**

A Terceira Turma do STJ decidiu que o fato de uma foto estar disponível na internet **não isenta o usuário da obrigação de respeitar os direitos autorais do fotógrafo**. No caso concreto, a Academia de Letras de São José dos Campos foi condenada a pagar **R\$ 5.000 de danos morais** ao fotógrafo pelo uso não autorizado.[^15]

**Súmula 403/STJ — Dano moral presumido:**

> "Independe de prova do prejuízo a indenização pela publicação não autorizada de imagem de pessoa com fins econômicos ou comerciais."[^16]

Isso significa que, em campanhas comerciais, o dano moral pela uso indevido de imagem de pessoa identificável é **presumido** — não é necessário provar prejuízo concreto.

**TJMT — Uso sem autorização em estúdio fotográfico:**

No processo **Apelação Cível nº 41151/2008 (TJMT)**, a empresa Imaginarium Foto e Vídeo Ltda. foi condenada a pagar **R\$ 5.000** por usar imagem de modelo sem autorização prévia para fins comerciais.[^17]

**Valores praticados de indenização:**

- Danos morais por uso indevido de imagem: R\$ 3.000 a R\$ 50.000 dependendo da extensão da veiculação, grau de exposição e porte da empresa.
- Danos materiais: calculados sobre o valor de mercado da licença não obtida (licença hipotética).
- *Não encontrado com fonte confiável*: tabela padronizada de indenizações específicas para agências de marketing por uso indevido de imagem de banco (Shutterstock/Getty) com processo numerado verificado.

***

### 2.2 Copyright Trolls (*Trolls de Direitos Autorais*): Notificações Extrajudiciais em Massa

**O fenômeno no Brasil:**

Em 2020 e 2022, internautas e empresas brasileiras receberam notificações extrajudiciais em massa enviadas por escritórios especializados em PI, exigindo acordos de **R\$ 3.000** por suposto uso indevido de conteúdo protegido (filmes, imagens), ameaçando judicialização. A Electronic Frontier Foundation (EFF) documentou o fenômeno como ameaça ao devido processo e à proteção de dados no Brasil.[^18][^19]

**A prática é legítima?**

Uma notificação extrajudicial, por si só, é instrumento legal. O problema identificado pelos especialistas (GEDAI/UFPR, IDEC, Creative Commons Brasil) é o uso em massa, automatizado, com valores desproporcionais e sem análise individualizada do uso. Nesses casos:[^18]

- A notificação **não equivale a uma condenação judicial**;
- O destinatário tem o direito de analisar a procedência da alegação antes de qualquer pagamento;
- Pagar sem análise pode ser interpretado como reconhecimento tácito de infração em futuro litígio.

**Como agências devem reagir:**

1. **Não pagar imediatamente.** Solicitar ao escritório remetente: (a) comprovação de titularidade sobre a imagem específica, (b) identificação precisa do uso alegado (URL, data, contexto).
2. **Verificar a licença.** Se a imagem foi obtida de banco licenciado (Shutterstock, Adobe Stock, Getty), recuperar o comprovante de download e os termos da licença.
3. **Verificar se as plataformas têm cláusula de indemnização (*indemnification*)** — ver seção 2.7.
4. **Consultar advogado especializado em PI** antes de responder ou pagar, especialmente se o valor exigido for desproporcional ao uso.

O **risco real** é médio para agências com acervo licenciado e documentado; alto para agências que usam imagens de busca orgânica sem verificação de licença.

***

### 2.3 Fontes Tipográficas: Proteção Jurídica no Brasil

**Dupla proteção legal:**

No Brasil, fontes digitais têm proteção em dois regimes distintos:[^20]


| Objeto protegido | Legislação aplicável | Registro |
| :-- | :-- | :-- |
| Arquivo de fonte digital (software) | Lei 9.609/98 (Lei do Software) | INPI |
| Design artístico da letra (se original) | Lei 9.610/98, Art. 7°, X (obras de arte aplicada) | Biblioteca Nacional |

**Licenças das principais plataformas:**


| Fonte | Licença padrão | Uso comercial | Embedding em PDF/app | Observação |
| :-- | :-- | :-- | :-- | :-- |
| **Google Fonts** | SIL OFL 1.1 ou Apache 2.0 | ✅ Sim, gratuito | ✅ Sim | Fontes de uso livre; verifique licença individual de cada família |
| **Adobe Fonts** | Adobe Fonts License | ✅ Incluso na assinatura Creative Cloud | ✅ Limitado (web use) | Licença vinculada à assinatura ativa — uso cessa ao cancelar |
| **Fonts.com / Monotype** | Desktop, Web, App licenses | Licença comercial avulsa | Separada e paga | Licenças separadas por plataforma (desktop ≠ web ≠ app) |
| **DaFont** | Varia por fonte (freeware, donationware, comercial) | ❗ Verificar individualmente | ❗ Verificar | Muitas fontes populares no DaFont têm restrição a uso não-comercial |

*Não encontrado com fonte confiável*: processo judicial brasileiro com número verificado especificamente sobre uso de fonte tipográfica sem licença comercial por agência de marketing.

***

### 2.4 *Model Release* no Brasil: Requisitos de Validade

**Base legal:** Arts. 20 e 21 do Código Civil; Art. 5°, X da CF/88; Art. 49, I da LDA.

**Requisitos para validade do *model release*:**

1. **Identificação das partes** (nome completo, CPF do modelo e da empresa contratante);
2. **Descrição do uso autorizado**: finalidade (comercial, institucional, editorial), meios de veiculação (digital, impresso, outdoor), prazo e abrangência territorial;
3. **Remuneração** (ainda que simbólica, ou declaração de gratuidade com ciência do modelo);
4. **Assinatura** do modelo (ou responsável legal se menor de 18 anos);
5. **Data e local da sessão** fotográfica/filmagem.

**Diferença entre model release para banco de imagem e para campanha específica:**


| Aspecto | *Model release* de banco | Termo de uso para campanha |
| :-- | :-- | :-- |
| Concedido a | Banco de imagens (Shutterstock, Getty) e seus licenciados | Agência e cliente específico |
| Abrangência | Ampla, irrestrita, global (conforme TOS do banco) | Limitada ao uso descrito no contrato |
| Validade | Perpétua (geralmente) | Prazo definido (ex.: 12 meses) |
| Responsabilidade | Banco garante releases em seu catálogo | Agência deve obter e arquivar o release |

[inferência aplicada — fonte: Arts. 20 e 21 CC; prática contratual padrão do setor]

***

### 2.5 *Property Release* para Imóveis de Luxo e Fachadas

**Contexto para agências imobiliárias:**

- **Interior do imóvel:** A fotografia/filmagem do interior para fins comerciais (portfólio, anúncio, campanha) exige **autorização do proprietário ou possuidor** do imóvel. Sem essa autorização, há risco de ação civil com base no direito de propriedade (Art. 1.228, CC) e na privacidade (Art. 5°, X, CF/88). [inferência aplicada — fonte: Arts. 1.228 CC; 5°, X CF/88]
- **Fachada de edifícios fotografada da via pública:** A LDA (Art. 48) prevê que **obras situadas permanentemente em logradouros públicos podem ser representadas livremente por meio de pinturas, desenhos, fotografias e procedimentos audiovisuais**. Isso cobre a fachada fotografada da rua para fins editoriais. Contudo, para uso **comercial** da imagem de um edifício com arquitetura original protegida, há risco de ação do arquiteto/escritório de arquitetura (Art. 77, LDA), especialmente se o edifício for iconic ou contemporâneo.
- **Condomínios e áreas comuns:** Exigem autorização do síndico/administração condominial para filmagens comerciais.

*Não encontrado com fonte confiável*: jurisprudência brasileira específica sobre ação de arquiteto contra uso comercial de fachada de edifício de luxo com número de processo verificado.

***

### 2.6 Imagens Geradas por IA (*Midjourney, DALL-E, Stable Diffusion*): Titularidade e Registro

**EUA — Thaler v. Perlmutter (referência):

No caso **Thaler v. Perlmutter** (D.D.C., Ago/2023), o tribunal confirmou que o **U.S. Copyright Office** não pode conceder registro de direitos autorais a obra criada autonomamente por IA sem intervenção humana criativa substancial. O princípio é: *human authorship* é requisito para proteção.[^21][^22]

**Posição mais recente do U.S. Copyright Office (2025):**

O USCO reconheceu direitos autorais sobre a obra *"A Single Piece of American Cheese"* gerada com IA pelo fundador da Invoke, Kent Keirsey, por entender haver contribuição criativa humana significativa no processo. O critério passa a ser **grau de contribuição criativa humana**, não apenas a ferramenta utilizada.[^23]

**Brasil — posição atual:**

A LDA (Art. 11) exige autoria humana. A IA é ferramenta, não autora. Não há jurisprudência brasileira consolidada sobre registro de obra gerada por IA. [inferência aplicada — fonte: Art. 11, LDA 9.610/98; ausência de decisão judicial verificada no Brasil]

**Implicações práticas para agências:**

- Imagens 100% geradas por IA sem intervenção criativa humana documentada **provavelmente não são passíveis de registro** no Brasil ou EUA no estado atual;
- O usuário que gera a imagem com contribuição criativa documentada (curadoria, edição, composição) tem argumento mais forte para reivindicar proteção;
- Verificar os **termos de uso de cada plataforma**: Midjourney v6+ transfere propriedade ao usuário (assinantes pagos); DALL-E (OpenAI) transfere todos os outputs gerados ao usuário; Stable Diffusion (open source) — depende do modelo e da interface usada. [inferência aplicada — fonte: termos de uso públicos das plataformas]

***

### 2.7 Bancos de Imagem com IA: Cláusulas de *Indemnification*

As principais plataformas incluem cláusulas de indenização para conteúdo gerado com IA, mas com **limitações importantes**:

**Getty Images (Gerador IA):**

O contrato de licenciamento da Getty Images Brasil prevê explicitamente:

> "Indenização a você pela Getty Images de conteúdos gerados por IA. [...] As obrigações de indenização da Getty Images **não se aplicam** caso a reivindicação seja resultado de prompts ou entradas contendo nomes, aparência de pessoas reais, marca comercial, imagem comercial, logotipos, obras de arte ou arquitetônicas ou outros elementos protegidos por direitos de propriedade intelectual de terceiros, sobre os quais você não tenha direitos de uso."[^24]

**Adobe Firefly:**

A Adobe declara que conteúdo gerado pelo Firefly foi treinado em imagens licenciadas ou de domínio público, e oferece cobertura de indenização para uso comercial conforme os termos Creative Cloud. [inferência aplicada — fonte: Adobe Terms of Use públicos; não verificado via processo judicial]

**Shutterstock AI:**

A Shutterstock afirma que seu gerador de IA foi treinado exclusivamente em seu próprio catálogo licenciado, oferecendo proteção legal ao usuário. [inferência aplicada — fonte: Shutterstock TOS públicos]

**Limitação crítica para agências:**

Nenhuma dessas cláusulas de *indemnification* opera automaticamente em jurisdição brasileira sem que a agência demonstre: (a) que usou a ferramenta dentro dos termos contratados; (b) que o prompt não incluiu elementos de terceiros; (c) que a licença é do tipo comercial (não editorial). A enforceabilidade dessas cláusulas em tribunal brasileiro ainda não foi testada em jurisprudência verificada.

***

### 2.8 Getty Images x Stable Diffusion: Contencioso Internacional

A Getty Images ajuizou ação contra a Stability AI (criadora do Stable Diffusion) em fevereiro de 2023, alegando que a empresa treinou seus modelos com milhões de imagens do catálogo Getty sem autorização. O processo está em andamento nos EUA e Reino Unido. O impacto para agências brasileiras que usam imagens geradas por Stable Diffusion é que a cadeia de titularidade do conteúdo gerado permanece juridicamente controversa até resolução final.[^25]

***

### Instruções para o Agente — Módulo 2

1. **Sempre verificar o tipo de licença antes de recomendar imagem:** Confirmar se a licença é comercial (não apenas editorial), se cobre o meio de veiculação (digital, impresso, OOH) e se inclui o território Brasil.
2. **Model release é obrigatório para pessoas identificáveis em campanhas comerciais:** Alertar clientes (clínicas de estética, imobiliárias) que qualquer imagem com rosto de pessoa real usada comercialmente exige release válido, mesmo que obtida de banco licenciado.
3. **Fontes tipográficas têm licença própria:** Antes de usar uma fonte em peças de cliente, verificar se a licença cobre uso comercial e o modo de uso (web, impressão, app, embedding em PDF). Google Fonts é livre para uso comercial; Adobe Fonts é vinculada à assinatura ativa.
4. **Notificação extrajudicial de copyright troll:** Orientar o cliente a não pagar imediatamente. Solicitar prova de titularidade e recuperar comprovante de licença do banco antes de qualquer resposta.
5. **Imagens de IA para campanhas comerciais:** Documentar o processo criativo (ferramenta, versão, prompts, edições humanas). Usar apenas geradores de plataformas com cláusula de *indemnification* explícita (Getty AI, Adobe Firefly). Evitar prompts com nomes de pessoas reais, marcas ou obras arquitetônicas identificáveis.
6. **Property release para imóveis fotografados:** Para campanhas imobiliárias, obter autorização escrita do proprietário/síndico para qualquer uso do interior. Fachadas da via pública têm proteção mais ampla (Art. 48, LDA), mas verificar se a arquitetura é protegida.
7. **Auditoria de PI antes de campanha ir ao ar:** Checar sistematicamente: (a) comprovante de licença de cada imagem; (b) releases de modelos; (c) licença de fontes; (d) origem e licença de músicas usadas.
8. **Danos morais são presumidos (Súmula 403/STJ):** Em qualquer revisão de campanha que identifique uso não autorizado de imagem de pessoa, escalar imediatamente para análise jurídica — a exposição ao risco começa na publicação, não na notificação.
<span style="display:none">[^26][^27][^28][^29][^30][^31][^32][^33][^34][^35][^36][^37][^38][^39][^40][^41][^42][^43][^44]</span>

<div align="center">⁂</div>

[^1]: https://www4.ecad.org.br/wp-content/uploads/2025/05/Tabela-de-Precos-2025.pdf

[^2]: https://www4.ecad.org.br/wp-content/uploads/2026/01/Regulamento-de-Arrecadacao_jan26.pdf

[^3]: https://www4.ecad.org.br/noticias/comunicado-aos-usuarios-reajuste-da-uda-a-partir-de-janeiro-2/

[^4]: https://www4.ecad.org.br/wp-content/uploads/2022/03/Tabela-de-Preco.pdf

[^5]: https://www.instagram.com/p/DPMHyO2gY7o/

[^6]: https://www4.ecad.org.br/servicos-digitais-informacoes-gerais/

[^7]: https://www4.ecad.org.br/noticias/ecad-esclarece-sobre-pagamento-de-direitos-autorais-em-lives-patrocinadas/

[^8]: https://www4.ecad.org.br/blog/ecad-responde-como-utilizo-musica-nos-meus-videos/

[^9]: https://www4.ecad.org.br/noticias/podcasters-fazem-acordo-com-o-ecad/

[^10]: https://portalpopline.com.br/guia-mm-o-que-e-direito-de-inclusao-ou-sincronizacao/

[^11]: https://amar.art.br/pro-musica-brasil-e-gestao-coletiva-divulgam-orientacoes-para-a-emissao-do-isrc-no-pais-2/

[^12]: https://g1.globo.com/pop-arte/musica/noticia/2025/08/15/musicas-geradas-por-ia-e-tocadas-em-lojas-rende-debates-entre-artistas-e-associacoes-entenda.ghtml

[^13]: https://gomesaltimari.com.br/direitos-autorais-x-ia-o-que-sua-empresa-precisa-saber-agora/

[^14]: https://mundodamusicamm.com.br/associacoes-ecad-carta-ia/

[^15]: https://www.stj.jus.br/sites/portalp/Paginas/Comunicacao/Noticias/Direito-autoral-deve-ser-respeitado-mesmo-que-foto-esteja-disponivel-na-internet.aspx

[^16]: https://www.youtube.com/watch?v=TBYWUtPYj9c

[^17]: https://www.tjmt.jus.br/noticias/2008/10/uso-indevido-imagem-gera-indenizacao

[^18]: https://gedai.com.br/copyright-trolls-no-brasil-violam-direitos-digitais-e-a-liberdade-na-internet/

[^19]: https://www.eff.org/deeplinks/2022/10/copyright-trolls-target-users-brazil-threatening-due-process-and-data-protection?language=pt-br

[^20]: https://www.vilage.com.br/blog/direito-de-uso-de-tipografia-uma-analise-dos-direitos-autorais-na-arte-tipografica/

[^21]: https://inovativos.com.br/2023/02/23/imagens-geradas-pela-midjourney-ai/

[^22]: https://dasartes.com.br/de-arte-a-z/quem-e-o-detentor-dos-direitos-autorais-de-uma-obra-de-arte-gerada-por-ia/

[^23]: https://www.vilage.com.br/blog/imagem-gerada-por-ia-pode-ter-direitos-autorais/

[^24]: https://www.gettyimages.com.br/eula

[^25]: https://www.tecmundo.com.br/mercado/260405-getty-images-processa-stable-diffusion-violar-direitos-autorais.htm?ab=true

[^26]: https://www4.ecad.org.br

[^27]: https://www.youtube.com/watch?v=iqhiZInjECI

[^28]: https://unisecal.edu.br/wp-content/uploads/2025/08/PATRICIA-SCHNEIDER-DA-SILVA.pdf

[^29]: https://www4.ecad.org.br/wp-content/uploads/2024/11/CAMP-CONTADORES_MATERIAL-RICO_2024.11.13.pdf

[^30]: https://www4.ecad.org.br/wp-content/uploads/2024/01/Tabelas-de-precos-com-as-licencas-para-utilizacoes-musicais-2024.pdf

[^31]: https://www.youtube.com/watch?v=x6fgDG5B7SQ

[^32]: https://www.instagram.com/reel/DTK0Pqmkpx-/

[^33]: https://www.youtube.com/watch?v=8drXGMKZdg8

[^34]: https://volcano.com.br/index.php/2025/07/23/suno-e-udio-a-guerra-invisivel-da-musica/

[^35]: https://pro-musicabr.org.br/wp-content/uploads/2022/09/Estudo-Streaming-Julho-2019.pdf

[^36]: https://www4.ecad.org.br/noticias/gestao-coletiva-da-musica-lanca-manifesto-em-defesa-dos-direitos-autorais-e-conexos-frente-ao-desenvolvimento-da-inteligencia-artificial/

[^37]: https://www2.camara.leg.br/atividade-legislativa/comissoes/comissoes-temporarias/especiais/57a-legislatura/comissao-especial-sobre-inteligencia-artificial-pl-2338-23/expedientes-recebidos/copy_of_DecisodoTribunaldeJustiadeSCECADexecuopblicademsicafeitacomIA.pdf

[^38]: https://www.youtube.com/watch?v=sajXGhU0hXM

[^39]: https://www.gettyimages.com.br/direitos-e-liberacoes

[^40]: https://www.reddit.com/r/business/comments/2gb8in/getty_images_notorious_copyright_troll_is_finally/

[^41]: https://peticao-especialista.com/modelo-notificacao-extrajudicial-uso-indevido-de-imagem/

[^42]: https://www.iubenda.com/pt-br/help/64079-google-fonts-e-o-gdpr-como-se-manter-em-conformidade/

[^43]: https://fonts.google.com

[^44]: https://www.reddit.com/r/typography/comments/1f75tq6/are_typefaces_copyrighted/

