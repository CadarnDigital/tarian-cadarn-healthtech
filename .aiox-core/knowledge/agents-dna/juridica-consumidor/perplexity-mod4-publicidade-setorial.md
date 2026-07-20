---
source_file: perplexity-mod4-publicidade-setorial.md
converted_at: 2026-03-23
original_extension: md
processor: Echo (aiox-m2m-etl)
extraction_quality: full
domain: Publicidade Setorial — Saúde, Advocacia, Financeiro, Educacional
source_type: perplexity-deep-research
source_tool: Perplexity Pro (Deep Research)
agent_target: juridica-consumidor
squad: squad-cadarn-juridica
module: 4
module_title: Publicidade Setorial por Segmento de ICP
---

<content>


# Você é um pesquisador especialista em regulação publicitária setorial no Brasil. Sua tarefa é produzir um módulo

exaustivo sobre regras de publicidade específicas por setor de atuação, com foco nos segmentos atendidos por agências
de marketing digital premium. Este documento será inserido em um pipeline RAG para alimentar um agente de IA jurídico.

Contexto de uso: Este documento será processado por um pipeline automatizado (M2M + RAG). O chunking é feito por
headers Markdown (\#\# e \#\#\#). Os metadados em HTML comment são parseados por regex antes do chunking e funcionam como
tags de classificação semântica — mantenha o formato exato. Output obrigatório: Markdown puro, sem exceções. O
documento será carregado como base de conhecimento de um agente Claude Code (CLI) utilizado por profissionais de uma
agência de marketing digital que atende prestadores de serviços premium em capitais brasileiras (Vitória/ES como
foco).

  <!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 4] [TEMA:
  publicidade-setorial-saude-estetica-advocacia-financeiro] -->
Cubra obrigatoriamente estes setores:

1. **Saúde e Estética** — O setor mais regulado do ICP da agência:
    - CFM Resolução 2.336/2023 (publicidade médica) — O que mudou: médicos podem divulgar equipamentos, técnicas,
pré/pós-operatório? Selfies com pacientes? Antes/depois? Detalhar o que é PERMITIDO e PROIBIDO.
    - CRO (Conselho Regional de Odontologia) — Código de Ética Odontológica, regras de publicidade para dentistas e
clínicas estéticas odontológicas.
    - ANVISA — RDCs aplicáveis a publicidade de produtos de saúde, cosméticos, suplementos. Regras para claims
("clinicamente comprovado", "dermatologicamente testado").
    - Clínicas de estética avançada — harmonização facial, procedimentos invasivos e não-invasivos. Quem pode anunciar
o quê (médico vs esteticista vs biomédico). Conflito entre CFM e Conselho de Biomedicina.
    - Influenciadores de saúde/estética — regras específicas: testemunhais de procedimentos, antes/depois de pacientes,
divulgação de preço.
2. **Advocacia e Serviços Jurídicos** — Provimento CFOAB 205/2021 (atualizado):
    - O que advogados PODEM fazer em redes sociais: conteúdo educativo, lives, podcasts, artigos.
    - O que advogados NÃO PODEM: captação ativa de clientela, promessa de resultado, publicidade comparativa,
mercantilização.
    - Marketing de conteúdo jurídico vs publicidade — onde está a linha.
    - Impulsionamento de posts — permitido ou vedado?
    - Cases de TED (Tribunal de Ética e Disciplina) — punições recentes a advogados por publicidade irregular.
3. **Serviços Financeiros** — Para agências que atendem consultores financeiros, fintechs, ou profissionais do
mercado:
    - BACEN — regulação de publicidade de serviços bancários e de pagamento
    - CVM — regras para divulgação de produtos de investimento (Instrução CVM 539, RCVM 179)
    - Proibição de promessa de rentabilidade garantida
    - Disclaimers obrigatórios ("investimentos envolvem riscos")
    - Influenciadores financeiros (finfluencers) — regulação e responsabilidade
4. **Serviços Educacionais e Infoprodutos** — Setor em crescimento no ICP:
    - MEC — regras de publicidade de instituições de ensino
    - Infoprodutos e cursos online — quando se enquadram como serviço educacional regulado
    - Promessas de resultado em cursos ("ganhe R\$ 10k em 30 dias") — enquadramento como publicidade enganosa
    - Garantia incondicional de 7 dias vs direito de arrependimento do CDC
5. **Tabela comparativa de compliance por setor** — Para uso operacional:
Colunas: Setor | Órgão regulador | Norma principal | O que PODE | O que NÃO PODE | Multa/Penalidade | Disclaimer
obrigatório
6. **Checklist universal de compliance publicitário** — 15-20 itens que TODA campanha deve verificar antes de
publicar, independente do setor: identificação publicitária, ofertas vinculantes, testemunhais, antes/depois, preços,
disclaimers, menores de idade, dados pessoais.

Regras de integridade:

- Cite resolução, artigo e órgão para TODA regra setorial
- Se uma resolução foi atualizada recentemente (ex: CFM 2.336/2023 substituiu a anterior), documente a mudança
- Se não encontrar fonte verificável: "não encontrado com fonte confiável"
- Doutrina: pode citar autores consagrados se a obra existir de fato
- Use HTML comments para metadados: <!-- [MÓDULO: 4] [SUBTEMA: nome] [TIPO: tipo] -->
- Chunks entre 300-800 palavras por seção \#\#/\#\#\#
- Formato: Markdown puro, headers \#\# e \#\#\#, tabelas onde aplicável

