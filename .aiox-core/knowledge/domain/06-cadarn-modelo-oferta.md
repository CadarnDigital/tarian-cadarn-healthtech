---
material: corpus-ia-saude-suplementar
capitulo: 6
titulo: "A Jogada da Cadarn Healtech — Modelo de Negócio, Oferta e Produto"
fontes: [health-estrategia-oferta-gemini, divergencias-metricas-saude-suplementar]
gerado_em: 2026-06-27
natureza: prescritivo
---

# Capítulo 6 — A Jogada da Cadarn Healtech: Modelo de Negócio, Oferta e Produto

> **Como ler este capítulo — e por que ele é diferente dos cinco anteriores.** Os Capítulos 1 a 5 descrevem **o mercado**: o que é a saúde suplementar, como a corretora opera e se sustenta, como funciona o faturamento da clínica e quem decide a compra. São descritivos e vêm das 13 pesquisas de base. Este capítulo muda de natureza. Ele é **prescritivo**: trata de **como a Cadarn Healtech pretende atuar** nesse mercado — o modelo de negócio, a oferta, a arquitetura técnica do produto, o ROI e a abordagem comercial. Toda a sua matéria-prima vem de uma fonte única e distinta: um arquivo de conversas estratégicas exploratórias conduzidas com os modelos Gemini e GPT [fonte: health-estrategia-oferta-gemini]. Por isso, daqui em diante, a citação de fonte é sempre a mesma.
>
> **Aviso epistêmico (Art. IV — No Invention).** Boa parte do que segue são **hipóteses de oferta e propostas geradas em diálogo com IA**, não decisões fechadas pela Cadarn nem dados validados de mercado. Os números de mercado (custos, VCMH, sinistralidade) que reaparecem aqui já foram tratados e referenciados nos capítulos anteriores; o que é **próprio deste capítulo** — o cálculo de ROI da oferta, os nomes de produto, as arquiteturas de IA, o posicionamento "BPO Tech" — deve ser lido como **matéria-prima estratégica a validar**, e não como verdade consolidada. Onde a fonte apresenta algo como sugestão de um modelo de IA, o texto preserva esse status ("a fonte propõe", "as conversas sugerem").

---

## 1. De fornecedor de software a BPO Tech — o modelo de negócio

### O ponto de partida: duas pontas da mesma cadeia nas mãos

O fato que reorganiza toda a estratégia é declarado explicitamente na fonte pelo próprio Fabiano: a Cadarn tem **acesso a dois players reais e complementares** — *"uma dona de corretora de plano de saúde"* (o lado da originação e manutenção do contrato) e *"um dono de uma empresa que faz faturamento hospitalar"* (o lado do prestador de serviço, processamento TISS/TUSS e conciliação) [fonte: health-estrategia-oferta-gemini]. Ter as **duas pontas da cadeia da saúde suplementar** simultaneamente é descrito na fonte como *"a posição mais estratégica possível"* e como *"o laboratório perfeito"* para colher dados, entender as dores mais caras do mercado e validar produtos [fonte: health-estrategia-oferta-gemini].

### O "Efeito Espelho das Ineficiências"

A fonte nomeia o insight que liga as duas pontas: o **"Efeito Espelho das Ineficiências"** [fonte: health-estrategia-oferta-gemini]. A ideia é que a dor de um lado é o reflexo da dor do outro:

- **Na corretora (back-office da apólice):** a dor é a perda de vidas por lentidão na implantação, o erro manual de cadastro de dependentes e as PMEs cobrando por funcionários desligados que continuam na fatura [fonte: health-estrategia-oferta-gemini].
- **No faturamento hospitalar (back-office do prestador):** a dor principal são as **glosas administrativas** — procedimentos negados pela operadora por falta de elegibilidade, dados incorretos do beneficiário ou falta de autorização [fonte: health-estrategia-oferta-gemini].

### O "Insight de Ouro"

