---
source_file: perplexity-mod1-vinculo-pejotizacao.md
converted_at: 2026-03-24
original_extension: md
processor: Echo (aiox-m2m-etl)
extraction_quality: full
domain: Vínculo Empregatício, Pejotização e Corretores de Imóveis
source_type: perplexity-deep-research
source_tool: Perplexity Pro (Deep Research)
agent_target: juridica-trabalhista
squad: squad-cadarn-juridica
module: 1
module_title: Vínculo Empregatício — Corretores, Pejotização e Terceirização
---

<content>


# Você é um pesquisador especialista em Direito do Trabalho brasileiro, com foco em relações de trabalho no setor de serviços e no mercado imobiliário. Sua

tarefa é produzir um módulo exaustivo sobre vínculos empregatícios, pejotização e relações de trabalho de corretores de imóveis com imobiliárias.

Contexto de uso: Este documento será processado por um pipeline automatizado (M2M + RAG). O chunking é feito por headers Markdown (\#\# e \#\#\#). Os metadados
em HTML comment são parseados por regex antes do chunking e funcionam como tags de classificação semântica — mantenha o formato exato. Output
obrigatório: Markdown puro, sem exceções. O documento será carregado como base de conhecimento de um agente Claude Code (CLI) utilizado por profissionais
de uma agência de marketing digital e por equipes de RH de clientes premium (imobiliárias de luxo, clínicas de estética, escritórios de advocacia) em
capitais brasileiras, com foco em Vitória/ES.

  <!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 1] [TEMA: vinculo-empregaticio-pejotizacao-corretores] -->
Cubra obrigatoriamente:

1. **Vínculo de corretor de imóveis com imobiliária** — Este é o tema MAIS importante deste módulo:
    - Lei 6.530/78 (exercício da profissão de corretor) — arts. relevantes
    - Art. 6º, parágrafo único da Lei 6.530/78 — "corretor associado": natureza jurídica, quando há autonomia real
    - Os 4 requisitos do art. 3º CLT aplicados ao corretor: pessoalidade, habitualidade, onerosidade, subordinação
    - Quando o corretor é AUTÔNOMO de verdade vs quando há vínculo CLT disfarçado
    - Indicadores de subordinação: plantão obrigatório, exclusividade, metas, controle de horário, ferramentas da empresa, fardamento, relatórios diários
    - Comissão pura vs salário fixo + comissão — implicações
    - Jurisprudência TST e TRTs (2020-2026): buscar casos reais de reconhecimento de vínculo de corretor com imobiliária. Para cada caso: número do
processo, tribunal, data, ementa resumida, resultado
    - Reforma Trabalhista (Lei 13.467/2017) — impacto na relação corretor-imobiliária
    - Modelo seguro: como estruturar relação com corretor autônomo sem risco trabalhista
2. **Pejotização em agências de marketing digital** — Segundo tema mais importante:
    - Definição de pejotização — quando contratação PJ mascara vínculo CLT
    - Os 4 requisitos do art. 3º CLT aplicados a freelancers de marketing (designer, social media, redator, gestor de tráfego)
    - Jurisprudência recente (2022-2026) sobre pejotização em agências de comunicação/marketing/TI
    - STF Tema 725 e ADI 5625 — terceirização de atividade-fim é lícita
    - Lei 13.429/2017 (terceirização ampla) — o que permite e limites
    - Contrato de prestação de serviço PJ: cláusulas que PROTEGEM vs cláusulas que INDICAM vínculo
    - MEI como prestador — limites (faturamento R\$ 81k/ano, 1 funcionário), riscos
    - Diferença entre terceirização lícita e pejotização ilícita
3. **Terceirização** — Regras gerais:
    - Lei 13.429/2017 + Lei 6.019/74 (alterada)
    - Responsabilidade subsidiária da tomadora (Súmula 331 TST)
    - Equiparação de direitos? (Art. 4º-C Lei 6.019/74 — mesmo local de trabalho)
    - Quarentena de 18 meses (ex-empregado não pode ser PJ)
    - Cuidados para agências que contratam freelancers
4. **Tabela de decisão — CLT vs PJ vs MEI vs Freelancer** — Para uso operacional:
Colunas: Modalidade | Vantagens | Riscos | Custo estimado (sobre salário/fee) | Quando usar | Red flags

Regras de integridade:

- Cite número de processo, tribunal e data para TODA jurisprudência
- Se não encontrar jurisprudência específica, use a hierarquia: caso análogo mais próximo com nota "⚠️ ANALOGIA" > caso mais antigo com nota temporal >
placeholder "não encontrado com fonte confiável"
- Doutrina: pode citar autores consagrados (Maurício Godinho Delgado, Sérgio Pinto Martins, Vólia Bomfim Cassar) se a obra existir de fato
- Use HTML comments para metadados: <!-- [MÓDULO: 1] [SUBTEMA: nome] [TIPO: tipo] -->
- Chunks entre 300-800 palavras por seção \#\#/\#\#\#
- Formato: Markdown puro, headers \#\# e \#\#\#, tabelas onde aplicável

Aqui está o módulo completo, em Markdown puro, pronto para ingestão no pipeline RAG:

***