```markdown
<!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 4] [TEMA: publicidade-setorial-saude-estetica-advocacia-financeiro] -->

# Módulo 4 — Regulação Publicitária Setorial no Brasil

**Escopo:** Regras de publicidade por setor para agências de marketing digital premium com ICP em saúde/estética, advocacia, serviços financeiros e educação/infoprodutos. Base de conhecimento para agente jurídico RAG.

**Aviso de validade:** Normas regulatórias mudam. Verificar atualizações junto ao órgão emissor antes de aplicar em campanhas reais. Data-base: março/2026.

---

## 1. Saúde e Estética

<!-- [MÓDULO: 4] [SUBTEMA: saude-estetica] [TIPO: visao-geral] -->

O setor de saúde e estética é o **mais regulado** do ecossistema publicitário brasileiro, com sobreposição de competências entre CFM, CFO, ANVISA, Conselho Federal de Biomedicina (CFBM) e CONAR. A ausência de compliance neste setor expõe clientes a processos éticos, multas sanitárias e ação penal por exercício ilegal da medicina.

---

### 1.1 CFM Resolução 2.336/2023 — Publicidade Médica

<!-- [MÓDULO: 4] [SUBTEMA: cfm-2336-2023] [TIPO: norma-principal] -->

**Norma:** Resolução CFM nº 2.336, de 13 de setembro de 2023. Publicada no D.O.U. e em vigor após 180 dias da publicação (março/2024). **Revogou** a Resolução CFM nº 1.974/2011, que vigou por mais de 12 anos.

**O que mudou em relação à 1.974/2011:**

| Tema | Resolução 1.974/2011 | Resolução 2.336/2023 |
|---|---|---|
| Imagens antes/depois | Vedadas em publicidade | **Permitidas** com finalidade educativa e autorização do paciente |
| Divulgação de preços | Vedada em peças publicitárias | **Permitida** (consultas e procedimentos) |
| Selfies com pacientes | Não regulamentada / interpretada como vedada | **Permitidas** desde que sóbrias |
| Campanhas promocionais | Vedadas | **Permitidas** |
| Depoimentos de pacientes | Vedados | **Permitido** repostar se sóbrios e sem promessa de resultado |
| Equipamentos/técnicas | Restrito a divulgação científica | Pode divulgar equipamentos disponíveis no consultório |

---

**O que o médico PODE fazer (Art. 3º e seguintes, Res. CFM 2.336/2023):**

- Usar redes sociais próprias para publicidade/propaganda para formar, manter ou aumentar clientela, além de informações acadêmicas e educativas (Art. 3º, III)
- Comprar espaço publicitário em veículos de comunicação (Art. 3º, II)
- Divulgar equipamentos disponíveis no seu local de trabalho
- Publicar imagens "antes e depois" com **caráter educativo**, mediante:
  - Autorização expressa e escrita do paciente
  - Garantia de privacidade (sem identificação do paciente sem consentimento)
  - Finalidade estritamente educativa, não como captação
- Publicar selfies com pacientes, desde que sóbrias
- Repostar elogios e depoimentos de pacientes, desde que sóbrios e sem induzir promessa de resultados
- Divulgar preços de consultas e procedimentos
- Realizar campanhas promocionais
- Conceder entrevistas e publicar artigos com finalidade educativa, de divulgação científica e promoção da saúde (Art. 3º, I)

**O que o médico NÃO PODE fazer:**

- Publicidade sensacionalista ou que explore o medo, a vaidade ou a insegurança do paciente
- Promessa de resultado ou garantia de cura (vedação absoluta — Art. 5º)
- Publicidade que induza o paciente a procedimentos desnecessários
- Participar de publicidade de produtos ou serviços que impliquem o uso de seu nome, imagem ou prestígio de forma que denigra a profissão
- Usar títulos ou especialidades não reconhecidos pelo CFM
- Permitir que terceiros (clínicas, franquias, influenciadores) veiculem antes/depois de seus pacientes — a publicação deve ser do próprio médico

**Identificação obrigatória nas peças (Art. 4º):**

- Nome completo do médico
- Número(s) de registro no(s) CRM(s)
- Especialidade(s) reconhecida(s) pelo CFM (se divulgada)

---

### 1.2 CRO — Código de Ética Odontológica e Publicidade

<!-- [MÓDULO: 4] [SUBTEMA: cro-odontologia-publicidade] [TIPO: norma-principal] -->

**Norma principal:** Código de Ética Odontológica (CEO), aprovado pela Resolução CFO nº 118/2012, com alterações posteriores. **Norma complementar:** Resolução CFO nº 196/2019 (regula uso de imagens). **Atenção:** O Código de Ética Odontológico está em processo de atualização (novembro/2024), com foco em modernização da publicidade digital — verificar nova resolução.

**Capítulo XVI do CEO — Anúncios, Propaganda e Publicidade (Art. 42 e seguintes):**

- Art. 42: Anúncios e publicidade podem ser feitos em qualquer meio de comunicação, desde que obedecidos os preceitos do Código
- Art. 43: **Identificação obrigatória** em todo material publicitário:
  - Nome e número de inscrição no CRO (pessoa física)
  - Nome da clínica/pessoa jurídica e identificação do responsável técnico
  - Especificação da profissão: "cirurgião-dentista"

**Resolução CFO nº 196/2019 — Uso de Imagens:**

- **Autoriza** selfies do cirurgião-dentista
- **Autoriza** imagens de antes e depois com finalidade educativa e autorização do paciente
- **Proíbe** divulgação de resultados por **terceiros**, inclusive pessoas jurídicas (clínicas não podem publicar antes/depois sem identificar o CD responsável)
- Toda publicação deve identificar o cirurgião-dentista responsável com nome e número de inscrição no CRO
- Em 2025, o CFO realizou alterações pontuais em cumprimento a decisão do CADE, removendo restrições anticompetitivas relacionadas a cartões de desconto

**O que o dentista/clínica NÃO PODE fazer:**

- Anunciar especialidade não reconhecida pelo CFO
- Fazer publicidade comparativa com outros profissionais ou clínicas
- Prometer resultados específicos ("sorriso perfeito em 3 dias")
- Publicar imagens de pacientes sem autorização expressa
- Usar termos que configurem exercício ilegal (ex.: clínica estética anunciando "procedimentos médicos")
- Divulgação de depoimentos sem identificação do profissional responsável

---

### 1.3 ANVISA — Publicidade de Produtos de Saúde, Cosméticos e Suplementos

<!-- [MÓDULO: 4] [SUBTEMA: anvisa-publicidade-saude] [TIPO: norma-principal] -->

**Normas aplicáveis:**

- **RDC nº 96/2008** — Publicidade de medicamentos (principal norma para propaganda de medicamentos)
- **RDC nº 243/2018** — Suplementos alimentares (rotulagem e propaganda)
- **RDC nº 580/2021** — Cosméticos (incorpora regras de alegações)
- **Lei nº 9.294/1996** — Restrições à publicidade de produtos que causem danos à saúde

**Medicamentos (RDC 96/2008):**

- Medicamentos de venda sob prescrição são **vedados** de publicidade ao público geral
- Medicamentos de venda livre: publicidade permitida com restrições expressas
- **Proibido em qualquer publicidade de medicamento:**
  - Afirmar que o produto é inofensivo ou sem contraindicações (Art. 7º)
  - Usar linguagem científica que induza o consumidor ao erro
  - Garantir eficácia ou cura
  - Recomendar produto para uso em crianças sem indicação terapêutica aprovada
  - Criar expectativa de venda (Art. 7º, IX)
  - Usar imagens ou personagens que associem o produto a crianças de forma persuasiva

**Cosméticos — Alegações Publicitárias:**

- **"Clinicamente comprovado"** / **"Dermatologicamente testado"**: permitidos apenas quando lastreados em estudos técnico-científicos que a empresa deve ter disponíveis para fiscalização pela ANVISA
- **"Trata", "cura", "elimina"** (linguagem terapêutica): **vedada** para cosméticos — cosméticos têm finalidade higiênica/estética, não terapêutica
- Promessas de mudança definitiva ou irreversível: vedadas para Grau 1 (cosméticos de baixo risco)
- **Alegações funcionais e de saúde** para alimentos: somente se previamente aprovadas pela ANVISA

**Suplementos Alimentares (RDC 243/2018):**

- É vedada qualquer alegação na rotulagem ou propaganda que sugira que o suplemento é tratamento, terapia ou cura de doenças (Art. específico da RDC 243/2018)
- Proibido alegar que o produto é fonte de nutrientes quando não houver respaldo na composição declarada
- Obrigatório constar na embalagem: "Este produto não é um medicamento"
- Proibido usar linguagem que confunda suplemento com medicamento

**Regra geral ANVISA para publicidade:**
> Qualquer alegação funcional ou de saúde não aprovada pela ANVISA é infração sanitária, sujeita a multa de R$ 2.000 a R$ 1.500.000 (Lei 6.437/1977, Art. 10).

---

### 1.4 Clínicas de Estética Avançada — Conflito Regulatório CFM vs. CFBM

<!-- [MÓDULO: 4] [SUBTEMA: estetica-avancada-biomedicina] [TIPO: conflito-regulatorio] -->

**Situação regulatória em março/2026:** Esta é uma área de **conflito regulatório ativo** entre o CFM e o Conselho Federal de Biomedicina (CFBM), com decisão judicial recente de grande impacto.

**Decisão do TRF-1 (março/2026):**
O Tribunal Regional Federal da 1ª Região decidiu pelo fim da prática de biomedicina estética invasiva autônoma. O entendimento consolidado pelo TRF-1 é que a Lei 6.684/1979 (que regulamenta a atividade do biomédico) não confere autorização para execução autônoma de atos médicos, proibindo a atuação de biomédicos em procedimentos invasivos e de natureza cirúrgica ou dermatológica estéticos, especialmente sem supervisão médica.

**Quem pode anunciar o quê:**

| Profissional | Procedimentos que PODE anunciar | VEDADO anunciar |
|---|---|---|
| **Médico** (com especialidade reconhecida) | Harmonização facial, toxina botulínica, preenchimento, peeling profundo, laser ablativo, lipoaspiração, rinoplastia | Procedimentos fora de sua área de formação |
| **Cirurgião-Dentista** | Harmonização orofacial (área bucomaxilofacial), botox nos músculos mastigatórios, preenchimento labial na região oral | Procedimentos além da face/região oral sem habilitação |
| **Biomédico** | Estética não-invasiva, análise de pele, limpeza de pele, drenagem linfática — **não pode** anunciar procedimentos invasivos como autônomos após o TRF-1 | Aplicação de toxina botulínica, preenchimentos, procedimentos invasivos como executor independente |
| **Esteticista** | Serviços de estética não-invasiva (massagem, drenagem, peeling superficial) | Qualquer procedimento invasivo, aplicação de substâncias injetáveis |

**Implicação para agências:**
Criar publicidade que anuncia biomédico realizando "harmonização facial" de forma autônoma pode configurar cumplicidade em publicidade enganosa (Art. 37, CDC) e indução ao exercício ilegal da medicina. **Verificar sempre o registro profissional do cliente e o âmbito legal de sua atuação antes de criar a campanha.**

---

### 1.5 Influenciadores de Saúde e Estética

<!-- [MÓDULO: 4] [SUBTEMA: influenciadores-saude-estetica] [TIPO: regras-influenciadores] -->

**Base legal:** CONAR — Código Brasileiro de Autorregulamentação Publicitária (Resolução 2023 sobre publi/publipost); CFM Res. 2.336/2023 (para influenciadores médicos); CDC Art. 36 (identificação de publicidade).

**Antes/depois de procedimentos por influenciadores:**

- **Influenciador não-médico** mostrando resultado de procedimento estético: obrigatório identificar como "#publi" se houver vínculo comercial com a clínica/médico
- O médico/clínica que patrocina o conteúdo **responde solidariamente** pelo conteúdo publicado pelo influenciador
- Imagem de antes/depois de paciente divulgada por influenciador a mando da clínica **somente é lícita** se o médico autorizar expressamente e o conteúdo tiver caráter educativo (interpretação extensiva da Res. 2.336/2023)
- Testemunhais de procedimentos: permitidos, mas devem refletir experiência real e não podem prometer resultado idêntico a outros consumidores

**Regras de identificação (CDC Art. 36 + CONAR):**

- Todo conteúdo pago ou com permuta (produto/serviço grátis em troca de divulgação) deve ser identificado como publicidade
- Formatos aceitos: #publi, #parceria, #ad, "conteúdo patrocinado" — visíveis sem necessidade de expandir o texto
- Obrigatório também em stories, reels e vídeos curtos

**Divulgação de preços:**

- Clínicas podem divulgar preços nas redes sociais (Res. CFM 2.336/2023 e Código de Ética Odontológica)
- Preço divulgado é vinculante (CDC Art. 30 e Art. 35) — o consumidor pode exigir o cumprimento da oferta
- Promoções com prazo: o prazo deve ser informado claramente

---

## 2. Advocacia e Serviços Jurídicos

<!-- [MÓDULO: 4] [SUBTEMA: advocacia-marketing-juridico] [TIPO: visao-geral] -->

A publicidade na advocacia é regulada primariamente pelo **Provimento CFOAB nº 205, de 29 de novembro de 2021**, que revogou os Provimentos 75/1992 e 94/2000, modernizando as regras para o ambiente digital. O Provimento 205/2021 criou também o **Comitê Regulador do Marketing Jurídico** no âmbito da OAB.

---

### 2.1 O que Advogados PODEM Fazer em Marketing Digital

<!-- [MÓDULO: 4] [SUBTEMA: advocacia-permitido] [TIPO: regras-permitidas] -->

**Canais e formatos permitidos (Provimento 205/2021):**

- **Redes sociais** (Instagram, Facebook, LinkedIn, Twitter/X, TikTok): divulgação de conteúdo informativo e educacional sobre direito
- **Sites e blogs institucionais**: compartilhamento de conteúdo técnico e especializado
- **Lives, podcasts e webinars**: permitidos com finalidade educativa e informativa
- **Artigos e e-books**: marketing de conteúdo jurídico é expressamente permitido
- **Google Ads e Social Ads (anúncios pagos)**: **permitidos**, desde que o conteúdo seja informativo/educativo e não promova captação agressiva
- **Impulsionamento de posts**: **expressamente autorizado** pelo Provimento 205/2021, com moderação e finalidade informativa

**Conteúdo permitido:**

- Divulgação de áreas de atuação e especialidades (reconhecidas pela OAB)
- Publicação de conquistas e resultados de causas (sem identificar clientes sem autorização)
- Participação em entrevistas e mídia como especialista
- Newsletter jurídica para base de contatos
- Criação de comunidades digitais para educação jurídica

**Exemplo de anúncio permitido:** "Entenda seus direitos na rescisão contratual" → direciona para artigo educativo com formulário de contato discreto.

---

### 2.2 O que Advogados NÃO PODEM Fazer

<!-- [MÓDULO: 4] [SUBTEMA: advocacia-vedado] [TIPO: regras-vedadas] -->

**Vedações expressas (Provimento 205/2021 + Código de Ética e Disciplina da OAB, Lei 8.906/1994):**

- **Captação ativa de clientela**: abordagem de pessoas em situação de vulnerabilidade (hospitais, delegacias, fóruns) ou envio de mensagens não solicitadas
- **Promessa de resultado**: "Garantimos a vitória", "Recupere seus direitos em 30 dias", "100% de êxito"
- **Publicidade comparativa**: mencionar nomes de outros escritórios ou profissionais de forma comparativa
- **Mercantilização da profissão**: divulgar valores de honorários de forma destacada como argumento de venda ("o escritório mais barato da cidade")
- **Publicidade sensacionalista**: explorar situações de catástrofe, acidentes, tragédias pessoais para captar clientes
- **Informações confidenciais**: mencionar dados de processos ou clientes sem autorização expressa
- **Títulos não reconhecidos**: se autodeclarar "especialista" em área não certificada pela OAB

**Exemplo de anúncio vedado:** "Ganhe sua causa com nosso escritório" / "Somos os melhores advogados de Vitória" / "Acidentado? Ligue agora e garanta sua indenização."

---

### 2.3 Marketing de Conteúdo Jurídico vs. Publicidade — A Linha Divisória

<!-- [MÓDULO: 4] [SUBTEMA: advocacia-conteudo-vs-publicidade] [TIPO: analise] -->

O Provimento 205/2021 introduz formalmente a distinção entre **publicidade** (divulgação institucional do escritório) e **marketing de conteúdo** (educação jurídica do público).

**Marketing de conteúdo jurídico (permitido sem restrições adicionais):**
- Artigos explicando institutos jurídicos
- Posts sobre mudanças legislativas
- Podcasts com análise de jurisprudência
- Guias de direitos do consumidor

**Publicidade institucional (permitida com limites):**
- Apresentação do escritório, equipe, diferenciais
- Anúncios de áreas de atuação
- Impulsionamento de conteúdo informativo

**Zona cinzenta:** Post educativo que termina com CTA ("fale conosco para resolver sua situação") é aceito se o tom for consultivo, não apelativo. O Tribunal de Ética e Disciplina (TED) avalia o conjunto da comunicação, não apenas o texto isolado.

**Linha prática para agências:** O criativo jurídico passa no teste ético se o foco principal é **informar o cidadão**, não **vender o advogado**. Qualquer comunicação que inverta essa ordem configura captação e pode ensejar processo disciplinar.

---

### 2.4 Impulsionamento de Posts — Regras Práticas

<!-- [MÓDULO: 4] [SUBTEMA: advocacia-impulsionamento] [TIPO: regras-praticas] -->

**Status legal:** O Provimento 205/2021 **expressamente autoriza** o impulsionamento de publicações (tráfego pago).

**Condições para impulsionamento lícito:**
- O conteúdo impulsionado deve ter caráter **educativo** e não sensacionalista
- Vedado impulsionar posts com linguagem de oferta, preço, garantia de resultado ou captação agressiva
- Google Ads: podem direcionar para páginas de conteúdo com formulários de contato discretos — vedado direcionar para páginas de venda com apelo comercial explícito
- O escritório deve **manter cópia dos criativos**, audiência-alvo, datas e objetivos para eventual análise pelo TED da Seccional

**Exemplo lícito de impulsionamento:**
- Anúncio: "Você sabe quais são seus direitos em caso de demissão sem justa causa?" → artigo educativo com formulário "fale com um especialista" ao final

**Exemplo vedado de impulsionamento:**
- Anúncio: "Escritório X — os melhores resultados em causas trabalhistas. Consulta gratuita. Ligue já."

---

### 2.5 Penalidades por Publicidade Irregular na Advocacia

<!-- [MÓDULO: 4] [SUBTEMA: advocacia-penalidades] [TIPO: penalidades] -->

**Base legal:** Estatuto da OAB (Lei 8.906/1994), Código de Ética e Disciplina da OAB.

**Penas aplicáveis pelo TED (Tribunal de Ética e Disciplina):**

1. **Censura** (pena mais leve): aplicada em infrações leves e primárias
2. **Suspensão** (30 dias a 12 meses): para infrações que envolvam captação ativa reiterada, promessa de resultado ou publicidade sensacionalista
3. **Exclusão dos quadros da OAB**: para casos gravíssimos (não usual em publicidade)

**Tipos de conduta que geram processos no TED:**
- Anúncio com promessa de resultado verificada por denúncia de concorrente ou consumidor
- Publicidade comparativa nomeando outros escritórios
- Uso de redes sociais para captação em ambiente de vulnerabilidade
- Gerenciamento de perfil por assessoria de marketing sem supervisão do advogado responsável

*Nota: Não foram localizados, com fonte verificável, acórdãos específicos do TED publicizados após 2023 sobre casos de redes sociais. As informações acima refletem as previsões normativas do Código de Ética e a jurisprudência disciplinar histórica da OAB.*

---

## 3. Serviços Financeiros

<!-- [MÓDULO: 4] [SUBTEMA: servicos-financeiros] [TIPO: visao-geral] -->

A publicidade de serviços financeiros no Brasil envolve múltiplos reguladores: **Banco Central do Brasil (BACEN)**, **Comissão de Valores Mobiliários (CVM)** e autorregulação da **ANBIMA**. O grau de regulação varia conforme o produto (conta bancária, investimento, crédito, câmbio) e o público-alvo.

---

### 3.1 BACEN — Publicidade de Serviços Bancários e de Pagamento

<!-- [MÓDULO: 4] [SUBTEMA: bacen-publicidade] [TIPO: norma-principal] -->

**Norma principal:** Resolução BCB nº 96/2021 (Política de Relacionamento com Clientes e Usuários de Serviços Financeiros) e Resolução CMN nº 4.949/2021 (transparência em operações de crédito). A publicidade bancária também é regida pelo **CDC (Lei 8.078/1990)** e pelo **Código de Proteção ao Consumidor de Serviços Financeiros** do BACEN.

**Princípios gerais do BACEN para publicidade financeira:**

- **Clareza e transparência**: informações devem ser prestadas de forma clara, adequada e inequívoca ao cliente (Resolução CMN 4.949/2021)
- **Proibição de informação enganosa**: vedada qualquer comunicação que induza o cliente a erro sobre taxas, encargos, condições ou riscos do produto
- **Informações obrigatórias em publicidade de crédito:**
  - Taxa de juros (mensal e anual, Custo Efetivo Total — CET)
  - Prazo total da operação
  - Valor total a pagar
- **Publicidade de conta de pagamento / fintechs**: devem identificar claramente a natureza da instituição (Instituição de Pagamento, não banco) e os limites da proteção ao usuário

**Práticas vedadas em publicidade financeira (BACEN):**

- Omitir o Custo Efetivo Total (CET) em publicidade de crédito
- Anunciar "taxa zero" sem informar encargos acessórios
- Criar expectativa de aprovação de crédito sem ressalvas sobre análise de risco
- Usar linguagem que explore situação de endividamento ou vulnerabilidade financeira do consumidor

---

### 3.2 CVM — Publicidade de Produtos de Investimento

<!-- [MÓDULO: 4] [SUBTEMA: cvm-investimentos] [TIPO: norma-principal] -->

**Normas principais:**
- **Resolução CVM nº 30/2021** (publicidade de fundos de investimento)
- **Resolução CVM nº 35/2021** — alterada pela **RCVM 179/2023** (assessores de investimento)
- **Resolução CVM nº 20/2021** (analistas de valores mobiliários)
- **ICVM 539** (deveres e procedimentos de suitability — substituída pela Resolução CVM 30/2021 no que tange a fundos)

**Regras para publicidade de investimentos:**

**Disclaimers obrigatórios (Res. CVM 30/2021 e práticas ANBIMA):**
```