Daí a fonte extrai o que chama de **"Insight de Ouro"**: a raiz de quase toda glosa administrativa no faturamento hospitalar **e** de toda cobrança indevida na corretora é exatamente a mesma — **assimetria de dados cadastrais e lentidão na atualização da base de vidas** [fonte: health-estrategia-oferta-gemini]. O encadeamento causal é direto: se o hospital tenta faturar um atendimento para uma vida que a corretora pediu exclusão (ou cuja inclusão ainda está travada no cadastro manual), **a operadora glosa** [fonte: health-estrategia-oferta-gemini]. As duas dores, vistas dos dois lados, são o mesmo problema de dados. Esse é o elo que valida operar nas duas pontas ao mesmo tempo: o dado de uma ponta valida a dor da outra [fonte: health-estrategia-oferta-gemini]. (O "sangramento invisível" da movimentação cadastral tardia foi quantificado pelo ângulo financeiro no Capítulo 3; aqui ele aparece como a raiz comum das duas operações.)

### O que é "BPO Tech" — e por que muda o modelo

A virada estratégica decisiva está numa correção de rumo que Fabiano faz na própria fonte. A intenção, declarada por ele, *"como uma das possibilidades, seria ser um BPO que trabalharia com cadastros e faturamento"* — **não** apenas vender software para BPOs existentes [fonte: health-estrategia-oferta-gemini]. A fonte sublinha a diferença: *"uma coisa é vender software para BPOs; outra, muito mais estratégica e com maior controle de margem, é ser um **BPO Tech**"* [fonte: health-estrategia-oferta-gemini].

**BPO Tech**, na definição da fonte, é usar a **própria tecnologia (IA) como vantagem competitiva desleal** para prestar serviços de faturamento e cadastro de forma mais rápida, mais barata e mais precisa que os concorrentes tradicionais [fonte: health-estrategia-oferta-gemini]. O diferencial não é "ter uma equipe", e sim *"possuir uma arquitetura invisível de IA que esmaga o custo de processamento"* [fonte: health-estrategia-oferta-gemini]. A consequência econômica é a chave do modelo: um BPO Tech *"nasce com a capacidade de escalar sem precisar multiplicar o tamanho da equipe na mesma proporção"* [fonte: health-estrategia-oferta-gemini]. Esse é exatamente o gargalo de viabilidade da corretora descrito no Capítulo 3 (custo de pessoal devorando a margem ao crescer) — só que aqui invertido a favor de quem detém a automação.

### O posicionamento de mercado

A fonte é explícita sobre **onde não competir**: a oportunidade *"não está em competir com as operadoras"* (Unimed Vitória, Grupo Athena/Samp, etc.), e sim em *"fornecer a inteligência de back-office que protege a margem dos prestadores de serviço e otimiza a gestão de contratos das centenas de corretoras locais"*, que hoje dependem de processos analógicos [fonte: health-estrategia-oferta-gemini]. O diagnóstico de mercado que sustenta isso: o ES é controlado por **poucas e gigantes operadoras**, mas a força de distribuição está **fragmentada em centenas de corretoras** que operam "no escuro tecnológico", e os prestadores estão sufocados por regras de auditoria complexas e opacas [fonte: health-estrategia-oferta-gemini]. (Os números desse mercado — ~500 corretoras na Grande Vitória, 1,39 mi de beneficiários, operadoras dominantes — estão consolidados nos Capítulos 1 e 2.)

---

## 2. A oferta — o "Trio da Eficiência Operacional"

A fonte estrutura a oferta sobre a corretora como um portfólio "end-to-end" que cobre o **ciclo de vida do cliente dentro da corretora**: **Entrada (Cadastro) → Manutenção (Faturamento) → Retenção (Sinistralidade)** [fonte: health-estrategia-oferta-gemini]. Esse ciclo é batizado de **"Trio da Eficiência Operacional"** (também chamado na fonte de "Trio de Ouro da Eficiência") [fonte: health-estrategia-oferta-gemini]. São três produtos encadeados:

### Produto 1 — Automação de Onboarding (Entrada)

Ataca o que a fonte chama de *"Gargalo da Foto de Documento"*: o time perde horas digitando dados de RG/CPF/CNH recebidos por foto no WhatsApp, cometendo erros de digitação que geram recusas nas operadoras (glosas cadastrais) [fonte: health-estrategia-oferta-gemini]. A solução é um pipeline técnico de três etapas (detalhado na Seção 3). O valor entregue: fim do erro humano no cadastro e redução das horas/homem gastas em digitação [fonte: health-estrategia-oferta-gemini].

### Produto 2 — Automação de Conciliação (Manutenção/Financeiro)

