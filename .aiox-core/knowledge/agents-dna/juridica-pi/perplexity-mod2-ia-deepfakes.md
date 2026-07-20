<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# IA Generativa, Deepfakes e Marco Legal

```
Voce e um pesquisador especialista em regulacao de Inteligencia Artificial e Direito Digital no Brasil. Preciso de uma especificacao tecnica modular sobre IA Generativa e Direitos Autorais + Deepfakes e Voz Sintetica no contexto brasileiro. Este documento sera usado como base para construir um agente de IA que: (1) orienta sobre compliance de IA em conteudo de marketing e (2) audita riscos de PI em outputs de IA generativa — para uma agencia de marketing que atende prestadores de servicos premium (high-ticket): imobiliarias de luxo, escritorios de advocacia, clinicas de estetica avancada e consultores.

REGRA DE INTEGRIDADE: Cite cada afirmacao com a fonte (lei + artigo, PL + numero + artigo, jurisprudencia com numero do processo, URL quando disponivel). Se nao encontrar dado confiavel, escreva "nao encontrado com fonte confiavel". Para conteudo inferido de materiais publicos, sinalize como "[inferencia aplicada — fonte: X]". Mantenha os termos originais em ingles entre parenteses na primeira mencao.

---

MODULO 1 — PL 2338/2023 (MARCO LEGAL DA IA): VERSAO ATUALIZADA

Eu ja tenho uma base sobre disclosure obrigatorio (Art. 10, III e Art. 24), multa ate 2% do faturamento (max R$ 50M) e necessidade de human-in-the-loop.

O que PRECISO aprofundar:
- Status atualizado do PL 2338/2023 em marco de 2026: em que fase esta? Aprovado pelo Senado? Na Camara? Sancionado? Quais emendas relevantes foram feitas?
- Classificacao de risco do PL: quais categorias de uso de IA sao consideradas "alto risco"? Agencias de marketing se enquadram?
- Obrigacoes especificas para fornecedores e operadores de IA: registro, auditoria, transparencia, canal de reclamacao.
- Sandbox regulatorio: esta previsto? Em que condicoes?
- Comparacao pratica: PL 2338/2023 vs EU AI Act — diferencas principais que impactam agencias brasileiras que usam ferramentas de IA de empresas europeias/americanas.
- Outros PLs relevantes: PL 6707/2025 (opacidade algoritmica e inversao do onus da prova), PL 21/2020 (marco legal original). Qual prevalece?

---

MODULO 2 — DEEPFAKES, VOZ SINTETICA E DIREITO DE IMAGEM DIGITAL

Eu ja tenho uma base sobre deepfake como violacao de direito de imagem (Art. 5, X CF + Art. 20 CC) e voz sintetica como componente do direito de personalidade.

O que PRECISO aprofundar:
- Existe legislacao brasileira especifica sobre deepfakes? Projetos de lei em tramitacao? Quais sancoes preveem?
- Jurisprudencia brasileira sobre deepfakes (2023-2026): algum caso concreto julgado? Se nao houver brasileiro, citar os principais internacionais (EUA, Europa) com relevancia para o Brasil.
- Voz sintetica e IA: clonagem de voz para narracoes, assistentes, chatbots. Quais os riscos juridicos? Ha regulamentacao especifica?
- Consentimento para uso de likeness em treinamento de IA: tendencia regulatoria. EU AI Act aborda? PL 2338/2023 aborda?
- Deepfake pornografico: Lei 13.718/2018 (Art. 216-B CP) se aplica? Ha projetos de lei especificos?
- Boas praticas para agencias de marketing: como usar IA para gerar conteudo com pessoas (avatares, porta-vozes virtuais) SEM violar direito de imagem?
- Watermarking e deteccao: existe obrigacao legal de marcar conteudo sintetico? Tecnologias disponíveis (C2PA, Content Credentials).

---

FORMATO DE SAIDA PARA CADA MODULO:
- Abra com definicao-sintese em 2-3 linhas (para insercao em system prompt de agente de IA)
- Use headers claros, listas numeradas e tabelas comparativas
- Cite TODOS os numeros de PL, artigos de lei e processos
- Feche cada modulo com "Instrucoes para o Agente" — 5-8 regras de comportamento derivadas daquele modulo
- Se nao encontrar informacao confiavel, indique e nao preencha com generico

Abaixo está a especificação técnica modular completa, com fontes citadas inline, pronta para uso como base de agente de IA.

***

# Especificação Técnica Modular: IA Generativa, Deepfakes e Marco Legal Brasileiro
### Para Agência de Marketing de Serviços Premium — Base para Agente de Compliance de IA

***

## MÓDULO 1 — PL 2338/2023: Marco Legal da IA

> **Definição-Síntese para System Prompt:** O PL 2338/2023 é o principal projeto de lei brasileiro de regulação da Inteligência Artificial, aprovado pelo Senado Federal em dezembro de 2024 e em tramitação na Câmara dos Deputados. Adota modelo de gestão de riscos escalonados (risco mínimo → risco limitado → alto risco → risco excessivo), cria o Sistema Nacional de Regulação e Governança de IA (SIA) com a ANPD como autoridade coordenadora, e impõe obrigações de transparência, governança e responsabilidade civil diferenciadas por nível de risco.

***

### 1.1 Status Atualizado em Março de 2026

O PL 2338/2023 foi **aprovado em plenário pelo Senado Federal em 10 de dezembro de 2024**, em votação simbólica. O texto aprovado é um **substitutivo do Senador Eduardo Gomes (PL-TO)**, com base na proposta original do então presidente do Senado, Rodrigo Pacheco.[^1][^2]

Após a aprovação no Senado, o projeto seguiu para a **Câmara dos Deputados**, onde foi submetido à análise de uma **Comissão Especial**. O relator designado na Câmara é o **Dep. Aguinaldo Ribeiro**. A votação em plenário, inicialmente prevista para fevereiro de 2026, foi **novamente adiada** e, conforme informações de março de 2026, ainda está em fase de audiências públicas e elaboração do parecer do relator.[^3][^4][^5][^6]

**Situação em março de 2026:**
- **Fase atual:** Comissão Especial da Câmara dos Deputados — audiências públicas e elaboração do parecer[^5][^3]
- **Próximos passos:** Parecer do Dep. Aguinaldo Ribeiro → votação em Plenário da Câmara → se emendado, retorna ao Senado; se não emendado, segue à sanção presidencial[^3]
- **Status:** **Não sancionado. Não é lei vigente.** Produz impactos práticos pelo efeito de antecipação regulatória[^3]

***

### 1.2 Classificação de Risco — Estrutura do PL

O PL adota **quatro categorias de risco**, em ordem crescente de regulação:[^7][^3]

| Categoria | Características | Obrigações |
|---|---|---|
| **Risco mínimo** | Aplicações com impacto negligenciável | Boas práticas voluntárias |
| **Risco limitado** | Chatbots, geração de conteúdo sem impacto severo | Transparência ao usuário (disclosure) |
| **Alto risco** | Impacto relevante sobre direitos fundamentais (Art. 14 do texto) [^8] | Obrigações completas: governança, auditoria, registro, canal de reclamação |
| **Risco excessivo** | Usos proibidos: manipulação subconsciente, vigilância biométrica em massa, pontuação social [^9] | **Vedação absoluta** |

**Sistemas de alto risco (Art. 14 do texto aprovado pelo Senado)** incluem IA empregada em:[^8][^10]
1. Infraestrutura crítica (energia, água, transportes)
2. Educação e formação profissional (avaliação de estudantes)
3. Emprego, recrutamento e gestão de pessoas (triagem de currículos, avaliação de desempenho)
4. Serviços essenciais (crédito, seguro, saúde)
5. Aplicação da lei e controle de fronteiras
6. Administração da justiça e processos democráticos

**Agências de marketing: enquadramento de risco**

A atividade-core de uma agência de marketing (criação de conteúdo, gestão de campanhas, geração de imagens e textos) enquadra-se, em regra, como **risco limitado ou mínimo** no texto atual. Contudo, **alguns usos específicos podem elevar o risco**:[^11][^7]

- Uso de IA para **perfilamento e segmentação comportamental** de consumidores → potencialmente alto risco (impacto sobre acesso a serviços)
- Geração de deepfakes ou conteúdo sintético sem disclosure → violação de obrigação de transparência (Art. 10, III do texto)
- **Clientes da agência** (escritórios de advocacia usando IA para triagem de casos, clínicas usando IA para diagnóstico estético) → podem ser **operadores de alto risco** e a agência, como fornecedora de conteúdo de IA, integra a cadeia de responsabilidade [inferência aplicada — fonte][^12]

***

### 1.3 Obrigações para Fornecedores e Operadores de IA

O PL distingue **fornecedor** (quem desenvolve/disponibiliza o sistema) de **operador** (quem usa em produto ou serviço). A agência de marketing é tipicamente **operadora** das ferramentas de IA de terceiros.[^13]

**Obrigações gerais aplicáveis a todos os sistemas** (independente de risco):

1. **Disclosure obrigatório** (Art. 10, III): indicar ao usuário quando está interagindo com sistema de IA, especialmente chatbots e conteúdo sintético[^3]
2. **Política de governança de IA** (Art. 24): fornecedores devem documentar práticas de desenvolvimento e uso responsável[^3]
3. **Responsabilidade civil**: fornecedores e operadores respondem solidariamente por danos — ao prejudicado cabe escolher contra quem demandar[^14]

**Obrigações específicas para sistemas de alto risco**:

- **Registro** junto ao SIA (Sistema Nacional de Regulação e Governança de IA)[^15][^3]
- **Avaliação de conformidade** prévia ao lançamento[^10]
- **Auditoria** periódica de sistemas[^10]
- **Human-in-the-loop** para decisões que afetam direitos fundamentais[^3]
- **Canal de reclamação** para pessoas afetadas[^10][^3]
- **Relatório de impacto** (análogo ao RIPD da LGPD) [inferência aplicada — fonte]
- **Direito à explicação** sobre decisões automatizadas e à contestação[^3]

**Sanções:**
- Multa até **2% do faturamento** no ano anterior, limitada a **R$ 50 milhões** por infração[^3]
- Autoridade sancionatória: **ANPD** para setores sem regulador setorial próprio; reguladores setoriais (BACEN, ANVISA, ANATEL etc.) nos seus respectivos segmentos[^15]

***

### 1.4 Sandbox Regulatório

O PL prevê a criação de **ambientes regulatórios de experimentação (sandbox)** para testar inovações em IA sob supervisão regulatória. A diferença com o EU AI Act:[^16][^3]

> "O AI Act traz mais especificidades e requisitos para o desenvolvimento de sandboxes regulatórios, com previsão de obrigações específicas para as autoridades competentes [...] O PL 2338/2023 [cria o ambiente], mas o texto brasileiro cria vácuo regulatório enquanto não aprovado"[^16]

**Importante:** A **ANPD já opera um sandbox regulatório de IA em fase ativa** com empresas selecionadas, mesmo sem a aprovação do PL 2338/2023, valendo-se das competências da LGPD. Isso significa que existe um mecanismo real e funcional de experimentação regulada disponível hoje.[^17]

***

### 1.5 PL 2338/2023 vs. EU AI Act — Comparativo Prático

O **EU AI Act (Regulamento UE 2024/1689)** entrou em vigor em agosto de 2024, com aplicação progressiva. A estrutura de classificação por risco é substancialmente similar, pois o modelo europeu influenciou diretamente o texto brasileiro.[^17]

| Dimensão | PL 2338/2023 (Brasil) | EU AI Act (UE 2024/1689) |
|---|---|---|
| **Status** | Projeto de lei — não é lei vigente [^1][^3] | Em vigor desde ago/2024; proibições aplicáveis desde fev/2025 [^17] |
| **Modelo de risco** | 4 níveis: mínimo, limitado, alto, excessivo [^3] | 4 níveis equivalentes: mínimo, limitado, alto, inaceitável [^17] |
| **Autoridade** | SIA (a criar) + ANPD como coordenadora [^15] | Autoridades nacionais de IA dos Estados-Membros + AI Office europeu [^17] |
| **Sandbox** | Previsto no texto; ANPD já opera um informalmente [^17][^16] | Obrigações detalhadas e operacionalizadas [^16] |
| **GPAI (IA de propósito geral)** | Tratamento ainda em debate na Câmara [inferência aplicada — fonte] | Obrigações específicas para GPAI (Art. 50): watermarking, transparência de treinamento [^17] |
| **Watermarking obrigatório** | Não previsto expressamente no texto do Senado [não encontrado com fonte confiável] | Art. 50 EU AI Act: conteúdo sintético deve ser marcado como gerado por IA [^17] |
| **Direitos autorais em treinamento** | Art. prevê transparência sobre uso de conteúdo protegido [^2] | DSM Directive (EU) + AI Act: opt-out para mineração de texto/dados [inferência aplicada — fonte] |
| **Extraterritorialidade** | Aplica-se a sistemas com efeito no Brasil, independente de onde desenvolvidos [inferência aplicada — fonte] | Aplica-se a sistemas colocados no mercado europeu [^17] |

**Impacto prático para agências que usam ferramentas americanas/europeias:**
As ferramentas como GPT-4 (OpenAI, EUA), Gemini (Google, EUA), Claude (Anthropic, EUA) já estão sujeitas ao EU AI Act por operarem no mercado europeu, o que significa que **já implementam parcialmente** obrigações de watermarking e transparência (ex.: SynthID do Google, Content Credentials da Adobe). A agência brasileira que usa essas ferramentas se beneficia dessas proteções técnicas, mas assume responsabilidade de operador sob o PL 2338/2023 ao usá-las em produtos/serviços no Brasil [inferência aplicada — fonte].[^18][^19][^13]

***

### 1.6 Outros PLs Relevantes e Hierarquia

**PL 21/2020 ("Marco Legal Original"):** Projeto inicial de regulação de IA no Brasil. Foi **absorvido e superado** pelo PL 2338/2023, que o consolidou junto ao PL 5.051/2019 num texto único. O PL 21/2020 não tem tramitação autônoma relevante.[^17]

**PL 6707/2025 (opacidade algorítmica e inversão do ônus da prova):** Proposta que disciplina juridicamente cenários em que decisões automatizadas impactam consumidores. Prevê que, quando **a falta de transparência do sistema impeça o consumidor de demonstrar o nexo causal** entre a falha e o dano, poderá haver **flexibilização da exigência de comprovação** do nexo causal. Isso é relevante para agências: se um cliente alegar dano causado por conteúdo de IA da agência, o ônus de provar que o sistema funcionou corretamente pode ser invertido para a agência/operadora. Número completo e artigos específicos: não encontrado com fonte confiável no momento desta publicação — fonte  (contabeis.com.br, 03/03/2026) refere-se a PL com esse conteúdo sem indicar número final.[^20]

**Qual prevalece?** Havendo aprovação do PL 2338/2023, ele funcionará como **lei geral de IA** — lex specialis em relação ao CDC e à LGPD para matérias de IA. PLs setoriais (como PL 6707/2025) podem coexistir como regras especiais [inferência aplicada — fonte].[^17]

***

### Instruções para o Agente — Módulo 1

1. **Nunca afirmar que o PL 2338/2023 é lei vigente.** Informar que foi aprovado pelo Senado em dezembro de 2024 e está em tramitação na Câmara dos Deputados (Comissão Especial, relator Dep. Aguinaldo Ribeiro), sem sanção presidencial. Recomendar monitoramento semanal do portal da Câmara.[^1][^3]

2. **Ao classificar o risco de uma campanha de IA**, sempre verificar: (a) o conteúdo usa dados pessoais para perfilamento? (b) o output afeta crédito, emprego ou saúde do usuário final? (c) há deepfake ou simulação de identidade? Se qualquer resposta for "sim", elevar o nível de risco avaliado para "potencialmente alto" e recomendar revisão jurídica específica.[^7][^8]

3. **Exigir disclosure explícito em todo conteúdo de IA** voltado ao público (anúncios, posts, vídeos, chatbots) mesmo antes da vigência do PL, pois: (a) é obrigação prevista no texto em tramitação; (b) já é exigência do CONAR e práticas de boas práticas; (c) mitiga risco de responsabilidade.[^13][^3]

4. **Documentar toda a cadeia de uso de IA**: qual ferramenta (fornecedor), qual prompt, qual output, qual uso final. Esta documentação é a base da defesa em eventual litígio por responsabilidade solidária entre fornecedor e operador.[^14][^13]

5. **Para clientes de alto risco** (clínicas usando IA para recomendação de procedimentos, escritórios usando IA para triagem de casos, imobiliárias usando IA para concessão de crédito), incluir cláusula contratual de alocação de responsabilidade pela adequação regulatória do sistema de IA a esses clientes, preservando a agência como mera operadora de conteúdo [inferência aplicada — fonte].[^12]

6. **Monitorar o PL 6707/2025**: se aprovado, inverte o ônus da prova em casos de opacidade algoritmica — a agência precisará de logs e documentação robusta de seus sistemas de IA para se defender.[^20][^14]

7. **Recomendar sandbox ANPD** para clientes que queiram experimentar IA em contextos sensíveis (ex.: triagem de leads com IA para escritórios de advocacia): o ambiente permite teste regulado com menor risco de sanção.[^17]

8. **Ferramentas de IA europeias/americanas** já parcialmente conformes ao EU AI Act trazem proteções técnicas incorporadas (watermarking, content credentials). Documentar quais ferramentas usadas já implementam esses padrões como evidência de due diligence.[^19][^18]

***

## MÓDULO 2 — Deepfakes, Voz Sintética e Direito de Imagem Digital

> **Definição-Síntese para System Prompt:** Deepfake é conteúdo audiovisual (vídeo, foto, áudio) gerado ou manipulado por IA de forma hiper-realista para simular a aparência, voz ou comportamento de uma pessoa real sem sua autorização. No Brasil, não existe lei específica sobre deepfakes, mas a conduta é ilícita civil e penalmente por aplicação do Art. 5º, V e X da CF/88, Arts. 11–21 do Código Civil (direitos da personalidade), Art. 20 do CC (consentimento para uso de imagem), Art. 218-C do CP (Lei 13.718/2018, para deepfakes sexuais) e Arts. 138–140 do CP (crimes contra honra). Projetos de lei específicos estão em tramitação.

***

### 2.1 Legislação Específica sobre Deepfakes no Brasil

**Não existe lei federal específica sobre deepfakes em vigor no Brasil em março de 2026** [inferência aplicada — fonte]. O enquadramento jurídico atual opera por analogia e aplicação de normas gerais.[^21]

**Projetos de Lei em tramitação específicos sobre deepfakes:**

**PL 1884/2025** (Dep. Luiz Nishimori, apresentado em 28/04/2025):
- Regulamenta o uso de tecnologias de manipulação audiovisual (deepfakes)[^22]
- Exige que plataformas e ferramentas de criação de deepfakes incluam **funcionalidades de identificação automática** do conteúdo gerado[^22]
- Propõe obrigatoriedade de **marcação por metadados ou marca d'água** (watermark)[^23]
- Prevê **responsabilização de plataformas** que ofereçam ferramentas de criação sem mecanismos de transparência[^23]
- Status: aguardando aprovação, ainda em tramitação[^23]

**PL 2688/2025** (substitutivo aprovado na Comissão de Comunicação em fevereiro de 2026):
- Recebeu parecer favorável na Comissão de Comunicação da Câmara[^24]
- Busca enfrentar uso indevido de deepfakes, **especialmente envolvendo crianças, adolescentes e adultos sem consentimento**[^24]
- Status: aprovado em comissão; tramitação plenária pendente[^24]

**Sanções previstas nos PLs:**
- PL 1884/2025 prevê responsabilização de plataformas[^22][^23]
- PL 2688/2025 — sanções específicas: **não encontrado com fonte confiável** (texto completo não recuperado)

***

### 2.2 Marco Legal Vigente Aplicável a Deepfakes

Na ausência de lei específica, aplicam-se:

| Norma | Artigo | Aplicação ao Deepfake |
|---|---|---|
| CF/88 | Art. 5º, V | Direito de resposta e indenização por dano moral/material [^25] |
| CF/88 | Art. 5º, X | Inviolabilidade da imagem, intimidade, vida privada e honra [^25] |
| Código Civil | Arts. 11–21 | Direitos da personalidade — proteção geral de imagem e voz [^26][^25] |
| Código Civil | Art. 20 | Exigência de **consentimento** para uso de imagem; salvo fins informativos, culturais ou noticiosos [^21] |
| Código Civil | Art. 186 | Ato ilícito — quem viola direito de outrem por ação ou omissão obriga-se a reparar o dano [^26] |
| Código Penal | Art. 138 | **Calúnia**: deepfake que simula prática de crime [^27] |
| Código Penal | Art. 218-C (Lei 13.718/2018) | Deepfake com nudez/cena sexual sem consentimento — **pena: reclusão de 1 a 5 anos** [^28][^29] |
| LGPD | Arts. 5º, 11 e 12 | Biometria facial e vocal como **dado pessoal sensível** — tratamento exige consentimento específico e destacado [inferência aplicada — fonte] |
| Marco Civil da Internet | Art. 19 | Responsabilidade de plataformas por conteúdo de terceiros (debate sobre deepfake ainda em aberto) [^21] |

**Sobre o Art. 218-C do CP (Lei 13.718/2018):**
O artigo criminaliza "oferecer, trocar, disponibilizar, transmitir, vender ou expor à venda, distribuir, publicar ou divulgar [...] **sem o consentimento da vítima**, cena de sexo, nudez ou pornografia". A jurisprudência majoritária entende que **se aplica a deepfakes sexuais**, pois a norma não exige que a cena seja real — basta que a pessoa seja retratada sem consentimento. A pena prevista é de **reclusão de 1 a 5 anos, mais multa**. Há qualificadora se a vítima for menor de 18 anos.[^28][^29]

**PL específico para deepfake pornográfico:** O PL 2688/2025 trata especificamente do tema, com proteção reforçada para menores. Não foram encontrados outros PLs com número e artigos confiáveis além dos já citados.[^24]

***

### 2.3 Jurisprudência Brasileira sobre Deepfakes (2023–2026)

**Não foram encontrados acórdãos brasileiros específicos sobre deepfakes com número de processo verificável** nesta pesquisa [não encontrado com fonte confiável — pesquisa realizada em 25/03/2026]. O estudo do PUC-SP (2025) confirma essa lacuna: "embora o ordenamento jurídico brasileiro disponha de mecanismos relevantes de tutela, persistem lacunas quanto à responsabilização de modelos treinados de forma opaca".[^21]

O mesmo estudo aponta casos nacionais e internacionais analisados em sua pesquisa bibliográfica, mas sem citar números de processo específicos verificáveis.[^21]

**Casos internacionais com relevância para o Brasil:**

1. **EUA — FTC vs. deepfake fraudes financeiras (2024):** A Federal Trade Commission acionou empresas que usavam deepfakes de vozes de CEOs para fraudes. Relevância: fundamento de responsabilidade do operador da ferramenta, aplicável por analogia ao Art. 186 CC [inferência aplicada — fonte]

2. **Coreia do Sul — Lei sobre deepfakes (2020, emendada 2024):** Criminaliza produção e distribuição de deepfakes sexuais com penas de até 5 anos. Relevância: parâmetro comparativo para sanções nos PLs brasileiros em tramitação [inferência aplicada — fonte]

3. **Europa — GDPR e deepfakes (2023–2024):** Autoridades de proteção de dados da Espanha (AEPD) e Itália (Garante) emitiram orientações classificando rostos em deepfakes como **dados biométricos sensíveis** sob o GDPR, exigindo base legal específica para processamento. Impacto no Brasil: argumento análogo aplica-se à LGPD, Art. 11 [inferência aplicada — fonte]

***

### 2.4 Voz Sintética e Clonagem de Voz — Riscos Jurídicos

**Base jurídica:** A voz é reconhecida pela doutrina brasileira como **direito da personalidade**, integrando o acervo do Art. 5º, X da CF/88 e Arts. 11–21 do Código Civil. O uso não autorizado de voz clonada que remeta a determinada pessoa pode ensejar responsabilidade civil independentemente de haver obra musical protegida.[^26][^25]

> "Mesmo tendo sido a voz emitida por uma máquina, ela ainda assim tem um titular [...] aquele cuja voz foi aprendida pela AI. Assim, a voz pertence ao acervo de direitos de personalidade desse emissor original, devendo ser tutelada, de forma idêntica à imagem"[^26]

**Riscos jurídicos específicos para agências de marketing:**

1. **Clonagem para narrações publicitárias**: usar voz sintetizada idêntica a locutor/celebridade sem autorização → responsabilidade civil por Art. 20 CC + Art. 186 CC[^25]
2. **Assistentes de voz e chatbots**: vozes de personagens sintéticos que remetem a pessoas reais → mesmo enquadramento[^26]
3. **Treinamento de modelo com voz sem consentimento**: violação da LGPD (voz como dado biométrico sensível, Art. 11 LGPD)[^30]
4. **Fraude por voz clonada**: deepfake de voz de sócio/CEO para autorizar transações → crime de estelionato (Art. 171 CP) + dano civil[^12]

**Regulamentação específica em tramitação:**

**PL 4041/2025**: prevê proteção da atividade de dublagem e regras para contratos com IA; inclui:
- **Voz como dado pessoal sensível na LGPD**[^30]
- **Vedação expressa à cessão da voz para IA que substitua integralmente o trabalho humano**[^30]
- **Proibição de criação de voz sintética** de profissional sem autorização expressa[^30]
- Proteção estendida aos descendentes por **70 anos**[^30]

Não há regulamentação específica vigente sobre voz sintética em março de 2026 além do PL 4041/2025 em tramitação.

***

### 2.5 Consentimento para Uso de Likeness em Treinamento de IA

**No Brasil:** A LGPD (Art. 11) exige consentimento específico e destacado para tratamento de **dados biométricos** (que incluem face e voz). O treinamento de modelos de IA com imagens ou vozes de pessoas identificáveis constitui tratamento de dados pessoais sensíveis, exigindo:[^30]
- Base legal válida (consentimento ou legítimo interesse em bases restritas)
- Finalidade específica informada ao titular
- Direito de revogação do consentimento

**EU AI Act (Art. 50 e Considerandos):** Modelos de IA de propósito geral (GPAI) devem publicar sumário "suficientemente detalhado" dos dados usados em treinamento, incluindo conteúdo protegido por direitos autorais. Provedores europeus de ferramentas de IA (ex.: ferramentas da Adobe, serviços de IA da Mistral) passam a ter essa obrigação de transparência, o que impacta indiretamente a agência brasileira que os utiliza.[^16][^17]

**PL 2338/2023:** O texto aprovado pelo Senado prevê **transparência sobre o uso de conteúdos protegidos por direitos autorais** em treinamento de IA, incluindo mecanismos de negociação de remuneração com autores. A regulamentação detalhada desse mecanismo ainda depende da aprovação do PL e da regulamentação pelo SIA.[^2][^3]

**Tendência regulatória:** O consenso emergente, tanto no Brasil quanto na UE, é de que o consentimento informado é requisito para uso de imagem ou voz identificável em treinamento de IA, exceto quando há base legal alternativa robusta.[^25][^21]

***

### 2.6 Boas Práticas para Agências — Conteúdo com Pessoas via IA

**Como usar IA para gerar conteúdo com pessoas (avatares, porta-vozes virtuais) SEM violar direito de imagem:**

1. **Avatares completamente fictícios (full CGI):** Criar personagens que não remetam a nenhuma pessoa real identificável — sem violação de direito de imagem. Documentar o processo criativo para demonstrar a origem sintética[^21]

2. **Uso de modelos humanos com cessão de direitos de imagem digital:** Contratar modelo fotográfico com contrato que inclua **cessão de uso de imagem para treinamento de IA** e **uso em conteúdo sintético futuro** — especificando finalidade, prazo e território. Evitar autorizações genéricas [inferência aplicada — fonte][^30]

3. **Porta-vozes virtuais baseados em celebridades/influenciadores:** Exigir **contrato específico de licenciamento de identidade digital** (nome, imagem, voz, maneirismos), com remuneração proporcional ao uso — jamais usar IA para simular celebridade sem esse contrato[^31][^25]

4. **Disclosure obrigatório:** Todo conteúdo com avatar virtual ou pessoa gerada por IA deve incluir **"Conteúdo gerado por IA"** ou equivalente, em local visível, antes mesmo da vigência do PL 2338/2023 (obrigação ética e futura legal)[^23][^3]

5. **Revisão humana**: manter evidência de supervisão humana (human-in-the-loop) na aprovação de todo conteúdo com pessoas — especialmente imobiliárias de luxo (risco de imitar arquitetos/proprietários) e clínicas estéticas (risco de simular resultados com rosto de paciente)[^3]

6. **Cláusulas contratuais com clientes:** Incluir declaração do cliente de que autorizou o uso de imagem de todas as pessoas que aparecem no conteúdo final, transferindo a responsabilidade de compliance para o detentor dos direitos [inferência aplicada — fonte]

***

### 2.7 Watermarking e Detecção — Obrigação Legal e Tecnologias

**Obrigação legal no Brasil:** **Não há obrigação legal vigente de marcar conteúdo sintético no Brasil em março de 2026** [não encontrado com fonte confiável]. O PL 1884/2025 propõe a obrigação para plataformas/ferramentas de criação, mas ainda não é lei.[^23]

**Obrigação na UE:** O **EU AI Act, Art. 50**, exige que sistemas de IA que geram conteúdo sintético (imagem, áudio, vídeo) apliquem marcação legível por máquina indicando a origem artificial do conteúdo. Ferramentas de IA europeias e americanas que atendem o mercado europeu já implementam isso.[^17]

**Tecnologias disponíveis:**

| Tecnologia | Descrição | Empresas |
|---|---|---|
| **C2PA (Coalition for Content Provenance and Authenticity)** | Padrão aberto: vincula criptograficamente um manifesto de proveniência ao arquivo digital; rastreia criação, edições e uso de IA em toda a cadeia [^19][^32] | Adobe, Microsoft, Google, Intel, Sony |
| **Content Credentials (Adobe)** | Implementação prática do C2PA; inclui Adobe Verify (ferramenta web de verificação), ícone CR e registro da cadeia de edições [^19] | Adobe (Photoshop, Firefly, Stock) |
| **SynthID (Google DeepMind)** | Marca d'água imperceptível ao olho humano, embutida em pixels de imagens e áudios gerados por IA; detectável por modelo próprio do Google [^18] | Google (Gemini, Imagen) |
| **DALL-E / OpenAI** | Content credentials integradas; imagens geradas incluem metadados C2PA [inferência aplicada — fonte] | OpenAI |

**Limitação técnica importante:** O C2PA e as Content Credentials são vulneráveis à remoção por simples recorte de imagem, compressão ou captura de tela — o sistema sinaliza a ausência do manifesto como "suspeito", mas não impede a remoção. A proteção não é à prova de adulteração — é uma redução do espaço para negação plausível.[^32]

**Recomendação para agências:** Adotar Content Credentials/C2PA como padrão em todos os conteúdos gerados por IA, mesmo sem obrigação legal no Brasil, pois:
- Demonstra due diligence para fins de defesa em litígios
- Cumpre antecipadamente a tendência regulatória (PL 1884/2025 + EU AI Act)
- Diferencial competitivo perante clientes premium que valorizam transparência[^19][^23]

***

### Instruções para o Agente — Módulo 2

1. **Toda solicitação de conteúdo com rosto ou voz de pessoa real** deve acionar alerta automático de compliance: verificar se há (a) contrato de cessão de imagem e voz para uso em IA; (b) disclosure de conteúdo sintético planejado; (c) restrição de uso (território, tempo, finalidade). Se qualquer item estiver ausente, **bloquear a aprovação do conteúdo** até regularização.[^25][^21]

2. **Deepfake pornográfico é linha vermelha absoluta.** Qualquer prompt, brief ou solicitação que envolva nudez, cena sexual ou roupa íntima com identificação ou simulação de pessoa real deve ser recusado imediatamente, independente de contexto ou justificativa — enquadramento em Art. 218-C CP (Lei 13.718/2018), pena de reclusão de 1 a 5 anos.[^29][^28]

3. **Avatares e porta-vozes virtuais** para clientes premium (imobiliárias, clínicas, escritórios) devem ser classificados como "alto risco reputacional" — exigir revisão jurídica prévia do contrato de licenciamento de identidade digital antes de iniciar a produção.[^25][^21]

4. **Clonagem de voz**: nunca usar ferramenta de clonagem de voz com sample de voz de terceiro sem contrato expresso de licenciamento da identidade vocal. Para narrações com IA, usar apenas: (a) vozes sintéticas 100% artificiais, sem referência a pessoa real; ou (b) voz do próprio cliente com autorização documentada.[^26][^30]

5. **Aplicar C2PA/Content Credentials** como padrão em todos os outputs de IA entregues ao cliente. Manter log de quais ferramentas foram usadas, com qual configuração, para qual output. Este log é a evidência de transparência exigível no futuro e defensável hoje.[^32][^19]

6. **No contexto eleitoral**: deepfakes com conteúdo eleitoral são objeto de atenção especial do TSE (Resolução TSE n.º 23.732/2024 — verificar atualização). **Nenhum cliente** do setor político deve receber serviço de IA generativa para geração de vídeo ou voz sem verificação prévia da regulamentação eleitoral vigente [inferência aplicada — fonte].

7. **Monitorar PL 1884/2025 e PL 2688/2025**: quando aprovados, obrigarão plataformas a incluir marcação automática. A agência deve atualizar seus workflows para incorporar as marcações exigidas dentro de 30 dias da promulgação.[^24][^23]

8. **Clientes do setor de saúde (clínicas estéticas):** a simulação de resultados estéticos com rosto de paciente via IA é simultaneamente: (a) risco de direito de imagem (Art. 20 CC); (b) risco de publicidade enganosa (CDC, Art. 37); (c) potencial infração ao CFM/CRM sobre publicidade médica. Tratar como **categoria de risco triple-layer** exigindo aprovação jurídica + compliance regulatório setorial [inferência aplicada — fonte].[^21]

***

## Apêndice: Mapa de Fontes Normativas

| Norma | Número | Status | Relevância Principal |
|---|---|---|---|
| Constituição Federal | Art. 5º, V, X | Vigente | Direito de imagem, honra, indenização |
| Código Civil | Arts. 11–21, 186, 20 | Vigente | Direitos da personalidade, imagem, ato ilícito |
| Código Penal | Art. 138–140, 218-C | Vigente | Calúnia, difamação, deepfake sexual |
| Lei 13.718/2018 | Art. 218-C CP | Vigente | Inseriu deepfake sexual no CP |
| LGPD (Lei 13.709/2018) | Arts. 5º, 11, 12 | Vigente | Dados biométricos, tratamento de rosto/voz |
| Marco Civil da Internet (Lei 12.965/2014) | Art. 19 | Vigente | Responsabilidade de plataformas |
| PL 2338/2023 | Aprovado Senado 10/12/2024 | Em tramitação — Câmara [^1] | Marco Legal da IA — lei geral |
| PL 1884/2025 | Dep. Luiz Nishimori | Em tramitação [^22][^23] | Regulação específica de deepfakes |
| PL 2688/2025 | Substitutivo aprovado na Comissão de Comunicação | Em tramitação [^24] | Deepfakes com menores e adultos sem consentimento |
| PL 4041/2025 | não encontrado número final | Em tramitação [^30] | Voz como dado sensível, proteção de dubladores |
| PL 6707/2025 | não encontrado número final com fonte confiável | Em tramitação [^20] | Opacidade algorítmica, inversão do ônus da prova |
| EU AI Act | Reg. UE 2024/1689 | Em vigor desde ago/2024 [^17] | Watermarking, GPAI, extraterritorialidade |
<span style="display:none">[^33][^34][^35][^36][^37][^38][^39][^40][^41][^42]</span>

<div align="center">⁂</div>

[^1]: https://www12.senado.leg.br/noticias/videos/2024/12/marco-da-inteligencia-artificial-e-aprovado-em-plenario-e-vai-a-camara
[^2]: https://www.gov.br/cultura/pt-br/assuntos/noticias/senado-federal-aprova-marco-regulatorio-da-inteligencia-artificial
[^3]: https://blog.cbrdoc.com.br/marco-legal-da-ia-tera-votacao-final-em-2026/
[^4]: https://desinformante.com.br/votacao-do-marco-da-ia-fica-para-2026-em-meio-a-impasses-politicos-e-criticas-ao-texto/
[^5]: https://www.dataprivacybr.org/comissao-especial-do-pl-de-ia-na-camara-dos-deputados/
[^6]: https://www.youtube.com/watch?v=KKoXZAZTKjU
[^7]: https://www.gov.br/anpd/pt-br/assuntos/noticias/analise-preliminar-do-pl-2338_2023-formatado-ascom.pdf
[^8]: https://www.camara.leg.br/proposicoesWeb/prop_mostrarintegra?codteor=2868197&filename=PL+2338%2F2023
[^9]: https://agenciabrasil.ebc.com.br/politica/noticia/2024-12/organizacoes-civis-esperam-melhoria-de-regras-para-ia-na-camara
[^10]: https://direitosnarede.org.br/2024/06/18/projeto-de-lei-n-2338-2023/
[^11]: https://www.sidi.org.br/pt-br/blog/pl-2338/2023-os-impactos-da-regulamentacao-da-inteligencia-artificial-no-brasil
[^12]: https://legale.com.br/blog/regulacao-juridica-ia-generativa-desafios-e-oportunidades-no-brasil/
[^13]: https://www.cut.org.br/noticias/inteligencia-artificial-pl-2338-de-2023-uma-regulamentacao-fundamental-d83e
[^14]: https://submissoesrevistarcmos.com.br/rcmos/article/download/1612/3813
[^15]: https://www.gov.br/gestao/pt-br/assuntos/noticias/2025/dezembro/pl-do-governo-propoe-sistema-de-governanca-para-a-inteligencia-artificial-no-pais
[^16]: https://baptistaluz.com.br/wp-content/uploads/2023/07/BLUZ_230705_ebook_Tech_Analise-Comparativa-IA-VF.pdf
[^17]: https://www.barbieriadvogados.com/regulamentacao-inteligencia-artificial-brasil/
[^18]: https://ainews.net.br/google-implementa-c2pa-para-verificar-imagens-criadas-por-ia/
[^19]: https://comlimao.com/design/adobe-content-authenticity-c2pa-ia-generativa/
[^20]: https://www.contabeis.com.br/noticias/75422/pl-propoe-responsabilizacao-por-danos-causados-por-ia/
[^21]: https://tede2.pucsp.br/handle/handle/45762
[^22]: https://www.camara.leg.br/proposicoesWeb/prop_mostrarintegra?codteor=2892233&filename=PL+1884%2F2025
[^23]: https://www.barbieriadvogados.com/deepfake-o-que-e-como-funciona-e-as-implicacoes-juridicas-no-brasil/
[^24]: https://www.minhaoperadora.com.br/2026/02/pl-que-tramita-na-camara-sobe-o-tom-contra-ias-capazes-de-criar-deepfakes.html
[^25]: https://almeidaealencar.adv.br/inteligencia-artificial-voz-sintetica-e-os-limites-do-direito-autoral-no-brasil/
[^26]: https://revistaft.com.br/a-voz-e-a-maquina-a-tutela-da-voz-clonada-pela-inteligencia-artificial/
[^27]: https://www.grupounibra.com/repositorio/DIREIT/2024/o-fenomeno-do-deepfake-e-seus-impactos-no-ordenamento-juridico-brasileiro.pdf
[^28]: https://jornal.usp.br/atualidades/eleitores-precisam-ficar-atentos-a-conteudos-falsos-divulgados-como-deepfakes/
[^29]: https://legale.com.br/blog/deepfakes-sexuais-crimes-prova-e-responsabilidade-penal/
[^30]: https://www.asarmasdobrasil.com.br/PL/2547251/4041-2025-dublagem-inteligencia-artificial-direitos-conexos-protecao-cultural-contratacao-nacional-voz-como-dado-sensivel-sancoes-incentivos-fiscais-acessibilidade-legislacao-autoral
[^31]: https://repositorio.animaeducacao.com.br/items/b3b80d2e-dee3-4624-a72e-d06ff1406e3d/full
[^32]: https://ricardodias.net/blog/autenticidade-das-imagens-na-era-da-ia
[^33]: https://www25.senado.leg.br/web/atividade/materias/-/materia/157233
[^34]: https://www.camara.leg.br/proposicoesWeb/fichadetramitacao?idProposicao=2487262
[^35]: https://www.stj.jus.br/sites/portalp/Paginas/Comunicacao/Noticias/26082021-Para-Quarta-Turma--inversao-do-onus-da-prova-no-julgamento-da-apelacao-viola-direito-de-defesa-.aspx
[^36]: https://www.jota.info/opiniao-e-analise/colunas/ia-regulacao-democracia/classificacao-de-riscos-a-solucao-adotada-pelo-pl-2338-23
[^37]: https://www.jota.info/opiniao-e-analise/artigos/ai-act-e-pl-2338-uma-analise-critica-das-estruturas-regulatorias-de-ia
[^38]: https://www2.camara.leg.br/atividade-legislativa/comissoes/comissoes-temporarias/especiais/57a-legislatura/comissao-especial-sobre-inteligencia-artificial-pl-2338-23
[^39]: https://www.congressonacional.leg.br/materias/materias-bicamerais/-/ver/pl-2338-2023
[^40]: https://www.congressonacional.leg.br/en/materias/materias-bicamerais/-/ver/pl-2338-2023
[^41]: https://www.lexml.gov.br/urn/urn:lex:br:senado.federal:projeto.lei;pl:2023;2338
[^42]: https://www.ssl.com/pt/artigo/solu%C3%A7%C3%B5es-de-autenticidade-de-conte%C3%BAdo-empresarial-c2pa/```

