# Módulo 3 — A Clínica

---

## Antes de ler

**Uma clínica atendeu 300 consultas no mês. Enviou todas as cobranças para a operadora. Recebeu 70% do valor esperado. Onde foi parar os outros 30% — e quem tem a responsabilidade de recuperar?**

Essa pergunta tem uma resposta técnica e uma resposta econômica. Este módulo vai te dar as duas.

---

## O texto

### O problema que ninguém vê de fora

Do lado de fora, uma clínica parece simples: médico atende, operadora paga. A receita flui.

Não é assim que funciona.

Entre o ato médico e o dinheiro disponível na conta da clínica existe uma esteira inteira de etapas administrativas. Cada etapa tem regras, prazos, formatos obrigatórios — e em cada etapa, um erro pode travar a receita ou, pior, fazer ela desaparecer para sempre.

Esse conjunto de etapas tem nome: **RCM — Revenue Cycle Management**, ou **Ciclo de Gestão da Receita**. É a engrenagem que transforma atendimento em recebimento. E o gargalo central não é "atender mais" — é **converter atendimento em recebimento sem deixar dinheiro parado pelo caminho**.

---

### A esteira: do atendimento ao pagamento

Vamos percorrer o caminho que uma cobrança médica percorre.

**1. Verificação de elegibilidade.** Antes de atender, a recepção verifica se aquele paciente está ativo no plano e se o procedimento está coberto. Uma carteirinha vencida, uma carência ativa, um procedimento que precisa de autorização prévia — esses problemas descartados na entrada evitam glosas na saída.

**2. Autorização prévia.** Muitos procedimentos exigem que a operadora autorize antes de acontecer. Se o médico fizer a cirurgia sem a autorização, a clínica corre o risco de não receber — mesmo que o procedimento seja tecnicamente correto.

**3. Registro clínico.** O médico registra o que fez: o código do procedimento, os materiais usados, a evolução clínica. Essa informação vai para o prontuário eletrônico. E é aqui que começa um dos problemas mais frustrantes do setor: o médico decide pelo melhor tratamento clínico sem necessariamente conhecer as regras contratuais da operadora. O resultado disso aparece na fatura — como glosa.

**4. Codificação.** O setor tem seu próprio vocabulário de códigos: o **TUSS — Terminologia Unificada da Saúde Suplementar**. Cada procedimento, cada material, cada taxa tem um código TUSS. Usar o código errado, desatualizado ou incompatível com o CID-10 (o código da doença) é causa imediata de glosa.

**5. Montagem e envio do lote.** As cobranças são agrupadas em **guias** (documentos que descrevem cada atendimento), depois empacotadas em **lotes** — arquivos no formato **XML** transmitidos eletronicamente para a operadora. Esse formato é padronizado pela ANS e se chama **TISS — Troca de Informação em Saúde Suplementar**. Uma tag no XML fora do lugar, um hash de segurança incorreto, um número de credenciamento inválido — o lote inteiro é rejeitado.

**6. Conferência antes do envio.** Antes de transmitir, o ideal é passar por um validador de TISS — uma ferramenta que confere a estrutura do arquivo e detecta erros antes de chegarem na operadora. Muitas clínicas pulam essa etapa. E pagam caro.

**7. Recebimento do demonstrativo de retorno.** Depois que o lote chega na operadora, ela devolve um **demonstrativo de retorno**: um relatório que diz o que aceitou pagar e o que recusou. A parte recusada tem nome: **glosa**.

**8. Recurso de glosa.** Quando a glosa é injusta — e frequentemente é —, a clínica pode contestar. Mas o recurso tem dois inimigos: os prazos curtos que as operadoras impõem e a complexidade técnica de saber exatamente como argumentar.

**9. Conciliação.** Por fim, a clínica cruza o que esperava receber com o que de fato entrou na conta bancária. Qualquer diferença — glosa não resolvida, pagamento a menor, vida cobrada que não estava no lote — precisa ser investigada e cobrada.

