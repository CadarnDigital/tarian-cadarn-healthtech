---
material: corpus-ia-saude-suplementar
capitulo: 4
titulo: "Faturamento na Saúde — Clínicas, Hospitais e BPO"
fontes: [bpo-faturamento-saude, health-bpo-faturamento, health-concorrentes-bpo-gemini, health-dossie-mesa-gpt, health-dossie-gemini-brasil, divergencias-metricas-saude-suplementar]
gerado_em: 2026-06-27
---

# Capítulo 4 — Faturamento na Saúde: Clínicas, Hospitais e BPO

Os capítulos anteriores olharam para o mercado de saúde suplementar pelo lado de quem vende e administra o plano: o cenário macro (Capítulo 1) e a corretora (Capítulos 2 e 3). Este capítulo vira a câmera para o outro extremo da cadeia — o **prestador de serviço**, ou seja, a clínica, o consultório, o laboratório e o hospital que atendem o paciente e precisam ser pagos pela operadora por esse atendimento.

Aqui o tema não é como o plano é vendido, e sim como o atendimento vira dinheiro na conta do prestador. Esse processo tem nome técnico, regras rígidas, um vilão recorrente — a glosa — e um mercado inteiro de empresas que se especializaram em executá-lo por terceirização. É isso que vamos destrinchar: primeiro o **processo de faturamento**, depois o **mercado de BPO** que o atende.

---

## 4.1 O ciclo de receita na saúde (RCM)

Quando uma clínica atende um paciente de convênio, o atendimento não se converte em receita automaticamente. Entre o ato médico e o dinheiro disponível em caixa existe uma esteira inteira de tarefas administrativas: conferir se o paciente tem direito ao procedimento, obter autorização, registrar o que foi feito, montar a cobrança no formato exigido, enviar à operadora, acompanhar o pagamento, contestar o que foi recusado e, por fim, conciliar o que entrou. Esse conjunto de etapas é o que o setor chama de **RCM — Revenue Cycle Management, ou Ciclo de Gestão da Receita**: a assunção integral do ciclo que transforma o atendimento prestado em receita efetivamente recebida [fonte: health-concorrentes-bpo-gemini].

O gargalo central do prestador, portanto, não é "atender mais" — é **converter atendimento em recebimento** sem deixar dinheiro parado pelo caminho [fonte: health-concorrentes-bpo-gemini]. Essa conversão é mais difícil do que parece porque a receita de uma clínica contemporânea entra por fontes fragmentadas e simultâneas: pagamentos particulares via cartão de crédito ou Pix, faturamento por múltiplas operadoras de saúde, venda de pacotes de procedimentos, laudos emitidos para outras empresas (o chamado *business-to-business*, empresa-para-empresa) e telemedicina [fonte: health-concorrentes-bpo-gemini].

Fechar as contas nesse cenário exige **conciliação** — o cruzamento meticuloso de quatro registros que precisam bater entre si: a produção clínica reportada no prontuário eletrônico, o arquivo enviado à operadora, o demonstrativo de repasse devolvido por ela e o extrato da conta corrente [fonte: health-concorrentes-bpo-gemini]. (O *demonstrativo de repasse*, também chamado de demonstrativo de retorno, é o documento em que a operadora informa, item a item, o que aceitou pagar e o que recusou.) A complexidade aumenta quando vários médicos dividem o mesmo espaço e a mesma receita — o modelo de *coworking* médico, em que profissionais compartilham a estrutura da clínica. Nesses casos é preciso fazer o **split de pagamento** (o fracionamento de um mesmo recebimento entre vários destinatários) e o **repasse médico** (a distribuição da parte de honorários que cabe a cada profissional). O modelo tradicional de gestão interna, baseado em planilhas, não costuma suportar esse fracionamento [fonte: health-concorrentes-bpo-gemini].

> O volume nacional de atendimentos que pressiona essa esteira (procedimentos, consultas e exames realizados pelos planos) é parte do panorama macro do setor — ver Capítulo 1. O que importa aqui é que esse volume explica por que o fechamento de contas, a glosa e o atraso de repasse se tornam dores estruturais do prestador.

---

## 4.2 O padrão TISS/TUSS e o envio de lotes