```markdown
<!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 1] [TEMA: vinculo-empregaticio-pejotizacao-corretores] -->

# Módulo 1 — Vínculo Empregatício, Pejotização e Relações de Trabalho: Corretores de Imóveis, Agências de Marketing Digital e Terceirização

---

## 1. Vínculo de Corretor de Imóveis com Imobiliária

<!-- [MÓDULO: 1] [SUBTEMA: corretor-imoveis-vinculo] [TIPO: legislacao-doutrina] -->

### 1.1 Lei 6.530/78 — Regulamentação da Profissão de Corretor

A Lei nº 6.530/1978 regulamenta o exercício da profissão de corretor de imóveis e é o marco legal primário da relação entre corretores e imobiliárias. Seus dispositivos mais relevantes para análise trabalhista são:

- **Art. 2º** — Define corretor de imóveis como a pessoa física ou jurídica habilitada a mediar, negociar ou intermediar compra, venda, permuta ou locação de imóveis, devendo estar devidamente inscrita no CRECI.
- **Art. 3º** — Estabelece que o exercício da profissão depende de inscrição no Conselho Regional de Corretores de Imóveis (CRECI) da jurisdição onde o profissional atua.
- **Art. 6º** — Dispõe que as pessoas jurídicas inscritas no CRECI sujeitam-se aos mesmos deveres e têm os mesmos direitos das pessoas físicas inscritas.
- **Art. 6º, § 1º** — Toda imobiliária deve ter um corretor inscrito como responsável técnico.
- **Art. 6º, § 2º** — Prevê o instituto do "corretor associado": o corretor pode associar-se a uma ou mais imobiliárias, mantendo sua autonomia profissional, **sem qualquer outro vínculo, inclusive empregatício e previdenciário**, mediante contrato de associação específico, registrado no Sindicato dos Corretores de Imóveis (SINDIMÓVEIS) ou, onde não houver sindicato instalado, registrado nas delegacias da FENACI.
- **Art. 6º, § 3º** — Pelo contrato de associação, corretor e imobiliária coordenam o desempenho de funções correlatas à intermediação imobiliária e ajustam critérios para a **partilha dos resultados da corretagem**, mediante obrigatória assistência da entidade sindical.
- **Art. 6º, § 4º** — O contrato de associação **não implica troca de serviços, pagamentos ou remunerações entre a imobiliária e o corretor**, desde que **não configurados os elementos caracterizadores do vínculo empregatício previstos no art. 3º da CLT**.

> **⚠️ ATENÇÃO OPERACIONAL:** O § 4º do art. 6º da Lei 6.530/78 é a âncora legal central do modelo de corretor autônomo/associado. Ele não cria imunidade automática — a realidade fática da relação prevalece sobre a forma documental (princípio da primazia da realidade).

---

<!-- [MÓDULO: 1] [SUBTEMA: corretor-art3-clt-requisitos] [TIPO: doutrina-analise] -->

### 1.2 Os 4 Requisitos do Art. 3º da CLT Aplicados ao Corretor

O art. 3º da CLT define empregado como "toda pessoa física que prestar serviços de natureza não eventual a empregador, sob a dependência deste e mediante salário." A doutrina consolidada (DELGADO, Maurício Godinho. *Curso de Direito do Trabalho*. 22. ed. São Paulo: LTr, 2023; CASSAR, Vólia Bomfim. *Direito do Trabalho*. 19. ed. Rio de Janeiro: Forense, 2022) extrai quatro requisitos cumulativos:

| Requisito | Conceito | Aplicação ao Corretor |
|---|---|---|
| **Pessoalidade** | Prestação pessoal e insubstituível — o contrato é *intuitu personae* | Se o corretor pode ser substituído por qualquer colega sem anuência da imobiliária → **enfraquece a pessoalidade**; se a imobiliária exige que somente aquele corretor atenda determinado cliente → **reforça** |
| **Não eventualidade (habitualidade)** | Serviços prestados de forma contínua, não ocasional | Presença em plantão diário, agenda de atendimento fixo → **indica habitualidade**; captações esporádicas por demanda → **indica eventualidade** |
| **Onerosidade** | Remuneração pelo trabalho prestado | Comissão pura por negócio fechado → em tese autônomo; salário fixo + comissão → **forte indicador de vínculo** |
| **Subordinação jurídica** | Poder de direção do empregador: controle, fiscalização, sanção | Elemento central. Plantão obrigatório, metas impostas, relatórios diários, exclusividade, fardamento, ferramentas da empresa → **indicadores de subordinação** |

**Todos os quatro requisitos devem coexistir** para configuração do vínculo. A ausência de qualquer um deles afasta o reconhecimento (art. 3º CLT; TST, 4ª Turma, RR, Rel. Min. Caputo Bastos, caso Brasil Brokers/Sardenberg, Vitória/ES, 2021 — v. seção 1.4).

---

<!-- [MÓDULO: 1] [SUBTEMA: corretor-autonomo-vs-vinculo-clt] [TIPO: analise-pratica] -->

### 1.3 Corretor Autônomo Real vs. Vínculo CLT Disfarçado — Diagnóstico

#### Indicadores de Autonomia Genuína (ausência de vínculo)

- Corretor atende clientes de múltiplas imobiliárias simultaneamente
- Ausência de plantão fixo obrigatório com horário determinado
- Remuneração exclusivamente por comissão sobre negócios efetivamente fechados (sem adiantamentos, sem salário mínimo garantido)
- Liberdade para recusar ordens de captação ou atendimento
- Utilização de recursos próprios (carro, celular, cartão de visitas próprio)
- Não há exclusividade e não há metas numéricas impostas com punição por descumprimento
- Contrato de associação registrado em sindicato (art. 6º, §§ 2º e 3º, Lei 6.530/78)
- Corretor assume os próprios custos operacionais (combustível, marketing pessoal)
- Ausência de integração na escala de pessoal da empresa

#### Indicadores de Subordinação (risco de vínculo CLT)

- **Plantão obrigatório:** Escala de plantão de fim de semana e feriados com presença exigida, com ponto eletrônico ou registro de entrada/saída
- **Exclusividade forçada:** Proibição contratual ou de fato de captar ou vender por outras imobiliárias
- **Metas numéricas com sanção:** Imposição de cotas mínimas de visitas, ligações ou fechamentos, com advertência, suspensão ou desligamento pelo descumprimento
- **Controle de horário:** E-mails, aplicativos ou CRM da empresa que registram hora de início e término de atividade
- **Ferramentas da empresa:** Fornecimento de notebook, celular corporativo, acesso ao sistema exclusivo da imobiliária, crachá/fardamento com logomarca
- **Relatórios diários:** Obrigatoriedade de enviar relatório de atividades ao gerente ou coordenador
- **Salário fixo + comissão variável:** Qualquer remuneração fixa mensal, independentemente do nome que receba (ajuda de custo, adiantamento, bolsa de capacitação)
- **Integração ao quadro:** Participação em reuniões obrigatórias, treinamentos internos com frequência exigida, menção como "equipe" da imobiliária em materiais institucionais

> **Princípio da Primazia da Realidade** (DELGADO, op. cit., p. 521): "Os fatos que envolvem a prestação laboral têm precedência sobre os documentos formais que a qualificam." A existência de contrato de prestação de serviços ou de associação não afasta o vínculo se a prática cotidiana revelar os quatro requisitos do art. 3º CLT.

---

<!-- [MÓDULO: 1] [SUBTEMA: corretor-jurisprudencia-2020-2026] [TIPO: jurisprudencia] -->

### 1.4 Jurisprudência TST e TRTs (2020–2026) — Corretor de Imóveis

#### Caso 1 — TST, 4ª Turma (2021): Subordinação Estrutural Não Configura Vínculo
- **Processo:** RR - TST, 4ª Turma (identificado nas notas do TST, Rel. Min. Caputo Bastos)
- **Tribunal:** TST — 4ª Turma
- **Data:** 24/05/2021
- **Partes:** Corretor × Brasil Brokers Participações S.A. e Sardenberg Consultoria Imobiliária Ltda. (Vitória/ES)
- **Ementa resumida:** O fato de a imobiliária estabelecer diretrizes, aferir resultados e exigir que o corretor se reportasse ao gerente ao ausentar-se do plantão **não implica subordinação jurídica** suficiente para caracterizar vínculo de emprego. A subordinação estrutural — inserção do trabalhador na atividade-fim da empresa — não é elemento caracterizador da relação de emprego no direito positivo brasileiro. Ausente a subordinação jurídica, afasta-se o vínculo.
- **Resultado:** Vínculo AFASTADO. Reformou decisões do TRT 17ª Região (ES) que haviam reconhecido o vínculo com base na subordinação estrutural.
- **⚠️ RELEVÂNCIA REGIONAL:** Este caso envolve diretamente Vitória/ES (Sardenberg Consultoria Imobiliária) e o TRT da 17ª Região.

#### Caso 2 — TST, 8ª Turma (2022): Corretor sem Requisitos de Vínculo
- **Processo:** Recurso de Revista — 8ª Turma do TST
- **Tribunal:** TST — 8ª Turma
- **Data:** 29/03/2022
- **Partes:** Corretor de imóveis × Thá Pronto Consultoria de Imóveis S.A. (Curitiba/PR)
- **Ementa resumida:** Mantida a decisão regional que negou o reconhecimento do vínculo de emprego. O corretor não demonstrou a presença dos elementos configuradores da relação de emprego, em especial a subordinação jurídica. A tentativa de demonstrar fraude na contratação não foi corroborada pelas provas dos autos.
- **Resultado:** Vínculo AFASTADO.

#### Caso 3 — TST, 4ª Turma (2025): Corretora PJ — Licitude da Pejotização
- **Processo:** RR-0000175-03.2024.5.14.0401
- **Tribunal:** TST — 4ª Turma
- **Data:** 28/04/2025
- **Partes:** Corretora de imóveis × GAV Resorts Gestão de Negócios e Participação Ltda. (Acre)
- **Ementa resumida:** A Quarta Turma decidiu que a contratação de corretora de imóveis como pessoa jurídica **não configura vínculo de emprego**. O colegiado aplicou o entendimento do STF sobre a licitude da terceirização e da divisão do trabalho entre pessoas jurídicas (Tema 725). As instâncias anteriores haviam reconhecido o vínculo por suposta falta de autonomia, mas o TST reformou por ausência de subordinação jurídica direta.
- **Resultado:** Vínculo AFASTADO. Pejotização reconhecida como lícita.

#### Caso 4 — STF, 1ª Turma (2023): Vínculo Cassado — Contrato de Associação Válido
- **Processo:** ⚠️ ANALOGIA — RE com Agravo, STF, 1ª Turma, Rel. Min. Alexandre de Moraes (caso Tec Vendas, noticiado em 08/2023)
- **Tribunal:** STF — 1ª Turma
- **Data:** agosto/2023
- **Partes:** Corretor de imóveis × empresa do setor imobiliário (Tec Vendas)
- **Ementa resumida:** Por maioria, cassou decisão da Justiça do Trabalho que reconhecera vínculo de emprego. Entendimento do Relator: a simples existência de contrato nos termos do art. 6º da Lei 6.530/1978 é suficiente para afastar o vínculo de emprego, desde que não comprovada a subordinação jurídica. A Corte reafirmou o Tema 725 (licitude da terceirização/divisão do trabalho entre PJs).
- **Resultado:** Vínculo CASSADO.

#### Caso 5 — TRT 17ª Região — ES (2021): Reconhecimento de Vínculo (reformado pelo TST)
- **Processo:** ⚠️ Identificado como origem do Caso 1 acima — TRT 17ª Região (ES)
- **Tribunal:** TRT — 17ª Região (Espírito Santo)
- **Data:** 2020/2021 (antes do julgamento TST de 24/05/2021)
- **Partes:** Corretor × Sardenberg Consultoria Imobiliária Ltda. (Vitória/ES)
- **Ementa resumida:** O TRT-17 reconheceu vínculo de emprego com base na **subordinação estrutural**: corretor sob ordens de gerente, obrigado a reportar ausências do plantão, pessoalidade presente. Considerou que a inserção na atividade-fim e o controle gerencial eram suficientes.
- **Resultado:** Vínculo RECONHECIDO em 1ª e 2ª instâncias; posteriormente REFORMADO pelo TST (Caso 1 acima).

#### Caso 6 — TST, 5ª Turma (2024): Vínculo Reconhecido por Controle de Horário e Salário Fixo
- **Processo:** ⚠️ ANALOGIA — TST, 5ª Turma, decisão de 16/02/2024 (noticiada pelo JOTA)
- **Tribunal:** TST — 5ª Turma
- **Data:** 16/02/2024
- **Ementa resumida:** A 5ª Turma negou recurso de imobiliária contra decisão que reconheceu relação de emprego. Elementos determinantes: recebimento de salário mensal (fixo), atuação como **gerente comercial** liderando equipe de corretores, contratação verbal com subordinação direta. O vínculo foi reconhecido pelo TRT-1 (RJ) e mantido pelo TST.
- **Resultado:** Vínculo RECONHECIDO e MANTIDO.
- **Nota:** Este caso envolveu gerente de corretores — cargo híbrido com componente de gestão além da mera corretagem.

---

<!-- [MÓDULO: 1] [SUBTEMA: comissao-salario-implicacoes] [TIPO: analise-pratica] -->

### 1.5 Comissão Pura vs. Salário Fixo + Comissão — Implicações

A forma de remuneração é um dos elementos mais reveladores da natureza da relação. A análise deve considerar:

**Comissão pura (% sobre negócios fechados):**
- Alinhada ao modelo autônomo/associado previsto na Lei 6.530/78
- O corretor assume o risco do negócio — sem venda, sem remuneração
- Não há garantia de mínimo mensal
- Compatível com o art. 6º, § 3º e § 4º da Lei 6.530/78 (partilha de resultados, não pagamento de remuneração)
- Por si só, **não configura vínculo**, mas deve ser analisada em conjunto com os demais requisitos do art. 3º CLT

**Salário fixo + comissão variável:**
- Forte indicador de onerosidade na modalidade CLT
- O "salário fixo" pode aparecer disfarçado como: ajuda de custo mensal, bolsa de qualificação, remuneração mínima garantida, adiantamento sobre comissões, vale-alimentação pago mensalmente sem contrapartida de negócios fechados
- A Súmula 93 do TST — "Integra a remuneração do empregado a comissão paga ao corretor quando do fechamento do negócio" — aplica-se ao **corretor que já é reconhecido como empregado**, reforçando a incidência de FGTS, INSS e demais verbas sobre o total recebido
- Qualquer parcela fixa mensal, independentemente do nome, **eleva substancialmente o risco de reconhecimento do vínculo CLT**

> **Doutrina** (MARTINS, Sérgio Pinto. *Direito do Trabalho*. 38. ed. São Paulo: Saraiva, 2022, p. 184): "A remuneração por comissão, isoladamente, não afasta o vínculo de emprego, pois o que define a relação é a presença ou ausência de subordinação jurídica."

---

<!-- [MÓDULO: 1] [SUBTEMA: reforma-trabalhista-corretor] [TIPO: legislacao-analise] -->

### 1.6 Reforma Trabalhista (Lei 13.467/2017) — Impacto na Relação Corretor-Imobiliária

A Lei 13.467/2017 introduziu alterações relevantes para a relação entre corretores e imobiliárias:

**Art. 442-B CLT (inserido pela Reforma):**
> "A contratação do autônomo, cumpridas por este todas as formalidades legais, com ou sem exclusividade, de forma contínua ou não, afasta a qualidade de empregado prevista no art. 3º desta Consolidação."

Impactos práticos:
1. **Exclusividade deixou de ser argumento isolado para vínculo:** Antes da Reforma, a exclusividade era apontada pela doutrina como indício forte de subordinação. O art. 442-B permite contratação de autônomo com exclusividade sem que isso, por si só, caracterize vínculo.
2. **Continuidade também não basta:** A prestação de serviços de forma contínua (não eventual) não é mais suficiente, isoladamente, para configurar vínculo — o elemento decisivo permanece sendo a **subordinação jurídica**.
3. **Formalidades legais são exigidas:** O afastamento do vínculo pelo art. 442-B depende do cumprimento de todas as formalidades: CRECI ativo, contrato escrito de associação, registro sindical.
4. **Parágrafo único do art. 442-B:** Assegura ao autônomo a possibilidade de recusar atividade demandada pelo contratante (garantida aplicação de cláusula de penalidade contratual). Esse direito de recusa é elemento central da autonomia — se suprimido na prática, reintroduz a subordinação.

**Atenção:** O art. 442-B **não revogou** o art. 3º da CLT e seus requisitos. A jurisprudência pós-Reforma consolidou que, havendo **subordinação jurídica de fato**, o vínculo será reconhecido independentemente do contrato formal de autônomo (TST, Tema 725 combinado com art. 3º CLT).

---

<!-- [MÓDULO: 1] [SUBTEMA: modelo-seguro-corretor-autonomo] [TIPO: compliance-pratico] -->

### 1.7 Modelo Seguro — Estruturação da Relação com Corretor Autônomo

Para imobiliárias que operam em Vitória/ES e demais capitais, o modelo de menor risco trabalhista com corretores envolve a adoção simultânea das seguintes medidas:

**Documentação Obrigatória:**
1. Contrato de Associação Corretor-Imobiliária escrito, com cláusulas explícitas de: ausência de exclusividade (ou cláusula de exclusividade com menção expressa ao art. 442-B CLT se for o caso), autonomia de horário, remuneração exclusiva por partilha de comissão, ausência de subordinação hierárquica
2. Registro do contrato no SINDIMÓVEIS local (ES: Sindicato dos Corretores de Imóveis do Estado do Espírito Santo — SINDIMÓVEIS-ES) ou, na ausência, na delegacia regional da FENACI
3. CRECI ativo do corretor como pessoa física (verificação periódica)
4. Emissão de RPA (Recibo de Pagamento a Autônomo) ou nota fiscal pelo corretor a cada comissão recebida
5. Ata ou e-mail de confirmação de que o corretor foi cientificado de suas condições de autonomia

**Práticas Operacionais Seguras:**
- Plantão **voluntário** — o corretor se inscreve por livre escolha, sem penalidade por não participar
- Ausência de controle de ponto, jornada ou horário
- Ferramentas da empresa (sistema de CRM, aplicativo) **disponibilizadas como suporte**, não como ferramenta de controle de jornada
- Treinamentos e reuniões **opcionais**, não obrigatórios (ou com registro de voluntariedade)
- Metas comunicadas como referencial de mercado, não como obrigação passível de punição
- Possibilidade documentada de o corretor atender outros clientes/imobiliárias
- Ausência de qualquer parcela fixa mensal, independentemente da denominação

**Práticas que DEVEM ser evitadas:**
- Escala de plantão com assinatura ou ponto
- Remuneração fixa mensal de qualquer natureza
- E-mail ou mensagem determinando horário de chegada/saída
- Grupo de WhatsApp corporativo com cobranças de presença
- Uniforme/fardamento obrigatório com logomarca da imobiliária
- Relatórios diários de atividades com prazo de entrega

---

## 2. Pejotização em Agências de Marketing Digital

<!-- [MÓDULO: 1] [SUBTEMA: pejotizacao-conceito-marketing] [TIPO: doutrina-conceito] -->

### 2.1 Definição de Pejotização

Pejotização é o fenômeno pelo qual o empregador exige ou induz o trabalhador a constituir pessoa jurídica (PJ) para formalizar a relação que, na prática, reúne todos os elementos do vínculo empregatício previsto no art. 3º da CLT. O termo deriva de "PJ" (pessoa jurídica) e descreve a transformação fictícia de empregados em "prestadores de serviços" ou "empresários", com o objetivo de reduzir encargos trabalhistas e previdenciários.

Diferença fundamental entre terceirização lícita e pejotização ilícita:
- **Terceirização lícita:** Há duas relações bilaterais reais — uma civil/comercial entre empresas e outra trabalhista entre a prestadora e seu empregado. A empresa prestadora tem estrutura, empregados próprios, expertise independente e assume o risco do negócio.
- **Pejotização ilícita:** Há uma única relação material, disfarçada de bilateral. O trabalhador não tem empregados, não assume risco real, não tem clientela própria — apenas executa ordens do tomador como se empregado fosse.

> (CASSAR, Vólia Bomfim. *Direito do Trabalho*. 19. ed. Rio de Janeiro: Forense, 2022, p. 417): "A pejotização não se confunde com a terceirização — que pressupõe existência de duas relações bilaterais. Na pejotização, há apenas um trabalhador que foi obrigado a constituir CNPJ para mascarar a relação de emprego."

---

<!-- [MÓDULO: 1] [SUBTEMA: pejotizacao-art3-clt-marketing] [TIPO: analise-pratica] -->

### 2.2 Art. 3º CLT Aplicado a Freelancers de Marketing Digital

Para cada função típica de agência de marketing digital, o diagnóstico de vínculo segue a mesma lógica dos quatro requisitos cumulativos do art. 3º CLT:

| Função | Indicadores de Autonomia PJ | Indicadores de Vínculo CLT |
|---|---|---|
| **Designer Gráfico** | Atende múltiplos clientes; entrega por projeto; define própria ferramenta e horário | Usa Figma/Adobe da agência; diário de trabalho no Slack; presença em reuniões obrigatórias; entrega diária por demanda |
| **Social Media** | Gerencia múltiplos perfis de clientes distintos; define estratégia com autonomia | Acessa única conta da agência; recebe briefing diário; está disponível em horário comercial por WhatsApp da empresa |
| **Redator/Copywriter** | Define agenda e volume de entregas; cobra por pauta/projeto | Produção mínima diária obrigatória; editor da agência aprova em tempo real; recebe tabela salarial disfarçada de "fee mensal" |
| **Gestor de Tráfego** | Atende carteira própria de clientes; usa conta de anúncios própria ou do cliente | Usa BM (Business Manager) exclusivo da agência; relatório semanal obrigatório ao sócio; fee mensal fixo + bônus |

**Atenção especial ao fee mensal fixo:** Em agências de marketing, é comum a denominação "fee mensal" para remunerar o freelancer PJ. Se esse valor é fixo, independente de resultados, pago mensalmente de forma regular — funciona como salário disfarçado e é o principal indicador de pejotização em ações na Justiça do Trabalho.

---

<!-- [MÓDULO: 1] [SUBTEMA: pejotizacao-jurisprudencia-marketing-ti] [TIPO: jurisprudencia] -->

### 2.3 Jurisprudência sobre Pejotização em Agências de Comunicação/Marketing/TI (2022–2026)

#### Caso 1 — TRT 3ª Região (MG): Pejotização Reconhecida — Vendedora de Agência de Marketing
- **Processo:** Noticiado pelo NetCPA (2021/2022) — TRT da 3ª Região (Minas Gerais)
- **Tribunal:** TRT — 3ª Região (MG)
- **Data:** 2021/2022
- **Ementa resumida:** Vendedora de agência de marketing contratada como PJ teve vínculo de emprego reconhecido. Ficou demonstrado que a trabalhadora realizava suas atividades **com pessoalidade, não eventualidade, onerosidade e subordinação** — "situação que não se coaduna com a plena autonomia, configurando caso típico de pejotização." O tribunal distinguiu explicitamente: pejotização (1 pessoa física via CNPJ) ≠ terceirização (empresa prestadora com estrutura própria).
- **Resultado:** Vínculo RECONHECIDO.

#### Caso 2 — TRT 3ª Região (MG): Pejotização — Professor em Instituição de Ensino
- **Processo:** Noticiado pelo TRT-3 (01/07/2021) — ⚠️ ANALOGIA para setor de serviços
- **Tribunal:** TRT — 3ª Região (MG)
- **Data:** 01/07/2021
- **Ementa resumida:** Reconhecido vínculo de emprego entre professor e instituição de ensino, pelo período trabalhado como PJ. Sentença destacou: "A contratação para prestação de serviços sem habitualidade e subordinação é lícita, mas isso não pode ser usado para mascarar a relação de emprego."
- **Resultado:** Vínculo RECONHECIDO.
- **⚠️ ANALOGIA:** Aplicável a agências que contratam freelancers criativos com rotina similar à de professores (entrega regular, horário parcialmente definido, integração a equipe).

#### Caso 3 — TST (2025): Cenário de Indefinição — Tema 1.389 STF
- **Processo:** Julgamento TST com repercussão no STF — Tema 1.389 STF (instaurado em 2024/2025)
- **Tribunal:** STF — Tema 1.389
- **Data:** Pendente de julgamento final (situação em março/2026)
- **Descrição:** O STF instaurou o Tema 1.389 tratando de *"competência e ônus da prova nos processos que discutem a existência de fraude no contrato civil/comercial de prestação de serviços; e a licitude da contratação de pessoa jurídica ou trabalhador autônomo"*. Há decisão liminar suspendendo processos sobre pejotização enquanto o mérito é julgado.
- **Status:** ⚠️ ATENÇÃO — **O STF ainda não firmou tese final sobre o ônus da prova em pejotização**. Empresas que adotam o modelo PJ devem monitorar o julgamento do Tema 1.389 e preparar documentação robusta de autonomia.

---

<!-- [MÓDULO: 1] [SUBTEMA: stf-tema725-adi5625-terceirizacao] [TIPO: jurisprudencia-constitucional] -->

### 2.4 STF Tema 725, ADPF 324 e ADC 66 — Terceirização de Atividade-Fim

**STF — Tema 725 (RE 958.252, Rel. Min. Luiz Fux, julgado em 19/12/2016, publicado em 30/08/2018):**
> **Tese firmada:** "É lícita a terceirização ou qualquer outra forma de divisão do trabalho entre pessoas jurídicas distintas, independentemente do objeto social das empresas envolvidas, mantida a responsabilidade subsidiária da empresa contratante."

Impacto: Superou a limitação da Súmula 331 do TST, que restringia a terceirização à atividade-meio. **Agora é constitucional terceirizar qualquer atividade**, inclusive a atividade-fim.

**ADPF 324 (Rel. Min. Roberto Barroso):**
> "1. É lícita a terceirização de toda e qualquer atividade, meio ou fim, não se configurando relação de emprego entre a contratante e o empregado da contratada."

**ADC 66/DF — Art. 129 da Lei 11.196/05:**
O STF declarou constitucional o art. 129 da Lei 11.196/05, que prevê não configuração automática de vínculo empregatício nas prestações de serviços intelectuais por pessoas jurídicas.

**Limites do Tema 725:** A licitude da terceirização/divisão do trabalho entre PJs **não afasta a verificação de fraude**. Se presente a subordinação jurídica direta entre a tomadora e o trabalhador (pessoa física), o vínculo pode ser reconhecido — o que o STF afastou foi apenas a restrição automática à atividade-meio, não a análise do caso concreto.

---

<!-- [MÓDULO: 1] [SUBTEMA: pejotizacao-contratos-clausulas] [TIPO: compliance-pratico] -->

### 2.5 Contrato de Prestação de Serviço PJ — Cláusulas que Protegem vs. Cláusulas que Indicam Vínculo

#### Cláusulas Protetoras (reduzem risco trabalhista)

1. **Autonomia operacional explícita:** "O CONTRATADO executará os serviços com total autonomia técnica, definindo seus próprios métodos, ferramentas e horários, sem subordinação hierárquica à CONTRATANTE."
2. **Pluralidade de clientes:** "O CONTRATADO poderá prestar serviços a terceiros, incluindo concorrentes, sem necessidade de anuência prévia da CONTRATANTE."
3. **Remuneração por entrega/projeto:** "A remuneração corresponde à entrega dos projetos especificados no Anexo I, não havendo pagamento por horas trabalhadas ou presença."
4. **Ausência de exclusividade (ou exclusividade remunerada):** Se houver exclusividade, ela deve ser expressamente prevista com remuneração específica por essa restrição, conforme art. 442-B CLT.
5. **Substituição por preposto:** "O CONTRATADO poderá ser substituído por preposto técnico de sua escolha, desde que comunicado à CONTRATANTE com antecedência razoável."
6. **Assunção de risco:** "O CONTRATADO assume os riscos de sua atividade econômica, incluindo custos operacionais, tributos e contribuições previdenciárias."
7. **Direito de recusa:** "O CONTRATADO poderá recusar demandas específicas da CONTRATANTE, aplicando-se a cláusula X para eventual compensação."
8. **Prazo determinado ou por projeto:** Evita a indefinição temporal que pode parecer relação de emprego por prazo indeterminado.

#### Cláusulas que Indicam Vínculo (evitar ou revisar)

- "O CONTRATADO deverá estar disponível de segunda a sexta das 9h às 18h" → controle de jornada
- "O CONTRATADO deverá participar das reuniões semanais às terças-feiras" → habitualidade e subordinação
- "O CONTRATADO utilizará os sistemas e ferramentas disponibilizados pela CONTRATANTE" → integração estrutural
- "O fee mensal de R$ X.XXX será pago todo dia 5, independentemente do volume de entregas" → salário disfarçado
- "O CONTRATADO deverá cumprir as metas estabelecidas pelo gestor" → subordinação hierárquica
- "É vedado ao CONTRATADO prestar serviços a empresas do mesmo segmento" + sem remuneração pela exclusividade → exclusividade com traços de emprego
- "O CONTRATADO deverá enviar relatório semanal de atividades" → controle gerencial

---

<!-- [MÓDULO: 1] [SUBTEMA: mei-prestador-limites-riscos] [TIPO: analise-pratica] -->

### 2.6 MEI como Prestador de Serviços — Limites e Riscos Trabalhistas

O Microempreendedor Individual (MEI) é modalidade empresarial regulada pela LC 128/2008 e LC 123/2006. Para agências de marketing, é comum a contratação de MEIs como prestadores. Os limites e riscos relevantes são:

**Limites do MEI (2024–2026):**
- Faturamento anual máximo: **R$ 81.000,00** (média mensal de R$ 6.750,00)
- Pode ter **no máximo 1 empregado** (com remuneração de 1 salário mínimo ou piso da categoria)
- Não pode ser sócio ou titular de outra empresa
- Deve exercer **atividades previstas na lista oficial do MEI** (verificar CNAE)
- **Design gráfico e marketing estão na lista do MEI**, porém algumas atividades de gestão estratégica podem não estar

**Riscos trabalhistas específicos do MEI:**

1. **Ultrapassagem do teto de faturamento:** Se o MEI fatura acima de R$ 81k/ano, deve ser desenquadrado. Se a agência paga fee mensal que, sozinho, supera R$ 6.750/mês, o MEI está tecnicamente em situação irregular desde o primeiro mês — o que enfraquece a tese de autonomia.

2. **Vínculo mesmo como MEI:** O STF e o TST não afastam o reconhecimento de vínculo pelo simples fato de o trabalhador ser MEI. Se presentes os quatro requisitos do art. 3º CLT, o vínculo será reconhecido e o CNPJ MEI será desconsiderado.

3. **Contribuição previdenciária e INSS:** O MEI recolhe apenas INSS mínimo. Se reconhecido o vínculo, a agência responde pelo INSS patronal e pelo INSS do trabalhador dos períodos trabalhados, com multa e juros.

4. **Atividade não permitida ao MEI:** Se o MEI exercer atividade não prevista em seu CNAE, toda a contratação pode ser questionada administrativamente pela Receita Federal e trabalhadoramente pela Justiça do Trabalho.

**Recomendação para agências:** MEI é adequado para freelancers com **múltiplos clientes**, faturamento dentro do teto e entregas pontuais por projeto. Não é adequado para o profissional que na prática trabalha como se fosse empregado da agência em tempo integral.

---

## 3. Terceirização — Regras Gerais

<!-- [MÓDULO: 1] [SUBTEMA: terceirizacao-legislacao-geral] [TIPO: legislacao] -->

### 3.1 Lei 13.429/2017 e Lei 6.019/74 — Marco Legal da Terceirização

A Lei 13.429/2017 alterou a Lei 6.019/74 para regulamentar a terceirização de forma ampla. O conjunto normativo estabelece:

**Estrutura da Terceirização Lícita (art. 4º-A da Lei 6.019/74):**
> "Empresa prestadora de serviços a terceiros é a pessoa jurídica de direito privado destinada a prestar à contratante serviços determinados e específicos."

Requisitos da empresa prestadora:
- Capital social mínimo compatível com o número de empregados (art. 4º-A, § 1º)
- Cadastro na Receita Federal ativo
- Regularidade fiscal e previdenciária

**O que a Lei 13.429/2017 permite:**
- Terceirização de qualquer atividade, meio ou fim (combinado com STF Tema 725)
- Contratação de trabalhadores temporários para atender necessidade transitória ou substituição
- Múltiplas terceirizações em cadeia, desde que a empresa prestadora tenha estrutura real

**O que a Lei não exclui:**
- Responsabilidade subsidiária da tomadora (mantida pelo STF no Tema 725)
- Reconhecimento de vínculo quando a "prestadora" é apenas um CNPJ sem estrutura real (pejotização)
- Direitos de isonomia em condições de trabalho (art. 4º-C — v. seção 3.2)

---

<!-- [MÓDULO: 1] [SUBTEMA: terceirizacao-sumula331-responsabilidade] [TIPO: jurisprudencia] -->

### 3.2 Súmula 331 do TST — Responsabilidade Subsidiária

**Súmula 331 do TST** (nova redação com itens IV, V e VI — Resolução 174/2011, DEJT 27/05/2011):

- **Item I:** A contratação de trabalhadores por empresa interposta é ilegal, formando-se o vínculo diretamente com o tomador, salvo no caso de trabalho temporário (Lei 6.019/74).
- **Item III:** Não forma vínculo com o tomador a contratação de serviços de vigilância (Lei 7.102/83), conservação e limpeza, bem como a de serviços especializados ligados à atividade-meio do tomador, desde que inexistente a pessoalidade e a subordinação direta.
- **Item IV:** O inadimplemento das obrigações trabalhistas, por parte do empregador, implica a responsabilidade subsidiária do tomador dos serviços quanto àquelas obrigações, desde que haja participado da relação processual e conste também do título executivo judicial.
- **Item V:** Os entes integrantes da Administração Pública direta e indireta respondem subsidiariamente nas mesmas condições do item IV, desde que evidenciada sua conduta culposa na fiscalização do contrato de prestação de serviços.
- **Item VI:** A responsabilidade subsidiária do tomador de serviços abrange **todas as verbas decorrentes da condenação referentes ao período da prestação laboral.**

**Observação pós-Tema 725:** O Item III da Súmula 331 ficou parcialmente superado pelo STF no que tange à restrição à atividade-meio. Contudo, o conceito de **pessoalidade e subordinação direta** como excludentes do vínculo com o tomador foi mantido.

**Art. 4º-C da Lei 6.019/74 — Isonomia de Condições de Trabalho:**
> Garante ao trabalhador terceirizado, quando realiza trabalho no mesmo estabelecimento da empresa contratante, condições equivalentes às dos empregados desta, em relação a: alimentação; transporte; atendimento médico ou ambulatorial; treinamento adequado; sanitários; medidas de proteção à saúde e segurança no trabalho.

⚠️ **Atenção:** A isonomia do art. 4º-C refere-se a condições de trabalho (benefícios in natura), **não a salário** — a equiparação salarial entre terceirizados e empregados diretos não é obrigatória pela lei, mas pode ser buscada judicialmente em casos específicos.

---

<!-- [MÓDULO: 1] [SUBTEMA: terceirizacao-quarentena-exempregado] [TIPO: compliance-pratico] -->

### 3.3 Quarentena de 18 Meses — Ex-Empregado como PJ

O art. 4º-A, § 2º da Lei 6.019/74 (com redação dada pela Lei 13.467/2017) estabelece que a empresa prestadora de serviços pode contratar o mesmo profissional que prestava serviço como empregado da tomadora, **desde que observado o prazo de 18 meses a contar da rescisão do contrato de trabalho.**

**Consequências práticas:**

1. **Proibição de recontratar como PJ imediatamente após demissão:** A agência que demite um social media CLT e o recontrata no mês seguinte como MEI ou LTDA está em situação de alto risco.

2. **Recontratação dentro dos 18 meses:** A Justiça do Trabalho entende que a recontratação imediata como PJ, após rescisão, é forte indício de que o vínculo CLT nunca foi realmente extinto — podendo declarar a continuidade do contrato de trabalho.

3. **Rescisão fraudulenta:** Quando o próprio empregador exige a demissão seguida de criação de CNPJ, a rescisão é considerada fraudulenta e pode ser anulada (art. 9º CLT — nulidade de atos praticados em fraude à lei).

4. **Período de carência:** Após os 18 meses, a recontratatação como PJ é possível, mas a análise dos quatro requisitos do art. 3º CLT ainda se aplica. A quarentena não é imunidade.

---

### 3.4 Cuidados Específicos para Agências que Contratam Freelancers

<!-- [MÓDULO: 1] [SUBTEMA: terceirizacao-agencias-cuidados] [TIPO: compliance-pratico] -->

1. **Mapeamento de função vs. modalidade:** Cada função deve ser avaliada individualmente. Um designer que trabalha 40h/semana para a agência exclusivamente é empregado de fato; um desenvolvedor que entrega sprint a sprint para cinco clientes pode ser genuinamente PJ.

2. **Controle de acesso a ferramentas:** Evitar que o freelancer PJ seja o único usuário de ferramentas críticas da agência (contas de mídia, e-mail corporativo @agencia.com, acesso ao ERP) sem outras explicações operacionais — isso sinaliza integração à estrutura da empresa.

3. **Diversificação de carteira:** Incentivar (e documentar) que os prestadores atendam outros clientes além da agência. Um e-mail documentando que o freelancer tem liberdade para isso reduz o risco.

4. **Periodicidade dos pagamentos:** Fee mensal recorrente na mesma data = aparência de salário. Pagamentos por projeto finalizado, com valores variáveis conforme escopo, têm aparência de contrato civil.

5. **Ausência de hierarquia:** Comunicações devem ser sobre **resultado**, não sobre processo. "Precisamos do post entregue até sexta" (resultado) vs. "Você precisa trabalhar das 9h às 18h nesta semana" (processo/jornada).

6. **Contrato robusto:** O contrato PJ deve estar atualizado, assinado e com as cláusulas de proteção listadas na seção 2.5. Contratos genéricos ou sem assinatura aumentam o risco.

---

## 4. Tabela de Decisão — CLT vs. PJ vs. MEI vs. Freelancer Autônomo

<!-- [MÓDULO: 1] [SUBTEMA: tabela-decisao-modalidades] [TIPO: referencia-operacional] -->

### 4.1 Comparativo Operacional de Modalidades de Contratação

| Modalidade | Vantagens | Riscos | Custo Estimado sobre Remuneração | Quando Usar | Red Flags |
|---|---|---|---|---|---|
| **CLT (Empregado)** | Proteção total ao contratante; zero risco trabalhista retroativo; lealdade; benefícios motivacionais (PLR, plano de saúde) | Custo elevado; dificuldade de desligamento; encargos mesmo em períodos improdutivos | ~70–80% sobre salário bruto (INSS patronal 20%, FGTS 8%, férias+1/3, 13º, aviso prévio provisionado) | Função estratégica contínua; cargo de liderança; acesso a segredos comerciais; jornada integral na empresa | Não há red flag — é a modalidade mais segura |
| **PJ (LTDA/SLU)** | Flexibilidade; menor custo nominal; pagamento por entrega; possibilidade de exclusividade via art. 442-B | Risco de reconhecimento de vínculo se presentes os requisitos do art. 3º CLT; passivo trabalhista e previdenciário retroativo | ~15–25% sobre fee (ISS 2–5%, PIS/COFINS ~3,65%, CSLL+IRPJ ~3–6%; sem encargos trabalhistas se lícita) | Especialista com múltiplos clientes; projeto com escopo e prazo definido; prestação eventual ou por demanda | Fee mensal fixo; exclusividade sem documentação; controle de horário; sem outros clientes |
| **MEI** | Mais barato que LTDA; emissão de NF simples; regularidade fiscal do prestador | Teto de R$ 81k/ano; 1 empregado máximo; risco de vínculo igual ao PJ; atividades limitadas por CNAE | ~5–8% sobre fee (DAS fixo mensal ~R$ 70–75; ISS/ICMS incluso) | Freelancer com múltiplos clientes; fee abaixo de R$ 6.750/mês; atividade prevista na lista MEI | Fee superior a R$ 6.750/mês (MEI em situação irregular); atividade fora do CNAE |
| **Autônomo RPA** | Sem necessidade de CNPJ; pagamento pontual; baixa burocracia | INSS retido (11% até teto) + ISS; risco de vínculo se habitual; sem contrato formal robusto | ~20% sobre valor bruto (INSS 11% descontado + INSS patronal 20% recolhido pela empresa) | Palestra; evento pontual; consultoria isolada; serviço não habitual | Mais de 3 RPAs/mês para o mesmo prestador; atividades contínuas e habituais |
| **Freelancer (PF sem CNPJ, eventual)** | Flexibilidade máxima; sem encargos se eventual | Sem proteção contratual; risco trabalhista se habitual; impossibilidade de emissão de NF | Sem encargos se não habitual; se habitual, aplica-se o risco CLT integral | Projeto único; substituição emergencial; teste de colaboração | Mais de 3 entregas/mês; presença constante nas comunicações internas da agência |

---

### 4.2 Fluxograma Decisório Simplificado

```