Esse ciclo inteiro, da autorização ao recebimento, pode levar 30, 60 ou até 90 dias. E qualquer problema em qualquer etapa reinicia o cronômetro.

---

### A glosa: o inimigo central

A glosa é a recusa, total ou parcial, do pagamento de uma conta médica pela operadora. É o termo mais temido no setor porque tem dois efeitos devastadores ao mesmo tempo.

**Efeito 1 — Margem.** Glosas podem comprometer até 30% do faturamento bruto anual de uma clínica se não houver processo robusto de recuperação. Em hospitais de grande complexidade, a taxa de glosa inicial chegou a **15,89% em 2024**, com pico de **17% no primeiro trimestre de 2025**.

**Efeito 2 — Caixa.** O ciclo de pagamentos dos convênios já é lento: 30, 60, às vezes 90 dias. Uma glosa adiciona tempo a esse prazo — a clínica precisa contestar, a operadora precisa reavaliar, mais 30, 60 dias passam. Clínicas promissoras foram à insolvência não por falta de pacientes, mas porque o dinheiro dos atendimentos ficou represado em glosas enquanto os funcionários precisavam de salário.

As causas mais comuns:
- Guia preenchida de forma incompleta ou com dado incorreto
- Código TUSS desatualizado ou incompatível com o CID-10
- Assinatura obrigatória faltando
- Autorização prévia ausente ou vencida
- Dado cadastral do beneficiário divergente (aqui aparece a conexão com o Módulo 2 — se a corretora não fez a movimentação cadastral corretamente, a clínica recebe uma glosa por elegibilidade)

**Um dado que reorganiza tudo:** cerca de **68% das glosas são administrativas** — geradas por erro burocrático, não por problema clínico. São evitáveis antes do envio. Isso transforma o problema de "como recuperar a glosa" para "como impedir que a glosa nasça".

---

### A diferença entre glosa inicial e glosa final

Nos grandes hospitais do Brasil, há um fenômeno revelador: a glosa inicial (o que foi recusado logo no primeiro processamento) foi de **15,89%** em 2024. Mas a glosa final (o que de fato ficou sem pagamento depois dos recursos) foi de apenas **1,96%**.

Isso significa que 14% do faturamento foi retido, contestado, e depois devolvido. A operadora glosa, o prestador contesta, a operadora paga.

O que isso revela? A glosa funciona também como um **mecanismo de dilatação de prazo de pagamento**. A operadora usa a glosa para segurar dinheiro enquanto o prestador trabalha para provar que tem razão. É um crédito compulsório e gratuito que a operadora extrai do prestador.

Para a clínica sem processo de recurso eficiente, esse dinheiro nunca volta. Para a clínica com processo, ele volta — mas meses depois, depois de muito trabalho.

---

### O padrão que governa tudo: TISS e TUSS

O faturamento médico não é livre. É governado por um padrão obrigatório definido pela ANS.

O **TISS** é o formato de transmissão — o "envelope" em que as cobranças são organizadas e enviadas para as operadoras, em arquivo XML. É atualizado periodicamente pela ANS; a versão atual (maio/2026) é o TISS 4.01.

O **TUSS** é o vocabulário — o "dicionário" de códigos que identifica cada procedimento, material e taxa. Código TUSS incompatível com o que foi feito é causa direta de glosa.

As guias dentro do TISS têm tipos específicos:
- **Guia de Consulta** — para consultas ambulatoriais
- **Guia SP/SADT** — Serviço de Apoio Diagnóstico e Terapêutico, para exames e terapias
- **Guia de Honorários Médicos** — para os honorários dos médicos
- **OPME** — Órteses, Próteses e Materiais Especiais, itens implantados em cirurgias

Cada guia tem campos obrigatórios, assinaturas específicas, e códigos que precisam bater. A falta de qualquer elemento é glosa certa.

---