Ataca os erros entre **vidas ativas vs. faturas cobradas**. A solução é um algoritmo de cruzamento de bases que aponta divergências automaticamente. O valor: recuperação imediata de dinheiro e redução da carga de trabalho do analista de faturamento [fonte: health-estrategia-oferta-gemini].

### Produto 3 — Consultoria de Sinistralidade (Retenção)

Ataca os reajustes abusivos e o cancelamento de contratos. A solução combina **dashboards preditivos** com **comunicação automatizada (nutrição)** para reduzir o uso indevido do plano. O valor: aumento da fidelidade e autoridade da corretora como consultor estratégico [fonte: health-estrategia-oferta-gemini]. (A mecânica de sinistralidade e a defesa atuarial na renovação estão nos Capítulos 1, 2 e 3; aqui ela é o produto de retenção.)

### Os dois enquadramentos de venda da oferta

A mesma oferta é apresentada na fonte sob **dois enquadramentos comerciais** complementares, conforme o ângulo de dor do cliente [fonte: health-estrategia-oferta-gemini]:

| Enquadramento | Foco | A dor explorada | A promessa |
|---|---|---|---|
| **"IA como Fábrica de Eficiência"** | Back-office | O custo invisível dos analistas (um analista que ganha R$ 2.400 custa quase R$ 5.000 — ver Cap. 3) | "Recuperação de caixa" via automação de conciliação e cadastro |
| **"IA como Consultoria de Retenção"** | Marketing/Vendas | Sinistralidade alta e reajustes que o RH do cliente culpa a corretora | "Dashboard de Saúde Corporativa" que torna a corretora parceira estratégica do RH |

*[fonte: health-estrategia-oferta-gemini]*

O princípio de venda que atravessa os dois: *"O segredo não é vender 'IA', é vender a **recuperação de caixa** através da automação"* [fonte: health-estrategia-oferta-gemini]. Esse princípio é a aplicação concreta da tese do Capítulo 5 ("ninguém compra IA de forma abstrata; o decisor compra redução de risco").

---

## 3. A arquitetura técnica

### O pipeline MVP de cadastro (Onboarding)

A fonte descreve a arquitetura de referência do produto de cadastro em **três etapas** [fonte: health-estrategia-oferta-gemini]:

1. **Extração** — usar **OCR** (Reconhecimento Óptico de Caracteres) com **Claude Vision (Haiku 4.5)**, apontado como excelente custo-benefício para documentos brasileiros, para ler a foto do documento e retornar um **JSON estruturado** [fonte: health-estrategia-oferta-gemini].
2. **Validação** — uma interface simples para o analista apenas "conferir" o que a IA extraiu — o **human-in-the-loop** (humano no circuito de validação). Materializa-se como um **CSV de validação** [fonte: health-estrategia-oferta-gemini].
3. **Injeção** — um script com **Playwright** (ferramenta de automação de navegador) que "digita" os dados no portal da operadora ou no ERP automaticamente — uma forma de **RPA** (Automação Robótica de Processos) [fonte: health-estrategia-oferta-gemini].

A arquitetura completa de referência [fonte: health-estrategia-oferta-gemini]:

- **OCR:** Claude Vision (Haiku 4.5).
- **Pipeline:** 3 etapas (Extração JSON → CSV de Validação → Automação via Playwright).
- **Input:** pasta no Google Drive ou chat (bot de WhatsApp/Telegram).
- **Output:** cadastro realizado com sucesso no sistema da corretora (Quiver, Segfy, Moltrio, etc. — os mesmos ERPs citados no Cap. 2).

Para a etapa de IA, a fonte recomenda usar **Prompt Caching** para baratear o custo de tokens ao processar volumes de documentos/faturas [fonte: health-estrategia-oferta-gemini].

### O catálogo de soluções de IA

Ao longo das conversas, a fonte propõe um grande conjunto de arquiteturas de IA aplicáveis ao back-office da saúde suplementar. Consolidadas por categoria (sem repetir as variações que dizem a mesma coisa, mas preservando cada mecânica e cada dado quantitativo distinto), são estas — todas apresentadas como **propostas a validar**, não como produtos prontos [fonte: health-estrategia-oferta-gemini]:

**A) Pré-auditoria anti-glosa (clínica/hospital) — a bandeira "Glosa Zero".** Um agente autônomo que atua **antes** do envio do lote de faturamento. Lê as guias TISS/TUSS, extrai as regras de elegibilidade da operadora via RAG e cruza com o histórico para identificar dados em falta, **códigos TUSS obsoletos** ou incompatibilidades que sabidamente geram glosas — bloqueando a glosa "no berço". Variações propostas: validação preditiva via API que **intercepta o XML** antes do envio; cruzamento do **prontuário** com o manual de auditoria específico da **Unimed Vitória ou da Samp**; foco na **alta complexidade hospitalar** (prontuários de internação, uso de **OPME** — Órteses, Próteses e Materiais Especiais), sinalizando ao faturista apenas as contas com alto risco de glosa. Usa **validadores TISS**, **TISS 4.01** como padrão de referência, e opera com **janelas de contexto isoladas** por operadora [fonte: health-estrategia-oferta-gemini].

**B) Cadastro e movimentação automatizada (corretora).** O "Automa-Cadastro": recebe os arquivos brutos das PMEs (PDFs de RH, listagens em Excel, fotos), padroniza os dados via Visão Computacional + LLM e faz o upload/preenchimento automatizado das movimentações de vidas, com checagem preventiva em tempo real contra CPFs inválidos ou nomes divergentes. Os agentes de RPA inserem os dados nos sistemas das operadoras ou no **SIB — Sistema de Informações de Beneficiários** (a base de beneficiários da ANS), reduzindo o tempo de onboarding *"de dias para minutos"*. Variação: **web scraping guiado por IA** para navegar os portais arcaicos das operadoras, eliminando o "batimento cadastral" manual [fonte: health-estrategia-oferta-gemini].

**C) Conciliação financeira (ambas as pontas) — o "AI Reconciler" / "Zero-Touch".** Pipeline que ingere PDFs/TXT/CSV heterogêneos de comissionamento e faturamento de múltiplas operadoras, extrai tabelas, identifica vidas cobradas indevidamente (exclusões não processadas), calcula repasses deduzindo impostos locais (como o **ISS**) e gera relatório de divergências. Versão "Zero-Touch": cruza os **demonstrativos de retorno** das operadoras com os XMLs originais e os extratos bancários, destacando apenas as exceções (pagamentos a menor ou não realizados) para a equipe humana tratar. Audita também **co-corretagem, comissões agenciadas não pagas e estornos indevidos**. A fonte chama atenção para faturas "camufladas", coparticipações repetidas e memórias de cálculo inflacionadas enviadas em formatos não estruturados [fonte: health-estrategia-oferta-gemini].

**D) RAG de compliance e regras (ambas as pontas).** Um sistema de **RAG** (Geração Aumentada por Recuperação) alimentado com as tabelas de preços, livretos de rede referenciada, prazos de carência, aditivos contratuais e manuais de **todas as operadoras ativas no ES** (Samp, Unimed, São Bernardo, Bradesco, SulAmérica), além das diretrizes da ANS, da Tabela TUSS e de normativas como a **RN 309 (pool de risco)** e o rol taxativo da ANS. Usos propostos: cotação em linguagem natural pela corretora (*"Qual operadora cobre o Hospital Santa Rita no plano PME de 3 a 9 vidas com menor custo?"*); defesa atuarial e redação automática de **recursos de glosa**; arbitragem regulatória de reajustes abusivos [fonte: health-estrategia-oferta-gemini].

**E) Sinistralidade preditiva (corretora) — o motor MLR.** Um modelo de machine learning que ingere o histórico de faturas e de utilização hospitalar para prever a curva de risco de uma carteira corporativa. Objetivo explícito: identificar a **regra "5/50"** (os 5% de pacientes crônicos que concentram ~50% dos custos da apólice — ver Cap. 5) e gerar alertas preditivos sobre uso excessivo de pronto-socorro, que, segundo a fonte, **custa de 3 a 8 vezes mais que consultas ambulatoriais** [fonte: health-estrategia-oferta-gemini]. Dá ao corretor munição de dados para contestar o reajuste anual antes que ele seja imposto. **MLR** (*Medical Loss Ratio*) é o termo internacional para sinistralidade [fonte: health-estrategia-oferta-gemini]. A fonte registra ainda um dado específico de mercado que dimensiona a urgência dessa dor: contratos pequenos, de **menos de 30 vidas**, sofrem reajustes médios sistematicamente acima dos contratos grandes, o que impulsiona o churn [fonte: health-estrategia-oferta-gemini]. Esse índice tem uma trajetória que vale fixar com precisão — a fonte exploratória capturou apenas um ponto dela: foi de **17,85% em 2023** (o número que a fonte registrou), subiu a um pico em 2024 e **recuou para 14,24% no acumulado de 2025**, ainda assim bem acima do reajuste dos contratos maiores e muito acima do teto de ~5% dos planos individuais [fonte: divergencias-metricas-saude-suplementar]. (É um recorte mais granular do que a faixa geral de 6,9% a 43,2% do Capítulo 1.)