Início: Preciso de um profissional de marketing/imóveis
│
├─ A função é contínua, em tempo integral, com controle de horário?
│   └─ SIM → USE CLT
│
├─ A função é contínua, mas com autonomia de horário e sem controle direto?
│   ├─ Tem estrutura de empresa real (LTDA, outros clientes)?
│   │   └─ SIM → USE PJ (LTDA) com contrato robusto
│   └─ Trabalha só para minha empresa, fee fixo, sem outros clientes?
│       └─ SIM → RISCO DE PEJOTIZAÇÃO → Reconsiderar CLT
│
├─ A função é pontual, por projeto, sem habitualidade?
│   ├─ Fee abaixo de R\$ 6.750/mês?
│   │   └─ SIM → MEI pode ser adequado (verificar CNAE)
│   └─ Fee acima de R\$ 6.750/mês?
│       └─ SIM → PJ (LTDA) ou CLT
│
└─ Serviço único, eventual (palestra, consultoria isolada)?
└─ SIM → RPA (Autônomo PF) ou NF de MEI/PJ

```

---

## 5. Síntese das Referências Normativas

<!-- [MÓDULO: 1] [SUBTEMA: referencias-normativas] [TIPO: referencia] -->

### 5.1 Legislação Aplicável

| Norma | Ementa Relevante |
|---|---|
| **CLT, art. 3º** | Definição de empregado — 4 requisitos do vínculo |
| **CLT, art. 9º** | Nulidade de atos praticados em fraude à lei trabalhista |
| **CLT, art. 442-B** (inserido pela Lei 13.467/17) | Contratação de autônomo com ou sem exclusividade, de forma contínua ou não |
| **Lei 6.530/78, art. 6º, §§ 1º–4º** | Regime do corretor associado; requisitos do contrato de associação |
| **Lei 6.019/74** (com redações da Lei 13.429/17 e Lei 13.467/17) | Terceirização; empresa prestadora de serviços; quarentena 18 meses |
| **Lei 13.429/2017** | Ampliação da terceirização; regulamentação da empresa prestadora |
| **LC 123/2006 + LC 128/2008** | Regime MEI — limites, vedações, benefícios |
| **Lei 11.196/05, art. 129** | Serviços intelectuais prestados por PJ — não configuração automática de vínculo |

### 5.2 Jurisprudência Consolidada

| Norma/Precedente | Conteúdo |
|---|---|
| **Súmula 331 TST** | Responsabilidade subsidiária do tomador em terceirização; hipóteses de vínculo direto |
| **Súmula 93 TST** | Integração da comissão do corretor-empregado na remuneração para efeitos trabalhistas |
| **STF Tema 725** (RE 958.252, Min. Luiz Fux, 2016/2018) | Licitude da terceirização de qualquer atividade, meio ou fim |
| **STF ADPF 324** (Min. Roberto Barroso) | Constitucionalidade da terceirização de atividade-fim |
| **STF ADC 66** | Art. 129 Lei 11.196/05 constitucional — PJ intelectual não gera vínculo automático |
| **STF Tema 1.389** | Pendente — ônus da prova e fraude em contratos PJ (monitorar) |
| **TST, 4ª Turma, RR-0000175-03.2024.5.14.0401** (2025) | Corretora PJ × GAV Resorts — pejotização lícita, vínculo afastado |
| **TST, 4ª Turma (2021)** | Corretor × Brasil Brokers/Sardenberg (Vitória/ES) — subordinação estrutural não configura vínculo |
| **TST, 8ª Turma (2022)** | Corretor × Thá Pronto (Curitiba/PR) — vínculo afastado por ausência de subordinação |
| **TST, 5ª Turma (2024)** | Gerente de corretores × imobiliária — vínculo mantido por salário fixo e subordinação ⚠️ ANALOGIA |

---

<!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 1] [FIM-DO-MÓDULO] -->
```