### O mercado que nasceu desse problema: BPO de faturamento

O problema é tão complexo e tão trabalhoso que criou um mercado inteiro de empresas especializadas em fazer esse trabalho por terceirização. Chama-se **BPO — Business Process Outsourcing**, ou terceirização de processos de negócio.

Um BPO de faturamento assume o ciclo inteiro de receita da clínica: coleta as guias, monta os lotes, faz a pré-auditoria, envia o XML, monitora o pagamento, contesta as glosas, concilia o que entrou.

**Por que isso faz sentido financeiramente?** Manter um analista de faturamento em CLT custa mais de R$ 7.000 por mês quando se somam salário e encargos. Um BPO especializado promete redução de 40% a 60% desse custo, com equipe treinada e SLA documentado.

**O mercado de BPO capixaba.** No Espírito Santo, existe ao menos um player regional com foco em clínicas e hospitais de médio porte com relacionamento forte com as operadoras locais (Soluzione Faturamento, em Vitória). No Brasil, dezenas de players atendem desde digitação pura de guias até consultoria estratégica de ciclo de receita — TISSMED, Fatura Clínica, Med Fac, Eficaz Med, MAC Finance, Loki, entre outros.

**O detalhe que diferencia:** a maioria não publica preços. Em levantamento de 9 empresas, 8 (88,9%) não divulgam valores publicamente. A única exceção rastreada é a TISSMED, com planos a partir de R$ 299/mês. O QualiTISS, que é mais uma ferramenta que um BPO, tem planos a partir de R$ 105/mês para volumes pequenos de guias.

**O diferencial mais raro:** integração com o sistema de gestão clínica já usado pela clínica. Entre os players mapeados, apenas a Loki declara integração com Doctoralia, iClinic, Feegow e Tasy. Os demais operam sem integração — o que implica digitação manual dos dados que já estão em outro sistema.

---

### Os cinco passos de um BPO de faturamento bem feito

Se alguém perguntar o que um BPO de faturamento faz, a resposta são cinco verticais:

**1. Pré-auditoria** — verificar antes do envio: elegibilidade, autorização, códigos TUSS corretos, hash de segurança, CBO do profissional. É a etapa que impede a glosa de nascer.

**2. Processamento** — coleta e digitação das guias, respeito às regras de cada operadora, montagem do XML.

**3. Gestão de glosas** — confrontar o que foi faturado com o demonstrativo de retorno, identificar cada recusa, submeter recurso dentro do prazo.

**4. Conciliação financeira** — cruzar os recebíveis por convênio, por médico, por tipo de atendimento. Gerar a DRE — Demonstração de Resultado — para que a clínica saiba onde está ganhando e onde está perdendo.

**5. Credenciamento** — interlocução com operadoras para incluir a clínica em novas redes e negociar reajuste de tabela.

---

### O gap de caixa que poucos calculam

Existe um problema além da glosa que afeta especialmente os prestadores de maior porte: o **gap de caixa** entre o prazo de receber dos convênios e o prazo de pagar os fornecedores.

Nos grandes hospitais brasileiros, esse gap piorou entre 2024 e 2025: o prazo médio de recebimento dos convênios (PMR) foi de 66,6 para 78,5 dias. O prazo médio de pagamento de fornecedores (PMP) caiu para 46 dias. Resultado: a clínica espera 78 dias para receber, mas precisa pagar em 46 — um buraco de 32 dias que ela banca com capital próprio ou crédito.

Glosa + prazo longo + gap de caixa = a equação que quebra clínicas que atendem bem e cobram mal.

---

## Frase de ouro

> "A clínica não tem problema de atendimento — tem problema de ______________. A ______________ é a recusa de pagamento da operadora, e cerca de 68% dela é causada por erro ______________, não por problema clínico. O melhor caminho não é recuperar depois — é ______________ antes do envio."

*Quatro espaços preenchidos = pode ir para o Módulo 4.*