O faturamento de contas médicas não é uma simples emissão de recibos e notas fiscais. Ele é governado estritamente por um padrão obrigatório definido pela ANS (a Agência Nacional de Saúde Suplementar, o regulador do setor — ver Capítulo 1): o **TISS — Troca de Informações na Saúde Suplementar** [fonte: health-concorrentes-bpo-gemini].

O TISS padroniza o formato e a troca eletrônica de dados entre o prestador e a operadora, feita por meio de arquivos no formato **XML** (um formato estruturado de dados que o computador da operadora consegue ler automaticamente) [fonte: health-concorrentes-bpo-gemini]. Esse padrão é atualizado periodicamente pela ANS; a versão vigente referenciada nas fontes é a de **Maio/2026** [fonte: health-concorrentes-bpo-gemini].

Andando junto com o TISS está o **TUSS — Terminologia Unificada da Saúde Suplementar**, que é a codificação que mapeia e categoriza milhares de procedimentos clínicos, materiais, taxas de sala e medicamentos [fonte: health-concorrentes-bpo-gemini]. Na prática, o TISS é o "envelope" (como os dados são organizados e transmitidos) e o TUSS é o "vocabulário" (que código corresponde a cada procedimento). Os dois precisam estar em perfeita harmonia: o envio TISS tem que usar a codificação TUSS correta, ou a cobrança não passa.

A cobrança propriamente dita é feita por meio de **guias** — os documentos que descrevem o que foi atendido. As fontes citam três tipos principais: a guia de **Consulta**, a guia de **SADT (Serviço de Apoio Diagnóstico Terapêutico**, que cobre exames e terapias) e a guia de **Honorários Médicos** [fonte: health-concorrentes-bpo-gemini]. Essas guias são agrupadas e enviadas em conjunto à operadora no que se chama de **lote** — um pacote de guias empacotado num único arquivo XML e transmitido de uma vez [fonte: health-concorrentes-bpo-gemini]. O ciclo operacional típico de quem faz esse trabalho vai da coleta e digitação das guias, passa pela exportação e envio do XML TISS, emissão de protocolos e monitoramento de pagamentos, e termina na recuperação de glosas e conciliação dos repasses [fonte: health-bpo-faturamento].

Antes de o lote sair, existe uma camada tecnológica que confere o arquivo: os **validadores TISS** (ferramentas como Ninsaúde Validador TISS, MEDTISS e ValidadorTISS) examinam a estrutura do XML antes da transmissão formal [fonte: health-concorrentes-bpo-gemini]. Eles checam, em microssegundos, pontos como a pertinência do número de credenciamento de quem executou o procedimento, o *hash* eletrônico da guia (uma assinatura digital que garante a integridade do arquivo), a numeração da carteirinha do beneficiário e a compatibilidade do CBO — o **Código Brasileiro de Ocupações**, que identifica a especialidade do profissional [fonte: health-concorrentes-bpo-gemini]. Esse filtro existe para bloquear erros "no berço", antes que virem recusa de pagamento.

---

## 4.3 A glosa — a recusa de pagamento

O resultado de qualquer inconsistência no faturamento, por menor que seja, é a **glosa**.

A glosa é a **recusa, parcial ou total, do pagamento de uma conta médica por parte da operadora de saúde** [fonte: health-concorrentes-bpo-gemini]. Ou seja: o prestador atendeu, enviou a cobrança, e a operadora respondeu que não vai pagar aquele item — ou só parte dele. As causas mais comuns descritas nas fontes são guias preenchidas de forma incompleta, uso de códigos TUSS defasados, falta de assinaturas obrigatórias, ausência de senha de autorização prévia, erros de digitação e divergências nos dados cadastrais do beneficiário [fonte: health-concorrentes-bpo-gemini].

As fontes nomeiam **duas famílias de glosa — a técnica e a administrativa** — mas não detalham a fronteira exata entre elas [fonte: health-concorrentes-bpo-gemini]. Pelo conjunto das causas descritas, é razoável organizar assim: a glosa **técnica** tende a se associar a problemas do próprio procedimento e de sua codificação (procedimento incompatível, código TUSS defasado, quantidade divergente), enquanto a glosa **administrativa** tende a se associar a falhas de processo e cadastro (ausência de senha/autorização, dados cadastrais divergentes, carteirinha inválida) [INFERÊNCIA — não verificada]. O ponto firme que as fontes sustentam é que existem essas duas categorias e que a auditoria prévia atua de forma profilática contra ambas [fonte: health-concorrentes-bpo-gemini].

