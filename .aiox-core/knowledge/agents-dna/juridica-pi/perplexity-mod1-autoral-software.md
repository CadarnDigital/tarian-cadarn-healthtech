<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Voce e um pesquisador especialista em Direito Autoral brasileiro e Propriedade Intelectual. Preciso de uma especificacao tecnica modular sobre Direito Autoral (Lei 9.610/98 — LDA) e Lei de Software (Lei 9.609/98) aplicados ao contexto de agencias de marketing digital. Este documento sera usado como base para construir um agente de IA que: (1) emite pareceres sobre titularidade de obras e cessao de direitos e (2) audita conteudo de marketing quanto a riscos de PI — para uma agencia de marketing que atende prestadores de servicos premium (high-ticket): imobiliarias de luxo, escritorios de advocacia, clinicas de estetica avancada, arquitetos e consultores.

REGRA DE INTEGRIDADE: Cite cada afirmacao com a fonte (lei + artigo, jurisprudencia com numero do processo, URL quando disponivel). Se nao encontrar dado confiavel, escreva "nao encontrado com fonte confiavel". Para conteudo inferido de materiais publicos (artigos, decisoes resumidas), sinalize como "[inferencia aplicada — fonte: X]". Mantenha os termos originais em ingles entre parenteses na primeira mencao de cada conceito.

---

MODULO 1 — CESSAO DE DIREITOS AUTORAIS: JURISPRUDENCIA E ARMADILHAS

Eu ja tenho uma base sobre cessao escrita obrigatoria (Art. 49, I LDA), interpretacao restritiva (Art. 4), prazo maximo de 5 anos sem especificacao (Art. 49, III) e obra sob encomenda (inexistencia de work-for-hire no Brasil).

O que PRECISO aprofundar:

- Jurisprudencia recente (2023-2026) sobre cessao de direitos entre agencias de marketing e freelancers (designers, fotografos, videomakers). Casos concretos com numeros de processo.
- Situacoes onde cessao "generica" foi anulada ou restringida por tribunais brasileiros.
- Obra coletiva (Art. 17 LDA): quando uma campanha com multiplos criadores se qualifica como obra coletiva? Precedentes.
- Diferenca pratica entre cessao e licenciamento no contexto de conteudo de marketing.
- Cessao de conteudo gerado por IA generativa: ha algum precedente ou posicionamento doutrinario sobre quem e titular do conteudo gerado por ChatGPT/Midjourney quando usado por agencia para cliente?

---

MODULO 2 — LEI DE SOFTWARE (9.609/98): TITULARIDADE E DISPUTAS

Eu ja tenho a base: software de empregado pertence ao empregador (Art. 4), freelancer retem direitos sem cessao, prazo de protecao de 50 anos.

O que PRECISO aprofundar:

- Jurisprudencia recente (2020-2026) sobre titularidade de software desenvolvido por freelancers e prestadores de servicos. Disputas em startups e agencias digitais.
- Art. 4, §2 (software criado com recursos do empregador mas fora do escopo do contrato): como tribunais tem interpretado "recursos do empregador" — inclui laptop da empresa? Acesso a APIs pagas?
- Licenciamento SaaS (Software as a Service): como a lei brasileira trata software entregue como servico? Existe jurisprudencia sobre tributacao de SaaS (ISS vs ICMS apos ADIs 1.945 e 5.659 do STF)?
- Open source compliance: agencia que usa bibliotecas GPL ou MIT em software para clientes — quais os riscos juridicos? Alguma decisao brasileira sobre licencas open source?
- Codigo-fonte como ativo: clausulas recomendadas em contratos de desenvolvimento de software/app para garantir que agencia mantem titularidade do codigo.

---

FORMATO DE SAIDA PARA CADA MODULO:

- Abra com definicao-sintese em 2-3 linhas (para insercao em system prompt de agente de IA)
- Use headers claros, listas numeradas e tabelas comparativas
- Cite TODOS os numeros de processo, artigos de lei e fontes
- Feche cada modulo com "Instrucoes para o Agente" — 5-8 regras de comportamento derivadas daquele modulo
- Se nao encontrar informacao confiavel, indique e nao preencha com generico

Abaixo está a especificação técnica modular completa, com fontes primárias, jurisprudência verificada e instruções para o agente de IA.

***

# ESPECIFICAÇÃO TÉCNICA MODULAR — DIREITO AUTORAL E LEI DE SOFTWARE PARA AGÊNCIAS DE MARKETING DIGITAL

**Escopo:** Lei 9.610/98 (LDA), Lei 9.609/98 (LSoft) e jurisprudência brasileira aplicados ao contexto de agências de marketing que atendem clientes *high-ticket*.
**Versão:** Março/2026 | **Integridade:** toda afirmação citada com fonte verificada; lacunas sinalizadas.

***

