---
source_file: perplexity-mod2-conar-autorregulamentacao.md
converted_at: 2026-03-23
original_extension: md
processor: Echo (aiox-m2m-etl)
extraction_quality: full
domain: CONAR e Autorregulamentação Publicitária Digital
source_type: perplexity-deep-research
source_tool: Perplexity Pro (Deep Research)
agent_target: juridica-consumidor
squad: squad-cadarn-juridica
module: 2
module_title: CONAR — Autorregulamentação Publicitária para Marketing Digital
---

<content>


# Você é um pesquisador especialista em autorregulamentação publicitária e Direito da Publicidade no Brasil. Sua tarefa

é produzir um módulo exaustivo sobre o CONAR (Conselho Nacional de Autorregulamentação Publicitária) e o Código
Brasileiro de Autorregulamentação Publicitária (CBAP), com foco em sua aplicação a marketing digital.

Contexto de uso: Este documento será processado por um pipeline automatizado (M2M + RAG). O chunking é feito por
headers Markdown (\#\# e \#\#\#). Os metadados em HTML comment são parseados por regex antes do chunking e funcionam como
tags de classificação semântica — mantenha o formato exato. Output obrigatório: Markdown puro, sem exceções. O
documento será carregado como base de conhecimento de um agente Claude Code (CLI) utilizado por profissionais de uma
agência de marketing digital que atende prestadores de serviços premium (imobiliárias de luxo, clínicas de estética,
escritórios de advocacia) em capitais brasileiras.

  <!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 2] [TEMA:
  CONAR-autorregulamentação-publicidade-digital] -->
Cubra obrigatoriamente:

1. **Estrutura e natureza jurídica do CONAR** — O que é, como funciona, composição, poder (ou ausência de) coercitivo.
Diferença entre CONAR e PROCON/SENACON. Por que o CONAR importa mesmo sem poder legal direto (reputação, precedente,
compliance).
2. **Princípios gerais do CBAP (Arts. 1-50)** — Os princípios mais relevantes para marketing digital: honestidade
(Art. 1), responsabilidade social (Art. 2), decência (Art. 6), identificação publicitária (Art. 28-30), publicidade
comparativa (Art. 32), testemunhais (Art. 27), segurança e acidentes (Art. 33-34). Para cada princípio, dê exemplo
prático de violação em campanha digital.
3. **Anexo P — Influenciadores Digitais** — Texto completo ou resumo detalhado do Anexo P. Regras de identificação
publicitária (\#publi, \#ad, parceria paga). Quando se aplica. Penalidades. Casos de representação contra
influenciadores (2023-2026).
4. **Anexo A — Bebidas Alcoólicas** — Regras relevantes para agências que atendem bares, restaurantes ou eventos
premium. Horários, menores, consumo responsável.
5. **Anexo H — Alimentos e Bebidas Não Alcoólicas** — Regras sobre health claims, antes/depois, publicidade para
crianças.
6. **Anexo Q — Apelos de Sustentabilidade (Greenwashing)** — O que configura greenwashing publicitário. Regras para
claims ESG em campanhas. Muito relevante para marcas premium que usam "sustentável" como diferencial.
7. **Processo de representação no CONAR** — Como funciona: quem pode denunciar, prazos, rito processual, tipos de
decisão (sustação, advertência, alteração, arquivamento). Consequências práticas de uma condenação no CONAR.
8. **Casos emblemáticos recentes (2023-2026)** — Representações envolvendo marketing digital, influenciadores, redes
sociais. Para cada caso: partes, conduta denunciada, decisão, fundamento. Se não encontrar casos recentes
verificáveis, indique "não encontrado com fonte confiável" e cite o caso análogo mais próximo com nota de analogia.
9. **Tabela de referência rápida** — Para uso operacional pelo agente: tabela com situação → artigo CBAP → risco →
ação recomendada. Exemplo: "Post de influencer sem \#publi → Art. 28 + Anexo P → ALTO → Adicionar identificação antes
de publicar".

Regras de integridade:

- Para artigos do CBAP: cite o número do artigo e transcreva o trecho relevante
- Para casos CONAR: cite partes, ano e decisão (se verificável)
- Se não encontrar fonte verificável: "não encontrado com fonte confiável"
- Doutrina: pode citar autores consagrados (Lucia Ancona, Adalberto Pasqualotto) se a obra existir de fato
- Use HTML comments para metadados: <!-- [MÓDULO: 2] [SUBTEMA: nome] [TIPO: tipo] -->
- Chunks entre 300-800 palavras por seção \#\#/\#\#\#
- Formato: Markdown puro, headers \#\# e \#\#\#, tabelas onde aplicável

Agora tenho todas as fontes necessárias — o CBAP edição 2025, o Boletim CONAR nº 226 (acórdãos de 2024), e dados atualizados sobre Anexo U (greenwashing, novembro 2025) e Guia de Influenciadores. Vou produzir o módulo completo.

```markdown
<!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 2] [TEMA: CONAR-autorregulamentação-publicidade-digital] -->

# Módulo 2 — CONAR e Código Brasileiro de Autorregulamentação Publicitária (CBAP): Guia Operacional para Marketing Digital

> **Nota de integridade editorial:** Este módulo cita artigos transcritos do CBAP Edição 2025 (PDF oficial, conar.org.br/pdf/Codigo-CONAR-2025.pdf). Os acórdãos citados constam do Boletim CONAR nº 226 (março 2025), referente a julgamentos de fevereiro/2024. Informações sobre Anexo U (greenwashing) refletem a atualização aprovada em 24/10/2025, em vigor desde novembro de 2025. Quando informação não pôde ser verificada com fonte primária, a nota "não encontrado com fonte confiável" é inserida. Números de Anexo corretos diferem de algumas referências circulantes na internet — veja correções nas seções relevantes.

---

## 1. Estrutura e Natureza Jurídica do CONAR

<!-- [MÓDULO: 2] [SUBTEMA: estrutura-CONAR] [TIPO: conceitual-jurídico] -->

### O que é o CONAR

O Conselho Nacional de Autorregulamentação Publicitária (CONAR) é uma **organização não governamental (ONG), sem fins lucrativos**, fundada em 5 de maio de 1980, em São Paulo. Não é autarquia, agência reguladora nem órgão do Poder Público. O CONAR é uma entidade da sociedade civil que reúne os principais elos da cadeia publicitária brasileira: anunciantes, agências e veículos.

**Entidades fundadoras:**
- ABA – Associação Brasileira de Anunciantes
- ABAP – Associação Brasileira de Agências de Propaganda
- ABERT – Associação Brasileira de Emissoras de Rádio e Televisão
- ANJ – Associação Nacional de Jornais
- ANER – Associação Nacional de Editores de Revistas
- Central de Outdoor

**Entidade cofundadora (2020):**
- IAB Brasil – Interactive Advertising Bureau (mídia interativa)

**Entidades aderentes:** ABRATEL, ABTA, FENEEC.

**Entidades associadas relevantes para agências digitais:** ABRADI (Agentes Digitais), ANAMID (Indústria Digital), AMI (Mídia Interativa), ABOOH (Out of Home), ABRABE (Bebidas), FEBRABAN, entre outras.

O CBAP está registrado no 2º Cartório de Registro de Títulos e Documentos de São Paulo sob o número 5678, de 11/05/1980.

---

### Composição e Funcionamento Interno

<!-- [MÓDULO: 2] [SUBTEMA: composição-funcionamento] [TIPO: organizacional] -->

O CONAR possui três camadas de governança:

1. **Diretoria:** presidente e três vice-presidentes, eleitos a cada dois anos. Presidente atual: Sergio Pompilio.
2. **Conselho Superior:** instância de política geral da entidade.
3. **Conselho de Ética:** órgão julgador, composto por conselheiros voluntários — publicitários e cidadãos de outras profissões. Organiza-se em **oito Câmaras** distribuídas geograficamente:
   - 1ª, 2ª, 6ª e 7ª Câmaras — São Paulo (SP)
   - 3ª Câmara — Rio de Janeiro (RJ)
   - 4ª Câmara — Brasília (DF)
   - 5ª Câmara — Porto Alegre (RS)
   - 8ª Câmara — Recife (PE)

Existe também a **Câmara Especial de Recursos**, para julgamento em segunda instância.

O **Departamento de Monitoria** realiza ciclos sistemáticos de fiscalização proativa (16 rodadas em 2024, analisando mais de 1.200 horas de TV e mais de 3.600 postagens em redes sociais).

O **Núcleo Preventivo** emite notificações extrajudiciais a anunciantes, agências e influenciadores, buscando adequação sem abertura formal de processo. Em 2024, foram emitidas 1.235 notificações, sendo 278 sobre identificação publicitária em posts de influenciadores e 957 sobre apostas.

---

### Natureza Jurídica: Poder sem Coerção

<!-- [MÓDULO: 2] [SUBTEMA: natureza-juridica-poder] [TIPO: conceitual-jurídico] -->

O CONAR **não possui poder coercitivo direto**. Suas decisões são tecnicamente *recomendações*: o CONAR recomenda ao veículo (emissora, plataforma, publisher) que altere ou suste a peça. O veículo que ignora uma decisão transitada em julgado, contudo, passa a responder solidariamente nos termos do Art. 45, alínea "e":

> *"Art. 45, e — a responsabilidade do Veículo será equiparada à do Anunciante sempre que a veiculação do anúncio contrariar os termos de recomendação que lhe tenha sido comunicada oficialmente pelo Conselho Nacional de Autorregulamentação Publicitária – CONAR."*

O Art. 49 do CBAP também estabelece:

> *"Art. 49 — Nenhum Anunciante, Agência, Editor, proprietário ou agente de um veículo publicitário deve promover a publicação de qualquer anúncio que tenha sido reprovado pelo Conselho Nacional de Autorregulamentação Publicitária – CONAR."*

**Por que o CONAR importa mesmo sem poder legal direto:**

| Dimensão | Impacto Prático |
|---|---|
| **Reputação setorial** | Condenação publicada em Boletim e site, acessível a clientes, concorrentes e imprensa |
| **Precedente normativo** | O Art. 16 do CBAP reconhece o Código como "fonte subsidiária" em processos judiciais e administrativos |
| **Compliance preventivo** | Marcas premium usam conformidade ao CONAR como sinal de governança publicitária |
| **Pressão sobre plataformas** | Meta, Google e YouTube operam políticas alinhadas ao CONAR; notificações CONAR podem gerar remoção de conteúdo pelas próprias plataformas |
| **Relação com PROCON/SENACON** | Decisão CONAR não vincula PROCON, mas é frequentemente citada como parâmetro de boa-fé do anunciante |

---

### CONAR × PROCON × SENACON

<!-- [MÓDULO: 2] [SUBTEMA: comparativo-CONAR-PROCON-SENACON] [TIPO: comparativo] -->

| Critério | CONAR | PROCON | SENACON |
|---|---|---|---|
| **Natureza** | ONG — autorregulação setorial | Órgão estadual/municipal de defesa do consumidor | Secretaria Nacional do Consumidor (Ministério da Justiça) |
| **Base legal** | CBAP (código privado) | CDC (Lei 8.078/90) | CDC + Lei 12.291/10 |
| **Poder sancionador** | Não — apenas recomendações | Sim — multas administrativas | Sim — multas e sanções nacionais |
| **Objeto** | Conteúdo ético do anúncio | Relação de consumo (produto/serviço, não só o anúncio) | Relações de consumo em âmbito nacional |
| **Quem pode ser atingido** | Anunciante, agência e veículo | Fornecedor (empresa) | Fornecedor (empresa) |
| **Prazo típico** | Semanas a meses | Meses a anos | Meses a anos |
| **Publicidade da decisão** | Alta (boletim público, site) | Moderada | Alta (Sindec/MJ) |

**Consequência prática:** uma campanha pode ser simultaneamente alvo de representação no CONAR (pela ética do conteúdo publicitário) e de reclamação no PROCON (por prática abusiva ao consumidor, como propaganda enganosa). As esferas são independentes e cumulativas.

---

## 2. Princípios Gerais do CBAP Aplicados ao Marketing Digital

<!-- [MÓDULO: 2] [SUBTEMA: principios-CBAP] [TIPO: normativo-com-exemplos] -->

### Estrutura do CBAP (Edição 2025)

O CBAP estrutura-se em:
- **Capítulo I** — Introdução (Arts. 1–18): preâmbulo, objetivos, interpretação
- **Capítulo II** — Princípios Gerais (Arts. 19–43): as 12 seções de conduta
- **Capítulo III** — Categorias Especiais (Art. 44): remete a 22 Anexos (A a X)
- **Capítulo IV** — As Responsabilidades (Arts. 45–49)
- **Capítulo V** — Infrações e Penalidades (Art. 50)

> **Importante:** O Art. 17 estabelece o *teste primordial*: *"Ao aferir a conformidade de uma campanha ou anúncio aos termos deste Código, o teste primordial deve ser o impacto provável do anúncio, como um todo, sobre aqueles que irão vê-lo ou ouvi-lo."* Em marketing digital, isso inclui o impacto do conjunto do perfil, não apenas de um post isolado.

---

### Art. 1 — Legalidade e Honestidade

<!-- [MÓDULO: 2] [SUBTEMA: art1-legalidade-honestidade] [TIPO: normativo] -->

> *"Art. 1º — Todo anúncio deve ser respeitador e conformar-se às leis do país; deve, ainda, ser honesto e verdadeiro."*

**Aplicação digital:** Toda campanha em redes sociais, email marketing, mídia programática e publicidade nativa está sujeita ao Art. 1. A honestidade abrange tanto o conteúdo verbal quanto o visual.

**Exemplo de violação:** Clínica de estética que usa imagem de paciente de outro profissional como resultado próprio; imobiliária que exibe fotos de imóveis já vendidos como disponíveis; escritório de advocacia que promete resultado garantido em processo judicial.

---

### Art. 2 — Responsabilidade Social

<!-- [MÓDULO: 2] [SUBTEMA: art2-responsabilidade-social] [TIPO: normativo] -->

> *"Art. 2º — Todo anúncio deve ser preparado com o devido senso de responsabilidade social, evitando acentuar, de forma depreciativa, diferenciações sociais decorrentes do maior ou menor poder aquisitivo dos grupos a que se destina ou que possa eventualmente atingir."*

**Aplicação digital:** Campanhas de segmentação por renda que humilham ou depreciam públicos de baixo poder aquisitivo. Em marketing de serviços premium, o cuidado é inverso: não usar linguagem que denigra quem não pode pagar pelo serviço.

**Exemplo de violação:** Anúncio para imobiliária de luxo com copy como "chega de vizinhos barulhentos" com imagens implicitamente associadas a classes C e D.

---

### Art. 19 — Respeitabilidade (Dignidade)

<!-- [MÓDULO: 2] [SUBTEMA: art19-respeitabilidade] [TIPO: normativo] -->

> *"Art. 19 — Toda atividade publicitária deve caracterizar-se pelo respeito à dignidade da pessoa humana, à intimidade, ao interesse social, às instituições e símbolos nacionais, às autoridades constituídas e ao núcleo familiar."*

**Aplicação digital:** Uso de imagens geradas por IA que distorcem a imagem de pessoas reais; campanhas de retargeting invasivas; posts que exploram tragédias para promover produtos.

---

### Art. 22 — Decência

<!-- [MÓDULO: 2] [SUBTEMA: art22-decencia] [TIPO: normativo] -->

> *"Art. 22 — Os anúncios não devem conter afirmações ou apresentações visuais ou auditivas que ofendam os padrões de decência que prevaleçam entre aqueles que a publicidade poderá atingir."*

**Importante:** O parâmetro é o público *que a publicidade poderá atingir* — em marketing digital, onde o alcance orgânico ultrapassa o público-alvo segmentado, o critério é mais amplo do que o público intencional da campanha.

**Exemplo de violação:** Anúncio de clínica de estética com linguagem sexual implícita veiculado em feed público (não restrito por idade).

---

### Art. 23 — Honestidade (Proteção ao Consumidor)

<!-- [MÓDULO: 2] [SUBTEMA: art23-honestidade] [TIPO: normativo] -->

> *"Art. 23 — Os anúncios devem ser realizados de forma a não abusar da confiança do consumidor, não explorar sua falta de experiência ou de conhecimento e não se beneficiar de sua credulidade."*

**Aplicação digital:** Suplementos alimentares com promessas de emagrecimento sem base científica; copywriting de urgência artificial ("últimas vagas", contador falso); dark patterns em landing pages.

---

### Art. 27 — Apresentação Verdadeira e Testemunhais

<!-- [MÓDULO: 2] [SUBTEMA: art27-apresentacao-verdadeira-testemunhais] [TIPO: normativo] -->

O Art. 27 é o mais extenso do CBAP. Seus parágrafos relevantes para marketing digital:

**§1 — Descrições:** *"Todas as descrições, alegações e comparações que se relacionem com fatos ou dados objetivos devem ser comprobatórias."* → Todo claim de resultado (antes/depois, rentabilidade, tempo de entrega) deve ter comprovação disponível.

**§2 — Alegações:** proíbe informações que, *"direta ou indiretamente, por implicação, omissão, exagero ou ambiguidade, leve o Consumidor a engano."* Inclui omissão de condições restritivas em letras pequenas em stories.

**§4 — Uso da palavra "Grátis":** permitido apenas quando não há custo algum. Proibido "frete grátis" sem informar outros encargos.

**§9 — Testemunhais:**
> *"a. O anúncio abrigará apenas depoimentos personalizados e genuínos, ligados à experiência passada ou presente de quem presta o depoimento; b. o testemunho utilizado deve ser sempre comprovável."*

**Exemplo de violação em digital:** Influenciadora de clínica de estética que declara resultado que não vivenciou; review patrocinado de hotel sem experiência real; depoimento de "cliente satisfeito" que é na verdade funcionário da empresa.

---

### Art. 28 — Identificação Publicitária

<!-- [MÓDULO: 2] [SUBTEMA: art28-identificacao-publicitaria] [TIPO: normativo-central] -->

> *"Art. 28 — O anúncio deve ser claramente distinguido como tal, seja qual for a sua forma ou meio de veiculação."*

Este é o artigo mais citado em representações de marketing digital. O Art. 30 complementa:

> *"Art. 30 — A peça jornalística sob a forma de reportagem, artigo, nota, texto-legenda ou qualquer outra que se veicule mediante pagamento, deve ser apropriadamente identificada para que se distinga das matérias editoriais e não confunda o Consumidor."*

O Art. 10 estende a obrigação ao merchandising:
> *"Art. 10 — A publicidade indireta ou 'merchandising' submeter-se-á igualmente a todas as normas dispostas neste Código, em especial os princípios de ostensividade (art. 9º) e identificação publicitária (art. 28)."*

**Aplicação digital:** posts de influenciadores, publipost em blogs, native ads, branded content, parceria em podcast.

**Exemplo de violação:** Post de influenciadora divulgando produto de skincare sem #publi, usando narrativa de descoberta orgânica quando há relação comercial — como ocorreu no caso Maga Cosméticos × Gabi Nascimento (Rep. 190/23, 1ª Câmara, 2024).

---

### Art. 32 — Publicidade Comparativa

<!-- [MÓDULO: 2] [SUBTEMA: art32-publicidade-comparativa] [TIPO: normativo] -->

> *"Art. 32 — a publicidade comparativa será aceita, contanto que respeite os seguintes princípios e limites: a. seu objetivo maior seja o esclarecimento, se não mesmo a defesa do consumidor; b. tenha por princípio básico a objetividade na comparação, posto que dados subjetivos, de fundo psicológico ou emocional, não constituem uma base válida de comparação; c. a comparação alegada ou realizada seja passível de comprovação; f. não se caracterize concorrência desleal, depreciação à imagem do produto ou à marca de outra empresa."*

**Exemplo de violação:** Post de clínica de estética comparando preços de procedimentos de concorrente com valores desatualizados ou distorcidos; imobiliária que usa imagens reais de empreendimento rival com legendas falsas.

---

### Art. 33 — Segurança e Acidentes

<!-- [MÓDULO: 2] [SUBTEMA: art33-seguranca] [TIPO: normativo] -->

> *"Art. 33 — Este Código condena os anúncios que: a. manifestem descaso pela segurança, sobretudo quando neles figurarem jovens e crianças; b. estimulem o uso perigoso do produto oferecido; c. deixem de mencionar cuidados especiais para a prevenção de acidentes."*

**Aplicação digital:** Reels de clínica mostrando procedimentos invasivos sem menção a riscos; tutoriais de cuidados com produtos químicos sem avisos de segurança; stories de academia promovendo exercícios de alta intensidade sem alertas para iniciantes.

---

### Art. 37 — Crianças e Jovens

<!-- [MÓDULO: 2] [SUBTEMA: art37-criancas-jovens] [TIPO: normativo] -->

O Art. 37 é extenso e fundamental. Resumo das vedações mais relevantes para digital:

> *"Nenhum anúncio dirigirá apelo imperativo de consumo diretamente à criança."*

> *"§3 — Este Código condena a ação de merchandising ou publicidade indireta contratada que empregue crianças, elementos do universo infantil ou outros artifícios com a deliberada finalidade de captar a atenção desse público específico, qualquer que seja o veículo utilizado."*

> *"§4 — Nos conteúdos segmentados, criados, produzidos ou programados especificamente para o público infantil, qualquer que seja o veículo utilizado, a publicidade de produtos e serviços destinados exclusivamente a esse público estará restrita aos intervalos e espaços comerciais."*

**Aplicação digital:** criadores de conteúdo infantil (YouTube Kids, Instagram) que inserem publi de produtos fora dos breaks delimitados; uso de personagens infantis para promover apostas (como ocorreu no caso 1991BET/influenciador mirim, Rep. 208/23).

---

### Arts. 36, 36-A e 36-B — Meio Ambiente e Aspectos Socioambientais

<!-- [MÓDULO: 2] [SUBTEMA: art36-meio-ambiente] [TIPO: normativo] -->

> *"Art. 36-A — É legítimo o uso de características socioambientais positivas nas mensagens publicitárias. São encorajadas publicidades que destaquem cuidados para com o meio ambiente, devendo respeitar as regras e princípios previstos neste Código e na legislação em vigor, de modo a assegurar a correção das alegações e coibir o greenwashing."*

> *"Art. 36-B — A publicidade que contenha alegações socioambientais deverá atender as especificações do Anexo 'U' e os seguintes princípios: a. Veracidade; b. Qualificação; c. Exatidão; d. Pertinência; e. Relevância; f. Concretude."*

Ver Seção 6 deste módulo para detalhamento do Anexo U.

---

## 3. Guia de Publicidade por Influenciadores Digitais

<!-- [MÓDULO: 2] [SUBTEMA: guia-influenciadores-digitais] [TIPO: normativo-operacional] -->

> **⚠️ Correção de Nomenclatura:** Algumas referências circulantes mencionam "Anexo P — Influenciadores Digitais". Isso está **incorreto**. No CBAP Edição 2025, **Anexo P = Cervejas e Vinhos** (Art. 44). O documento regulatório para influenciadores é o **"Guia de Publicidade por Influenciadores Digitais"**, publicado pelo CONAR em dezembro de 2020, que não tem numeração de Anexo formal ao CBAP, mas é citado como peça auxiliar normativa nos acórdãos do Conselho de Ética. Nos acórdãos, a citação típica é: *"do Código e seu Anexo P [Cervejas e Vinhos, quando pertinente] e Guia de Publicidade por Influenciadores Digitais"* — são documentos distintos.

### Escopo de Aplicação

O Guia aplica-se quando estiverem **cumulativamente** presentes três requisitos:

1. **Divulgação de bens ou serviços** pelo influenciador
2. **Contrapartida comercial ou financeira** ao influenciador, pelo anunciante e/ou agência
3. **Controle de conteúdo** pelo anunciante/agência — definição de conteúdo, tempo, frequência ou forma de postagem

> **Atenção — Ganho Indireto:** O Guia esclarece que *"ganho indireto é considerado vínculo publicitário entre influenciador e anunciante."* Isso inclui recebimento de produtos, acesso a eventos, convites para viagens, cupons de desconto exclusivos e qualquer benefício não monetário. O caso Maga × Gabi Nascimento (Rep. 190/23) demonstrou que a influenciadora mantinha contrato de parceria com a marca e distribuía cupons aos seguidores, o que caracterizou vínculo publicitário mesmo sem contrato de post específico para aquela publicação.

### Regras de Identificação Publicitária

O Guia padroniza termos e ferramentas para identificação:

**Termos aceitos (em posição de destaque, visível antes do fold):**
- `#publicidade`
- `#publi`
- `#publipost`
- `parceria paga`
- `conteúdo patrocinado`
- Ferramentas nativas de plataformas: Instagram "Parceria Paga", YouTube "Incluindo link pago"

**Termos insuficientes (não aceitos como identificação isolada):**
- `#ad` (ambíguo para o público brasileiro geral)
- Menção no final de longa legenda
- Identificação apenas nos créditos do vídeo
- Marcação de perfil da marca sem identificação explícita de relação comercial

> O CONAR emitiu 278 notificações preventivas em 2024 sobre identificação publicitária em posts de influenciadores (Boletim 226, março 2025).

### Responsabilidades

O Art. 45 do CBAP e o Guia distribuem responsabilidades:

- **Anunciante:** responsabilidade total pelo conteúdo, mesmo veiculado pelo influenciador
- **Agência:** responsabilidade solidária com o anunciante
- **Influenciador:** responsabilidade pelo cumprimento das regras de identificação e pela veracidade dos testemunhais (Art. 27, §9)
- **Plataforma (veículo):** pode ser notificada, conforme Art. 45-c; a Meta já forneceu esclarecimentos ao CONAR em julgamentos (cf. Rep. 208/23)

### Conteúdo Gerado pelo Influenciador × Conteúdo Aprovado pela Agência

Mesmo quando o conteúdo é gerado espontaneamente pelo influenciador (UGC — User Generated Content), se há relação comercial preexistente, as regras se aplicam. No caso HNK BR/Heineken (Rep. 166/23), o influenciador Viva Mais SP publicou vídeo de tour na fábrica sem identificação de patrocínio. A defesa alegou não haver relação comercial — a câmara arquivou a representação quanto ao caráter publicitário mas advertiu o influenciador pela falta de cuidado com a mensagem.

### Casos de Representação Envolvendo Influenciadores (2023–2024)

**Caso 1 — 1991BET.COM, 777Max × Influenciador Mirim (Rep. 208/23)**
- **Partes:** CONAR (de ofício) × 1991Bet.com, 777Max e influenciador menor de idade
- **Conduta:** Divulgação de apostas esportivas em Instagram por influenciador menor de 18 anos
- **Decisão:** Sustação + advertência (1ª Câmara, unanimidade)
- **Fundamento:** Arts. 1, 3, 6, 37 e 50, letras "a" e "c" do Código; Lei 14.790/23; MP 1.182/23
- **Relevância:** CONAR comunicou decisão ao Ministério Público Federal e Ministério da Fazenda

**Caso 2 — Galderma × Nutriex/Rennova (Rep. 094/23, recurso)**
- **Partes:** Galderma Brasil × Nutriex — campanha com influenciadoras no Instagram
- **Conduta:** Alegações de superioridade comparativa sem comprovação; posts de influenciadoras com afirmações "melhor do mercado" sobre produto injetável voltado a profissionais de saúde
- **Decisão:** Alteração + advertência (4ª, 5ª e Câmara Especial de Recursos, unanimidade)
- **Fundamento:** Arts. 23, 27, 32, 33, 43 e 50, letras "a" e "b"
- **Nota relevante:** A segunda relatora estendeu a condenação ao post de influenciadora com 26,5 milhões de seguidores, ressaltando que "sequer é mencionado que o uso deve ser por meio de profissional"

**Caso 3 — Maga Cosméticos × Gabi Nascimento (Rep. 190/23)**
- **Partes:** Consumidora (via CONAR) × Maga + influenciadora Gabi Nascimento
- **Conduta:** Uso de filtro/Photoshop em post de skincare sem identificação publicitária; ausência de #publi a despeito de contrato de parceria e distribuição de cupons
- **Decisão:** Alteração + advertência (1ª Câmara, unanimidade)
- **Fundamento:** Arts. 1, 3, 6, 23, 27 e 50, letra "b" do Código
- **Destaque:** CONAR firmou que o uso de filtros não é proibido per se, mas é proibido quando induz o consumidor a erro sobre a eficácia do produto

**Caso 4 — HNK BR/Heineken × Influenciadores (Rep. 166/23)**
- **Partes:** CONAR (de ofício) × HNK BR (Heineken) + influenciadores Viva Mais SP, Brazuca Dicas, Diego MKT Gastronômico
- **Conduta:** Tour na fábrica Heineken publicado sem identificação publicitária
- **Decisão:** Advertência ao Viva Mais SP (pelo alcance e responsabilidade); arquivamento para HNK BR (ausência de relação comercial comprovada)
- **Fundamento:** Arts. 1, 3, 6, 28 e 50, letra "a"; Guia de Publicidade por Influenciadores Digitais

**Caso 5 — Pernod Ricard × Gabriel Picolo (Rep. 242/23)**
- **Partes:** CONAR (de ofício) × Pernod Ricard Brasil + influenciador Gabriel Picolo (Ballantine's × Borderlands)
- **Conduta:** Uso de personagem de game com classificação etária 16+ para divulgação de whisky
- **Decisão:** Arquivamento (6ª Câmara, unanimidade)
- **Fundamento:** Art. 27, nº 1, letra "a" do RICE
- **Nota:** A defesa comprovou que o público do game é majoritariamente adulto e a campanha foi segmentada para maiores de 18 anos

---

## 4. Anexo A — Bebidas Alcoólicas

<!-- [MÓDULO: 2] [SUBTEMA: anexo-A-bebidas-alcoolicas] [TIPO: normativo-setorial] -->

> **Relevância para agências:** Clientes que atendem bares, restaurantes premium, eventos, importadoras de vinho e destilados precisam observar o Anexo A em toda comunicação digital, incluindo posts orgânicos que exibam o produto à venda.

O Anexo A do CBAP regula toda publicidade de bebidas alcoólicas, definidas como aquelas classificadas como tal pelas normas e regulamentos oficiais.

### Restrições de Horário e Meio

Para **TV e rádio (programação regular):**

> *"Comerciais, spots, inserts de vídeo, textos-foguete, caracterizações de patrocínio, vinhetas de passagem e mensagens de outra natureza, inclusive o merchandising ou publicidade indireta, publicidade virtual e as chamadas para os respectivos programas só serão veiculados no período compreendido entre 21h30 (vinte e uma horas e trinta minutos) e 6h (seis horas) (horário local)."*

**Para mídia exterior (outdoor, busdoor, painéis digitais OOH):**
Com base no acórdão Brown-Forman × CONAR (Rep. 222/23), o Conselho consolidou o entendimento de que **anúncios de bebidas alcoólicas em mídia exterior não podem apresentar nada além do produto, sua marca e/ou slogan**. O relator votou pela alteração de peça de Jack Daniel's que associava o produto a uma cena de Fórmula 1, mesmo com "se beber não dirija" presente na peça.

**Para plataformas digitais (aplicação analógica):**
O Anexo A foi concebido em época anterior às redes sociais, mas o CONAR aplica seus princípios a qualquer meio. Diretrizes operacionais:
- Segmentação por idade (18+) obrigatória em todos os formatos pagos
- Stories e Reels com bebidas alcoólicas: não devem ser direcionados a menores
- Parcerias com influenciadores para bebidas alcoólicas: aplicam-se todas as restrições de conteúdo, mais as do Guia de Influenciadores

### Vedações de Conteúdo

As principais proibições do Anexo A:

- **Associação a dirigir ou operar máquinas:** nenhuma imagem ou copy que relacione consumo de álcool e volante, mesmo indiretamente
- **Menores de idade:** vedada a participação de menores como modelos ou em cenas de consumo; vedado o apelo a público menor de 18 anos
- **Consumo excessivo:** proibido incentivar consumo em quantidade excessiva ou apresentar consumo compulsivo como positivo
- **Solução para problemas pessoais:** vedado associar álcool à resolução de problemas emocionais, profissionais ou afetivos
- **Aprovação social ou superioridade:** vedado sugerir que o consumo proporciona popularidade, sucesso ou vantagem social
- **Apelo imperativo:** sem frases imperativas como "Beba X" dirigidas diretamente ao consumidor

> **Nota sobre Anexo P (Cervejas e Vinhos):** O Anexo P do CBAP trata especificamente de cervejas e vinhos, com regras complementares ao Anexo A para esses subcategorias. Em 2024, o Departamento de Monitoria analisou 166 conteúdos sobre bebidas alcoólicas e detectou 75 possíveis irregularidades.

---

## 5. Anexo H — Produtos Alimentícios

<!-- [MÓDULO: 2] [SUBTEMA: anexo-H-alimentos] [TIPO: normativo-setorial] -->

> **Relevância para agências:** Em 2024, "Alimentos" foi o setor com mais representações abertas no CONAR (23% do total, 308 casos). O principal motivo foi a proliferação de suplementos alimentares com alegações de saúde (health claims) incompatíveis com a regulamentação sanitária e a autorregulamentação publicitária.

### Regras Gerais do Anexo H

O Anexo H aplica-se a todos os produtos alimentícios e bebidas não alcoólicas, abrangendo:

**1. Health Claims (Alegações de Saúde):**
- Toda alegação de benefício à saúde (emagrecimento, ganho muscular, imunidade, energia) deve ter **base científica comprovável** (Art. 27, §8: *"O anúncio só utilizará informação científica pertinente e defensável, expressa de forma clara até para leigos"*)
- Vedado prometer resultados que dependem de outros fatores (dieta, exercício) sem mencionar essas condicionantes
- Produtos suplementares com claims como "queima gordura", "aumenta testosterona" sem laudo técnico constituem violação ao Código e à regulamentação ANVISA

**2. Publicidade Comparativa de Alimentos:**
- Seguem as mesmas regras do Art. 32
- Comparações nutricionais devem usar a mesma porção de referência e metodologia equivalente

**3. Imagens Antes/Depois:**
- Imagens de transformação corporal implicam testemunho de resultado (Art. 27, §9)
- O resultado deve ser genuíno e comprovável
- Deve-se informar o contexto completo (tempo, dieta, exercício)
- Uso de filtros ou edição que distorça o "antes" ou o "depois" viola o Art. 27 e o Guia de Influenciadores

**4. Publicidade para Crianças (Art. 37 combinado com Anexo H):**
- Vedado o uso de personagens, mascotes ou elementos infantis para promover alimentos de baixo valor nutricional
- Vedado o apelo imperativo de consumo dirigido à criança
- Vedado prometer popularidade, afeto ou aprovação social em troca do consumo do alimento

### Aplicação a Clientes de Clínicas de Estética e Suplementos

Para agências que atendem clínicas estéticas que também comercializam suplementos nutricionais (colágeno, proteínas, termogênicos):

- Qualquer alegação de resultado estético derivado do suplemento deve ter respaldo da ANVISA e ser comprovável
- Posts de influenciadores com suplementos: aplicar Guia + Art. 27, §9 + Anexo H conjuntamente
- Risco ALTO para claims de "definição muscular em X semanas" ou "perda de X kg garantida"

---

## 6. Anexo U — Apelos de Sustentabilidade (Greenwashing)

<!-- [MÓDULO: 2] [SUBTEMA: anexo-U-sustentabilidade-greenwashing] [TIPO: normativo-atualizado] -->

> **⚠️ Correção de Nomenclatura:** O documento solicitado como "Anexo Q — Apelos de Sustentabilidade" corresponde, na estrutura real do CBAP, ao **Anexo U — Apelos de Sustentabilidade**. O **Anexo Q** do CBAP trata de "Testemunhais, Atestados, Endossos" — tema distinto.

> **Atualização crítica:** O Anexo U foi **integralmente revisado** por decisão de 24/10/2025, em vigor desde novembro de 2025, em antecipação à COP30 (Brasil, 2025). Esta é a versão vigente.

### Base Normativa

O Anexo U está fundado nos Arts. 36, 36-A e 36-B do CBAP:

> *"Art. 36-A — É legítimo o uso de características socioambientais positivas nas mensagens publicitárias. [...] de modo a assegurar a correção das alegações e coibir o greenwashing."*

> *"Art. 36-B — A publicidade que contenha alegações socioambientais deverá atender as especificações do Anexo 'U' e os seguintes princípios: a. Veracidade; b. Qualificação; c. Exatidão; d. Pertinência; e. Relevância; f. Concretude."*

### Os Seis Princípios Anti-Greenwashing (Art. 36-B)

| Princípio | Definição operacional | Exemplo de violação |
|---|---|---|
| **Veracidade** | Alegações devem ser verdadeiras e verificáveis | "Empresa carbono neutro" sem certificação ou metodologia |
| **Qualificação** | Benefícios parciais ou pontuais devem ser contextualizados | "Embalagem 100% reciclável" quando o produto em si tem alto impacto ambiental |
| **Exatidão** | Expressar com precisão o alcance do benefício | "Produto sustentável" sem especificar qual dimensão |
| **Pertinência** | Relação lógica entre a alegação e as práticas reais da empresa | Incorporadora com alto índice de desmatamento que se anuncia como "verde" |
| **Relevância** | O benefício deve ser significativo no impacto total | Substituição de canudo plástico por marca com frota de caminhões altamente poluentes |
| **Concretude** | Metas futuras precisam de planos verificáveis e acessíveis | "Seremos neutros em carbono até 2030" sem plano publicado |

### O Que Configura Greenwashing Publicitário

O Anexo U (versão novembro 2025) define greenwashing como qualquer prática de comunicação enganosa ou exagerada sobre supostos compromissos ambientais. Na prática para agências:

**Greenwashing explícito:**
- Usar termos como "eco", "verde", "sustentável", "natural", "limpo", "zero impacto" sem comprovação
- Exibir selos ambientais falsos ou criados pela própria empresa sem certificação de terceiros
- Afirmar que um produto é "biodegradável" sem especificar as condições necessárias para isso

**Greenwashing implícito (mais comum em marketing digital):**
- Imagens de natureza, florestas e animais em campanhas de empresas sem qualquer política ambiental
- Hashtags como #sustentável, #ecoconsciente sem correspondência na operação
- Relatórios ESG mencionados em anúncios sem referência verificável ou acessível

**Greenwashing por omissão:**
- Destacar único atributo positivo e omitir impactos negativos do ciclo de vida do produto (seleção estratégica de dados)
- Informar redução de emissões em porcentagem sem linha de base

### Implicações para Marcas Premium

Imobiliárias de luxo, clínicas e escritórios que usam sustentabilidade como diferencial estão sob escrutínio crescente:

- **Imobiliárias:** termos como "construção verde", "LEED", "eficiência energética" devem estar amparados em certificação e documentação técnica disponível ao público
- **Clínicas de estética:** claims de "produtos naturais", "orgânicos", "sem crueldade animal" exigem comprovação e, quando aplicável, certificação de entidade reconhecida
- **Escritórios de advocacia:** publicidade de prática de "ESG Advisory" deve refletir estrutura real de serviços — claims de impacto social devem ser verificáveis

> As novas diretrizes indicam maior rigor probatório do Conselho, reduzindo o espaço para discursos genéricos de sustentabilidade sem base técnica (Migalhas, nov. 2025).

---

## 7. Processo de Representação no CONAR

<!-- [MÓDULO: 2] [SUBTEMA: processo-representacao] [TIPO: processual] -->

### Quem Pode Denunciar

O CONAR recebe representações de:

1. **Consumidores** (diretamente pelo site conar.org.br) — 64,9% das representações abertas em 2024
2. **Associados** (entidades membros) — 19,5%
3. **CONAR de ofício** (iniciativa da própria Diretoria) — 11,7%
4. **Conselho Superior** — 3,9%
5. **Autoridades públicas** (podem comunicar ao CONAR, que abre de ofício)
6. **Anunciantes concorrentes** (via entidades associadas)

### Rito Processual

**Fase 1 — Recebimento e Triagem:**
- Denúncia recebida pelo CONAR
- Análise de admissibilidade: verificação de competência e pertinência ao CBAP
- Possibilidade de encaminhamento ao Núcleo Preventivo para resolução sem instauração formal

**Fase 2 — Instauração:**
- Abertura formal da representação com número de processo
- Notificação ao(s) representado(s): anunciante, agência e/ou veículo

**Fase 3 — Instrução:**
- Apresentação de defesa pelo(s) representado(s)
- Possibilidade de réplica e tréplica em casos técnicos complexos
- **Reunião de Conciliação:** tentativa de acordo entre as partes sem julgamento formal. Em 2024, foram 41 reuniões, com acordo em 13 casos.

**Fase 4 — Medida Liminar (excepcional):**
- Em casos graves, o CONAR pode deferir sustação liminar antes do julgamento (como ocorreu no caso Rep. 208/23 com o influenciador mirim)

**Fase 5 — Julgamento:**
- Realizado em sessão da Câmara competente (presencial ou virtual)
- Relator apresenta voto; conselheiros deliberam
- Voto aceito por unanimidade ou maioria

**Fase 6 — Recurso:**
- Recurso ordinário à Câmara Especial de Recursos
- Possibilidade de segunda relatora e nova deliberação

### Tipos de Decisão

| Decisão | Descrição | Consequência Prática |
|---|---|---|
| **Sustação** | Determina a imediata interrupção da veiculação | Veículo notificado para remover; plataforma pode ser acionada; ignorar = responsabilidade solidária |
| **Alteração** | Recomenda modificação específica do anúncio | Agência e anunciante devem adaptar a peça antes de nova veiculação |
| **Advertência** | Censura formal ao anunciante/agência/influenciador | Publicada no Boletim e site do CONAR; impacto reputacional |
| **Sustação + Advertência** | Combinação das duas sanções acima | Mais grave; frequente em reincidência ou violações severas |
| **Arquivamento** | Denúncia sem procedência | Anunciante absolvido; pode ser usado como precedente de boa conduta |

**Dados de 2024 (244 casos julgados):**
- 32% → advertência
- 31% → sustação
- 24% → alteração
- 13,2% → arquivamento

### Consequências Práticas de uma Condenação

1. **Publicação no Boletim do CONAR** (trimestral, distribuído às entidades associadas)
2. **Registro no site público** do CONAR (conar.org.br), com partes e decisão identificadas
3. **Pressão sobre plataformas:** Meta, Google e veículos tendem a remover conteúdo após notificação formal do CONAR
4. **Uso em processos judiciais:** decisão CONAR pode ser apresentada como elemento de boa ou má-fé em ações cíveis (Art. 16 CBAP)
5. **Risco PROCON/SENACON:** a mesma conduta pode ser objeto de processo administrativo paralelo
6. **Impacto reputacional:** marcas premium são especialmente sensíveis à associação pública com práticas publicitárias condenadas

---

## 8. Casos Emblemáticos (2023–2024)

<!-- [MÓDULO: 2] [SUBTEMA: casos-emblematicos-2023-2024] [TIPO: jurisprudência] -->

> **Nota metodológica:** Os casos abaixo constam do Boletim CONAR nº 226 (março 2025), referente a representações julgadas em fevereiro de 2024. Os números de representação são do processo original (abertos em 2023). Decisões de 2025/2026 não foram localizadas em fonte primária verificável à data de geração deste módulo.

### Caso 1 — 1991BET.COM × Influenciador Mirim (Rep. 208/23)

- **Anunciante:** 1991Bet.com e 777Max
- **Veículo/influenciador:** Perfil de influenciador menor de idade no Instagram
- **Conduta:** Divulgação de apostas de quota fixa por influenciador menor de 18 anos em stories e bio do Instagram
- **Decisão:** Sustação agravada por advertência; moção para envio ao MPF e Ministério da Fazenda
- **Fundamento:** Arts. 1, 3, 6, 37 e 50, letras "a" e "c"; Lei 14.790/23
- **Relevância digital:** Primeiro caso documentado no CONAR com envio de decisão para esfera penal em contexto de influenciador mirim; Meta forneceu resposta ao Conselho afirmando remoção do conteúdo

### Caso 2 — Galderma × Nutriex/Rennova (Rep. 094/23)

- **Anunciante:** Nutriex Imp. Exp. de Produtos Nutricionais e Farmoquímicos
- **Veículo:** Instagram (perfil da marca + perfis de influenciadoras)
- **Conduta
<span style="display:none">[^1][^10][^11][^12][^13][^14][^15][^16][^17][^18][^19][^2][^20][^21][^22][^23][^24][^25][^3][^4][^5][^6][^7][^8][^9]</span>

<div align="center">⁂</div>

[^1]: http://conar.org.br/pdf/Codigo-CONAR-2025.pdf
[^2]: http://www.conar.org.br/pdf/conar226.pdf
[^3]: http://www.conar.org.br
[^4]: https://www.gov.br/secom/pt-br/acesso-a-informacao/legislacao/ca2digobrasdeautoregulanovo.pdf
[^5]: https://www.meioemensagem.com.br/comunicacao/conar
[^6]: https://www.abrabe.org.br/wp-content/uploads/2016/09/codigo-e-anexos-2013-07-19.pdf
[^7]: https://www.meioemensagem.com.br/comunicacao/o-codigo-de-etica-publicitaria-do-conar-para-influenciadores
[^8]: http://www.conar.org.br/codigo/codigo.php
[^9]: http://www.conar.org.br/pdf/codigo-conar-2021_6pv.pdf
[^10]: https://lrilaw.com.br/2021/04/12/publicidade-por-influenciadores-digitais-recomendacoes-do-conar/
[^11]: https://tnpetroleo.com.br/noticia/publicidade-responsavel-os-6-principais-compromissos-eticos-para-2025/
[^12]: https://lrilaw.com.br/2022/09/09/conar-e-o-principio-da-identificacao-publicitaria/
[^13]: https://andreikampff.com.br/publicidade-de-apostas-e-influenciadores-restricoes-e-alcance-das-normas-vigentes/
[^14]: http://www.conar.org.br/index.php?noticias&id=1197
[^15]: http://www.conar.org.br/pdf/Codigo-CONAR-2024.pdf
[^16]: https://www.arpensp.org.br/noticia/6879
[^17]: https://www.migalhas.com.br/depeso/443596/conar-atualiza-as-regras-de-combate-ao-greenwashing
[^18]: https://modeloinicial.com.br/materia/direito-processual-acao-penal-publica-condicionada
[^19]: https://www.icict.fiocruz.br/sites/www.icict.fiocruz.br/files/Cod%20Bras%20de%20Autorregulamentacao%20Publica_Conar.pdf
[^20]: https://www.trenchrossi.com/alertas-legais/conar-anuncia-novas-regras-para-combater-o-greenwashing/
[^21]: https://trilhante.com.br/curso/acao-penal-penal/aula/representacao
[^22]: https://lrilaw.com.br/2025/03/12/regulacao-da-publicidade-de-bebidas-alcoolicas-segundo-o-conar/
[^23]: http://www.conar.org.br/pdf/271025_artogo36_anexo_u_v6.pdf
[^24]: https://www.facebook.com/comunicacao.unoesc/videos/-anexo-a-do-conar-bebidas-alco%C3%B3licas-voc%C3%AA-sabia-que-a-publicidade-de-bebidas-alc/1430987517968767/
[^25]: https://www.sinaprosp.org.br/conar-adota-novas-regras-para-coibir-greenwashing-na-publicidade/```


</content>