"Rentabilidade passada não representa garantia de rentabilidade futura."
"O investimento em [produto] envolve riscos, inclusive possibilidade de perda do capital investido."
"Leia o prospecto/regulamento antes de investir."

```

**Proibições absolutas:**
- **Garantia de rentabilidade**: proibição absoluta de prometer retorno fixo, mínimo garantido ou rentabilidade específica (exceto produtos com garantia legal como LCI/LCA e poupança — e mesmo assim com limites)
- **Comparação enganosa**: benchmarks devem ser relevantes e devidamente identificados
- **Omissão de riscos**: qualquer comunicação sobre benefícios deve ser acompanhada de menção proporcional aos riscos
- **Publicidade de produto não registrado**: vedado anunciar valor mobiliário sem registro ou com dispensa de registro na CVM

**Assessores de Investimento (RCVM 179/2023):**
- Assessores vinculados a escritórios autorizados pela CVM podem fazer marketing de seus serviços
- Vedado se apresentar como gestor ou como quem possui discricionariedade sobre o capital do cliente, quando não for
- Obrigatório identificar o escritório e o vínculo com a corretora/distribuidora

---

### 3.3 Finfluencers — Regulação e Responsabilidade

<!-- [MÓDULO: 4] [SUBTEMA: finfluencers] [TIPO: regras-influenciadores] -->

**Contexto:** Os finfluencers (influenciadores financeiros) possuem aproximadamente 208 milhões de seguidores no Brasil e aumentaram 96% as publicações que mencionam produtos de investimento nos últimos anos (dado ANBIMA/IBPAD).

**Posição da CVM:**
A CVM não regula diretamente a atuação dos finfluencers como categoria, mas **impõe responsabilidade às entidades reguladas que os contratam**. Quando uma corretora, gestora ou distribuidora contrata um finfluencer, ela responde pela conformidade do conteúdo produzido.

**Regras para contratação de finfluencers por entidades reguladas (ANBIMA):**
- A ANBIMA estabeleceu em seu Código de Distribuição normas para instituições aderentes que contratem influenciadores digitais
- Obrigatório: deixar claro que a divulgação é patrocinada (transparência contratual)
- O conteúdo deve ser aprovado pela área de compliance da instituição contratante antes da publicação
- Vedado ao finfluencer contratado prometer rentabilidade ou omitir riscos

**Finfluencers e a atividade de analista de valores mobiliários:**
A CVM considera analista de valores mobiliários quem elabora e divulga relatórios e análises sobre ativos para o público (Res. CVM 20/2021). Finfluencers que fazem recomendações específicas de compra/venda podem ser enquadrados como analistas não habilitados — infração que pode resultar em multa e responsabilidade civil.

**Regra prática para agências:**
- Sempre identificar conteúdo patrocinado com "#publi", "#ad" ou "conteúdo patrocinado"
- Nunca criar roteiro que prometa retorno garantido
- Exigir do cliente financeiro regulado aprovação de compliance antes de publicar conteúdo de finfluencer patrocinado

---

## 4. Serviços Educacionais e Infoprodutos

<!-- [MÓDULO: 4] [SUBTEMA: educacao-infoprodutos] [TIPO: visao-geral] -->

O setor educacional possui dupla regulação: **MEC** para instituições formais de ensino e **CDC** para todos os fornecedores de serviços educacionais, incluindo cursos online e infoprodutos. A principal fonte de irregularidade publicitária neste setor são as **promessas de resultado financeiro**.

---

### 4.1 MEC — Publicidade de Instituições de Ensino Reguladas

<!-- [MÓDULO: 4] [SUBTEMA: mec-ensino-regulado] [TIPO: norma-principal] -->

**Norma principal:** Lei nº 9.394/1996 (LDB — Lei de Diretrizes e Bases da Educação Nacional); Decreto 9.235/2017 (regulamenta a Educação Superior).

**Regras para publicidade de IES (Instituições de Educação Superior):**

- **Somente IES com autorização/reconhecimento do MEC** podem anunciar diplomas com validade nacional
- **Vedado** anunciar que um curso confere certificação profissional sem que esta seja reconhecida pelo órgão competente (ex.: anunciar curso como "habilitação" para praticar atividade regulamentada)
- **Anunciar nota do MEC/ENADE** é permitido desde que a nota seja atual (verificar ciclo mais recente do SINAES)
- **Cursos de pós-graduação lato sensu** (extensão/MBA): sujeitos às regras do CNE; vedado chamar de "mestrado" ou "doutorado" sem ser stricto sensu reconhecido
- **Franquias de ensino**: cada unidade deve verificar seu próprio status de autorização — vedado usar o CNPJ da franqueadora para conferir legitimidade a unidades não autorizadas

---

### 4.2 Infoprodutos e Cursos Online — Enquadramento Legal

<!-- [MÓDULO: 4] [SUBTEMA: infoprodutos-regulacao] [TIPO: analise] -->

**Status regulatório:** Cursos online e infoprodutos (ebooks, videoaulas, mentorias) **não são serviços educacionais regulados pelo MEC** quando não conferem diplomas com validade nacional. São tratados como **serviços/produtos de consumo** sujeitos integralmente ao **CDC (Lei 8.078/1990)**.

**Quando um infoproduto pode violar o CDC:**

- **Art. 37 — Publicidade enganosa:** toda comunicação que afirme, omita ou seja capaz de induzir o consumidor ao erro sobre o produto é enganosa
- **Promessas de resultado financeiro** ("ganhe R$ 10.000 em 30 dias", "abandone seu emprego em 3 meses") são consideradas **publicidade enganosa** quando:
  - O resultado prometido não é factualmente alcançável pela maioria dos compradores
  - A promessa não é acompanhada de informações sobre o esforço, variáveis e riscos envolvidos
  - Baseia-se em casos excepcionais apresentados como resultado típico

**Posição do PROCON e do SENACON:**
- Promessas de resultado quantificado em publicidade de cursos são investigadas pelo PROCON como publicidade enganosa (Art. 37, CDC)
- Multas administrativas: SENACON pode aplicar multas de até R$ 9.7 milhões por infração (Lei 12.529/2011 c/c CDC)

---

### 4.3 Garantia de 7 Dias — Obrigação Legal vs. Diferencial de Marketing

<!-- [MÓDULO: 4] [SUBTEMA: garantia-7-dias-cdc] [TIPO: analise-juridica] -->

**Base legal:** CDC Art. 49 — Direito de Arrependimento.

> "O consumidor pode desistir do contrato, no prazo de 7 dias a contar de sua assinatura ou do ato de recebimento do produto ou serviço, sempre que a contratação de fornecimento de produtos e serviços ocorrer fora do estabelecimento comercial, especialmente por telefone ou a domicílio."

**Análise prática para publicidade de infoprodutos:**

- A **"garantia de 7 dias"** amplamente divulgada por produtores digitais **não é um diferencial** — é uma **obrigação legal** decorrente do Art. 49 do CDC, pois toda compra online se enquadra como "fora do estabelecimento comercial"
- Usar "7 dias de garantia" como argumento de vendas é juridicamente impreciso e pode ser considerado prática enganosa por omissão (o consumidor entende ser uma concessão voluntária do vendedor)
- Prazos **superiores a 7 dias** (30, 60, 90 dias) configuram garantia contratual voluntária do fornecedor, que o obriga a cumpri-la
- **Liberar conteúdo gradualmente** (ex.: aulas liberadas após 7 dias) para dificultar o exercício do direito de arrependimento é prática **abusiva** vedada pelo CDC Art. 51

**Recomendação de compliance para agências:**
- Em vez de "garantia de 7 dias", usar "30 dias de satisfação garantida" (se o cliente oferecer prazo maior) — isso sim é diferencial real
- Nunca usar o prazo legal de 7 dias como argumento de venda, pois expõe o cliente a questionamentos do PROCON

---

## 5. Tabela Comparativa de Compliance por Setor

<!-- [MÓDULO: 4] [SUBTEMA: tabela-compliance-setorial] [TIPO: referencia-operacional] -->

| Setor | Órgão Regulador | Norma Principal | O que PODE | O que NÃO PODE | Multa/Penalidade | Disclaimer Obrigatório |
|---|---|---|---|---|---|---|
| **Medicina / Clínica Médica** | CFM | Res. CFM 2.336/2023 | Antes/depois educativo (com autorização), preços, selfies, depoimentos sóbrios, campanhas | Promessa de resultado, sensacionalismo, títulos não reconhecidos, terceiros publicando antes/depois do paciente | Suspensão de CRM, cassação | Nome + CRM + especialidade em toda peça |
| **Odontologia** | CFO / CRO | CEO (Res. CFO 118/2012) + Res. CFO 196/2019 | Antes/depois educativo, selfies, divulgação de serviços, anúncios pagos | Divulgação por terceiros sem identificação do CD, especialidade não reconhecida, promessa de resultado | Suspensão de CRO, cassação | Nome + número CRO + "Cirurgião-Dentista" |
| **Estética Avançada** | CFM + CFBM + ANVISA | Res. CFM 2.336/2023 + Lei 6.684/1979 + TRF-1 (2026) | Médico: anunciar todos os procedimentos de sua especialidade | Biomédico anunciar procedimentos invasivos autônomos (vedado pelo TRF-1/2026) | Processo crime por exercício ilegal da medicina | Identificação do profissional médico responsável |
| **Cosméticos / Suplementos** | ANVISA | RDC 96/2008, RDC 243/2018, RDC 580/2021 | Claims aprovados pela ANVISA, "testado dermatologicamente" com evidência disponível | "Cura", "trata", "elimina doenças", claims funcionais sem aprovação ANVISA | Multa R$ 2k–R$ 1,5mi (Lei 6.437/1977) | "Este produto não é um medicamento" (suplementos) |
| **Advocacia** | OAB / CFOAB | Provimento 205/2021 + Código de Ética OAB | Conteúdo educativo, redes sociais, Google Ads informativos, impulsionamento moderado, podcasts, lives | Promessa de resultado, captação ativa, publicidade comparativa, sensacionalismo, mercantilização | Censura, suspensão 30 dias–12 meses, exclusão | Identificação do advogado responsável pelo escritório |
| **Investimentos / Valores Mobiliários** | CVM | Res. CVM 30/2021 + RCVM 179/2023 + Res. CVM 20/2021 | Marketing institucional de serviços, educação financeira, divulgação de produtos com riscos informados | Garantia de rentabilidade, omissão de riscos, recomendação sem habilitação de analista, produto sem registro | Multa CVM (até R$ 500 mil por infração) | "Rentabilidade passada não representa garantia futura" + "Investimentos envolvem riscos" |
| **Serviços Bancários / Fintechs** | BACEN / CMN | Res. CMN 4.949/2021 + Res. BCB 96/2021 | Publicidade institucional, divulgação de produtos com CET informado | Omitir CET, anunciar "taxa zero" sem ressalvas, criar expectativa de aprovação garantida | Multas BACEN (administrativas) | CET (em crédito), natureza da instituição (IP vs banco) |
| **Educação Superior** | MEC / CNE | Lei 9.394/1996 + Decreto 9.235/2017 | Divulgar nota MEC/ENADE atual, áreas e cursos autorizados | Anunciar diploma sem autorização MEC, chamar extensão de "mestrado" | Multa MEC, descredenciamento | Status de autorização/reconhecimento MEC |
| **Infoprodutos / Cursos Online** | SENACON / PROCON | CDC (Lei 8.078/1990) — Art. 37 e 49 | Divulgar benefícios reais do produto, garantia voluntária > 7 dias como diferencial | Promessa de resultado financeiro quantificado, liberar conteúdo após 7 dias para dificultar reembolso | Multa PROCON até R$ 9,7mi (Lei 12.529/2011) | Direito de arrependimento de 7 dias (Art. 49 CDC) |

---

## 6. Checklist Universal de Compliance Publicitário

<!-- [MÓDULO: 4] [SUBTEMA: checklist-compliance] [TIPO: ferramenta-operacional] -->

Este checklist deve ser aplicado a **toda campanha** antes da publicação, independente do setor. Cada item deve ser verificado e o responsável deve assinar o documento de aprovação.

**BLOCO A — Identificação e Transparência**

- [ ] **A1. Identificação publicitária:** O conteúdo pago ou patrocinado está claramente identificado como "#publi", "#ad", "conteúdo patrocinado" ou equivalente visível sem necessidade de expandir texto? (CDC Art. 36 + CONAR)
- [ ] **A2. Identificação do anunciante:** Nome e dados do anunciante estão identificáveis na peça (especialmente obrigatório para médicos, dentistas e advogados)?
- [ ] **A3. Registro profissional:** Para profissões regulamentadas (médico, dentista, advogado, assessor de investimento), o número de registro no conselho competente está presente?

**BLOCO B — Veracidade e Substantiation**

- [ ] **B4. Claims verificáveis:** Toda afirmação sobre o produto/serviço ("clinicamente comprovado", "100% eficaz", "aprovado por X") possui comprovação documental disponível para apresentar à fiscalização?
- [ ] **B5. Promessa de resultado:** A peça está livre de promessas de resultado não verificáveis, especialmente financeiras ("ganhe R$ X") ou de saúde ("emagreça Y kg")?
- [ ] **B6. Testemunhais reais:** Depoimentos e casos de sucesso são reais e refletem resultados típicos (não excepcionais)? Se excepcional, isso está explicitado?
- [ ] **B7. Antes/depois:** Se a peça usa imagens de antes/depois, há autorização escrita do paciente/cliente, o profissional responsável está identificado e o conteúdo tem caráter educativo?

**BLOCO C — Oferta e Preço**

- [ ] **C8. Oferta vinculante:** O preço anunciado está correto e atualizado? Lembrar que oferta publicitária é vinculante (CDC Art. 30 e 35)?
- [ ] **C9. Condições da oferta:** Prazo de validade da promoção está indicado? Limitações de estoque ou cotas estão informadas?
- [ ] **C10. Custo total:** Em serviços financeiros ou com parcelamento, o custo efetivo total (CET) está informado claramente?

**BLOCO D — Disclaimers Setoriais**

- [ ] **D11. Disclaimer financeiro:** Para investimentos, o aviso "rentabilidade passada não representa garantia futura" e "investimentos envolvem riscos" está presente?
- [ ] **D12. Disclaimer de saúde:** Para produtos de saúde, o aviso legal da ANVISA aplicável está presente ("Este produto não é um medicamento", etc.)?
- [ ] **D13. Disclaimer educacional:** Para cursos e infoprodutos, o direito de arrependimento de 7 dias (CDC Art. 49) está informado?

**BLOCO E — Públicos Vulneráveis**

- [ ] **E14. Menores de idade:** A campanha está livre de apelos direcionados a crianças ou adolescentes em desacordo com o ECA (Lei 8.069/1990) e o CONAR — Seção 11?
- [ ] **E15. Público vulnerável:** A peça evita explorar medo, insegurança, urgência artificial ou vulnerabilidade econômica de forma abusiva (CDC Art. 37 §2º)?

**BLOCO F — Dados Pessoais e LGPD**

- [ ] **F16. Uso de imagem:** Há autorização expressa e documentada de toda pessoa identificável que aparece na peça publicitária?
- [ ] **F17. Coleta de dados:** Formulários e landing pages ligados à campanha possuem aviso de privacidade (LGPD — Lei 13.709/2018) e finalidade de uso dos dados informada?
- [ ] **F18. Uso de dados de clientes:** Depoimentos, estudos de caso e antes/depois foram autorizados pelo titular dos dados (LGPD Art. 7º)?

**BLOCO G — Conformidade Setorial Específica**

- [ ] **G19. Revisão pelo profissional responsável:** Campanhas para setores regulados (saúde, direito, finanças) foram revisadas e aprovadas pelo profissional habilitado do cliente antes da publicação?
- [ ] **G20. Arquivo de compliance:** A agência mantém cópia do criativo aprovado, data de aprovação, nome do responsável e eventuais ressalvas para defesa em caso de fiscalização?

---

*Documento gerado com base em fontes regulatórias vigentes em março/2026. Validade estimada até setembro/2026. Revisar atualizações do CFM, CFO, CVM, BACEN e CFOAB antes de aplicar em novas campanhas.*

<!-- [MÓDULO: 4] [SUBTEMA: fim-documento] [TIPO: metadado] [PRÓXIMA_REVISÃO: 2026-09] -->
```