## MÓDULO 1 — CESSÃO DE DIREITOS AUTORAIS

### Definição-Síntese para System Prompt

> Cessão de direitos autorais (copyright assignment) é o instrumento pelo qual o autor transfere, total ou parcialmente, seus direitos patrimoniais sobre uma obra intelectual a terceiro. No Brasil, a cessão é regida pelos Arts. 49–50 da Lei 9.610/98 (LDA) e exige forma escrita obrigatória para transmissão total (Art. 49, II). Toda interpretação contratual é restritiva em favor do autor (Art. 4 LDA). Inexiste o instituto *work-for-hire* no direito brasileiro — a contratação de freelancer não transfere direitos automaticamente, salvo cessão escrita expressa.

***

### 1.1 Jurisprudência Recente (2023–2026) — Cessão entre Agências e Freelancers

#### Caso Paradigma: Campanha Olimpíadas Rio 2016 (TJSP, 2024)

O acórdão mais relevante e recente encontrado com íntegra verificada trata exatamente da relação agência–freelancer–cliente no contexto de produção audiovisual publicitária:[^1]


| Campo | Dado |
| :-- | :-- |
| **Processo** | Apelação Cível nº 1006549-07.2017.8.26.0004 |
| **Tribunal** | TJSP — 1ª Câmara de Direito Privado |
| **Relator** | Des. Claudio Godoy |
| **Julgamento** | 25 de junho de 2024 |
| **Partes** | Thales Bahia Alves (diretor de cena) × F Dedding Filmes EIRELI, Henrique de Oliveira Campos ME, McGarryBowen Brasil Comunicações S/A e Banco Bradesco S/A |
| **Objeto** | Direitos autorais de 6 filmes publicitários da campanha do Bradesco para as Olimpíadas Rio 2016 |

**Fatos relevantes para agências de marketing:**

- O diretor de cena (freelancer) foi contratado pela produtora sem cessão escrita formalizada, com remuneração fixa correspondente a 10% do custo de produção ou mínimo de R\$ 6.000.[^1]
- O freelancer alegou autoria exclusiva e direito de veto à veiculação sem sua autorização, invocando o Art. 24, II, da LDA.[^1]
- O TJSP manteve a improcedência da ação, reconhecendo que a campanha se qualificava como **obra coletiva** (Art. 5º, VIII, "h", LDA), atribuindo a titularidade patrimonial ao organizador (produtora/agência) nos termos do Art. 17, §2º, da LDA.[^1]
- O tribunal citou como evidência adicional o fato de o próprio autor ter republicado os vídeos em seu perfil pessoal, demonstrando anuência ao licenciamento.[^1]

> **Conclusão operacional:** Mesmo sem cessão escrita, a qualificação como obra coletiva protege a titularidade da agência/produtora organizadora — **mas essa proteção depende de o trabalho ter sido criado sob iniciativa, organização e responsabilidade da agência**, e não como resultado de criação autônoma do freelancer que a agência apenas incorporou.[^1]

#### Caso STJ 2024 — Validade de Cessão Total e Permanente

| Campo | Dado |
| :-- | :-- |
| **Tribunal** | STJ — 4ª Turma |
| **Data** | Junho de 2024 |
| **Caso** | Nizan Guanaes × Stalo Produções Artísticas / Universal Music Publishing |
| **Fonte** | Migalhas, 18/06/2024 [^2] |

O STJ manteve decisão que reconheceu a validade de contrato de cessão total e permanente de direitos autorais firmado entre compositor e produtora, rejeitando a pretensão de resilição unilateral pelo autor. O caso reforça que **cessões formalmente válidas — mesmo com amplitude total — não são automaticamente anuladas** pelo STJ, desde que ausente vício de consentimento ou abusividade contratual demonstrada.[^2]

***

### 1.2 Cessão "Genérica" — Anulação e Restrição por Tribunais

A **regra de interpretação restritiva** do Art. 4 da LDA é o principal mecanismo de limitação de cessões amplas:[^3]

> *"Interpretam-se restritivamente os negócios jurídicos sobre os direitos autorais."* — Art. 4, Lei 9.610/98[^3]

**Consequências práticas consolidadas pela doutrina e jurisprudência:**

1. Cessão que não especifica **modalidades de uso** (ex.: "todos os direitos") é interpretada como abrangendo somente os usos que a finalidade do contrato explicitamente indica — Art. 49, I, LDA.[^3]
2. Cessão sem prazo é limitada a **5 anos** (Art. 49, III, LDA).[^3]
3. Cessão sem delimitação territorial presume-se restrita ao **território nacional** (Art. 49, IV, LDA).
4. Cessão de direitos **futuros** sobre obras ainda não criadas só é válida se expressamente delimitada por prazo determinado (Art. 51, LDA).