O **impacto financeiro** da glosa é severo e tem duas dimensões. A primeira é de margem: glosas podem comprometer **até 30% de todo o faturamento bruto anual** de uma clínica se não houver um processo robusto de recuperação [fonte: health-concorrentes-bpo-gemini]. A segunda, menos óbvia e mais perigosa, é de caixa. Como o ciclo financeiro dos convênios já paga em prazos elásticos — 30, 60 ou 90 dias —, o atraso adicional gerado por uma glosa e seu recurso pode levar consultórios promissores à insolvência [fonte: health-concorrentes-bpo-gemini]. Em outras palavras, a glosa não é só perda de margem: é um **risco de caixa**, porque trava dinheiro que o prestador já contava receber [fonte: health-concorrentes-bpo-gemini].

Quando uma glosa acontece, o prestador não fica obrigado a aceitá-la passivamente. Ele pode interpor um **recurso de glosa** — uma contestação técnica enviada à operadora para tentar reaver o pagamento recusado [fonte: health-concorrentes-bpo-gemini]. O recurso, porém, tem dois inimigos: o **prazo recursal** (as operadoras impõem janelas exíguas para contestar) e a **complexidade técnica** (é preciso saber exatamente o que motivou a glosa e como rebatê-la). Trabalha-se aqui confrontando o que foi efetivamente faturado com o valor depositado pela operadora, identificando cada recusa e submetendo o recurso dentro do prazo [fonte: health-concorrentes-bpo-gemini].

Por isso a estratégia mais valorizada não é recuperar a glosa depois — é **impedir que ela aconteça**. A lógica é da pré-auditoria: validar o XML (credenciamento, *hash*, carteirinha, CBO, códigos) antes da transmissão formal, bloqueando a glosa "no berço" [fonte: health-concorrentes-bpo-gemini]. Uma das ferramentas do segmento (Ninsaúde) chega a reportar que rotinas guiadas por seus recursos mitigam em **99,25%** a perda de capital de trabalho gasta em auditorias contínuas de preparação do faturamento [fonte: health-concorrentes-bpo-gemini].

### Quanto a glosa custa — os números do setor (e por que variam tanto)

Os percentuais de glosa que circulam no mercado parecem contraditórios — vão de 7% a quase 18% —, mas a contradição é aparente: **dependem do recorte de quem mede**. Há dois sistemas de medição distintos, e confundi-los gera erro de leitura [fonte: divergencias-metricas-saude-suplementar]:

- **O setor inteiro (Painel de Indicadores de Glosa da ANS).** Medindo todos os ~6.700 prestadores do país — de grandes hospitais a pequenas clínicas e laboratórios —, a **glosa inicial** fica em torno de **7,31%** e a **glosa final** em **7,14%**, com prazo médio de pagamento de cerca de 33,6 dias [fonte: health-dossie-mesa-gpt | fonte: divergencias-metricas-saude-suplementar].
- **Os grandes hospitais privados (Observatório Anahp).** No recorte de ~176 hospitais de alta complexidade, o número é bem mais alto: **glosa inicial de 15,89% em 2024**, com pico de **17% no 1º trimestre de 2025**, mas **glosa final em torno de 1,96%** depois dos recursos [fonte: health-dossie-mesa-gpt | fonte: divergencias-metricas-saude-suplementar]. A apresentação da FBH à Câmara de Saúde Suplementar registrou a mesma trajetória de alta — a glosa inicial gerencial subiu de 11,89% (2023) para 15,89% (2024) [fonte: health-dossie-mesa-gpt].

A diferença entre os dois recortes não é erro: hospitais Anahp são maiores e mais complexos, a métrica "gerencial" inclui valores ainda em recurso, e a média da ANS é diluída por milhares de prestadores menores [fonte: divergencias-metricas-saude-suplementar]. (Um terceiro número que circula — glosa inicial de 18,02% / final de 1,84% — aparece numa fonte exploratória, mas **não foi confirmado em fonte primária**; fica registrado como não verificado [fonte: divergencias-metricas-saude-suplementar].)