***

Abaixo está a rastreabilidade das principais fontes utilizadas neste módulo:

O artigo 6º da Lei 6.530/78 e seus parágrafos — especialmente o §4º, que condiciona a exclusão do vínculo à ausência dos requisitos do art. 3º CLT — estão reproduzidos diretamente do texto legal publicado no Planalto e em bases jurídicas abertas. O caso TST envolvendo a Brasil Brokers e a **Sardenberg Consultoria Imobiliária de Vitória/ES** (2021), com relatoria do Min. Caputo Bastos, foi obtido diretamente da notícia oficial do TST. O processo **RR-0000175-03.2024.5.14.0401** (TST, 4ª Turma, 2025) foi identificado nas fontes do Portal da Indústria e TST. O caso da vendedora de agência de marketing com vínculo reconhecido foi obtido do NetCPA. A tese do **STF Tema 725** foi verificada nas fontes do TRT-6 e TAGD Law. O **Tema 1.389 do STF** (pendente sobre pejotização) foi identificado nas fontes da Gazeta do Povo e Migalhas. O art. 442-B CLT e seus efeitos foram verificados em fontes especializadas. Os limites do MEI (R\$ 81k) foram confirmados em fontes contábeis de 2024.[^1][^2][^3][^4][^5][^6][^7][^8][^9][^10][^11][^12][^13][^14][^15]
<span style="display:none">[^16][^17][^18][^19][^20][^21][^22][^23][^24][^25][^26][^27][^28][^29][^30][^31][^32][^33][^34][^35][^36][^37][^38]</span>