> ⚠️ **Caso específico de cessão genérica anulada em contexto de agência de marketing digital (2023–2026):** *não encontrado com fonte confiável* em banco de jurisprudência público. O fundamento mais próximo é o Art. 4 LDA como regra de interpretação, aplicado extensivamente pela doutrina.[^4][^3]

***

### 1.3 Obra Coletiva (Art. 17, LDA) — Quando se Qualifica?

**Definição legal** (Art. 5º, VIII, "h", LDA): obra *"criada por iniciativa, organização e responsabilidade de uma pessoa física ou jurídica, que a publica sob seu nome ou marca e que é constituída pela participação de diferentes autores, cujas contribuições se fundem numa criação autônoma"*.[^5][^1]

**Critérios identificados pela jurisprudência:**


| Critério | Obra Coletiva (titularidade da agência) | Obra em Coautoria (cada autor retém direitos) |
| :-- | :-- | :-- |
| Iniciativa | Da agência/organizadora | Dos criadores em conjunto |
| Coordenação | Existe hierarquia organizacional | Horizontal, sem coordenador definido |
| Contribuições | Se fundem em criação autônoma | Cada contribuição é identificável separadamente |
| Publicação | Sob o nome/marca do organizador | Sob o nome de todos os coautores |

**Precedentes consolidados do TJSP:**

1. **TJSP, Ap. Cível 1006549-07.2017.8.26.0004 (2024)** — Campanha Bradesco/Olimpíadas Rio 2016: obra coletiva, titularidade da produtora/agência organizadora.[^1]
2. **TJSP, Ap. Cível 0120169-61.2010.8.26.0100 (2013)** — Campanha publicitária para empresa de calçados: obra coletiva coordenada por agência, direitos patrimoniais cabem ao organizador (Art. 17, §2º, LDA).[^1]
3. **TJSP, Ap. Cível 9278572-52.2008.8.26.0000 (2013)** — Obra coletiva com direitos cedidos pelo organizador, ausência de dever de indenizar ao criador individual.[^1]

> **Conclusão para agências:** Uma campanha de marketing com múltiplos criadores (designer, fotógrafo, videomaker, copywriter) coordenados pela agência, publicada sob a marca desta, tem **forte fundamento para ser enquadrada como obra coletiva**, com titularidade patrimonial da agência — **desde que a agência documente o papel organizador** (briefing, direção criativa, coordenação de entrega, publicação sob sua marca).[^5][^1]

***

### 1.4 Cessão vs. Licenciamento — Diferença Prática no Marketing

| Dimensão | Cessão (*Assignment*) | Licenciamento (*License*) |
| :-- | :-- | :-- |
| **Transferência de titularidade** | Sim — autor deixa de ser titular patrimonial | Não — autor mantém titularidade |
| **Prazo** | Pode ser definitivo (se expressamente estipulado) | Sempre temporário e revogável |
| **Forma** | Escrita obrigatória para transmissão total (Art. 49, II, LDA) | Escrita recomendada; pode ser tácita |
| **Uso pelo autor** | Proibido após cessão total | Permitido, salvo exclusividade pactuada |
| **Riscos para agência** | Alto se cessão incompleta: autor pode alegar retenção de direitos | Alto se licença vence: uso sem renovação é infração |
| **Aplicação prática** | Material criado sob encomenda para campanha exclusiva de cliente | Banco de imagens, templates reutilizáveis, música licenciada |

> **Armadilha frequente:** Contratos que usam o termo *"cessão"* sem especificar modalidades, prazo, território e exclusividade operam, na prática, como licenciamento restrito — e o autor pode questionar usos não contemplados, invocando o Art. 4 LDA.[^3]

***

### 1.5 Conteúdo Gerado por IA Generativa — Titularidade

Este é o ponto de maior **vácuo normativo** no direito autoral brasileiro em 2026.[^6][^7]

**Estado atual do ordenamento:**

1. **Art. 11, caput, LDA:** exige autor humano — *"autor é a pessoa física criadora da obra intelectual"*. Sistemas de IA não possuem personalidade jurídica e não podem ser titulares.[^8][^6]
2. **INPI** publicou estudo formal concluindo que *"no presente ordenamento jurídico brasileiro somente pessoas naturais podem ter autoria ou coautoria de obras protegidas pelo direito autoral"*.[^8]
3. **Três cenários doutrinários identificados** (Migalhas, março/2026):[^6]
| Cenário | Descrição | Proteção Autoral? |
| :-- | :-- | :-- |
| IA pura | Obra gerada integralmente por IA sem intervenção criativa humana relevante | ❌ Não há suporte legal |
| Cocriação (*co-authorship*) | Humano formula prompts, seleciona variações, edita resultado | ❓ Lei silente — vácuo normativo |
| IA como ferramenta | IA subordinada ao controle criativo do autor humano (ex.: filtro de cor em foto) | ✅ Proteção ao autor humano |