O dado mais revelador é o **abismo entre a glosa inicial e a final**. Nos grandes hospitais, reter ~16% no início e devolver tudo menos ~2% no fim significa que **a maior parte da glosa não era dívida real — era dinheiro legítimo do prestador retido temporariamente** [fonte: health-dossie-gemini-brasil]. Ou seja, a glosa funciona também como um **mecanismo de dilatação de prazo de pagamento**: um crédito compulsório e gratuito que a operadora extrai do prestador enquanto a conta é contestada [fonte: health-dossie-gemini-brasil]. E o mais importante para quem oferece solução: análises do ciclo de receita apontam que cerca de **68% das glosas são administrativas — evitáveis antes do envio** [fonte: health-dossie-gemini-brasil], o que desloca o valor da pré-auditoria de "recuperar depois" para "impedir no berço".

Os motivos que mais retêm dinheiro têm nome e cifra. Um ranking consolidado do ciclo de receita coloca no topo: **valor apresentado a maior na fatura (R$ 496 mi), valor unitário acima da tabela contratual (R$ 299 mi), ausência de valoração no arquivo (R$ 213 mi), cobrança em duplicidade (R$ 108 mi) e senha de autorização ausente ou vencida (R$ 100 mi)** [fonte: health-dossie-gemini-brasil]. Quatro dos cinco maiores são checáveis automaticamente antes do envio — exatamente o terreno da pré-auditoria.

Há ainda o lado do **prazo**, não só do percentual. O setor mede o descompasso de caixa por dois indicadores: o **PMR — Prazo Médio de Recebimento** (dias entre faturar e receber da operadora) e o **PMP — Prazo Médio de Pagamento** (dias que o prestador tem para pagar fornecedores e equipe). Nos grandes hospitais, o PMR **piorou de 66,6 para 78,5 dias** entre o 3º trimestre de 2024 e o de 2025, enquanto o PMP caiu para ~46 dias — abrindo um **gap de caixa de mais de 32 dias** que o prestador precisa bancar com capital próprio ou crédito [fonte: health-dossie-gemini-brasil]. É esse gap, somado à glosa, que transforma "atender bem" em "quebrar mesmo faturando".

---

## 4.4 O faturamento em clínicas e em hospitais

A raiz do problema, nas clínicas, é o que as fontes chamam de **entropia administrativa**: a maioria dos consultórios cresce em volume de pacientes muito antes de montar uma retaguarda (*backoffice*) capaz de aguentar as exigências das operadoras [fonte: health-concorrentes-bpo-gemini]. Quando o faturamento é delegado a uma recepção sobrecarregada e sem especialização, o erro é quase inevitável — e cada erro vira glosa.

Para organizar esse trabalho, as empresas do setor estruturam a operação em **cinco vertentes complementares** [fonte: health-concorrentes-bpo-gemini]:

1. **Auditoria Prévia / Front-end** — validação de elegibilidade do paciente, controle de senhas de autorização e checagem dos códigos TUSS *antes* de empacotar o lote XML. É a etapa profilática contra glosas.
2. **Processamento / Middle-end** — coleta (às vezes física, via motoboy; às vezes 100% digital) e digitação minuciosa das guias de Consulta, SADT e Honorários, respeitando as regras contratuais de cada operadora.
3. **Gestão de Glosas e Recursos / Back-end** — confronto entre o que foi faturado e o que foi depositado, identificação das glosas e submissão dos recursos dentro do prazo, recuperando ativamente a receita retida.
4. **Inteligência Financeira e Conciliação** — organização dos recebíveis por centro de custo, fonte pagadora e tipo de atendimento, gerando previsibilidade de caixa e estruturando a **DRE — Demonstração do Resultado do Exercício** (o relatório que mostra lucro ou prejuízo do período).
5. **Credenciamento e Negociação Contratual** — interlocução com operadoras para habilitar a clínica em novas redes e pleitear reajustes de tabela, como a **CBHPM (Classificação Brasileira Hierarquizada de Procedimentos Médicos**, a tabela de referência de valores de procedimentos).

Visto como fluxo de ponta a ponta, o ciclo de BPO de faturamento percorre sete passos: (1) coleta/digitação de guias → (2) exportação/envio do XML TISS → (3) emissão de protocolos → (4) monitoramento de pagamentos → (5) recursos de glosas → (6) conciliação de repasses → (7) DRE gerencial [fonte: health-bpo-faturamento].