***

O documento acima está pronto para ingestão no pipeline RAG. Abaixo estão as notas de integridade relevantes para o agente:

**Fontes verificadas neste módulo:**

- CFM Resolução 2.336/2023: confirmada em vigor desde março/2024, substituindo a Res. 1.974/2011[^1][^2][^3][^4]
- CFO — Código de Ética Odontológica + Resolução CFO 196/2019, com alteração pontual do CADE em julho/2025[^5][^6][^7][^8]
- ANVISA RDC 96/2008 (medicamentos), RDC 243/2018 (suplementos), regras gerais de propaganda[^9][^10][^11]
- Provimento CFOAB 205/2021: confirmado como norma vigente, com autorização expressa de impulsionamento[^12][^13][^14][^15][^16]
- CVM RCVM 179/2023 (assessores de investimento); finfluencers — posição da CVM de responsabilizar a entidade regulada contratante[^17][^18][^19]
- TRF-1 — decisão de março/2026 pelo fim da biomedicina estética invasiva autônoma[^20]
- CDC Art. 37 e 49 (publicidade enganosa e direito de arrependimento)[^21]

**Itens com fonte não completamente verificável neste módulo:**

- Acórdãos específicos do TED/OAB sobre publicidade irregular pós-2023: *não encontrado com fonte confiável e pública*
- Texto consolidado do novo Código de Ética Odontológica em revisão (2024): *não publicado definitivamente até a data de geração*
- BACEN — norma específica de publicidade brasileira (as buscas retornaram predominantemente normas do Banco de Portugal): a base regulatória do BACEN é a Res. CMN 4.949/2021 e Res. BCB 96/2021, aplicadas por analogia às regras de transparência
<span style="display:none">[^22][^23][^24][^25][^26][^27][^28][^29][^30][^31][^32][^33][^34][^35][^36][^37][^38][^39][^40][^41][^42][^43]</span>