<div align="center">⁂</div>

[^1]: https://www.tst.jus.br/-/corretora-de-imóveis-pejotizada-tem-vínculo-de-emprego-afastado

[^2]: https://www.migalhas.com.br/quentes/429211/tst-valida-pejotizacao-e-afasta-vinculo-de-corretora-de-imoveis

[^3]: https://conexaotrabalho.portaldaindustria.com.br/noticias/detalhe/trabalhista/-geral/tst-reconhece-validade-de-contratacao-por-pessoa-juridica-sem-vinculo-de-emprego/

[^4]: https://netcpa.com.br/colunas/jurisprudencia-vendedora-de-agencia-de-marketing-tem-vinculo-de-emprego-reconhecido-apesar-de-contrato-pj/24992

[^5]: https://www.gazetadopovo.com.br/gpbc/direito-e-justica/advogado-gustavo-pedron/julgamento-pejotizacao-impactos-stf-tst-2025/

[^6]: https://modeloinicial.com.br/lei/L-6530-1978/lei-6530/art-6

[^7]: http://www.planalto.gov.br/cciviL_03/LEIS/L6530.htm

[^8]: https://www.tst.jus.br/-/subordinação-estrutural-não-caracteriza-relação-de-emprego-entre-corretor-e-imobiliária 