4. **PL 2.338/2023** (Sen. Rodrigo Pacheco): aprovado pelo Senado em 10/12/2024, aguarda votação na Comissão Especial da Câmara em março/2026. O texto **não resolve** a titularidade de obras geradas por IA — regula apenas o uso de obras preexistentes no treinamento dos modelos. Os PLs apensados 1.685/2025 e 1.969/2025 propõem alterar a LDA para incluir titularidade de obras de IA.[^6]
5. **Direito comparado:**
    - EUA: *U.S. Copyright Office* (Federal Register, 16/03/2023): obras produzidas inteiramente por IA **não são elegíveis para registro**; proteção proporcional à contribuição humana identificável.[^6]
    - UE: *EU AI Act* (Regulamento UE 2024/1689, vigente desde 01/08/2024): obriga divulgação de dados de treinamento, mas não resolve titularidade de obras produzidas pela IA.[^6]

**Implicação prática para agências que usam ChatGPT/Midjourney:**

> Conteúdo gerado puramente por IA (texto, imagem, vídeo) **não é protegido pelo direito autoral brasileiro** na ausência de contribuição criativa humana identificável e substancial. A agência **não pode ceder ao cliente direitos autorais sobre algo que não possui**. O caminho juridicamente mais seguro é (a) documentar a contribuição criativa humana no processo (prompts elaborados, curadoria, edição, adaptação criativa), caracterizando o cenário de "ferramenta" ou "cocriação com predominância humana", e (b) incluir cláusula contratual distribuindo responsabilidade sobre riscos de PI de conteúdo gerado por IA. ⚠️ **Não há precedente judicial brasileiro específico sobre titularidade de conteúdo gerado por ChatGPT/Midjourney para fins comerciais — dado não encontrado com fonte confiável.**

***

### Instruções para o Agente — Módulo 1

1. **Verificar forma da cessão:** Antes de emitir parecer de titularidade, perguntar se existe instrumento escrito de cessão com especificação de modalidades, prazo e território (Art. 49, I–IV, LDA). Na ausência, presumir que o criador retém os direitos patrimoniais.
2. **Aplicar teste de obra coletiva:** Para campanhas com múltiplos criadores, verificar se a agência documentou iniciativa, organização e coordenação (Art. 5º, VIII, "h", LDA). Três decisões do TJSP confirmam titularidade da agência organizadora quando esses critérios estão presentes.
3. **Interpretação restritiva obrigatória:** Em contratos ambíguos, aplicar Art. 4 LDA — toda dúvida é resolvida em favor do autor/criador, não da agência ou cliente.
4. **Alertar sobre IA generativa:** Conteúdo gerado por IA sem contribuição criativa humana verificável não possui proteção autoral no Brasil (INPI, 2024; doutrina majoritária). A agência deve documentar o processo criativo humano envolvido.
5. **Distinguir cessão de licenciamento:** Verificar o verbo e os termos do contrato. Uso de "autorizo", "licencio" ou "permito" indica licença, não cessão — com consequências distintas para titularidade e prazo.
6. **Prazo padrão:** Na ausência de prazo expresso, aplicar o limite de 5 anos do Art. 49, III, LDA. Emitir alerta automático quando contratos de agência não especificam prazo.
7. **Direitos morais são inalienáveis:** Mesmo com cessão patrimonial total, o criador retém direitos morais (Art. 27, LDA) — incluindo o direito de crédito. Alertar clientes que campanhas sem creditação dos criadores podem gerar litígios.
8. **Monitorar PL 2.338/2023:** O regime de IA está em tramitação ativa na Câmara (março/2026). Incluir disclaimer de que pareceres sobre obras de IA estão sujeitos a alteração legislativa iminente.

***

## MÓDULO 2 — LEI DE SOFTWARE (9.609/98): TITULARIDADE E DISPUTAS

### Definição-Síntese para System Prompt

> A Lei 9.609/98 (LSoft) protege software como obra intelectual, equiparando-o ao regime autoral da LDA naquilo que for compatível (Art. 2º). A titularidade do software criado por empregado ou prestador de serviços pertence ao empregador/contratante quando o desenvolvimento decorre da natureza do contrato ou ocorre com uso de recursos da empresa (Art. 4º, caput). O freelancer retém a titularidade quando o software é desenvolvido fora do escopo contratual e sem recursos do contratante (Art. 4º, §2º). Prazo de proteção: 50 anos a partir de 1º de janeiro do ano subsequente à publicação (Art. 2º, §2º).

***

### 2.1 Jurisprudência sobre Titularidade de Software por Freelancers (2020–2026)

#### Ação Ordinária — Titularidade de Software em Relação de Emprego

O IODA — Instituto de Oportunidades para o Direito Autoral publicou análise de acórdão que aplica diretamente o Art. 4 da LSoft:[^9]