**F) Atendimento e retenção (corretora) — "Care-Support Agent".** Assistente que centraliza as interações pulverizadas no WhatsApp, faz leitura de intenções (segunda via de boleto, rede credenciada, contestação de reajuste), executa automação de primeiro nível e abre chamados estruturados com priorização por criticidade regulatória. Combina-se com um **workflow de retenção** que qualifica leads em **~30 segundos** e mantém follow-up contínuo da carteira [fonte: health-estrategia-oferta-gemini]. (Os ganhos de retenção de até 76% e a liberação de até 90% das horas de prospecção estão quantificados no Cap. 3.)

**G) Triagem de pacientes / navegação (front-office, lado da PME).** Assistentes de linguagem natural que interagem com os funcionários da empresa-cliente, triando sintomas leves e redirecionando para telemedicina ou rede ambulatorial — cortando o custo "fee-for-service" hospitalar na raiz e, com isso, a sinistralidade do contrato. Inclui um **Monitor de Elegibilidade em background**, que faz chamadas de rotina aos webservices das operadoras para identificar carências e bloqueios antes de o paciente chegar à recepção [fonte: health-estrategia-oferta-gemini].

### As barreiras arquiteturais e psicológicas que o produto precisa vencer

A fonte é clara sobre os requisitos não-funcionais para ter tração B2B nesse setor avesso a risco [fonte: health-estrategia-oferta-gemini]:

- **Segurança em nível bancário** — logs de auditoria, criptografia, janelas de contexto isoladas para conformidade com a **LGPD** no tráfego de dados sensíveis (doenças preexistentes, tratamentos oncológicos). A segurança é tratada como ponto de partida irrevogável da negociação (ver também Cap. 5).
- **Interoperabilidade "Plug and Play"** — conectar-se via **APIs abertas** a ERPs e **PEPs (Prontuário Eletrônico do Paciente)** legados, sem exigir integrações milionárias nem substituição dos softwares já estabelecidos.
- **Postura de "copiloto"** — a IA atua como *"facilitador silencioso e infalível"*, nunca como o produto em si.

---

## 4. O ROI e a engenharia da oferta

Esta é a peça mais concreta e mais própria deste capítulo: a fonte fecha um **cálculo de ROI completo** para a oferta de automação à corretora [fonte: health-estrategia-oferta-gemini]. Ele parte do custo de um analista de back-office no **Lucro Presumido** (o cenário onde a automação é mais lucrativa para o cliente).

### O cálculo, passo a passo

**1. O custo atual (o que o cliente paga):** o custo mensal total de um analista de back-office no Lucro Presumido (salário R$ 2.400 + benefícios + encargos + impostos patronais) é de **R$ 5.036,08** [fonte: health-estrategia-oferta-gemini]. (Este número é o mesmo do Cap. 3 — aqui ele entra como base do ROI.) Anualizado em 13 meses (para incluir o 13º): R$ 5.036,08 × 13 ≈ **R$ 65.469/ano** [fonte: health-estrategia-oferta-gemini].

**2. O investimento na solução (o que a Cadarn cobra):**
- **Setup (implementação):** R$ 3.000,00 (única vez).
- **Mensalidade (manutenção da IA):** R$ 1.500,00/mês.
- **Custo anual da automação:** (R$ 1.500 × 12) + R$ 3.000 = **R$ 21.000,00/ano** [fonte: health-estrategia-oferta-gemini].

**3. O resultado (automatizar 1 posto de trabalho):**
- **Economia bruta anual:** R$ 65.469,00.
- **Custo da automação:** R$ 21.000,00.
- **Ganho líquido anual:** R$ 65.469 − R$ 21.000 = **R$ 44.469,00**.
- **ROI:** (R$ 44.469 / R$ 21.000) × 100 = **211,7%** [fonte: health-estrategia-oferta-gemini].