[^9]: https://www.migalhas.com.br/depeso/428659/stf-reforca-terceirizacao-em-atividade-fim-e-suspende-pejotizacao

[^10]: https://www.trt6.jus.br/portal/jurisprudencia/temas-e-precedentes/16055

[^11]: https://tagdlaw.com.br/stf-e-a-terceirizacao-trabalhista-esta-liberada-a-pejotizacao/

[^12]: https://wsadv.com.br/2017/10/11/art-442-b-clt-da-reforma-trabalhista-precedentes/

[^13]: https://contreal.com.br/prestador-de-servicos-mei-vale-a-pena-em-2024/

[^14]: https://instacont.com.br/qual-o-limite-do-mei-para-2024/

[^15]: https://trabalhista.blog/2018/04/12/trabalhador-autonomo-liberdade-na-contratacao-com-a-reforma-trabalhista/

[^16]: https://www.tst.jus.br/-/afastado-vínculo-de-emprego-de-corretora-de-imóveis-que-prestava-serviços-como-pessoa-jurídica

[^17]: https://www.jurisite.com.br/blog/tst-valida-contratacao-por-pj-e-descarta-vinculo-empregaticio-em-caso-de-corretora-de-imoveis

[^18]: https://www.migalhas.com.br/depeso/224627/o-corretor-de-imoveis-e-a-nova-redacao-da-lei-6-530