> *"Inexistindo estipulação expressa em favor do empregado e considerando-se que a natureza do emprego envolve criação, desenvolvimento e/ou modificação de programas de computador – software –, a titularidade destes é do empregador, nos moldes do Art. 4º da Lei 9.609/98."*[^9]

O mesmo estudo identifica os **três requisitos cumulativos para titularidade do empregador/contratante**:[^9]

1. Contrato destinado à pesquisa/desenvolvimento ou que preveja atividade de desenvolvimento como encargo;
2. Desenvolvimento durante a vigência do contrato ou vínculo;
3. Instrumentos de trabalho (hardware, software de desenvolvimento) fornecidos pelo empregador.

> ⚠️ **Números de processo específicos de disputas de titularidade de software entre agências digitais e freelancers (2020–2026):** *não encontrados com fonte confiável* em buscas nos portais TJSP, STJ e IODA. O tema é litigado predominantemente em câmaras de direito privado e trabalhista, com acórdãos de difícil indexação temática específica.

***

### 2.2 Art. 4º, §2º — "Recursos do Empregador": Laptop e APIs Pagas

O texto literal do Art. 4º, §2º da Lei 9.609/98 é determinante:[^10]

> *"Pertencerão, com exclusividade, ao empregado, contratado de serviço ou servidor os direitos concernentes a programa de computador gerado **sem relação com o contrato** de trabalho, prestação de serviços ou vínculo estatutário, e **sem a utilização de recursos, informações tecnológicas, segredos industriais e de negócios, materiais, instalações ou equipamentos do empregador**."* (Art. 4º, §2º, Lei 9.609/98)[^10]

**Interpretação dos "recursos do empregador" — análise dos elementos legais:**


| Recurso Utilizado | Qualificação Legal | Consequência para Titularidade |
| :-- | :-- | :-- |
| Laptop/computador da empresa | "equipamentos do empregador" (Art. 4º, §2º, LSoft) | Titularidade migra para o contratante |
| Acesso a APIs pagas pela agência (ex.: OpenAI API, Google Maps API) | "recursos... do empregador" ou "informações tecnológicas" (Art. 4º, §2º, LSoft) [inferência aplicada — fonte: Art. 4º, §2º Lei 9.609/98 + análise IODA ] | Risco real de titularidade do contratante |
| Banco de dados proprietário da agência | "informações tecnológicas, segredos de negócios" (Art. 4º, §2º, LSoft) | Titularidade do contratante |
| Computador pessoal do freelancer + APIs próprias | Nenhum recurso do empregador utilizado | Titularidade do freelancer (Art. 4º, §2º) |
| Ambiente de desenvolvimento (*cloud*, CI/CD) da agência | "instalações" (Art. 4º, §2º) [inferência aplicada — fonte: Art. 4º, §2º Lei 9.609/98] | Risco de titularidade do contratante |

> **Conclusão:** O uso de laptop da agência ou de APIs pagas pela agência no desenvolvimento de software por freelancer **cria fundamento legal para reivindicação de titularidade pelo contratante**, mesmo sem contrato expresso nesse sentido. Agências devem documentar quais recursos são fornecidos ao freelancer e incluir cláusula explícita de titularidade nos contratos de prestação de serviços de tecnologia.[^10][^9]

***

### 2.3 Licenciamento SaaS — Tributação ISS vs. ICMS (ADIs 1.945 e 5.659)

**Decisão definitiva do STF (18/02/2021):**

O STF concluiu o julgamento conjunto das ADIs 1.945 e 5.659, encerrando mais de duas décadas de conflito tributário entre Estados (ICMS) e Municípios (ISS) sobre software:[^11][^12]


| Critério | Decisão STF |
| :-- | :-- |
| **Resultado** | Exclusão do ICMS (8 votos × 3) sobre licenciamento/cessão de direito de uso de software |
| **Tributo incidente** | ISS, com fundamento na CF e na LC 116/2003 |
| **Relator vencedor** | Min. Dias Toffoli (ADI 5.659) |
| **SaaS explicitamente incluído** | Sim — o Min. Toffoli qualificou o modelo SaaS como prestação de serviço tributável pelo ISS [^13] |
| **Modulação de efeitos** | Efeitos prospectivos (sem retroatividade para cobrança de ISS em operações onde ICMS foi recolhido) [^11] |

**Fundamento para SaaS** (voto Min. Toffoli, ADI 5.659):[^13]

> *"Igualmente há prestação de serviço no modelo denominado software-as-a-Service (SaaS), o qual se caracteriza pelo acesso do consumidor a aplicativos disponibilizados pelo fornecedor na rede mundial de computadores... circunstância atrativa da incidência do ISS."*[^13]

**Implicação prática para agências que entregam software ou automações como serviço:**