<div align="center">⁂</div>

[^1]: https://portal.cfm.org.br/noticias/cfm-atualiza-resolucao-da-publicidade-medica/

[^2]: https://www.migalhas.com.br/quentes/393424/cfm-muda-regra-e-permite-antes-e-depois-de-pacientes-na-internet

[^3]: https://cremers.org.br/novas-regras-da-publicidade-medica-entram-em-vigor/

[^4]: https://portal.cfm.org.br/noticias/resolucao-libera-fotos-como-antes-e-depois/

[^5]: https://website.cfo.org.br/redes-sociais-na-odontologia-fique-atento-as-normas-eticas-e-acerte-na-publicacao-dos-conteudos/

[^6]: https://blog.dentalspeed.com/publicidade-odontologica/

[^7]: https://website.cfo.org.br/em-cumprimento-a-decisao-do-cade-cfo-realiza-alteracoes-pontuais-no-codigo-de-etica/

[^8]: https://website.cfo.org.br/etica-para-cirurgioes-dentistas-recem-formados-principais-pontos-de-atencao/

[^9]: https://bvsms.saude.gov.br/bvs/saudelegis/anvisa/2018/rdc0243_26_07_2018.pdf

[^10]: https://bvsms.saude.gov.br/bvs/saudelegis/anvisa/2008/rdc0096_17_12_2008.html