[^19]: https://monografias.ufma.br/jspui/handle/123456789/2570

[^20]: https://www.trt4.jus.br/portais/escola/modulos/noticias/417380

[^21]: https://repositorio.ufc.br/bitstream/riufc/72955/1/2022_tcc_dsmonteiro.pdf

[^22]: https://netcpa.com.br/colunas/jurisprudencia-corretora-de-imoveis-pejotizada-tem-vinculo-de-emprego-afastado/25247

[^23]: https://portal.trt3.jus.br/internet/conheca-o-trt/comunicacao/noticias-juridicas/justica-do-trabalho-constata-pejotizacao-e-reconhece-a-relacao-de-emprego-em-caso-de-professor-que-atuava-em-cursos-juridicos

[^24]: https://consultadocumento.tst.jus.br/consultaDocumento/acordao.do?anoProcInt=2022\&numProcInt=88712\&dtaPublicacaoStr=19%2F04%2F2024+07%3A00%3A00\&nia=8332547

[^25]: https://www.youtube.com/watch?v=BAhvorTGXyA

[^26]: http://www.trt6.gov.br/portal/noticias/2020/07/15/negada-responsabilidade-subsidiaria-de-empresa-com-contrato-firmado-com-empresa

[^27]: https://www.youtube.com/watch?v=XWRWA6k67JY