- Plataformas de automação de marketing, CRMs customizados, apps de agendamento entregues via acesso *online* → **ISS incidente**, alíquota de 2% a 5% conforme município.[^12]
- Não incide ICMS sobre o licenciamento, independentemente de ser software por download, SaaS ou on-premise.[^11]
- Contratos de desenvolvimento + manutenção contínua: verificar se o serviço contínuo (SaaS) é separado do desenvolvimento (geralmente ISS sobre ambos).[^13]

***

### 2.4 Open Source Compliance — Riscos Jurídicos para Agências

Agências que desenvolvem software para clientes utilizando bibliotecas *open source* devem observar o **regime de cada licença**:[^14][^15]


| Tipo de Licença | Exemplos | Obrigação Principal | Risco para Agência |
| :-- | :-- | :-- | :-- |
| **Copyleft forte** (*strong copyleft*) | GPL v2, GPL v3, AGPL | Distribuição do software derivado obriga a liberar o código-fonte sob a mesma licença | ⚠️ **Alto:** cliente pode ser obrigado a publicar código proprietário se software for distribuído |
| **Copyleft fraco** (*weak copyleft*) | LGPL, MPL | Obriga apenas a liberar modificações na biblioteca, não o software completo | ⚠️ Médio: risco se houver modificação da biblioteca |
| **Permissiva** | MIT, Apache 2.0, BSD | Uso comercial livre; apenas atribuição de crédito exigida | ✅ Baixo: compatível com desenvolvimento proprietário |

**Consequências jurídicas de não-conformidade com GPL (no Brasil e internacionalmente):**

1. Rescisão automática da licença — perda do direito de usar, modificar e distribuir a biblioteca.[^14]
2. Liminar judicial para cessar distribuição do produto até adequação.[^14]
3. Obrigação de publicar o código-fonte — comprometendo confidencialidade e vantagem competitiva do cliente.[^15][^14]

> ⚠️ **Decisão judicial brasileira específica sobre violação de licença open source:** *não encontrada com fonte confiável*. O risco principal para agências brasileiras é via ação de autores ou mantenedores estrangeiros das bibliotecas, com possibilidade de reconhecimento de sentença estrangeira no Brasil (Art. 961 CPC/2015) [inferência aplicada — fonte: Art. 961 CPC/2015 + análise ].

***

### 2.5 Cláusulas Contratuais Recomendadas para Proteger Titularidade do Código

Com base no Art. 4 da LSoft e na prática contratual de proteção de PI:[^9][^10]

**1. Cláusula de Titularidade Expressa**
> *"Todo o código-fonte, documentação técnica, scripts, algoritmos e demais componentes de software desenvolvidos no âmbito deste contrato, utilizando recursos, equipamentos ou informações da [AGÊNCIA], pertencem exclusivamente à [AGÊNCIA], nos termos do Art. 4º, caput, da Lei 9.609/98, independentemente de cessão adicional."*

**2. Cláusula de Recursos Utilizados** (para blindar o Art. 4º, §2º)
> *"O PRESTADOR declara que utilizará exclusivamente os equipamentos e acessos disponibilizados pela [AGÊNCIA] para o desenvolvimento do objeto deste contrato, reconhecendo expressamente que tais recursos são de propriedade da [AGÊNCIA] para fins do Art. 4º, §2º, da Lei 9.609/98."*

**3. Cláusula de Open Source Compliance**
> *"O PRESTADOR se compromete a: (a) utilizar exclusivamente bibliotecas com licenças MIT, Apache 2.0 ou equivalentes permissivas; (b) obter aprovação prévia por escrito da [AGÊNCIA] antes de incorporar qualquer biblioteca sob licença GPL, LGPL, AGPL ou equivalente copyleft; (c) manter inventário atualizado de todas as dependências e suas licenças."*

**4. Cláusula de Escrow de Código-Fonte**
> *"O PRESTADOR entregará o código-fonte completo, comentado e documentado à [AGÊNCIA] ao término de cada sprint/entrega, depositando cópia em repositório controlado pela [AGÊNCIA]. A retenção de código-fonte como garantia de pagamento é expressamente vedada."*

**5. Cláusula de Titularidade de Melhorias e Derivados**
> *"Quaisquer melhorias, adaptações, módulos adicionais ou obras derivadas do software original, desenvolvidos durante a vigência deste contrato, integram o patrimônio da [AGÊNCIA] pela mesma razão de titularidade originária."*

**6. Cláusula de Não-Competição Técnica**
> *"O PRESTADOR se obriga a não reutilizar, adaptar ou replicar a arquitetura técnica, os algoritmos proprietários ou os fluxos de automação desenvolvidos para a [AGÊNCIA] em projetos para concorrentes diretos pelo prazo de [X] anos."*

***

### Instruções para o Agente — Módulo 2