[^11]: https://www.gov.br/anvisa/pt-br/assuntos/fiscalizacao-e-monitoramento/propaganda/propaganda

[^12]: https://advbox.com.br/blog/provimento-marketing-juridico/

[^13]: https://www.projuris.com.br/blog/provimento-205-2021/

[^14]: https://pedrorafael.adv.br/o-que-diz-o-provimento-205-da-oab/

[^15]: https://desmistificando.com.br/advogado-pode-impulsionar-publicacao/

[^16]: https://www.whatsbotgpt.store/blog/provimento-2052021-oab-no-marketing-juridico-regras-atualizadas-o-que-pode-e-o-que-nao-pode-pdf-exemplos-e-checklist

[^17]: https://thielmann.adv.br/2024/05/31/finfluencers-e-a-cvm-em-que-pe-esta-a-regulacao-dos-influenciadores-digitais-de-financas-no-brasil/

[^18]: https://rdm.org.br/wp-content/uploads/2025/10/083-132.-GUIMARAES-Vitor-Camolesi.-Finfluencers-Regulacao-de-influenciadores-digitais-financeiros-no-mercado-de-capitais.pdf

[^19]: https://conteudo.cvm.gov.br/legislacao/resolucoes/resol179.html

[^20]: https://cremers.org.br/trf-1-decide-pelo-fim-da-pratica-da-biomedicina-estetica-invasiva/