Há especificidades por tipo de prestador. Na **clínica**, sobretudo a multiprofissional e a de *coworking*, o ponto crítico é o **split de pagamentos** e o rateio de honorários entre os médicos que atenderam — daí a importância de relatórios analíticos de fechamento mensal fragmentados por profissional, que resolvem o atrito crônico da divisão de honorários entre sócios [fonte: health-concorrentes-bpo-gemini]. No **hospital** e nas clínicas cirúrgicas, o gargalo se desloca para os procedimentos de alto custo: a aprovação de **OPME — Órteses, Próteses e Materiais Especiais** (os materiais implantados ou usados em cirurgias) pode demorar semanas, e o acompanhamento dessa aprovação, do agendamento de internações e do diálogo direto com o hospital evita o cancelamento de procedimentos rentáveis [fonte: health-concorrentes-bpo-gemini]. Vale registrar que parte dos players atua justamente em clínicas **e** hospitais de pequeno e médio porte, com digitação de guias, auditoria de contas e envio TISS conforme o padrão da ANS [fonte: health-bpo-faturamento].

---

## 4.5 O mercado de BPO de faturamento

Toda essa operação pode ser feita dentro de casa ou terceirizada. A terceirização é o que se chama de **BPO — Business Process Outsourcing (Terceirização de Processos de Negócio)**: a transferência de uma função inteira da empresa para um fornecedor especializado externo [fonte: health-concorrentes-bpo-gemini]. No faturamento de saúde, isso significa entregar o ciclo de receita (RCM) a uma equipe externa de auditores e faturistas, para que o prestador foque no ato médico [fonte: health-concorrentes-bpo-gemini].

### Por que esse mercado existe: o custo da estrutura interna

O motor econômico do segmento é uma conta simples. Manter um analista ou faturista júnior/pleno em regime **CLT (Consolidação das Leis do Trabalho)** custa recorrentemente **mais de R$ 7.000 por mês** quando se somam salário-base e encargos (FGTS, férias, INSS, 13º, vale-transporte e alimentação), além de estrutura física e treinamento constante frente às mudanças das normas da ANS [fonte: health-concorrentes-bpo-gemini]. Sob um contrato de BPO, esse custo fixo vira um serviço com SLA (*Service Level Agreement*, o acordo de nível de serviço que define prazos e qualidade contratados), livre dos riscos de absenteísmo, com **economia líquida projetada de 40% a 60%** frente ao departamento interno convencional [fonte: health-concorrentes-bpo-gemini].

### Modelos de contrato e faixas de preço

As fontes descrevem **três modelos de precificação** [fonte: health-concorrentes-bpo-gemini]:

1. **Mensalidade fixa (fee de assinatura)** — valor recorrente para serviços previsíveis de BPO. Exemplo de referência: a Proos informa precificação **a partir de R$ 1.290/mês** para a delegação financeira de consultórios médicos [fonte: health-concorrentes-bpo-gemini].
2. **Remuneração variável (success fee)** — honorário percentual atrelado ao êxito obtido, geralmente vinculado à recuperação de glosas ou ao faturamento líquido validado. Alinha os incentivos: o fornecedor só ganha quando entrega resultado financeiro mensurável [fonte: health-concorrentes-bpo-gemini].
3. **Franquias e tiers por volume** — escalonamento por volumetria de guias, típico dos softwares de faturamento. Exemplo: o QualiTISS oferece planos inaugurais por **cerca de R$ 105/mês**, com envio validado de lotes de até 100 guias mensais [fonte: health-concorrentes-bpo-gemini].

A característica mais marcante desse mercado, porém, é a **opacidade de preços**. A quase totalidade dos players **não divulga valores publicamente**: num levantamento de 9 empresas, 8 (88,9%) não publicam preço [fonte: health-bpo-faturamento]. A grande exceção é a **TISSMED**, que anuncia planos a partir de **R$ 299/mês** (para cerca de 100 guias) — o único preço público declarado no segmento de BPO TISS para clínicas [fonte: health-bpo-faturamento].

### Os players do mercado

O mercado brasileiro de BPO de faturamento e contas médicas (referência 2024–2026) reúne fornecedores com escopos distintos, da digitação pura à consultoria estratégica. O quadro abaixo consolida os players mapeados nas fontes — apresentados aqui como **descrição neutra do segmento**, sem juízo sobre posicionamento competitivo:

| Player | Foco operacional | Diferencial declarado | Sede |
|---|---|---|---|
| **TISSMED** | Clínicas e hospitais de pequeno/médio porte | Recuperação de glosas orientada a dados; **98% de sucesso em recursos** administrativos; **R$ 299/mês** (preço público); 15+ anos de atuação | RJ (uma fonte) / SP (outra)* |
| **Fatura Clínica** | PMEs, clínicas e consultórios em geral | Terceirização operacional completa + treinamento de secretárias; correção do erro na origem | São José dos Campos (SP) |
| **Med Fac** | Médicos autônomos, clínicas cirúrgicas | Assessoria "humanizada"; *concierge* de internação e aprovação de OPME/cirurgias de alto custo | Brasília (DF) |
| **Eficaz Med** | Consultórios especializados (ex.: ortopedia) | Redução drástica da taxa de glosa; relatórios de produtividade por médico; credenciamento | RJ |
| **OSIDE** | Operadoras e PMEs de saúde | Rastreabilidade documental; digitação em escala; digitalização/higienização de arquivos | SP |
| **Solution Med** | Laboratórios e centros de diagnóstico | Logística física das guias (motoboy) + preparo, digitação e exportação do XML | Regional |
| **Carelli Associados** | PMEs de saúde | Substituição do faturamento interno com redução de passivo trabalhista (vs. CLT) | Regional |
| **Faturebem** | Clínicas compartilhadas e sociedades | Foco em **split de pagamentos**; relatórios fragmentados por médico | Nacional |
| **AdmClyn** | Clínicas multiespecialidades | Controle de recursos e glosas; gestão de cronogramas de reajuste contratual | Nacional |
| **Seimed** | Consultórios médicos | Faturamento terceirizado + vertical de credenciamento (ex.: Qualicorp, Hapvida) | Nacional |
| **Gonçalves Contabilidade** | Clínicas médicas em SP | Expertise contábil do setor; TISS 4.01; gestão de glosas; DRE por especialidade | SP |
| **MAC Finance** | Clínicas, hospitais e laboratórios | "Solução 360º" (TISS/TUSS, glosas **<5%**, conciliação, credenciamento); atendimento nacional | Nacional |
| **Reset Empresarial** | Clínicas e consultórios | Planos Essencial/Performance/Premium Saúde; indicadores e apoio gerencial | SP |
| **Invoicemed** | Clínicas médicas e odontológicas | Enfermeiros para auditoria; recuperação de glosas; contabilidade de recebíveis | Nacional |
| **Soluzione Faturamento** | Clínicas e hospitais de médio porte | Relacionamento forte com operadoras locais; **sede no Espírito Santo** | Vitória (ES) |
| **Loki** | Clínicas, hospitais e labs (todos os portes) | Automação 24/7; dashboards de glosas; **único com integrações declaradas** (Doctoralia, iClinic, Feegow, Tasy) | Global |
| **Maida Health** | **Operadoras** (não atende clínicas) | BPO Tech com IA + cadastro de beneficiários; serve o lado da operadora no ciclo TISS | Nacional |

\* As fontes divergem sobre a sede da TISSMED: uma indica Rio de Janeiro/RJ (com 17+ anos de *know-how*), outra a localiza em SP (atuação desde 2008) [fonte: health-bpo-faturamento | fonte: health-concorrentes-bpo-gemini].

Dois recortes ajudam a ler a tabela. Primeiro, a **Maida Health** é o único player voltado às **operadoras**, e não às clínicas — útil para delimitar a fronteira do segmento de faturamento do prestador [fonte: health-bpo-faturamento]. Segundo, existe um player **regional capixaba** (Soluzione Faturamento, em Vitória/ES) com foco em clínicas e hospitais de médio porte e relacionamento forte com operadoras locais [fonte: health-bpo-faturamento].

Adjacente a esse núcleo de faturamento existe uma camada de **BPO Financeiro e Contabilidade especializada em saúde** — empresas como Proos, Cestacorp, RRT Contabilidade, Moresco, Contabilizei e Support Health — que atacam o colapso de tesouraria da clínica (contas a pagar, inadimplência no particular, enquadramento tributário) em vez do envio TISS propriamente dito [fonte: health-concorrentes-bpo-gemini]. Algumas combinam as duas frentes; a MAC Finance, por exemplo, integra faturamento TISS a planejamento tributário [fonte: health-concorrentes-bpo-gemini].