A leitura de fechamento da fonte: *"Para cada R$ 1,00 que o cliente investe na automação, ele economiza/recupera cerca de **R$ 2,11** por ano"*, além de ganhar escalabilidade e reduzir erros [fonte: health-estrategia-oferta-gemini]. O investimento é *"menos de 1/3 do custo de um funcionário"* e o retorno começa *"já no primeiro mês de operação automatizada"* [fonte: health-estrategia-oferta-gemini].

### O ganho em horas

A fonte também dimensiona o ROI em tempo, não só em dinheiro [fonte: health-estrategia-oferta-gemini]:

- **Cadastro/Onboarding:** uma corretora que faz 100 inclusões/mês, a 10 minutos cada (digitação + conferência), gasta **~16 horas/mês**; com automação, cai para **~1 hora** (só a validação final).
- **Conciliação:** mais **20 a 30 horas/mês** salvas por analista.
- **Total:** quase **50 horas mensais** de trabalho braçal devolvidas ao back-office [fonte: health-estrategia-oferta-gemini].

A fonte ainda estima, num outro recorte, que a tecnologia pode reduzir o trabalho operacional **em até 75%** [fonte: health-estrategia-oferta-gemini]. O pitch que traduz esse ganho: *"Hoje, a sua corretora é uma fábrica de digitação... Com isso, a sua equipe para de 'digitar' e começa a 'auditar'"* — ganhando escala para dobrar a carteira sem contratar mais ninguém para o back-office [fonte: health-estrategia-oferta-gemini].

### O contorno do Fator R — o ponto mais sofisticado da oferta

Aqui está a objeção mais técnica e a resposta mais inteligente da fonte. **A objeção:** se a corretora automatiza e simplesmente "corta" a folha, ela pode cair abaixo dos 28% do Fator R e ser penalizada com carga tributária maior (a mecânica do Fator R está no Cap. 3). Automação cega poderia, portanto, destruir o benefício fiscal [fonte: health-estrategia-oferta-gemini].

**A resposta da fonte: não se vende "corte de custo", vende-se "Eficiência Estratégica".** Existem **três formas de contornar o problema** e transformar a automação em aliada do Fator R [fonte: health-estrategia-oferta-gemini]:

1. **Realocação** — o funcionário deixa de ser "digitador" e vira "consultor". A folha permanece a mesma (ou cresce), mas aquele funcionário agora faz **gestão de sinistralidade** e **atendimento consultivo**, aumentando o valor entregue ao cliente e reduzindo churn. Mantém a folha, melhora a produtividade e protege o Fator R [fonte: health-estrategia-oferta-gemini].
2. **Aumento do Pró-Labore / Meritocracia (concentração de folha)** — com a economia gerada, a empresa aumenta os salários dos funcionários de alta performance ou o pró-labore dos sócios. Mantém o volume da folha alto o suficiente para os 28%, mas com estrutura mais enxuta e tecnológica [fonte: health-estrategia-oferta-gemini].
3. **Escala (crescimento de receita)** — a automação permite faturar 2x ou 3x com os mesmos funcionários. Se a receita sobe e a folha se mantém, a empresa fica mais rentável; o excedente pode ir para mais marketing ou bonificação por performance, mantendo o Fator R saudável [fonte: health-estrategia-oferta-gemini].

O argumento de venda que a fonte costura a partir disso: *"Muita gente acha que automação serve para demitir gente e reduzir folha, mas isso seria um erro tributário para você... Você escala sua receita sem precisar inchar sua estrutura."* [fonte: health-estrategia-oferta-gemini]. Isso transforma a oferta de IA num **serviço de engenharia financeira e operacional**, não apenas um software [fonte: health-estrategia-oferta-gemini]. (No cenário Simples Nacional, onde o custo do analista é menor — R$ 3.816,14/mês, ver Cap. 3 —, o ROI direto é menor, mas a fonte aponta que o argumento do Fator R fica ainda mais forte [fonte: health-estrategia-oferta-gemini].)

---

## 5. A abordagem comercial

### A estratégia de entrada: o diagnóstico no lugar da proposta