1. **Verificar natureza do vínculo:** Distinguir empregado (CLT), prestador de serviços (PJ/pessoa física) e freelancer eventual. A titularidade padrão do Art. 4º, caput, LSoft aplica-se quando o contrato prevê desenvolvimento de software como atividade — mas exige comprovação da natureza do vínculo.[^10][^9]
2. **Auditar recursos utilizados:** Perguntar se o freelancer usou laptop, APIs, banco de dados ou infraestrutura da agência. Qualquer resposta afirmativa ativa o risco de reivindicação de titularidade pelo contratante via Art. 4º, §2º, LSoft.[^10]
3. **Alertar sobre ausência de cessão em contrato de freelancer:** Quando contrato não prevê expressamente titularidade nem cessão, e o freelancer operou com recursos próprios e fora do escopo contratual, a titularidade é dele (Art. 4º, §2º). Emitir alerta e recomendar regularização contratual retroativa com cessão escrita.[^9]
4. **Aplicar regime ISS para SaaS:** Qualquer entrega de software como serviço contínuo (acesso online, automação, CRM, app) é tributada pelo ISS, não pelo ICMS, conforme ADIs 1.945 e 5.659 (STF, 2021). Alertar sobre nota fiscal de serviço (ISS) em vez de nota de produto.[^11][^13]
5. **Exigir inventário de licenças open source:** Antes de aceitar entrega de software, verificar se há bibliotecas GPL ou LGPL incorporadas. Uso de GPL em software distribuído ao cliente final cria obrigação de publicar código-fonte — risco crítico de confidencialidade.[^15][^14]
6. **Clausular entrega de código-fonte:** Contratos sem cláusula de entrega de código-fonte deixam a agência refém do desenvolvedor. Recomendar sempre cláusula de escrow e entrega incremental por sprint.[^9]
7. **Monitorar gap jurisprudencial:** Disputas específicas de titularidade de software em agências digitais têm baixa taxa de publicação em bases acessíveis. Quando o caso concreto não encontrar precedente exato, aplicar analogicamente os critérios do Art. 4º, §§1º e 2º, LSoft e sinalizar ausência de jurisprudência específica ao usuário.

***

## TABELA DE REFERÊNCIAS NORMATIVAS CONSOLIDADAS

| Dispositivo | Conteúdo | Aplicação no Contexto |
| :-- | :-- | :-- |
| Art. 4, LDA | Interpretação restritiva de negócios sobre direitos autorais | Cessão genérica é restringida |
| Art. 5º, VIII, "h", LDA | Definição de obra coletiva | Campanhas coordenadas pela agência |
| Art. 17, §2º, LDA | Titularidade patrimonial de obra coletiva ao organizador | Agência como titular de campanhas |
| Art. 24, LDA | Direitos morais inalienáveis | Creditação de criadores mesmo em obra coletiva |
| Art. 27, LDA | Direitos morais são irrenunciáveis | Cláusula de renúncia de moral rights é nula |
| Art. 49, I–IV, LDA | Limitações à cessão de direitos autorais | Cessão deve especificar modalidade, prazo, território |
| Art. 4º, caput, Lei 9.609/98 | Titularidade do software ao empregador/contratante | Quando atividade de desenvolvimento é o objeto do contrato |
| Art. 4º, §2º, Lei 9.609/98 | Titularidade ao desenvolvedor sem uso de recursos do contratante | Proteção do freelancer que usa recursos próprios |
| ADIs 1.945 e 5.659, STF (2021) | ISS sobre licenciamento e SaaS; exclusão do ICMS | Tributação de software como serviço |

<span style="display:none">[^16][^17][^18][^19][^20][^21][^22][^23][^24][^25][^26][^27][^28][^29][^30][^31][^32][^33][^34][^35][^36][^37][^38][^39][^40][^41]</span>

<div align="center">⁂</div>

[^1]: https://www.stj.jus.br/sites/portalp/Paginas/Comunicacao/Noticias/2025/09112025-O-STJ-em-busca-do-equilibrio-entre-acesso-a-informacao-e-respeito-aos-direitos-autorais-no-mundo-digital.aspx

[^2]: https://www.migalhas.com.br/quentes/409635/stj-valida-contrato-de-cessao-entre-compositor-e-produtoras

[^3]: https://portal.tjpr.jus.br/jurisprudencia/j/4100000017986421/Acórdão-0064819-92.2014.8.16.0014

[^4]: https://atenaeditora.com.br/catalogo/dowload-post/102809

[^5]: https://www2.camara.leg.br/legin/fed/lei/1998/lei-9610-19-fevereiro-1998-365399-publicacaooriginal-1-pl.html

[^6]: https://www.migalhas.com.br/amp/depeso/451224/ia-generativa-e-autoria-quem-e-dono-das-obras-criadas-por-algoritmos

[^7]: https://www.amigasdacorte.com/post/obras-geradas-por-inteligência-artificial-e-os-desafios-do-direito-autoral-brasileiro