[^21]: https://advbox.com.br/blog/consumidor-cdc-publicidade-enganosa/

[^22]: https://sistemas.cfm.org.br/normas/arquivos/resolucoes/BR/2023/2336_2023.pdf

[^23]: https://sistemas.cfm.org.br/normas/visualizar/resolucoes/BR/2023/2336

[^24]: https://fiscalizacao.cremesp.org.br/faq/

[^25]: https://sistemas.intercom.org.br/pdf/link_aceite/nacional/17/10162024194929671042f94e27c.pdf

[^26]: https://ojs.focopublicacoes.com.br/foco/article/view/5845

[^27]: https://aba.com.br/wp-content/uploads/2021/11/PAPER-ABA-Por-uma-Publicidade-Livre-Pujante-Transparente-Ética-e-Responsável-ok-digital-1.pdf

[^28]: https://website.cfo.org.br/wp-content/uploads/2018/03/codigo_etica.pdf

[^29]: https://www.instagram.com/reel/DRpa02tgF6w/

[^30]: https://croba.org.br/alteracao-no-codigo-de-etica-da-odontologia-visa-modernizar-a-publicidade-e-propaganda/

[^31]: https://www.garrastazu.adv.br/atualizacoes-da-anvisa-para-cosmeticos-o-que-mudou-com-as-novas-regulamentacoes