O princípio comercial central da fonte: **não oferecer uma reunião nem uma proposta — oferecer um "Diagnóstico de Eficiência Operacional"** [fonte: health-estrategia-oferta-gemini]. A Cadarn analisa o processo de cadastro e faturamento do cliente e mostra onde ele está "queimando dinheiro" com processos manuais. A estratégia validada pelo próprio mercado de BPO, segundo a fonte: oferecer uma **Auditoria/Diagnóstico Gratuito** dos últimos 30 a 90 dias de operação, processar os dados históricos com IA em background e entregar um relatório que aponta exatamente **quantos reais a empresa perdeu** — *"a dor do dinheiro perdido exposta pelo relatório quebrará qualquer objeção cultural ou relacional"*, abrindo a porta para contratação sob **Success Fee** ou **assinatura recorrente** [fonte: health-estrategia-oferta-gemini].

### O ICP e o "cavalo de Troia"

A fonte é específica sobre **quem buscar** [fonte: health-estrategia-oferta-gemini]:

- **Não** buscar as corretoras individuais (1 funcionário) — não têm caixa para implementar IA.
- Buscar as de **médio porte (10 a 15 funcionários)** — já sentem o peso da folha e precisam automatizar para não serem engolidas por Assessorias/MGAs (ver Cap. 3).

E sobre **por onde começar**: o **"cavalo de Troia"** sugerido é a **Conciliação de Comissões**, por ser o processo que mais causa dor de cabeça e perda financeira direta — resolver isso ganha a confiança do dono [fonte: health-estrategia-oferta-gemini]. (Note que esta recomendação convive com a do Cap. 5, que sugere o "Diagnóstico de 20 movimentações cadastrais" como porta de entrada — são duas opções de oferta de entrada a testar.)

### A planilha de diagnóstico de processos

Como instrumento da abordagem, a fonte propõe uma **"Planilha de Diagnóstico de Processos"**, em que se pede à corretora para listar [fonte: health-estrategia-oferta-gemini]:

1. Quantos novos cadastros fazem por mês?
2. Quantas faturas auditam por mês?
3. Quantas horas estimadas gastam com isso?

Com esses números, preenche-se a planilha de ROI e entrega-se ao dono o impacto visual de *"R$ X perdidos por ano"* — descrito como *"o que assina o contrato"* [fonte: health-estrategia-oferta-gemini].

### O roteiro de reunião de diagnóstico

A fonte detalha um roteiro completo de condução da reunião, com a postura de **"investigue, não apresente"** — usando perguntas como *"Como vocês tratam...", "Qual é o impacto disso no custo..."* [fonte: health-estrategia-oferta-gemini]. O roteiro tem quatro blocos:

1. **Abertura (enquadramento de expertise)** — ancorar na pressão de custos do mercado (VCMH 15,1%, reajuste PME como causa de churn — ver Cap. 1) e posicionar-se como analista de estrutura, não vendedor de robô [fonte: health-estrategia-oferta-gemini].
2. **Bloco Fiscal (o Fator R)** — perguntar o regime tributário, se trabalham ativamente o Fator R (Anexo V → Anexo III), como controlam o percentual da folha. O "pulo do gato": se o cliente diz que "o contador resolve", rebater que folha abaixo de 28% significa pagar 15%+ de imposto sem necessidade [fonte: health-estrategia-oferta-gemini].
3. **Bloco Operacional (gargalos do back-office)** — perguntar o tempo médio de onboarding de PME nos portais (Samp, Unimed, MedSênior), como fazem a conciliação de comissões, e expor o custo oculto (assistente que custa +100% sobre o salário — ver Cap. 3) [fonte: health-estrategia-oferta-gemini].
4. **Bloco Estratégico (sinistralidade/retenção)** — perguntar a estratégia de defesa de reajuste das PMEs e o acesso aos dados de sinistralidade; fazer a ponte para a IA como liberadora de tempo para a consultoria de valor [fonte: health-estrategia-oferta-gemini].

O **encerramento (call to action)** não é proposta de preço — é a oferta do **Diagnóstico de Eficiência** sobre uma amostra real (a conciliação de uma fatura de comissão ou a implantação de uma PME). A fonte ainda sugere escrever um **e-mail de convite** para agendar essa reunião diagnóstica, focado nos pontos de dor [fonte: health-estrategia-oferta-gemini].

### O plano de validação — Product Discovery acelerado