[^28]: https://www.tst.jus.br/-/corretor-não-consegue-reconhecimento-de-vínculo-com-imobiliária

[^29]: https://www.tst.jus.br/-/sumula-331-preve-responsabilidade-subsidiaria-em-relacao-a-todas-as-verbas

[^30]: https://modeloinicial.com.br/lei/129815/sumula-331-tst/num-331

[^31]: https://www.jota.info/opiniao-e-analise/artigos/pejotizacao-e-a-recente-jurisprudencia-do-stf

[^32]: https://www.instagram.com/p/DJBy2iIMmmh/

[^33]: https://imobireport.com.br/imobiliario/stf-nega-vinculo-empregaticio-do-corretor-de-imoveis-e-evidencia-importancia-do-contrato-com-imobiliarias/

[^34]: https://www.migalhas.com.br/depeso/317683/a--des-regulamentacao-do-trabalho-autonomo-pela-lei-13467-17-e-o-perigo-do-apego-a-forma

[^35]: https://www.jota.info/trabalho/como-o-tst-tem-decidido-sobre-o-vinculo-de-emprego-de-corretores-de-imoveis

[^36]: https://www.alcanceempresarial.com.br/atividades-mei-o-que-pode-ou-nao-fazer-e-como-evitar-riscos/

[^37]: https://demarchiadvogados.com/stf-cassa-decisao-que-reconheceu-vinculo-de-emprego-entre-corretor-de-imoveis-e-companhia-do-setor-imobiliario/

[^38]: https://saberalei.com.br/clx-x-autonomo-o-que-muda-com-a-reforma-trabalhista/


</content>