[^32]: https://www.youtube.com/watch?v=AY2JFrml7JY

[^33]: https://www.reclameaqui.com.br/segredo-das-empresas/propaganda-enganosa-curso-nao-entrega-o-conteudo-anunciado_BeYFxJ232rx-OpNw/

[^34]: https://fi-admin.bvsalud.org/document/view/cwxre

[^35]: https://diariodarepublica.pt/dr/detalhe/aviso-banco-portugal/5-2024-898867027

[^36]: https://www.bportugal.pt/sites/default/files/documents/2024-09/projeto_de_aviso_da_consulta_publica_2_2024.pdf

[^37]: https://www.cgd.pt/Ajuda/Espaco-Cliente/Informacao-util/Documents/Aviso-BdP-10_2008.pdf

[^38]: https://revistas.unifacs.br/index.php/redu/article/viewFile/4220/2875

[^39]: https://www.deco.proteste.pt/dinheiro/contas-ordem/noticias/publicidade-produtos-servicos-bancarios-regras-mais-apertadas

[^40]: https://www.bfa.ao/media/1597/aviso-nº-09_2014-10-de-dezembro.pdf

[^41]: https://www.bcb.gov.br/content/cidadaniafinanceira/documentos_cidadania/guia_de_excelencia/guia_de_excelencia_oferta_de_produtos_servi%C3%A7os_financeiros.pdf

[^42]: https://portal.cfm.org.br/noticias/conselho-federal-de-medicina-alerta-por-lei-procedimentos-esteticos-invasivos-devem-ser-executados-apenas-por-medicos/

[^43]: https://bfa.ao/media/1606/aviso-nº-03_2015-20-de-abril.pdf


</content>