Por fim, a fonte propõe **não construir um SaaS robusto agora**, e sim rodar um **Product Discovery acelerado** usando o acesso privilegiado às duas pontas, em três fases [fonte: health-estrategia-oferta-gemini]:

- **Fase 1 — Diagnóstico de Dados (esta semana).** No faturamento hospitalar: extrair relatório dos últimos 3-6 meses de glosas, filtrando as motivadas por "erros administrativos", "elegibilidade do beneficiário" ou "falta de autorização". Na corretora: listar as 3 maiores reclamações de reajuste ou divergência de fatura dos últimos meses [fonte: health-estrategia-oferta-gemini].
- **Fase 2 — MVP de Planilha / "Wizard of Oz" (próximas 2 semanas).** Em vez de programar uma plataforma, criar um script em Python conectado a uma LLM (Claude via API, com Prompt Caching), rodar a IA para estruturar/limpar/cruzar os arquivos, e medir tempo e erros encontrados vs. o trabalho humano manual [fonte: health-estrategia-oferta-gemini]. ("Wizard of Oz" é o método de validar um produto operando o "motor" manualmente nos bastidores antes de automatizá-lo de fato; "Design Partner" é o parceiro de co-desenvolvimento que cede os dados reais para essa validação [fonte: health-estrategia-oferta-gemini].)
- **Fase 3 — Validação Comercial (próximo mês).** Com os relatórios das duas pontas, calcular o ROI real (*"Nossa IA encontrou R$ 15.000 em erros de faturamento em 10 minutos"* / *"Identificamos 8% de guias com risco iminente de glosa antes do envio"*). Esses números reais viram o argumento de vendas para escalar para outras corretoras e hospitais da região [fonte: health-estrategia-oferta-gemini].

---

## 6. Síntese do capítulo

A jogada da Cadarn Healtech, como a fonte a desenha, condensa-se em seis ideias-âncora:

1. **Ser BPO Tech, não vendedor de software.** Usar IA como vantagem competitiva desleal para prestar cadastro e faturamento mais rápido, barato e preciso — escalando sem multiplicar a equipe [fonte: health-estrategia-oferta-gemini].
2. **As duas pontas são o laboratório.** Corretora + faturamento hospitalar nas mãos permitem que o dado de uma ponta valide a dor da outra — o **Efeito Espelho**, cuja raiz comum (**Insight de Ouro**) é a assimetria de dados cadastrais [fonte: health-estrategia-oferta-gemini].
3. **A oferta é um trio encadeado** (Onboarding → Conciliação → Sinistralidade), vendido como "recuperação de caixa", nunca como "IA" [fonte: health-estrategia-oferta-gemini].
4. **A arquitetura é enxuta e híbrida** — OCR (Claude Vision Haiku 4.5) → validação humana → RPA (Playwright) —, com um catálogo de soluções de IA (anti-glosa, conciliação, RAG de compliance, MLR preditivo, atendimento) sob requisitos de segurança bancária e interoperabilidade Plug and Play [fonte: health-estrategia-oferta-gemini].
5. **O ROI é a munição**: automatizar 1 posto no Lucro Presumido rende ROI de **211,7%** (R$ 44.469/ano de ganho líquido; R$ 2,11 por R$ 1) e devolve ~50 horas/mês — sem quebrar o Fator R, via realocação, concentração de folha ou escala [fonte: health-estrategia-oferta-gemini].
6. **A venda entra pelo diagnóstico gratuito**, ancorada num roteiro investigativo e num Product Discovery de três fases sobre dados reais das duas pontas, convertendo em Success Fee ou assinatura [fonte: health-estrategia-oferta-gemini].

> **Fronteiras deste capítulo.** Os números de mercado que aqui reaparecem (custos de pessoal, VCMH, sinistralidade, regra 5/50, recuperação de glosa) estão consolidados e referenciados nos Capítulos 1 a 5 — este capítulo os reutiliza apenas como base da oferta. O que é próprio daqui — modelo BPO Tech, Efeito Espelho, Trio da Eficiência, arquitetura técnica, ROI 211,7%, contorno do Fator R, plano de validação — vem de uma fonte exploratória única [fonte: health-estrategia-oferta-gemini] e tem status de **hipótese estratégica a validar**, não de fato de mercado. As perguntas em aberto que essas conversas deixaram estão reunidas no **Anexo — Perguntas Estratégicas**.
