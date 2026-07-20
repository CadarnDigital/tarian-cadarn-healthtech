---
source_file: perplexity-lgpd-compliance.md
converted_at: 2026-03-23
original_extension: md
processor: Echo (aiox-m2m-etl)
extraction_quality: full
domain: LGPD e Compliance Digital
source_type: perplexity-deep-research
source_tool: Perplexity Pro (Deep Research)
agent_target: juridica-lgpd
squad: squad-cadarn-juridica
modules: 4
---

<content>

# Manual de Compliance LGPD para Agência de Engenharia de Lucro — Módulos 1 a 4

> **Aviso metodológico:** Toda afirmação abaixo está vinculada a uma fonte verificável. Onde a informação não pôde ser confirmada com certeza, aplica-se a regra de integridade: *"não encontrado com fonte confiável"*. Termos técnicos em inglês são apresentados na primeira menção. Este documento foi produzido com base em pesquisa realizada em março de 2026.

***

# MÓDULO 1 — SANÇÕES E FISCALIZAÇÕES ANPD (2024–2026)

## Definição-síntese (para system prompt)

> A ANPD (Autoridade Nacional de Proteção de Dados — Brazil's Data Protection Authority) instaurou ou concluiu múltiplos processos sancionatórios entre 2023 e 2026. Os precedentes estabelecem que: ausência de base legal explícita (Art. 7º LGPD), inexistência de Encarregado/DPO (Art. 41 LGPD) e descumprimento de ordens da Autoridade são as infrações mais recorrentes e de maior risco jurídico imediato para agentes de tratamento no Brasil.

***

## Tabela de Casos Sancionatórios e Fiscalizatórios

### Caso 1 — Telekall Infoservice (Primeiras Multas da ANPD)

| Campo | Detalhe |
| :-- | :-- |
| **Nome da empresa** | Telekall Infoservice (setor: telemarketing) |
| **Nº do processo ANPD** | Publicado no DOU de 06/07/2023; número de processo interno não divulgado publicamente |
| **Tipo de infração** | Ausência de base legal para tratamento de dados pessoais + não atendimento à ANPD durante processo de fiscalização |
| **Sanção aplicada** | Duas multas de R\$ 7.200,00 cada = **total R\$ 14.400,00** |
| **Fase atual** | Concluído (publicado no DOU; desconto de 25% para pagamento sem recurso) |
| **Resumo técnico** | Empresa de telemarketing realizava tratamento de dados pessoais de terceiros para fins de prospecção sem conseguir comprovar qual das hipóteses legais do Art. 7º fundamentava a atividade. Adicionalmente, descumpriu o dever de cooperação com a ANPD durante o processo, recusando-se a fornecer documentos solicitados — infração separada ao Regulamento de Fiscalização. |
| **Artigos LGPD violados** | **Art. 7º** (bases legais para tratamento) + **Art. 41** (designação de Encarregado) + **Art. 5º, Resolução CD/ANPD nº 1/2021** (deveres durante fiscalização) |
| **Lição para agência de marketing** | **Toda operação de tratamento de dados para fins de marketing (listas de prospecção, captação de leads, telemarketing, e-mail marketing) deve ter base legal documentada antes de iniciar.** A ausência de documentação equivale à ausência de base legal para a ANPD. |

[Fonte: ANPD, gov.br, notícia publicada em 06/07/2023: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-aplica-a-primeira-multa-por-descumprimento-a-lgpd] [Fonte: Araújo Policastro, análise jurídica: https://araujopolicastro.com.br/anpd-aplica-primeiras-sancoes-por-violacao-a-lgpd/][^1][^2]

***

### Caso 2 — Empresa não nomeada (Sanções de fevereiro de 2024, primeiras sanções do ano)

| Campo | Detalhe |
| :-- | :-- |
| **Nome da empresa** | Não divulgado publicamente (setor: não especificado) |
| **Nº do processo ANPD** | Não encontrado com fonte confiável |
| **Tipo de infração** | Ausência de ROT (Records of Processing Activities); ausência de RIPD após solicitação da ANPD; comunicação tardia de incidente de segurança; não apresentação de plano de gestão de incidentes |
| **Sanção aplicada** | 4 advertências (violações de gravidade variada: leves e graves) |
| **Fase atual** | Concluído (advertências publicadas em fevereiro de 2024) |
| **Resumo técnico** | A empresa não mantinha Registro das Operações de Tratamento (ROT), não elaborou RIPD quando solicitado pela ANPD, comunicou incidente de segurança aos titulares fora do prazo e descumpriu prazo para entrega do plano de gestão de incidentes — este último classificado como infração **grave** por caracterizar obstrução à fiscalização. |
| **Artigos LGPD violados** | **Art. 37** (ROT) + **Art. 38** (RIPD) + **Art. 48** (comunicação de incidentes) + **Art. 5º, Regulamento de Dosimetria** |
| **Lição para agência de marketing** | Manter ROT atualizado, RIPD elaborado e plano de resposta a incidentes são obrigações que a ANPD considera prioritárias em 2024–2025. |

[Fonte: Tauil \& Chequer Advogados, análise das primeiras sanções de 2024: https://www.tauilchequer.com.br/pt/insights/publications/2024/02/anpd-applies-first-sanctions-of-2024][^3]

***

### Caso 3 — Meta / Treinamento de IA com dados de brasileiros

| Campo | Detalhe |
| :-- | :-- |
| **Nome da empresa** | Meta Platforms, Inc. (Facebook, Instagram, WhatsApp) |
| **Nº do processo ANPD** | **Despacho Decisório Nº 20/2024/PR/ANPD** (Medida Preventiva, 02/07/2024) |
| **Tipo de infração** | Uso de dados pessoais publicados em plataformas Meta para treinamento de sistemas de IA sem base legal adequada; falta de transparência; limitação de direitos de titulares; riscos específicos para crianças e adolescentes |
| **Sanção aplicada** | Medida Preventiva: suspensão cautelar imediata da nova política de privacidade para fins de IA + **multa diária de R\$ 50.000,00 por descumprimento** |
| **Fase atual** | **Parcialmente concluído:** em 30/08/2024, a ANPD acatou o "plano de conformidade" apresentado pela Meta e levantou a suspensão, permitindo retomada condicionada ao cumprimento do plano |
| **Resumo técnico** | A Meta atualizou sua política de privacidade para usar dados pessoais de usuários brasileiros no treinamento de IA generativa com base em **legítimo interesse**. A ANPD identificou: (a) base legal inadequada — legítimo interesse sem teste de balanceamento documentado; (b) ausência de transparência suficiente sobre o uso dos dados; (c) limitação ao exercício de direitos dos titulares (opt-out insuficiente); (d) tratamento de dados de crianças sem salvaguardas específicas. Após negociação, a Meta apresentou mecanismo de opt-out acessível e plano de conformidade aceito pela ANPD. |
| **Artigos LGPD violados (indícios)** | **Art. 7º, IX** (legítimo interesse sem preenchimento dos requisitos) + **Art. 10** (requisitos do legítimo interesse) + **Art. 14** (proteção de dados de crianças) + **Art. 18** (direitos dos titulares) |
| **Lição para agência de marketing** | **O uso de legítimo interesse para processar dados em larga escala para fins de IA ou marketing automatizado exige teste de balanceamento documentado (LIA — Legitimate Interest Assessment). A ANPD demonstrou disposição para agir cautelarmente em 24–48 horas quando os direitos de titulares estão em risco.** |

[Fonte: ANPD, notícia oficial: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-determina-suspensao-cautelar-do-tratamento-de-dados-pessoais-para-treinamento-da-ia-da-meta] [Fonte: QCA Advogados, análise do Despacho Decisório Nº 20/2024: https://www.qca.adv.br/anpd-suspende-tratamento-ia-da-meta/] [Fonte: G1, levantamento da suspensão: https://g1.globo.com/politica/noticia/2024/08/30/anpd-acata-plano-de-conformidade-da-meta-e-libera-uso-de-dados-de-brasileiros-para-treinar-ia][^4][^5][^6]

***

### Caso 4 — Fiscalização Setorial (Dezembro 2024): 20 Empresas sem Encarregado/DPO

| Campo | Detalhe |
| :-- | :-- |
| **Empresas notificadas** | 20 empresas privadas (startups, multinacionais, capital aberto). Lista parcial pública incluiu: **BlueFit Academias** e **Bytedance Brasil Tecnologia Ltda (TikTok)**, além de outras dos setores de tecnologia, telefonia, educação, saúde, transporte e varejo |
| **Nº do processo ANPD** | Ciclo de Monitoramento ANPD — alinhado ao Mapa de Temas Prioritários 2024–2025 (Resolução CD/ANPD nº 10/2023) |
| **Tipo de infração** | Ausência de designação de Encarregado/DPO (Data Protection Officer) e/ou ausência de canal de comunicação adequado com titulares de dados |
| **Sanção aplicada** | Notificação para regularização — sem multa imediata; irregularidades persistentes podem gerar processo sancionador com multas de até 2% do faturamento, limitadas a R\$ 50 milhões por infração |
| **Fase atual** | 🔄 **STATUS: EM TRAMITAÇÃO** — desdobramentos em 2025/2026 não encontrados com fonte confiável para confirmação de conclusão |
| **Resumo técnico** | Após entrar em vigor a Resolução CD/ANPD nº 18/2024 (regulamentando a atuação do Encarregado), a ANPD iniciou monitoramento ativo das 20 maiores empresas que continuavam sem cumprir o Art. 41 da LGPD. A fiscalização é **proativa** (não dependeu de denúncia), sinalizando nova postura enforcement. |
| **Artigos LGPD violados** | **Art. 41** (designação de Encarregado) + **Art. 52** (sanções administrativas) |
| **Lição para agência de marketing** | **A ausência de DPO/Encarregado nomeado com canal de comunicação público já é suficiente para abertura de processo fiscalizatório. Toda agência e todos os seus clientes que realizam tratamento de dados em escala devem ter Encarregado designado conforme Resolução CD/ANPD nº 18/2024.** |

[Fonte: ANPD, notícia oficial, 12/12/2024: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-fiscaliza-20-empresas-por-falta-de-encarregado-e-canal-de-comunicacao] [Fonte: G1, 13/12/2024: https://g1.globo.com/tecnologia/noticia/2024/12/13/anpd-notifica-20-empresas-por-descumprirem-regra-de-protecao-de-dados.ghtml] [Fonte: IDS.org.br, análise: https://ids.org.br/noticia/anpd-inicia-processo-de-fiscalizacao-de-20-empresas-por-falta-de-encarregado][^7][^8][^9]

***

### Casos Adicionais: Cookies, Pixels, Data Brokers

**Processos específicos envolvendo cookies, pixels de remarketing ou compartilhamento com data brokers:** não encontrado com fonte confiável nenhum processo sancionatório concluído pela ANPD até março de 2026 especificamente sobre cookies/pixels/remarketing/lookalike audiences. A ANPD publicou o **Guia de Cookies (2022)** como instrumento orientativo, mas não há registro público de auto de infração específico para estas práticas no período pesquisado.

**Deliberação CD-10/2025 (multas diárias por descumprimento de medidas cautelares):** não encontrado com fonte confiável o texto completo ou número exato desta deliberação específica. O instrumento de multa diária já foi exercido no caso Meta (R\$ 50.000/dia, Despacho Decisório Nº 20/2024/PR/ANPD) com base nas competências cautelares da ANPD estabelecidas na Lei nº 13.853/2019 (Art. 52, §4º da LGPD). [Fonte: ANPD, Despacho Decisório Nº 20/2024/PR/ANPD][^4]

**Processos instaurados em 2025–2026 não amplamente divulgados:** a Truzzi Advogados reportou em junho/2025 que "para 2025, o plano de fiscalização já está em andamento, indicando uma busca ativa por infrações, não mais dependendo apenas de denúncias" [Fonte: https://truzzi.com.br/a-era-da-orientacao-acabou-as-primeiras-multas-da-anpd-e-o-novo-cenario-da-lgpd/], mas processos individuais de 2025–2026 adicionais específicos não foram encontrados com fonte confiável.[^10]

***

⚠️ **ZONAS DE RISCO ESPECÍFICAS — MÓDULO 1**

> **Para agências Martech, os precedentes indicam cinco zonas de risco crítico:**
> 1. **Captação de leads sem base legal documentada** → Risco direto idêntico ao caso Telekall (Art. 7º)
> 2. **Pixels de remarketing e lookalike audiences sem consentimento explícito** → Risco análogo ao caso Meta (Art. 7º, IX sem LIA documentado)
> 3. **Ausência de Encarregado/DPO no cliente** → Risco direto idêntico à fiscalização setorial de dez/2024 (Art. 41)
> 4. **Compartilhamento de listas com parceiros de mídia (Meta Ads, Google Ads) sem cláusula contratual LGPD** → Risco de corresponsabilidade como controlador conjunto (Art. 52)
> 5. **Não cooperação com ANPD em eventual investigação** → Infração autônoma, multa separada (Art. 5º, Resolução nº 1/2021)

***

## INSTRUÇÕES PARA O AGENTE — MÓDULO 1

1. **Ao revisar formulários de captação de leads (landing pages, pop-ups, formulários de contato), verificar obrigatoriamente se há base legal explícita conforme Art. 7º da LGPD. Se ausente ou não documentada, bloquear aprovação e gerar alerta de alto risco.** [Fonte: Caso Telekall Infoservice, DOU 06/07/2023; Art. 7º LGPD]
2. **Ao auditar campanhas que utilizem pixel de Meta (Facebook Pixel), Google Tag ou similar para remarketing, exigir evidência de base legal documentada: se consentimento, verificar cookie banner com opt-in ativo; se legítimo interesse, exigir LIA documentado. Ausência de qualquer dos dois = bloquear campanha.** [Fonte: Despacho Decisório Nº 20/2024/PR/ANPD (caso Meta); Art. 7º, IX c/c Art. 10 LGPD]
3. **Ao elaborar contrato de prestação de serviços de marketing digital para cliente, verificar se o cliente possui Encarregado/DPO designado com canal de comunicação público. Se não possuir, incluir cláusula de obrigação do cliente e alertar sobre risco de processo fiscalizatório conforme precedente ANPD dez/2024.** [Fonte: ANPD fiscalização 20 empresas, 12/12/2024; Art. 41 LGPD + Resolução CD/ANPD nº 18/2024]
4. **Em hipótese alguma recomendar ao cliente descumprir ou ignorar solicitação de documentos da ANPD. Descumprimento de ordem da Autoridade é infração autônoma que gera multa separada da infração principal.** [Fonte: Caso Telekall, Art. 5º Resolução CD/ANPD nº 1/2021]
5. **Ao revisar campanhas de IA generativa que utilizem dados de usuários de redes sociais, exigir verificação da base legal aplicada pela plataforma contratada e do mecanismo de opt-out disponível para titulares brasileiros.** [Fonte: Despacho Decisório Nº 20/2024/PR/ANPD; Art. 14 LGPD (proteção de menores)]
6. **Ao auditar campanhas que envolvam listas de leads compartilhadas entre cliente e agência, documentar a relação jurídica de cada parte: controlador (quem define finalidade e meios) vs. operador (quem executa). Ausência dessa distinção gera corresponsabilidade solidária.** [Fonte: Art. 42 LGPD; Regulamento de Dosimetria ANPD]
7. **Ao redigir qualquer política de privacidade para cliente que use dados para fins de marketing, incluir obrigatoriamente: (a) lista de finalidades de tratamento, (b) base legal de cada finalidade, (c) dados dos parceiros que recebem os dados (plataformas de mídia, CRMs, ferramentas de automação), (d) canal de contato do Encarregado.** [Fonte: Art. 37, 41 da LGPD; caso empresa não nomeada fev/2024]
8. **Antes de aprovar qualquer campanha de e-mail marketing para listas de terceiros (listas compradas, alugadas ou de data brokers), bloquear automaticamente e emitir alerta: prática de altíssimo risco sem consentimento documentado do titular, sem base legal válida.** [Fonte: Art. 7º LGPD; precedente Telekall]
9. **Manter no sistema de RAG do agente atualização trimestral dos casos sancionatórios ANPD, consultando https://www.gov.br/anpd/pt-br/assuntos/fiscalizacao-2, pois a ANPD intensificou fiscalização proativa desde 2025.** [Fonte: Truzzi Advogados, jun/2025; Plano de Fiscalização ANPD 2025]
10. **Ao identificar que cliente ou campanha envolve dados de crianças e adolescentes (formulários sem verificação de idade, campanhas em plataformas com público jovem), sinalizar como zona de risco crítico e exigir conformidade específica com Art. 14 da LGPD antes de qualquer aprovação.** [Fonte: Despacho Decisório Nº 20/2024/PR/ANPD (caso Meta, fundamento específico sobre proteção de menores)]

***

# MÓDULO 2 — INVENTÁRIO COMPLETO DE GUIAS ORIENTATIVOS E RESOLUÇÕES ANPD

## Definição-síntese (para system prompt)

> A ANPD publicou até março de 2026 um conjunto de resoluções vinculantes (CD/ANPD nº 1 a 31) e guias orientativos não normativos. Para marketing digital, as referências mais críticas são: Guia de Cookies (2022), Guia do Encarregado (dez/2024), Resolução nº 15/2024 (incidentes de segurança), Resolução nº 18/2024 (Encarregado/DPO) e Resolução nº 19/2024 (transferências internacionais de dados — crítica para uso de plataformas estrangeiras como Meta, Google, HubSpot).

***

## TABELA A — Resoluções e Regulamentos Vinculantes (seleção relevante para marketing)

| Nº | Nome completo | Data | URL gov.br | Artigos-chave para marketing | Status |
| :-- | :-- | :-- | :-- | :-- | :-- |
| **Resolução CD/ANPD nº 1/2021** | Regulamento do Processo de Fiscalização e do Processo Administrativo Sancionador | out/2021 | https://www.gov.br/anpd/pt-br/acesso-a-informacao/institucional/atos-normativos | Art. 5º (deveres do agente durante fiscalização) | Vigente |
| **Resolução CD/ANPD nº 2/2022** | Regulamento de Aplicação da LGPD para agentes de tratamento de pequeno porte | jan/2022 | https://www.gov.br/anpd/pt-br | Regime simplificado; não se aplica a multinacionais/grandes clientes | Vigente |
| **Resolução CD/ANPD nº 4/2023** | Regulamento de Dosimetria e Aplicação de Sanções Administrativas | fev/2023 | https://www.gov.br/anpd/pt-br/acesso-a-informacao/institucional/atos-normativos | Critérios de cálculo de multas; fatores agravantes e atenuantes | Vigente |
| **Resolução CD/ANPD nº 15/2024** | Regulamento de Comunicação de Incidente de Segurança | abr/2024 | https://www.abrapp.org.br/legislacao/resolucao-cd-anpd-no-15-de-24-de-abril-de-2024/ | Prazos de comunicação; obrigações do controlador; notificação à ANPD e aos titulares | Vigente |
| **Resolução CD/ANPD nº 18/2024** | Regulamento sobre Atuação do Encarregado pelo Tratamento de Dados Pessoais (DPO) | jul/2024 | https://www.tjba.jus.br/extrajudicial/wp-content/uploads/2024/08/RESOLUCAO-ANPD-No-18-Encarregado-de-Dados.pdf | Art. 7–16 (obrigações do DPO; nomeação; canal de comunicação) | Vigente |
| **Resolução CD/ANPD nº 19/2024** | Regulamento de Transferência Internacional de Dados Pessoais | ago/2024 | https://www.gov.br/anpd/pt-br/assuntos/noticias/resolucao-normatiza-transferencia-internacional-de-dados | Bases legais para transferência; DPA com operadores internacionais; cláusulas-padrão | Vigente |
| **Resolução CD/ANPD nº 23/2024** | Agenda Regulatória 2025–2026 | dez/2024 | https://www.gov.br/anpd | Temas prioritários: IA, crianças, legítimo interesse | Vigente |
| **Resolução CD/ANPD nº 30/2025** | Mapa de Temas Prioritários 2026–2027 | dez/2025 | https://www.gov.br/anpd/pt-br/acesso-a-informacao/institucional/atos-normativos | IA, compartilhamento de dados, direitos dos titulares | Vigente |
| **Resolução CD/ANPD nº 31/2025** | Altera Agenda Regulatória 2025–2026 | dez/2025 | https://legismap.com.br/leis-e-normas/resolucao-cd-anpd-n-031-de-23-12-2025 | Ajustes na agenda de regulamentação de IA e legítimo interesse | Vigente |

[Fonte: ANPD, Regulamentações oficiais: https://www.gov.br/anpd/pt-br/acesso-a-informacao/institucional/atos-normativos/regulamentacoes_anpd][^11]

***

## TABELA B — Guias Orientativos (não normativos, referência de interpretação)

| Nome completo | Data | URL gov.br | Resumo | Relevância para agência de marketing |
| :-- | :-- | :-- | :-- | :-- |
| **Guia Orientativo de Cookies e Proteção de Dados Pessoais** | out/2022 | https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia-orientativo-cookies | Define bases legais para cada tipo de cookie; orienta sobre consentimento vs. legítimo interesse; recomenda cookie banner granular | **ALTA** — diretamente aplicável a toda landing page, site e campanha digital |
| **Guia Orientativo sobre Atuação do Encarregado pelo Tratamento de Dados Pessoais** | dez/2024 | https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/copy_of_guia_da_atuacao_do_encarregado_anpd | Complementa Resolução nº 18/2024; orienta sobre nomeação, conflito de interesses, substituto, canal de comunicação | **ALTA** — todo cliente da agência deve ter DPO conforme este guia |
| **Guia sobre RIPD (Relatório de Impacto à Proteção de Dados — DPIA)** | 2021 (versão inicial) | https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes | Orienta quando elaborar RIPD, estrutura mínima, quem deve elaborar | **ALTA** — campanhas com dados sensíveis (saúde/estética) ou em larga escala exigem RIPD |
| **Guia sobre Segurança da Informação** | 2021 | https://www.gov.br/anpd/pt-br/centrais-de-conteudo | Medidas técnicas e administrativas para proteção de dados | **MÉDIA** — relevante para contratos com clientes sobre obrigações de segurança |
| **Guia sobre Bases Legais** | 2023 | https://www.gov.br/anpd/pt-br/centrais-de-conteudo | Orienta sobre aplicação de cada hipótese do Art. 7º | **ALTA** — base para qualquer análise de legalidade de campanha |
| **Guia sobre Legítimo Interesse** | 🔄 **STATUS: EM TRAMITAÇÃO** — não publicado como guia independente até março/2026 | Previsto na Agenda Regulatória | Regulamentação específica do legítimo interesse prevista na Agenda 2025–2026 | **ALTA** (quando publicado) — afeta toda operação de marketing que usa Art. 7º, IX |

[Fonte: ANPD, notícia do Guia do Encarregado: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-lanca-guia-sobre-atuacao-do-encarregado] [Fonte: Sindinfor, análise das normativas ANPD: https://sindinfor.org.br/guia-pratico-das-novas-normativas-da-anpd-como-se-preparar-e-evitar-riscos-regulatorios/][^12][^13]

***

## Análise Expandida dos Documentos Críticos

### 1. Guia de Cookies e Proteção de Dados Pessoais (ANPD, 2022)

O Guia de Cookies da ANPD é o documento mais diretamente aplicável ao dia a dia de uma agência de marketing digital [Fonte: PDF oficial ANPD, https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia-orientativo-cookies-e-protecao-de-dad...]. Seus pontos críticos para operações de marketing:[^14]

**Bases legais por tipo de cookie:**

- **Cookies estritamente necessários** (funcionamento técnico do site): **legítimo interesse** é base legal adequada, sem necessidade de consentimento [Fonte: Guia ANPD Cookies, p.23-24][^14]
- **Cookies analíticos/de medição de audiência**: **legítimo interesse** pode ser aplicado "em determinados contextos" — mas exige avaliação caso a caso do teste de balanceamento [Fonte: LEC.com.br, análise do Guia ANPD: https://lec.com.br/guia-orientativo-da-anpd/][^15]
- **Cookies de publicidade e remarketing (marketing cookies)**: **consentimento** é a base legal recomendada; o Guia ressalva que "legítimo interesse nem sempre poderá ser utilizado" para cookies publicitários e recomenda aplicar o teste de balanceamento para verificar se os direitos do titular prevalecem [Fonte: Souto Correa Advogados, análise: https://www.soutocorrea.com.br/client-alerts/anpd-lanca-guia-orientativo-sobre-cookies-e-protecao-de-dados-pessoais/][^16]
- **Cookies de funcionalidade** (preferências do usuário): **consentimento** recomendado [Fonte: AdOpt/GoAdopt, análise detalhada do Guia: https://goadopt.io/blog/anpd-cookies-guia-orientativo-cookies-protecao-de-dados-pessoais/][^17]

**Implicações práticas:**

- Todo pixel de remarketing (Meta Pixel, Google Tag, TikTok Pixel) ativado sem consentimento explícito do visitante constitui violação ao Guia de Cookies ANPD
- Cookie banner com design de "dark pattern" (ex: botão "aceitar tudo" em verde e "recusar" escondido) não atende ao requisito de consentimento **livre, informado e inequívoco (freely given, specific, informed and unambiguous consent)** — Art. 8º LGPD
- Política de cookies deve ser documento separado da Política de Privacidade, acessível de forma destacada
- O Guia não proíbe cookies de publicidade, mas exige que o consentimento seja obtido antes da ativação — não após

***

### 2. Guia sobre Legítimo Interesse

🔄 **STATUS: EM TRAMITAÇÃO** — Guia específico sobre legítimo interesse **não foi publicado pela ANPD até março de 2026**. A regulamentação do legítimo interesse está prevista na Agenda Regulatória 2025–2026 (Resolução CD/ANPD nº 23/2024 e alterações da Resolução nº 31/2025) como tema prioritário [Fonte: Sindinfor, análise normativas ANPD: https://sindinfor.org.br/guia-pratico-das-novas-normativas-da-anpd]. Até a publicação do guia específico, a referência interpretativa mais robusta disponível é o framework do Data Privacy Brasil/Bruno Bioni (detalhado no Módulo 3).[^12]

***

### 3. Resolução CD/ANPD nº 18/2024 + Guia do Encarregado (dezembro 2024)

A **Resolução CD/ANPD nº 18, de 16 de julho de 2024** aprova o Regulamento sobre atuação do Encarregado pelo tratamento de dados pessoais (DPO — Data Protection Officer) [Fonte: TJBA, PDF da Resolução: https://www.tjba.jus.br/extrajudicial/wp-content/uploads/2024/08/RESOLUCAO-ANPD-No-18-Encarregado-de-Dados.pdf]. Em **19 de dezembro de 2024**, a ANPD publicou o Guia Orientativo complementar [Fonte: ANPD, notícia oficial: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-lanca-guia-sobre-atuacao-do-encarregado].[^18][^13]

**Pontos críticos:**

- O Encarregado deve ser canal de comunicação entre o controlador e a ANPD em processos administrativos [Fonte: Campos Thomaz, análise do Guia: https://camposthomaz.com/comunicado-ct/anpd-publica-novo-guia-orientativo][^19]
- O Guia recomenda indicação simultânea de um **substituto** para o Encarregado
- O Guia orienta sobre prevenção de **conflitos de interesse**: o Encarregado não deve estar subordinado a quem decide as finalidades de tratamento
- Para agências: a agência como **operadora** de dados dos clientes não precisa obrigatoriamente nomear DPO (depende do volume de tratamento), mas o **cliente/controlador** precisa. O contrato deve deixar isso explícito
- A fiscalização de dez/2024 tornou o cumprimento do Art. 41 + Resolução 18/2024 uma prioridade de enforcement imediato [Fonte: ANPD fiscalização 20 empresas][^9]

***

### 4. Guia sobre RIPD (Relatório de Impacto à Proteção de Dados — Data Protection Impact Assessment / DPIA)

O Guia ANPD sobre RIPD (DPIA) orienta que o relatório é obrigatório quando solicitado pela ANPD (Art. 38 LGPD) e recomendado quando o tratamento é de alto risco [Fonte: caso empresa não nomeada, fev/2024: advertência por não elaborar RIPD após solicitação ANPD].[^3]

**Para agências de marketing, o RIPD é especialmente relevante para:**

- Clínicas de estética avançada: tratamento de **dados sensíveis de saúde** (Art. 11 LGPD) — risco inerentemente alto
- Escritórios de advocacia: dados de processos judiciais, dados sensíveis
- Campanhas com criação de **perfis detalhados** de comportamento (profiling) para targeting
- Uso de IA/machine learning para **decisões automatizadas** que afetam titulares (lead scoring, credit scoring)
- Tratamento em larga escala de dados de crianças (Art. 14 LGPD)

**Estrutura mínima do RIPD segundo orientações ANPD:**

1. Descrição sistemática das operações de tratamento
2. Finalidade e base legal
3. Avaliação de necessidade e proporcionalidade
4. Riscos para os titulares
5. Medidas para mitigação dos riscos

***

### 5. Regulamento de Dosimetria de Sanções (Resolução CD/ANPD nº 4/2023)

O Regulamento de Dosimetria define como as multas são calculadas [Fonte: referência em múltiplos casos ANPD]. **Fatores que agravam a sanção:**[^3]

- Reincidência (mesma infração cometida novamente)
- Dolo (intenção de violar)
- Descumprimento de ordens da ANPD (infração autônoma, como no caso Telekall)
- Obstrução à fiscalização
- Grande volume de dados ou número de titulares afetados
- Tratamento de dados sensíveis ou de crianças

**Fatores que atenuam a sanção:**

- Adoção de medidas corretivas voluntárias antes da sanção
- Cooperação total com a ANPD durante investigação
- Implementação de política de governança em privacidade
- Comunicação proativa de incidentes

**Desconto de 25%:** previsto para pagamento imediato sem recurso (precedente Telekall) [Fonte: Araújo Policastro: https://araujopolicastro.com.br/anpd-aplica-primeiras-sancoes-por-violacao-a-lgpd/][^1]

***

### 6. IA e Proteção de Dados: Regulamentação em Curso

🔄 **STATUS: EM TRAMITAÇÃO** — A ANPD não publicou até março de 2026 regulamento ou guia específico e definitivo sobre IA e proteção de dados. O tema consta como prioritário na Agenda Regulatória 2025–2026 (Resolução CD/ANPD nº 23/2024) e no Mapa de Temas Prioritários 2026–2027 (Resolução CD/ANPD nº 30/2025) [Fonte: gov.br, lista de regulamentações: https://www.gov.br/anpd/pt-br/acesso-a-informacao/institucional/atos-normativos/regulamentacoes_anpd]. O caso Meta/IA (2024) estabeleceu precedente cautelar aplicando Art. 7º, IX e Art. 10 ao contexto de IA generativa, mas sem regulamento específico publicado.[^11]

***

⚠️ **ZONAS DE RISCO ESPECÍFICAS — MÓDULO 2**

> 1. **Ativar cookies de publicidade sem consentimento** = violação direta ao Guia de Cookies ANPD (mais comum erro de agências)
> 2. **Usar legítimo interesse para cookies analíticos sem teste de balanceamento** = risco moderado (guia admite mas exige avaliação)
> 3. **Cliente sem Encarregado/DPO nomeado** = risco de processo fiscalizatório imediato (precedente dez/2024)
> 4. **Compartilhamento de dados com plataformas internacionais (Meta, Google, HubSpot) sem cláusula de transferência internacional** = violação à Resolução nº 19/2024
> 5. **Tratamento de dados de saúde em clínicas de estética sem RIPD** = alto risco, Art. 11 + Art. 38 LGPD

***

## INSTRUÇÕES PARA O AGENTE — MÓDULO 2

1. **Ao gerar política de privacidade para site com pixels de rastreamento ou cookies de publicidade, aplicar obrigatoriamente os requisitos do Guia de Cookies ANPD (2022): (a) base legal = consentimento para cookies de marketing; (b) cookie banner com opt-in granular por categoria; (c) mecanismo de opt-out a qualquer momento; (d) política de cookies como documento separado.** [Fonte: Guia ANPD Cookies 2022, https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia-orientativo-cookies]
2. **Ao auditar cookie banner de cliente, verificar: (a) cookies de publicidade/remarketing NÃO estão ativados por padrão antes do consentimento; (b) opção de recusa é tão acessível quanto a de aceite; (c) lista de parceiros de terceiros que recebem dados via cookie está declarada. Se qualquer item falhar, emitir alerta bloqueador.** [Fonte: Guia ANPD Cookies 2022; Art. 8º LGPD (consentimento livre e informado)]
3. **Ao avaliar se legítimo interesse pode ser base legal para cookies analíticos, aplicar o teste de balanceamento: (a) há interesse legítimo genuíno do controlador? (b) o tratamento é necessário para essa finalidade? (c) os direitos do titular prevalecem? Se qualquer etapa falhar, usar consentimento.** [Fonte: Guia ANPD Cookies 2022, p.23-24; Art. 10 LGPD]
4. **Antes de assinar contrato com cliente, verificar se ele possui Encarregado/DPO designado com canal de comunicação público conforme Resolução CD/ANPD nº 18/2024. Se não possuir, incluir cláusula de obrigação e prazo de adequação.** [Fonte: Resolução CD/ANPD nº 18, 16/07/2024; Guia do Encarregado, dez/2024]
5. **Ao gerar contrato com cliente que use plataformas internacionais (Meta, Google Analytics, HubSpot, Salesforce), incluir obrigatoriamente cláusula de transferência internacional de dados pessoais conforme Resolução CD/ANPD nº 19/2024, identificando os países de destino e a base legal para a transferência.** [Fonte: Resolução CD/ANPD nº 19/2024]
6. **Ao criar política de privacidade para clínica de estética ou profissional de saúde, classificar dados de saúde como dados sensíveis (Art. 11 LGPD), exigir consentimento específico e destacado, e avaliar necessidade de RIPD antes de iniciar qualquer campanha de remarketing baseada em dados de saúde.** [Fonte: Art. 11 LGPD; Guia RIPD ANPD; Resolução CD/ANPD nº 4/2023 (fatores de agravamento)]
7. **Para projetos envolvendo IA (chatbots, lead scoring automatizado, personalização por algoritmo), informar ao cliente que regulamentação específica de IA + LGPD está em tramitação na ANPD (Agenda 2025–2026) e que o risco regulatório é elevado. Aplicar cautela máxima: documentar base legal, finalidade e mecanismo de revisão humana (Art. 20 LGPD).** [Fonte: Resolução CD/ANPD nº 23/2024 (Agenda Regulatória); Art. 20 LGPD; Caso Meta/IA]
8. **Ao calcular severidade de risco em auditoria de campanha, aplicar os fatores agravantes da Resolução CD/ANPD nº 4/2023: dolo, reincidência, dados sensíveis, dados de crianças, grande volume de titulares. Qualquer fator agravante presente = risco alto.** [Fonte: Resolução CD/ANPD nº 4/2023 (Regulamento de Dosimetria)]
9. **Ao detectar incidente de segurança envolvendo dados de leads ou clientes (vazamento de banco de dados, acesso não autorizado a CRM), acionar imediatamente o protocolo conforme Resolução CD/ANPD nº 15/2024: comunicação à ANPD e aos titulares dentro dos prazos estabelecidos. Atraso na comunicação = infração autônoma.** [Fonte: Resolução CD/ANPD nº 15, abr/2024; caso empresa não nomeada, fev/2024]

***

# MÓDULO 3 — BRUNO BIONI E DATA PRIVACY BRASIL: DOUTRINA APLICADA AO MARKETING

## Definição-síntese (para system prompt)

> Bruno Bioni (Doutor USP, fundador da Associação Data Privacy Brasil de Pesquisa) é o principal doutrinador brasileiro em proteção de dados, influenciando diretamente a LGPD e as regulamentações ANPD. O Data Privacy Brasil publicou o framework de **Avaliação de Legítimo Interesse (LIA — Legitimate Interest Assessment)** mais detalhado disponível em português, com teste multifatorial de proporcionalidade aplicável a operações de marketing digital. Na ausência de guia regulatório específico da ANPD sobre legítimo interesse, este framework é a referência de mercado mais adotada.

***

## 3.1 Framework de Legítimo Interesse para Marketing

### O Teste de Proporcionalidade / LIA (Legitimate Interest Assessment)

O Data Privacy Brasil publicou o estudo **"O Legítimo Interesse na LGPD: quadro geral e exemplos de aplicação"** (2021) [Fonte: PDF Data Privacy Brasil: https://www.dataprivacybr.org/wp-content/uploads/2021/10/O-legitimo-interesse-na-LGPD.pdf] e sua versão em inglês [Fonte: PDF Data Privacy Brasil Research Association: https://www.observatorioprivacidade.com.br/wp-content/uploads/2021/05/LI-under-LGPD_Data-Privacy-Brasil-Research-Association.pdf], estabelecendo o LIA com as seguintes fases:[^20][^21]

**Fase 1 — Legitimidade do Interesse (Purpose Test)**

- O interesse do controlador é lícito, específico e genuíno?
- O interesse está em consonância com o princípio da boa-fé e não frustra a legítima expectativa do titular?
- Exemplo para marketing: campanha de remarketing para visitantes que abandonaram carrinho tem interesse legítimo genuíno — sim. Compra de listas de terceiros sem vínculo anterior — não.

**Fase 2 — Necessidade (Necessity Test)**

- O tratamento de dados é estritamente necessário para atingir a finalidade?
- Há forma alternativa menos invasiva de atingir o mesmo resultado?
- Princípio da minimização de dados: apenas os dados mínimos necessários devem ser tratados.
- Exemplo para marketing: pixel de conversão que captura dados completos de navegação quando só precisa confirmar a conversão — falha no teste de necessidade.

**Fase 3 — Balanceamento e Salvaguardas (Balancing Test)**

- Os interesses do controlador prevalecem sobre os direitos e liberdades fundamentais do titular?
- Pontos a considerar: natureza dos dados, expectativa do titular, impacto no exercício de direitos, vulnerabilidade do titular.
- Transparência e mecanismo de opt-out como salvaguardas que podem inclinar o balanceamento a favor do controlador.

[Fonte: Eticca, análise detalhada do teste: https://www.eticca.com.br/o-teste-de-proporcionalidade-do-legitimo-interesse/] [Fonte: UFRGS, aplicação das bases legais ao marketing: https://www.seer.ufrgs.br/resseveraverumgaudium/article/download/125569/87251][^22][^23]

***

### Aplicação Específica para Operações de Marketing

| Operação | Legítimo Interesse é suficiente? | Condições / Observações |
| :-- | :-- | :-- |
| **Remarketing (visitantes do site)** | Possivelmente sim, com ressalvas | Exige LIA documentado; cookie banner com opt-out claro; dados mínimos; relação prévia com o titular |
| **Lookalike audiences (Meta/Google)** | Risco alto — provavelmente não sem consentimento | Envolve compartilhamento com terceiro; titular não tem relação direta com controlador; ANPD tende a exigir consentimento |
| **Lead scoring (pontuação automatizada)** | Depende do impacto | Se gerar decisão que afete o titular, Art. 20 LGPD exige revisão humana a pedido; LIA exige teste de necessidade |
| **E-mail marketing para base própria (opt-in prévio)** | Sim, com transparência | Titular tem relação prévia; finalidade compatível com a original; opt-out obrigatório em cada disparo |
| **WhatsApp marketing para leads opt-in** | Possivelmente sim | Mesmo raciocínio do e-mail marketing; mas regras de opt-in da Meta são cumulativas com a LGPD |

[Fonte: Data Privacy Brasil, "O Legítimo Interesse na LGPD", 2021] [Fonte: UFRGS, aplicabilidade das bases legais ao marketing digital][^23][^20]

***

## 3.2 Publicações Data Privacy Brasil 2024–2026

**Nota de integridade:** O site www.dataprivacybr.org estava fora do escopo de fetch direto nesta pesquisa. As publicações específicas de 2024–2026 do Data Privacy Brasil **não foram encontradas com fonte confiável suficiente** para listagem com URLs verificados. A organização é ativa e publica regularmente no site oficial e no Observatório da Privacidade (observatorioprivacidade.com.br). Recomenda-se consulta direta em https://www.dataprivacybr.org/publicacoes para o inventário atualizado.

***

## 3.3 Contribuições para Regulamentação e IA

Bruno Bioni e o Data Privacy Brasil participaram ativamente das consultas públicas sobre a regulamentação da LGPD [Fonte: Data Privacy Brasil Research Association, mencionada em múltiplas publicações acadêmicas]. Sobre IA especificamente: o Data Privacy Brasil publicou posicionamentos sobre a necessidade de regulamentação específica para IA no Brasil, incluindo participação nos debates sobre o PL 2338/2023 (Marco Regulatório da IA), mas publicações específicas de 2024–2026 sobre este tema **não foram encontradas com URL verificável** nesta pesquisa. Consultar: https://www.dataprivacybr.org.[^21][^20]

***

## 3.4 Checklists e Frameworks Práticos

O framework mais diretamente utilizável publicado pelo Data Privacy Brasil é o próprio **LIA (Legitimate Interest Assessment) Template** publicado no estudo "O Legítimo Interesse na LGPD" (2021), que inclui exemplo prático completo de aplicação do teste a um caso hipotético [Fonte: PDF Data Privacy Brasil: https://www.dataprivacybr.org/wp-content/uploads/2021/10/O-legitimo-interesse-na-LGPD.pdf]. Checklists adicionais específicos para marketing de 2024–2026: **não encontrado com fonte confiável** — consultar diretamente o repositório do Data Privacy Brasil.[^20]

***

⚠️ **ZONAS DE RISCO ESPECÍFICAS — MÓDULO 3**

> 1. **Usar legítimo interesse como base "coringa"** para qualquer operação de marketing sem passar pelo LIA = prática que falha no teste de necessidade e balanceamento
> 2. **Remarketing via lookalike audiences** sem consentimento é o cenário de maior risco: titular não tem relação com o controlador, dados são compartilhados com terceiro (Meta/Google), volume é amplo — todos fatores que pesam contra o controlador no balanceamento
> 3. **E-mail marketing sem opt-out claro em cada mensagem** = viola a salvaguarda mínima que poderia inclinar o balanceamento a favor do controlador
> 4. **Lead scoring que implica decisão automatizada** sem mecanismo de revisão humana = violação do Art. 20 LGPD, independente da base legal

***

## INSTRUÇÕES PARA O AGENTE — MÓDULO 3

1. **Ao avaliar se legítimo interesse (Art. 7º, IX c/c Art. 10 LGPD) é base legal adequada para uma campanha, aplicar obrigatoriamente o teste em 3 fases: (1) legitimidade do interesse, (2) necessidade, (3) balanceamento. Se falhar em qualquer etapa, recomendar consentimento explícito e documentar o motivo.** [Fonte: Data Privacy Brasil, "O Legítimo Interesse na LGPD", 2021, https://www.dataprivacybr.org/wp-content/uploads/2021/10/O-legitimo-interesse-na-LGPD.pdf]
2. **Para remarketing (visitantes do site), o LIA pode ser favorável SE: (a) titular visitou o site voluntariamente; (b) cookie banner com opt-out granular está ativo; (c) dados tratados são mínimos (não incluem dados sensíveis); (d) o LIA está documentado no ROT do cliente. Ausência de qualquer condição = usar consentimento.** [Fonte: Data Privacy Brasil, LIA framework 2021; Guia ANPD Cookies 2022]
3. **Para lookalike audiences (Meta/Google), não aprovar campanha com base em legítimo interesse sem análise jurídica específica do cliente: o compartilhamento de dados com terceiro (plataforma de mídia) para criação de público similar tende a reprovar no teste de balanceamento para a maioria dos cenários de marketing.** [Fonte: Data Privacy Brasil, LIA framework 2021; Art. 7º, IX c/c Art. 10 LGPD]
4. **Para e-mail marketing para base própria (opt-in documentado), legítimo interesse pode ser base legal adequada; exigir que todo disparo contenha link de opt-out funcional e que a finalidade do e-mail seja compatível com a finalidade declarada no momento do opt-in.** [Fonte: Data Privacy Brasil, LIA framework; Art. 10, I LGPD (atividades do controlador)]
5. **Ao revisar campanhas de lead scoring ou decisão automatizada (algoritmos de pontuação, chatbots que filtram leads), verificar se há mecanismo de revisão humana a pedido do titular conforme Art. 20 LGPD. Ausência = alerta bloqueador, independente da base legal.** [Fonte: Art. 20 LGPD; Data Privacy Brasil, posicionamentos sobre IA]
6. **Documentar o LIA como parte do ROT do cliente para cada operação de marketing que use legítimo interesse. O LIA deve ser revisado anualmente ou quando a finalidade de tratamento mudar.** [Fonte: Data Privacy Brasil, LIA framework 2021; Art. 37 LGPD (ROT)]
7. **Ao gerar cláusulas contratuais LGPD para contratos entre agência e cliente, incluir representação do cliente de que realizou o LIA para operações de marketing baseadas em legítimo interesse e que o resultado foi favorável ao controlador.** [Fonte: Data Privacy Brasil, LIA framework; Art. 42, §1º LGPD (responsabilidade solidária)]

***

# MÓDULO 4 — WHATSAPP BUSINESS API: COMPLIANCE META + LGPD (2025–2026)

## Definição-síntese (para system prompt)

> A partir de 01/07/2025, o WhatsApp Business API (Application Programming Interface) migrou para modelo de cobrança por mensagem entregue (per-message billing), por categoria de template. Para compliance, toda campanha via WhatsApp API exige dupla conformidade: (1) política de opt-in da Meta (regras técnicas de consentimento da plataforma) e (2) base legal da LGPD (Art. 7º, I — consentimento, ou Art. 7º, IX — legítimo interesse com LIA). As duas camadas são cumulativas, não alternativas.

***

## 4.1 Novo Modelo de Cobrança (vigente desde 01/07/2025)

### Migração: Conversa → Mensagem por Mensagem

Até 30/06/2025, o modelo de cobrança era **por conversa** (janela de 24 horas de interação, tarifa única por janela). A partir de 01/07/2025, a Meta migrou para **cobrança por template entregue (per-message/per-template)**, onde cada template enviado e entregue é cobrado individualmente com base em duas variáveis: categoria do template e código do país do destinatário [Fonte: Digisac, documentação do novo modelo: https://digisac.com.br/nova-cobranca-whatsapp-api-2025/] [Fonte: Whatsflow, análise do novo modelo: https://whatsflow.com.br/whatsapp-business-2025-nova-forma-de-cobranca/].[^24][^25]

### Categorias de Templates

| Categoria | Definição | Uso para marketing | Cobrança |
| :-- | :-- | :-- | :-- |
| **Marketing** | Mensagens promocionais, ofertas, lançamentos, novidades, convites | Principal categoria de campanhas outbound | Cobrada por template entregue |
| **Utility (Utilidade)** | Mensagens transacionais: confirmação de pedido, boleto, agendamento, atualização de status | Pós-venda, nurturing transacional | Cobrada por template entregue; **isenta se enviada dentro da janela de 24h iniciada pelo cliente** |
| **Authentication (Autenticação)** | Códigos de verificação, OTP (One-Time Password) | Verificação de identidade | Cobrada por template entregue |
| **Service (Serviço)** | Respostas a mensagens iniciadas pelo cliente (conversas de atendimento) | Suporte, resposta a leads inbound | **1.000 mensagens/mês gratuitas por conta WABA** |

[Fonte: Digisac, categorias de templates: https://digisac.com.br/nova-cobranca-whatsapp-api-2025/] [Fonte: Huggy Blog, análise do novo modelo jul/2025: https://blog.huggy.io/nova-precificacao-do-whatsapp/][^25][^26]

### Janelas de Atendimento

- **Janela de 24 horas (Customer Service Window):** Iniciada por mensagem do cliente (inbound). Dentro desta janela, templates de **utilidade são isentos de cobrança**. Templates de **marketing dentro da janela ainda são cobrados**. [Fonte: Digisac][^25]
- **Click-to-WhatsApp (CTWA):** Janela de **72 horas** iniciada quando o usuário clica em anúncio CTWA. Vantagem para marketing: janela maior para engajamento, conversas iniciadas pelo usuário (portanto Service, com 1.000 gratuitas/mês). [Fonte: não encontrado com fonte confiável o detalhamento completo das regras CTWA no novo modelo pós-julho/2025 — consultar documentação atual em developers.facebook.com/docs/whatsapp]

***

## 4.2 Regras de Opt-in e Consentimento

### Requisitos Meta para Opt-in (2025/2026)

A Meta exige que todo destinatário de mensagens de template de **marketing** tenha dado opt-in explícito e documentado para receber comunicações da empresa via WhatsApp. Os requisitos mínimos da Meta para opt-in válido são: [Fonte: Whatsflow, regras da plataforma: https://whatsflow.com.br/whatsapp-business-2025-nova-forma-de-cobranca/][^24]

- O opt-in deve deixar claro que o usuário concordará em receber mensagens via WhatsApp
- Deve identificar o nome da empresa que enviará as mensagens
- Deve ser obtido de forma explícita (não implícita pelo fornecimento do número de telefone)
- Deve haver mecanismo de opt-out claro


### Interseção Opt-in Meta × LGPD

A conformidade com as regras de opt-in da Meta **não equivale automaticamente** ao consentimento válido da LGPD. A LGPD exige consentimento **livre, informado e inequívoco (freely given, specific, informed and unambiguous consent)** conforme Art. 7º, I c/c Art. 8º. Para ser válido sob a LGPD, o opt-in deve:

1. Ser obtido para finalidade específica (ex: "receber ofertas de imóveis de alto padrão via WhatsApp")
2. Ser revogável a qualquer momento com a mesma facilidade com que foi concedido (Art. 8º, §5º LGPD)
3. Ser documentado pelo controlador (ônus da prova é do controlador — Art. 8º, §2º LGPD)
4. Não ser condicionado à prestação do serviço quando não for necessário para esse fim (Art. 8º, §3º LGPD)

A diferença prática: opt-in em formulário de landing page que diz apenas "aceito os termos e política de privacidade" **não é suficiente** para a LGPD — precisa de checkbox separado e específico para WhatsApp marketing [Fonte: Art. 7º, I e Art. 8º LGPD].

***

## 4.3 Templates e Políticas de Mensagens

### Processo de Aprovação de Templates

- Templates de **marketing** passam por revisão manual ou automatizada da Meta antes de serem usados
- A Meta verifica: linguagem não enganosa, ausência de conteúdo proibido (jogos de azar, produtos regulados sem autorização, conteúdo adulto), formatação adequada
- Templates reprovados podem ser revisados e resubmetidos, mas rejeições repetidas afetam o quality rating da conta


### Quality Rating e Message Limits

A Meta monitora continuamente a qualidade das contas WABA (WhatsApp Business Account) com base em:

- Taxa de bloqueio pelo destinatário (block rate)
- Taxa de denúncia de spam (report rate)
- Taxa de engajamento (respostas, cliques)

**Tiers de envio** são determinados pelo quality rating:

- Quality Rating alto → limites de envio mais elevados
- Quality Rating baixo → limite reduzido ou conta em revisão/suspensão

[Fonte: Huggy Blog, análise detalhada: https://blog.huggy.io/nova-precificacao-do-whatsapp/][^26]

### Causas de Suspensão de Conta

Violações que causam suspensão ou banimento da conta WABA incluem: envio de templates não aprovados, envio de spam para usuários sem opt-in, alta taxa de bloqueio/denúncia, uso de números adquiridos ilegalmente (listas compradas), e violação da **Acceptable Use Policy (AUP)** da Meta. Casos específicos documentados de suspensão de agências brasileiras: **não encontrado com fonte confiável** nesta pesquisa.

***

## 4.4 Interseção Meta + LGPD

### Documentação Oficial Meta sobre Compliance LGPD

A Meta possui documentação sobre privacidade e conformidade legal no WhatsApp Business, mas **documentação específica e oficial da Meta direcionada à LGPD brasileira** para API não foi encontrada com URL verificável nesta pesquisa. A documentação de privacidade aplicável é a **WhatsApp Business Platform Privacy Policy** (https://www.whatsapp.com/legal/business-data-processing-terms) que cobre o DPA (Data Processing Agreement) da plataforma.

### Estrutura Controlador × Operador (Controller vs. Processor)

No uso do WhatsApp Business API para campanhas de marketing:


| Parte | Papel LGPD | Responsabilidade |
| :-- | :-- | :-- |
| **Cliente (imobiliária, clínica, escritório)** | **Controlador (Controller)** | Define finalidade e meios do tratamento; responsável pela base legal; titular do opt-in |
| **Agência de marketing** | **Operador (Processor)** — quando executa em nome do cliente | Trata dados conforme instruções do controlador; responsável por segurança operacional; deve ter DPA com o cliente |
| **Meta/WhatsApp** | **Operador/Suboperador (Sub-processor)** | Trata dados para viabilizar o serviço de mensageria; possui seus próprios termos de DPA |

A agência pode ser considerada **controladora conjunta (joint controller)** se influenciar as finalidades de tratamento (ex: usar os dados para otimizar campanhas da própria agência). Neste caso, a responsabilidade é solidária (Art. 42 LGPD).

### Cláusulas Mínimas em Contratos com Clientes para WhatsApp API

Com base na Resolução CD/ANPD nº 19/2024 (transferência internacional) e Art. 39 da LGPD (contratos com operadores):

1. 

<span style="display:none">[^27][^28][^29][^30][^31][^32][^33][^34][^35][^36][^37][^38][^39][^40][^41][^42][^43][^44][^45]</span>

<div align="center">⁂</div>

[^1]: https://araujopolicastro.com.br/anpd-aplica-primeiras-sancoes-por-violacao-a-lgpd/

[^2]: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-aplica-a-primeira-multa-por-descumprimento-a-lgpd

[^3]: https://www.tauilchequer.com.br/pt/insights/publications/2024/02/anpd-applies-first-sanctions-of-2024

[^4]: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-determina-suspensao-cautelar-do-tratamento-de-dados-pessoais-para-treinamento-da-ia-da-meta

[^5]: https://g1.globo.com/politica/noticia/2024/08/30/anpd-acata-plano-de-conformidade-da-meta-e-libera-uso-de-dados-de-brasileiros-para-treinar-ia-usuario-podera-negar-acesso.ghtml

[^6]: https://www.qca.adv.br/anpd-suspende-tratamento-ia-da-meta/

[^7]: https://g1.globo.com/tecnologia/noticia/2024/12/13/anpd-notifica-20-empresas-por-descumprirem-regra-de-protecao-de-dados.ghtml

[^8]: https://ids.org.br/noticia/anpd-inicia-processo-de-fiscalizacao-de-20-empresas-por-falta-de-encarregado-e-canal-de-comunicacao-adequado/

[^9]: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-fiscaliza-20-empresas-por-falta-de-encarregado-e-canal-de-comunicacao

[^10]: https://truzzi.com.br/a-era-da-orientacao-acabou-as-primeiras-multas-da-anpd-e-o-novo-cenario-da-lgpd/

[^11]: https://www.gov.br/anpd/pt-br/acesso-a-informacao/institucional/atos-normativos/regulamentacoes_anpd

[^12]: https://sindinfor.org.br/guia-pratico-das-novas-normativas-da-anpd-como-se-preparar-e-evitar-riscos-regulatorios/

[^13]: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-lanca-guia-sobre-atuacao-do-encarregado

[^14]: https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia-orientativo-cookies-e-protecao-de-dados-pessoais.pdf

[^15]: https://lec.com.br/guia-orientativo-da-anpd/

[^16]: https://www.soutocorrea.com.br/client-alerts/anpd-lanca-guia-orientativo-sobre-cookies-e-protecao-de-dados-pessoais/

[^17]: https://goadopt.io/blog/anpd-cookies-guia-orientativo-cookies-protecao-dados-pessoais/

[^18]: https://www.tjba.jus.br/extrajudicial/wp-content/uploads/2024/08/RESOLUCAO-ANPD-No-18-Encarregado-de-Dados.pdf

[^19]: https://camposthomaz.com/comunicado-ct/anpd-publica-novo-guia-orientativo-sobre-atuacao-do-encarregado-pelo-tratamento-de-dados-pessoais/

[^20]: https://www.dataprivacybr.org/wp-content/uploads/2021/10/O-legitimo-interesse-na-LGPD.pdf

[^21]: https://www.observatorioprivacidade.com.br/wp-content/uploads/2021/05/LI-under-LGPD_Data-Privacy-Brasil-Research-Association.pdf

[^22]: https://www.eticca.com.br/o-teste-de-proporcionalidade-do-legitimo-interesse/

[^23]: https://www.seer.ufrgs.br/resseveraverumgaudium/article/download/125569/87251

[^24]: https://whatsflow.com.br/whatsapp-business-2025-nova-forma-de-cobranca/

[^25]: https://digisac.com.br/nova-cobranca-whatsapp-api-2025/

[^26]: https://blog.huggy.io/nova-precificacao-do-whatsapp/

[^27]: https://www.gov.br/anpd/pt-br/assuntos/fiscalizacao-2/saiba-como_fiscalizamos

[^28]: https://gsga.com.br/pt/informativo/anpd-divulga-lista-de-processos-de-fiscalizacao-em-andamento

[^29]: https://www.deeplegal.com.br/blog/como-automatizar-relatorios-de-conformidade-com-ia

[^30]: https://www.hapnerkroetz.com.br/publicacoes/anpd-aplica-primeira-multa-por-descumprimento-da-lgpd

[^31]: https://mmcafe.com.br/blog/lgpd-e-inteligencia-artificial-o-guia-definitivo-para-empresas-brasileiras-em-2026

[^32]: https://www1.tozzinifreire.com.br/boletins/anpd-dois-anos-de-fiscalizacao-e-aplicacao-de-sancoes-no-brasil

[^33]: https://privacidade.unicamp.br/2023/07/18/anpd-aplica-a-primeira-multa-por-descumprimento-a-lgpd/

[^34]: https://www.gov.br/anpd/pt-br/acesso-a-informacao/institucional/atos-normativos/atos_gestao_interna/resolucao-cd-anpd-no24-2025

[^35]: https://legismap.com.br/leis-e-normas/resolucao-cd-anpd-n-031-de-23-12-2025

[^36]: https://dspace.mj.gov.br/handle/1/14760

[^37]: https://www.toisa.com.br/noticias/anpd-aprova-mapa-de-temas-prioritarios-para-2024-2025

[^38]: https://www.abrapp.org.br/legislacao/resolucao-cd-anpd-no-15-de-24-de-abril-de-2024/

[^39]: https://www.gov.br/anpd/pt-br/assuntos/noticias/resolucao-normatiza-transferencia-internacional-de-dados

[^40]: https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/copy_of_guia_da_atuacao_do_encarregado_anpd.pdf

[^41]: https://www.ipea.gov.br/protecaodedados/arquivos/Resolucao_cd_regulamento_atuacao_encarregado.pdf

[^42]: https://www.trenchrossi.com/alertas-legais/anpd-publica-guia-orientativo-da-atuacao-do-encarregado-de-dados-pessoais/

[^43]: https://lgpd.embras.net/2024/12/20/anpd-lanca-guia-sobre-atuacao-do-encarregado/

[^44]: https://tiinside.com.br/13/12/2024/anpd-fiscaliza-20-empresas-por-falta-de-encarregado-e-canal-de-comunicacao-adequado/

[^45]: https://lefosse.com/noticias/alerta/anpd-publica-guia-orientativo-sobre-atuacao-do-encarregado-pelo-tratamento-de-dados-pessoais/


</content>