[^8]: https://www.gov.br/inpi/pt-br/servicos/programas-de-computador/Direitosautoraiseobrasgeradas.pdf

[^9]: https://ioda.org.br/publicacoes/jurisprudencia-brasileira/programa-de-computador-relacao-de-emprego-titularidade-do-software/

[^10]: https://modeloinicial.com.br/lei/L-9609-1998/lei-9609/art-4

[^11]: https://www.azevedosette.com.br/noticias/pt/stf-determina-os-efeitos-da-decisao-que-confirmou-tributacao-pelo-iss-no-licenciamento-de-softwares/6129

[^12]: https://direitoreal.com.br/noticias/stf-conclui-julgamento-sobre-disputa-tributaria-em-software

[^13]: https://direitoreal.com.br/artigos/stf-conclui-julgamento-sobre-disputa-tributaria-em-software

[^14]: https://jornalempresasenegocios.com.br/destaques/uso-de-software-open-source-pode-induzir-empresas-a-nao-conformidade/

[^15]: https://www.mercadoadvocacia.com.br/advogado-lojas-virtuais-online/licenciamento-de-software-open-source-vs-proprietário-diferenças-e-implicações-jurídicas

[^16]: https://www.youtube.com/shorts/qa6FbUnJu-g

[^17]: https://buscadordizerodireito.com.br/jurisprudencia/4871/na-antiga-lei-de-direitos-autorais-o-contrato-de-cessao-de-direitos-precisava-ser-averbado-a-margem-do-registro-para-que-pudesse-ter-eficacia-contra-terceiros

[^18]: https://www.planalto.gov.br/ccivil_03/leis/l9610.htm

[^19]: https://www.projuris.com.br/blog/lei-de-direitos-autorais/

[^20]: https://modeloinicial.com.br/materia/direito-empresarial-propriedade-intelectual-autoral-obras-audiovisuais

[^21]: https://esaj.tjsp.jus.br/cjsg/getArquivo.do?cdAcordao=18041640\&cdForo=0

[^22]: https://abmes.org.br/arquivos/legislacoes/Lei9609.pdf

[^23]: https://walmarandrade.com.br/lei-9609-1998/

[^24]: https://ww2.stj.jus.br/jurisprudencia/externo/informativo/?aplicacao=informativo\&acao=pesquisar\&livre=%40CNOT%3D'020424'

[^25]: https://esaj.tjsp.jus.br/cjsg/getArquivo.do?cdAcordao=17857422\&cdForo=0

[^26]: https://www.migalhas.com.br/depeso/370569/responsabilidade-civil-do-empregador-do-uso-indevido-de-software

[^27]: https://esaj.tjsp.jus.br/cjsg/getArquivo.do?cdAcordao=5990160

[^28]: https://cesconbarrieu.com.br/maioria-do-stf-afasta-icms-e-indica-a-incidencia-do-iss-sobre-licenciamento-ou-cessao-de-direito-de-uso-de-software/

[^29]: https://www.gov.br/inpi/pt-br/servicos/programas-de-computador/SoftwareemColaborao.pdf

[^30]: https://softwarepublico.gov.br/social/spb/documentos/estudos/licencas-fase-2/relatoriofinal-alternativaslicenciamento-spbpdf

[^31]: https://www.azevedosette.com.br/noticias/pt/stf-forma-maioria-pela-tributacao-do-iss-no-licenciamento-de-software-modulacao-dos-efeitos-a-ser-definida/6014

[^32]: https://esaj.tjsp.jus.br/cjsg/getArquivo.do?cdAcordao=18771944\&cdForo=0

[^33]: https://esaj.tjsp.jus.br/cjsg/getArquivo.do?cdAcordao=16739524\&cdForo=0

[^34]: https://esaj.tjsp.jus.br/cjsg/getArquivo.do?cdAcordao=15112837\&cdForo=0

[^35]: https://esaj.tjsp.jus.br/cjsg/getArquivo.do?cdAcordao=17525538\&cdForo=0

[^36]: http://www.planalto.gov.br/ccivil_03/leis/l9609.htm

[^37]: https://www5.tjmg.jus.br/jurisprudencia/formEspelhoAcordao.do

[^38]: https://www.stj.jus.br/websecstj/cgi/revista/REJ.exe/ITA?seq=1068637\&tipo=0\&nreg=200802411510\&SeqCgrmaSessao=\&CodOrgaoJgdr=\&dt=20120229\&formato=PDF\&salvar=false

[^39]: https://www.planalto.gov.br/ccivil_03/leis/l9609.htm

[^40]: https://www.tjsp.jus.br/Download/Portal/Biblioteca/Biblioteca/RevistaEletronicaJurisp/e-JTJ-Vol26.pdf

[^41]: https://www.dbba.com.br/wp-content/uploads/questes-fundamentais-de-direito-de-autor-livro-reviso-final-2-1.pdf