### Integrações e base tecnológica

Um diferencial decisivo — e raro — é a **integração com o sistema de gestão clínica** que a clínica já usa. Entre os players analisados, **apenas a Loki declara integração** com plataformas como Doctoralia, iClinic, Feegow e Tasy; os demais operam sem integração declarada, o que implica retrabalho manual [fonte: health-bpo-faturamento]. Por baixo de toda a operação roda uma base tecnológica comum: os **validadores TISS** já citados, somados a **RPA — Robotic Process Automation (Automação Robótica de Processos**, robôs que executam tarefas repetitivas) e **OCR — Optical Character Recognition (Reconhecimento Óptico de Caracteres**, leitura automática de documentos fotografados) [fonte: health-concorrentes-bpo-gemini].

Por fim, como todo o tráfego envolve prontuários e códigos de diagnóstico (CID), o segmento opera sob as obrigações da **LGPD — Lei Geral de Proteção de Dados**: protocolos restritivos de tráfego, VPNs, assinatura criptográfica de duplo fator e controle de acesso são parte do serviço, justamente para encerrar o fluxo inadequado de arquivos de paciente trafegando por e-mails de contadores ou recepcionistas [fonte: health-concorrentes-bpo-gemini].

### Critérios de seleção

Para escolher um fornecedor de BPO de faturamento, as fontes consolidam cinco critérios objetivos [fonte: health-bpo-faturamento]:

1. **Integração** com o sistema de gestão clínico já em uso (Doctoralia, iClinic, Feegow, Tasy) — sem ela, há retrabalho garantido.
2. **SLA de glosas documentado** — um compromisso explícito de prazo e meta. Nas fontes, a MAC Finance é o player que declara publicamente um teto (reduzir glosas a **<5%**) [fonte: health-bpo-faturamento].
3. **Evidências de compliance com a ANS** — conformidade com o padrão TISS e normas do regulador.
4. **Contrato formalizado** com valor fixo (ou por guia), SLA de entrega e controle de qualidade — necessário justamente porque a maioria não publica preço nem condições [fonte: health-bpo-faturamento].
5. **Depoimentos e cases verificáveis** — prova de resultado.

Como baseline de custo, as fontes sugerem usar a TISSMED (R$ 299/mês, preço público, 15+ anos de experiência) como ponto de partida de comparação antes de avaliar as propostas sem preço público [fonte: health-bpo-faturamento].

---

## 4.6 Síntese do capítulo

Do lado do prestador, atender é a parte fácil; **receber é o problema**. O ciclo de receita (RCM) percorre uma esteira longa, governada pelo padrão obrigatório TISS/TUSS, em que cada guia é empacotada em lotes XML e enviada à operadora. O ponto de falha recorrente é a **glosa** — a recusa, parcial ou total, do pagamento —, que ataca em duas frentes: corrói até 30% do faturamento bruto e, pior, trava o caixa de quem já opera com prazos de 30/60/90 dias. Combatê-la exige tanto **pré-auditoria** (impedir a glosa no berço, via validação do XML) quanto **recurso de glosa** (recuperar o que foi recusado, dentro de prazos exíguos).

Esse processo deu origem a um mercado próprio de **BPO de faturamento**, movido pela aritmética de que a estrutura interna em CLT custa caro (mais de R$ 7.000/mês por analista) e a terceirização promete 40% a 60% de economia. É um mercado **opaco em preços** (quase ninguém publica valores, sendo a TISSMED a exceção a R$ 299/mês), com **dezenas de players** de escopo variado — da digitação pura à consultoria estratégica —, modelos de contrato em mensalidade fixa, success fee ou tiers por volume, e diferenciais que vão de integração com sistemas de gestão (raro — só a Loki) a compliance LGPD. A escolha de um fornecedor se ancora em cinco critérios objetivos: integração, SLA de glosas, compliance ANS, contrato formal e cases verificáveis.

> **Fronteiras com os demais capítulos:** o panorama macro do setor e seus números gerais estão no Capítulo 1; a corretora e seu modelo de negócio, nos Capítulos 2 e 3; e o perfil de quem decide a contratação desse tipo de serviço, junto da jornada de compra, é tema do Capítulo 5. Este capítulo se limitou ao **processo** de faturamento e ao **mercado** que o atende.
