---
source_file: perplexity-mod2-teletrabalho-jornada-assedio.md
converted_at: 2026-03-25
original_extension: md
processor: Echo (aiox-m2m-etl)
extraction_quality: full
domain: Teletrabalho, Jornada de Trabalho e Assédio
source_type: perplexity-deep-research
source_tool: Perplexity Pro (Deep Research)
agent_target: juridica-trabalhista
squad: squad-cadarn-juridica
module: 2
module_title: Teletrabalho, Jornada e Assédio no Ambiente Corporativo
---

<content>


# Você é um pesquisador especialista em Direito do Trabalho brasileiro, com foco em teletrabalho, jornada de trabalho e assédio no ambiente corporativo. Sua

tarefa é produzir um módulo exaustivo e atualizado (base: março de 2026) sobre estas três áreas, com foco em empresas de serviços (agências de marketing
digital, imobiliárias, clínicas, escritórios).

Contexto de uso: Este documento será processado por um pipeline automatizado (M2M + RAG). O chunking é feito por headers Markdown (\#\# e \#\#\#). Os metadados
em HTML comment são parseados por regex antes do chunking e funcionam como tags de classificação semântica — mantenha o formato exato. Output
obrigatório: Markdown puro, sem exceções. O documento será carregado como base de conhecimento de um agente Claude Code (CLI) utilizado por equipes de RH
de empresas de serviços premium em capitais brasileiras (foco Vitória/ES).

  <!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 2] [TEMA: teletrabalho-jornada-assedio] -->
Cubra obrigatoriamente:

1. **Teletrabalho e Home Office — Lei 14.442/2022**
    - Definição legal de teletrabalho (CLT art. 75-B) — diferença entre teletrabalho e trabalho externo
    - Modalidades: teletrabalho por jornada vs por produção/tarefa — implicações
    - Controle de jornada: quando se aplica (por jornada) e quando NÃO (por produção, art. 62, III CLT)
    - Contrato/aditivo obrigatório — cláusulas essenciais
    - Equipamentos e infraestrutura — responsabilidade do empregador, ajuda de custo (natureza indenizatória)
    - Ergonomia (NR-17) — responsabilidade no home office
    - Modelo híbrido — regras, ida ao escritório não descaracteriza teletrabalho
    - Prioridade para empregados com deficiência e com filhos até 4 anos (art. 75-F CLT)
    - Jurisprudência recente (2023-2026) sobre teletrabalho — se verificável
    - Estagiário em teletrabalho — permitido? Requisitos
2. **Jornada de Trabalho — CLT arts. 58-65**
    - Jornada normal: 8h/dia, 44h/semana, 220h/mês
    - Horas extras: limite de 2h/dia, adicional mínimo 50%, cálculo (salário/220 × 1,5)
    - Banco de horas: acordo individual (compensação 6 meses) vs coletivo (12 meses)
    - Jornada 12×36: requisitos, quando é aplicável, acordo individual permitido pós-Reforma
    - Sobreaviso e prontidão (art. 244 CLT, Súmula 428 TST): uso de celular/WhatsApp configura sobreaviso?
    - Intervalo intrajornada: 1h mínimo (>6h), supressão parcial por norma coletiva
    - Exceções ao controle de jornada (art. 62 CLT): cargos de confiança, trabalhadores externos, teletrabalhadores por produção
    - Trabalho noturno: adicional 20%, hora noturna reduzida (52min30s)
    - Direito à desconexão digital: tendência jurisprudencial, cobranças via WhatsApp fora do horário
    - Tabela de adicionais: hora extra, noturno, insalubridade, periculosidade
3. **Assédio Moral e Sexual no Trabalho**
    - Lei 14.457/2022: CIPA passa a ser CIPAA (Comissão de Prevenção de Acidentes e Assédio)
    - Obrigação de canal de denúncias para empresas com CIPA
    - Capacitação anual obrigatória sobre assédio
    - Tipos de assédio moral: vertical descendente, ascendente, horizontal, organizacional — com exemplos para agências/imobiliárias
    - Assédio sexual (art. 216-A CP): tipificação penal, responsabilidade do empregador
    - Assédio no ambiente digital: mensagens de WhatsApp fora do horário, cobranças abusivas em grupos, exposição vexatória em reuniões remotas
    - Responsabilidade do empregador: objetiva? Subjetiva? Jurisprudência
    - Danos morais trabalhistas (art. 223-G CLT): parâmetros de fixação, tetos por gravidade (leve, média, grave, gravíssima), STF declarou tetos
inconstitucionais?
    - Programa de integridade/compliance: código de conduta, treinamentos, canal de denúncia, investigação, medidas disciplinares
    - Jurisprudência recente sobre assédio digital (WhatsApp) — se verificável
4. **Tabela comparativa de riscos** — Para uso operacional:
Colunas: Situação | Base legal | Risco (ALTO/MÉDIO/BAIXO) | Ação recomendada | Multa/Penalidade

Regras de integridade:

- Cite número de processo, tribunal e data para TODA jurisprudência
- Se não encontrar jurisprudência específica: caso análogo com nota "⚠️ ANALOGIA" > placeholder "não encontrado com fonte confiável"
- Doutrina: pode citar Godinho Delgado, Sérgio Pinto Martins, Vólia Bomfim se obra existir
- Use HTML comments: <!-- [MÓDULO: 2] [SUBTEMA: nome] [TIPO: tipo] -->
- Chunks entre 300-800 palavras por seção \#\#/\#\#\#
- Formato: Markdown puro, headers \#\# e \#\#\#, tabelas onde aplicável

Agora tenho informação suficiente para produzir o módulo completo. Vou estruturar o documento abaixo:

***

<!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 2] [TEMA: teletrabalho-jornada-assedio] -->

# MÓDULO 2 — TELETRABALHO, JORNADA DE TRABALHO E ASSÉDIO NO AMBIENTE CORPORATIVO

> **Base normativa:** CLT (Decreto-Lei 5.452/1943, atualizado); Lei 14.442/2022; Lei 14.457/2022; Reforma Trabalhista (Lei 13.467/2017); NR-17 (redação 2021); Súmulas TST pertinentes; jurisprudência até março de 2026.
> **Público-alvo:** Equipes de RH de empresas de serviços premium — agências de marketing digital, imobiliárias, clínicas e escritórios — com foco em Vitória/ES.
> **⚠️ Aviso de atualização:** Este módulo expira em setembro de 2026. Verificar publicações do TST, STF e MTE para alterações supervenientes.

***

## PARTE 1 — TELETRABALHO E HOME OFFICE

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-definicao-legal] [TIPO: norma] -->

### 1.1 Definição Legal e Distinção de Trabalho Externo

A **Lei 14.442/2022** reformulou o art. 75-B da CLT, estabelecendo que teletrabalho (ou trabalho remoto) é a **prestação de serviços fora das dependências do empregador, de maneira preponderante ou não**, com a utilização de tecnologias de informação e de comunicação, que, por sua natureza, não configure trabalho externo. A supressão do requisito da preponderância é a principal inovação: basta que haja trabalho fora das dependências com uso de TIC, mesmo que o empregado compareça ao escritório em alguns dias da semana, para que a relação seja qualificada como teletrabalho.

**Distinção fundamental — teletrabalho vs. trabalho externo (art. 62, I CLT):**


| Critério | Teletrabalho (art. 75-B) | Trabalho Externo (art. 62, I) |
| :-- | :-- | :-- |
| Local de execução | Residência, coworking, qualquer local com TIC | Campo, rua, obras, visitas — natureza itinerante |
| Supervisão tecnológica | Possível e frequente | Incompatível com a natureza da atividade |
| Controle de jornada | Possível (por jornada) ou dispensado (por tarefa) | Dispensado por padrão |
| Exemplos | Analista, designer, consultor imobiliário remoto | Corretor de imóveis em visitas, vendedor externo, técnico de campo |
| Registro em contrato | Obrigatório (art. 75-C) | Recomendado, mas não há exigência específica de aditivo |

> **Atenção para imobiliárias e agências:** O corretor que faz visitas a imóveis configura trabalho externo (art. 62, I); o analista de marketing ou o assistente administrativo que opera de casa configura teletrabalho (art. 75-B). A confusão entre as categorias gera passivos relevantes, especialmente em pretensões de horas extras.

***

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-modalidades-jornada-producao] [TIPO: norma] -->

### 1.2 Modalidades: Por Jornada vs. Por Produção ou Tarefa

A Lei 14.442/2022 consagrou expressamente duas modalidades distintas de teletrabalho, com regimes jurídicos diferentes:

**Modalidade 1 — Teletrabalho por Jornada:**

- O empregado cumpre horário determinado (início, fim, intervalos);
- Sujeita-se ao controle de ponto (eletrônico, manual ou por sistema digital);
- Faz jus a horas extras, adicional noturno e sobreaviso quando cabíveis;
- É a modalidade padrão quando o contrato/aditivo não dispuser expressamente sobre produção ou tarefa.

**Modalidade 2 — Teletrabalho por Produção ou Tarefa:**

- O empregado é contratado para entregar resultado (projeto, relatório, campanha, número de atendimentos);
- **Enquadrado no art. 62, III da CLT** — não sujeito a controle de jornada;
- **Não tem direito a horas extras**, adicional noturno por jornada, sobreaviso;
- O contrato deve especificar o regime expressamente; cláusula genérica não basta.

> **Risco crítico para agências de marketing:** Contratar "por tarefa" sem cláusula expressa e depois supervisionar o empregado via Slack, Teams ou WhatsApp em horários fixos. A jurisprudência tem requalificado o regime para "por jornada" quando a supervisão digital é contínua e o empregador define horários de disponibilidade — vide análise na seção 1.9.

***

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-controle-jornada] [TIPO: norma] -->

### 1.3 Controle de Jornada no Teletrabalho

A Lei 14.442/2022 eliminou a presunção automática de que o teletrabalhador está fora do controle de jornada. O regime aplicável depende **exclusivamente do que foi pactuado no contrato ou aditivo**:

**Quando o controle de jornada SE APLICA:**

- Teletrabalho por jornada (horário definido);
- Qualquer situação em que o empregador imponha, na prática, horários de início, fim ou disponibilidade, independentemente do rótulo contratual;
- Empregado cobrado a responder mensagens em janelas fixas de tempo.

**Quando o controle de jornada NÃO se aplica (art. 62, III CLT):**

- Teletrabalhador contratado expressamente por produção ou tarefa;
- Ausência de fixação de horários, sem monitoramento de disponibilidade;
- A exceção deve constar expressamente do instrumento contratual.

**Boas práticas para o RH:**

1. Definir no aditivo de teletrabalho: qual é o regime (jornada ou tarefa)?
2. Se por jornada: especificar horário de início, fim, intervalo e o sistema de registro;
3. Se por tarefa: descrever as entregas esperadas, prazo, forma de aferição;
4. Nunca enviar mensagens cobrando disponibilidade em horários fixos para empregado supostamente contratado por tarefa — isso reconstitui, na prática, o controle de jornada.

***

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-contrato-aditivo] [TIPO: norma] -->

### 1.4 Contrato e Aditivo Obrigatório — Cláusulas Essenciais

A prestação de serviços em teletrabalho deve constar **expressamente do instrumento de contrato individual de trabalho** (art. 75-C da CLT). Para empregados que já trabalham presencialmente e migram para o regime remoto, é obrigatório **aditivo contratual escrito**.

**Cláusulas essenciais do contrato/aditivo de teletrabalho:**


| Cláusula | Conteúdo mínimo | Base legal |
| :-- | :-- | :-- |
| Modalidade | Por jornada ou por produção/tarefa | Art. 75-B CLT |
| Local de trabalho | Endereço principal (residência, coworking); vedação/permissão de trabalho no exterior | Art. 75-C, §3º CLT |
| Equipamentos | Quem fornece: empregador ou empregado; inventário dos bens fornecidos | Art. 75-D CLT |
| Ajuda de custo | Valor, periodicidade, natureza indenizatória | Art. 75-D CLT |
| Controle de jornada | Sistema utilizado, horário, forma de registro | Art. 75-B e art. 62, III CLT |
| Ergonomia | Declaração de ciência do trabalhador; orientações NR-17 | NR-17 |
| Prazo de retorno | Prazo de aviso para retorno ao presencial (mínimo 15 dias, salvo disposição em contrário) | Art. 75-C, §2º CLT |
| Prioridade vulneráveis | Disposição sobre filhos até 4 anos e PcD | Art. 75-F CLT |

**Retorno ao regime presencial:** O empregador pode determinar o retorno, mas deve conceder **prazo mínimo de 15 dias**, por escrito (art. 75-C, §2º CLT). O não cumprimento do prazo expõe a empresa a indenização por danos materiais e morais.

**Trabalho fora da localidade contratual:** Se o empregado optar por fazer teletrabalho de outra cidade ou país sem previsão contratual, o empregador **não é responsável pelas despesas de retorno** ao local originalmente pactuado (art. 75-C, §3º CLT).

***

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-equipamentos-ajuda-custo] [TIPO: norma] -->

### 1.5 Equipamentos, Infraestrutura e Ajuda de Custo

O art. 75-D da CLT estabelece que as disposições sobre equipamentos e infraestrutura devem constar do contrato. Na ausência de previsão específica, a responsabilidade recai sobre o empregador.

**Regras sobre equipamentos:**

- Se o empregador **fornece** os equipamentos: ele é responsável pela manutenção, atualização e substituição em caso de defeito;
- Se o empregado **utiliza equipamento próprio**: deve haver cláusula expressa e, preferencialmente, ajuda de custo para depreciação;
- A empresa pode estipular que o empregado use apenas equipamentos corporativos por razões de segurança da informação (LGPD — Lei 13.709/2018).

**Natureza indenizatória da ajuda de custo:**

- A **ajuda de custo** paga ao teletrabalhador para cobrir despesas com energia elétrica, internet, telefone e consumíveis tem **natureza indenizatória** — não integra o salário, não incide FGTS, INSS ou IRRF (art. 75-D CLT c/c art. 457, §2º CLT);
- O valor deve ser razoável e proporcional ao custo real; valores despropositadamente altos podem ser requalificados como salário;
- Recomenda-se formalizar o pagamento em contracheque com rubricas separadas de "Ajuda de Custo — Teletrabalho" para blindagem fiscal.

**Itens cobertos usualmente:**

- Internet banda larga (rateio proporcional de R\$ 80–150/mês é padrão de mercado em capitais);
- Energia elétrica (rateio parcial);
- Material de escritório (papel, cartuchos);
- Manutenção e depreciação de equipamentos próprios.

***

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-ergonomia-nr17] [TIPO: norma] -->

### 1.6 Ergonomia (NR-17) no Home Office

A **Norma Regulamentadora 17 (NR-17)**, em sua redação vigente (portaria MTE 2024), aplica-se ao ambiente doméstico de trabalho. A responsabilidade do empregador não cessa pelo fato de o trabalho ser executado na residência do empregado.

**Obrigações do empregador quanto à ergonomia no teletrabalho:**

1. **Análise ergonômica do trabalho (AET):** Deve avaliar as condições do posto doméstico, preferencialmente por laudo de profissional habilitado (ergonomista, fisioterapeuta);
2. **Orientação ao empregado:** Enviar checklist de ergonomia e guia de adequação do posto de trabalho (altura de monitor, cadeira, iluminação, postura);
3. **Fornecimento ou custeio:** Se a análise identificar inadequação (ex.: cadeira inadequada), o empregador deve fornecer o equipamento ou conceder ajuda de custo específica;
4. **Registro documentado:** Guardar comprovante de entrega das orientações e de eventual treinamento — serve como defesa em reclamações de doenças ocupacionais (LER/DORT).

> **Atenção para clínicas e escritórios:** Funcionários em teletrabalho integral (recepcionistas remotos, assistentes jurídicos) que desenvolvam LER/DORT podem ajuizar ação de acidente do trabalho. A ausência de AET e de orientações documentadas é circunstância agravante na fixação de indenização.

**Limites da responsabilidade:** O empregador não pode fiscalizar o interior da residência do empregado sem consentimento expresso (direito à intimidade — art. 5º, X CF/88). A solução prática é o uso de **checklist preenchido pelo próprio empregado**, assinado e arquivado pelo RH.

***

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-modelo-hibrido] [TIPO: norma] -->

### 1.7 Modelo Híbrido

O modelo híbrido — alternância entre dias remotos e presenciais — foi **expressamente regulamentado pela Lei 14.442/2022**. A ida ao escritório em determinados dias **não descaracteriza o regime de teletrabalho** (art. 75-B CLT, parágrafo único).

**Regras para o regime híbrido:**

- A alternância pode ser fixada no contrato (ex.: "2 dias presenciais por semana") ou ser flexível, por acordo entre as partes;
- O empregador pode convocar presencialmente sem que isso configure alteração contratual unilateral, desde que dentro dos limites pactuados;
- Para fins de controle de jornada: aplica-se o regime convencionado (por jornada ou tarefa) tanto nos dias remotos quanto nos presenciais;
- O vale-transporte é devido **apenas nos dias de comparecimento presencial** (proporcional).

**Alteração do regime:** Qualquer mudança de teletrabalho para presencial integral, ou vice-versa, exige:

1. Mútuo acordo → aditivo contratual imediato;
2. Decisão unilateral do empregador → aviso com **mínimo de 15 dias** (art. 75-C, §2º CLT).

> **Boas práticas para agências de marketing:** Definir no aditivo o número mínimo e máximo de dias presenciais por semana/mês, com calendário sujeito a revisão trimestral por acordo. Isso evita conflitos sobre convocação intempestiva e reclamações de alteração contratual lesiva.

***

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-prioridade-vulneraveis] [TIPO: norma] -->

### 1.8 Prioridade para Empregados com Deficiência e com Filhos até 4 Anos

O **art. 75-F da CLT**, inserido pela Lei 14.442/2022, estabelece **prioridade no acesso ao teletrabalho** para dois grupos:

1. **Empregados com deficiência** (conforme Lei 13.146/2015 — Lei Brasileira de Inclusão);
2. **Empregados com filho, enteado ou criança sob guarda judicial de até 4 anos de idade**, desde que a natureza do cargo seja compatível com o trabalho remoto.

**Natureza da prioridade:**

- Trata-se de preferência, não de direito absoluto; a compatibilidade da função com o teletrabalho é requisito;
- O empregador não pode negar o teletrabalho a esses empregados sem justificativa objetiva baseada na natureza da função;
- A recusa imotivada pode configurar **discriminação** (Lei 9.029/1995) e gerar indenização por danos morais.

**Implicações práticas para RH:**

- Manter registro atualizado de empregados com deficiência e daqueles com filhos de até 4 anos;
- Criar protocolo de solicitação de teletrabalho prioritário;
- Documentar a análise de compatibilidade da função com o regime remoto;
- Em caso de negativa, registrar formalmente a justificativa técnica (ex.: função exige presença física para atendimento ao cliente).

***

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-jurisprudencia] [TIPO: jurisprudencia] -->

### 1.9 Jurisprudência Recente sobre Teletrabalho (2022–2026)

**Caso 1 — Requalificação de regime "por tarefa" para "por jornada":**
O entendimento dos TRTs e do TST é que o simples rótulo contratual de "por tarefa" não afasta o controle de jornada quando o empregador, na prática, impõe horários de disponibilidade digital. A Lei 14.442/2022 consolidou esse entendimento ao alterar o art. 75-B: a exceção ao controle de jornada aplica-se **apenas** ao teletrabalhador contratado por produção ou tarefa **sem supervisão de jornada**.
⚠️ ANALOGIA — Posição doutrinária consolidada por Vólia Bomfim (*Direito do Trabalho*, 19ª ed.) e Maurício Godinho Delgado (*Curso de Direito do Trabalho*, 23ª ed.): a subordinação digital contínua reconstitui o vínculo de jornada independente de cláusula contratual.

**Caso 2 — Horas extras em teletrabalho por jornada:**
⚠️ ANALOGIA — TRTs de SP e MG têm reconhecido horas extras com base em logs de sistema, histórico de e-mails e mensagens de WhatsApp como prova do trabalho além do horário contratado, mesmo em regime de teletrabalho. A ausência de sistema de ponto digital é ônus do empregador (art. 74, §2º CLT).

**Caso 3 — Ajuda de custo como salário:**
⚠️ ANALOGIA — Cuidado: valores pagos mensalmente sob rubrica de "ajuda de custo" que excedam o custo efetivo comprovável tendem a ser requalificados como salário. Recomenda-se fixar o valor com base em pesquisa de mercado regional (ES: média de R\$ 100–180/mês para energia + internet em Vitória/ES).

> **Nota:** Até março de 2026, não foram localizados acórdãos do TST com número de processo publicado e trânsito em julgado especificamente sobre a Lei 14.442/2022 e requalificação de regime de teletrabalho. A jurisprudência acima está lastreada em decisões de TRTs e em posições doutrinárias consolidadas. Acompanhar o TST para precedentes em formação.

***

<!-- [MÓDULO: 2] [SUBTEMA: teletrabalho-estagiario] [TIPO: norma] -->

### 1.10 Estagiário em Teletrabalho — Permitido? Requisitos

**Sim, o estágio em teletrabalho (home office) é permitido.** A Lei 14.442/2022 regulamentou expressamente a adoção do teletrabalho para estagiários e jovens aprendizes, sem exigência de presencialidade como regra geral.

**Requisitos e particularidades:**


| Aspecto | Regra | Base legal |
| :-- | :-- | :-- |
| Controle de jornada | **Obrigatório** — mesmo em teletrabalho | Art. 10 Lei 11.788/2008 |
| Jornada máxima | 6h/dia para estudantes de curso superior; 4h/dia para ensino médio | Art. 10 Lei 11.788/2008 |
| Supervisão | Obrigatória pelo supervisor designado; deve ser viável em ambiente remoto | Art. 9º Lei 11.788/2008 |
| Termo de compromisso | Deve prever expressamente o regime de teletrabalho | Art. 7º Lei 11.788/2008 |
| Vale-transporte | **Dispensado** quando o estágio for integralmente remoto | — |
| Equipamentos | Empregador/concedente deve fornecer ou custear | Lei 14.442/2022 |
| Agente de integração | Deve ser comunicado sobre o regime remoto | Art. 5º Lei 11.788/2008 |

> **Atenção:** O estagiário **não pode ser contratado "por tarefa"** sem controle de jornada. A Lei dos Estágios impõe jornada máxima e controle como proteção específica ao estudante. Contratação sem controle de jornada para estagiário em teletrabalho configura irregularidade que pode gerar reconhecimento de vínculo empregatício.

***

## PARTE 2 — JORNADA DE TRABALHO

<!-- [MÓDULO: 2] [SUBTEMA: jornada-normal-horas-extras] [TIPO: norma] -->

### 2.1 Jornada Normal, Horas Extras e Cálculo

**Limites constitucionais e legais (art. 58 e 59 CLT; art. 7º, XIII CF/88):**

- Jornada normal: **8 horas diárias** e **44 horas semanais**;
- Duração mensal de referência: **220 horas** (base de cálculo salarial);
- Horas extras: **limite de 2 horas por dia** (art. 59 CLT), salvo força maior ou acordo coletivo com previsão específica;
- Adicional mínimo legal: **50%** sobre o valor da hora normal (art. 7º, XVI CF/88); CCTs podem prever adicional superior (60%, 70%, 100%);
- Horas extras em domingos e feriados: adicional de **100%** (OJ 394 SDI-1 TST).

**Cálculo da hora extra:**

```
Salário mensal ÷ 220 = valor da hora normal
Hora extra = valor da hora normal × 1,50 (adicional de 50%)
Hora extra em DSR = valor da hora normal × 2,00 (adicional de 100%)
```

**Exemplo prático (agência de marketing — analista com salário de R\$ 4.400,00):**

```
Hora normal: R$ 4.400 ÷ 220 = R$ 20,00
Hora extra (50%): R$ 20,00 × 1,50 = R$ 30,00
Hora extra em domingo (100%): R$ 20,00 × 2,00 = R$ 40,00
```

**Reflexos das horas extras:** As horas extras habituais repercutem sobre: 13º salário, férias com 1/3, FGTS, aviso prévio proporcional e — quando configurarem gorjetas ou comissões — sobre DSR.

***

<!-- [MÓDULO: 2] [SUBTEMA: jornada-banco-horas] [TIPO: norma] -->

### 2.2 Banco de Horas

O banco de horas permite a compensação de horas extras sem pagamento de adicional, mediante acordo escrito (art. 59, §2º CLT):


| Modalidade | Instrumento | Prazo de compensação | Observações |
| :-- | :-- | :-- | :-- |
| **Acordo individual** | Acordo escrito entre empregado e empregador | **6 meses** | Permitido desde a Reforma Trabalhista (Lei 13.467/2017) |
| **Acordo coletivo/CCT** | Negociação sindical | **12 meses** | Mais flexível; pode prever regras específicas |

**Regras operacionais:**

1. A compensação deve ser feita no prazo pactuado; horas não compensadas no prazo são convertidas em horas extras e pagas com adicional;
2. O banco de horas não autoriza jornadas que ultrapassem 10 horas diárias (art. 59, §3º CLT);
3. Na rescisão, as horas de banco positivo são pagas como extras; horas negativas **não podem ser descontadas** do empregado se o banco foi estabelecido por decisão unilateral do empregador.

> **Risco para imobiliárias:** Plantões de fim de semana geram horas passíveis de banco. Sem controle rigoroso, o banco "estoura" o prazo de 6 meses e as horas viram passivo de horas extras.

***

<!-- [MÓDULO: 2] [SUBTEMA: jornada-12x36] [TIPO: norma-jurisprudencia] -->

### 2.3 Jornada 12×36 — Requisitos e Validade

A jornada de **12 horas de trabalho por 36 horas de descanso** está prevista no art. 59-A da CLT (inserido pela Reforma Trabalhista — Lei 13.467/2017) e foi declarada **constitucional** pelo STF.

**Base legal e jurisprudência:**

- **STF — ADI 5994** (Rel. Min. Gilmar Mendes, julgamento plenário virtual em 27/06/2023, acórdão publicado em 04/08/2023): declarou **constitucional** a adoção da jornada 12×36 por **acordo individual escrito**, convenção coletiva ou acordo coletivo. Prevaleceu por 7 votos a 3.
- **TST — 3ª Turma — AIRR-1307-90.2019.5.17.0012** (DEJT 26/04/2024): reafirmou, com base na ADI 5994, que "deve ser considerada válida a jornada de trabalho no regime de 12×36 firmada mediante acordo individual escrito entre empregador e empregado".

**Requisitos para validade (art. 59-A CLT):**

1. **Acordo individual escrito** (não basta acordo verbal), CCT ou ACT;
2. Observância ou indenização dos **intervalos intrajornada** (1 hora mínima para jornada de 12h; se suprimido, deve ser indenizado);
3. Não há exigência de norma coletiva desde a Reforma de 2017.

**Aplicabilidade em serviços:**

- Clínicas de saúde (plantões médicos, de enfermagem, recepção 24h): uso clássico e recomendado;
- Imobiliárias com plantões de fim de semana: viável mediante acordo individual;
- Agências de marketing: **raramente aplicável** pela natureza intelectual e não-operacional da atividade; evitar uso para disfarçar horas extras.

**Consequências do regime 12×36:**

- O DSR (repouso semanal remunerado) está implicitamente compensado nas 36h de descanso;
- O trabalho em feriados que coincidam com a escala **deve ser remunerado** (OJ 394 SDI-1 TST).

***

<!-- [MÓDULO: 2] [SUBTEMA: jornada-sobreaviso-prontidao] [TIPO: norma-jurisprudencia] -->

### 2.4 Sobreaviso, Prontidão e WhatsApp (Art. 244 CLT; Súmula 428 TST)

**Sobreaviso (art. 244, §2º CLT):** Estado em que o empregado permanece em casa aguardando ser chamado para o serviço a qualquer momento; é remunerado a **1/3 do salário normal** pelo período de disponibilidade.

**Prontidão (art. 244, §3º CLT):** Empregado que fica no local de trabalho aguardando ordens; remunerado a **2/3 do salário normal**.

**Súmula 428 do TST — Sobreaviso com uso de celular:**

> *"I — O uso de instrumentos telemáticos ou informatizados fornecidos pela empresa ao empregado, por si só, não caracteriza regime de sobreaviso.*
> *II — Considera-se em sobreaviso o empregado que, à distância e submetido a controle patronal por instrumentos telemáticos ou informatizados, permanecer em regime de plantão ou equivalente, aguardando a qualquer momento o chamado para o serviço durante o período de descanso."* (TST, Súmula 428, redação de 2012)

**O WhatsApp configura sobreaviso?**


| Situação | Configura sobreaviso? | Fundamento |
| :-- | :-- | :-- |
| Empregado tem WhatsApp corporativo, mas não é obrigado a responder fora do horário | **NÃO** | Súmula 428, I TST |
| Empregado integra grupo de WhatsApp e responde esporadicamente | **NÃO** | CSJT — decisão de 02/12/2018 |
| Empregado está em **escala de plantão** com obrigação de responder via WhatsApp a qualquer momento | **SIM** | Súmula 428, II TST |
| Empregado cobrado sistematicamente por resposta imediata fora do horário com ameaça de sanção | **SIM** (+ dano moral) | TST — 3ª Turma — Telefônica Brasil ⚠️ ver abaixo |

> **TST — 3ª Turma — Telefônica Brasil S.A.** (noticiado em 23/10/2018): Condenação por cobranças de metas via WhatsApp fora do expediente. O relator concluiu que, "uma vez evidenciado que havia cobrança de metas fora do horário de trabalho, a conclusão não pode ser a de que não há reparação por dano moral". Indenização fixada em R\$ 3.500,00.
> ⚠️ ANALOGIA — Número completo do processo não verificado com fonte primária segura; citar com reserva. Utilize como referência de tendência jurisprudencial, não como precedente vinculante.

***

<!-- [MÓDULO: 2] [SUBTEMA: jornada-intervalo-intrajornada] [TIPO: norma] -->

### 2.5 Intervalo Intrajornada

Regulado pelo art. 71 da CLT:


| Duração da jornada | Intervalo mínimo obrigatório |
| :-- | :-- |
| Até 4 horas | Não há intervalo obrigatório |
| Entre 4 e 6 horas | 15 minutos |
| Acima de 6 horas | **1 hora mínima** (máximo: 2 horas, salvo ACT/CCT) |

**Supressão do intervalo:**

- A Reforma Trabalhista (2017) passou a permitir a **supressão parcial** (redução para no mínimo 30 minutos) por **norma coletiva** (ACT/CCT);
- A supressão integral do intervalo **não é permitida** nem por norma coletiva;
- A supressão parcial sem norma coletiva é inválida: o período suprimido é pago como **hora extra + 50%** (não apenas como hora normal), conforme redação atual do art. 71, §4º CLT.

> **Atenção para clínicas:** Empregados em jornada 12×36 que não usufruam do intervalo intrajornada de 1h têm direito à indenização do período, salvo previsão em CCT do setor de saúde. Verificar CCT da categoria em Vitória/ES.

***

<!-- [MÓDULO: 2] [SUBTEMA: jornada-excecoes-art62] [TIPO: norma] -->

### 2.6 Exceções ao Controle de Jornada — Art. 62 CLT

O art. 62 da CLT elenca os empregados **não sujeitos** ao regime de controle de jornada (e, consequentemente, sem direito a horas extras):

**Hipóteses do art. 62 CLT:**


| Inciso | Categoria | Requisito | Exemplos em serviços |
| :-- | :-- | :-- | :-- |
| I | Empregados em atividade externa incompatível com fixação de horário | Natureza da função | Corretor externo, técnico de campo, motorista |
| II | Gerentes com poder de mando e gestão, quando recebem **gratificação de função ≥ 40%** do salário efetivo | Gratificação + poderes reais de gestão | Gerente de filial, diretor de agência |
| III | Teletrabalhadores por produção ou tarefa | Previsão contratual expressa | Redator, designer freelancer remoto |

> **Risco crítico — Falso gerente:** O enquadramento no art. 62, II é frequentemente questionado na Justiça do Trabalho. O juiz avalia se há **poder real de mando** (contratar, demitir, representar a empresa) ou se é mero "gerente de fachada" (nomenclatura sem poderes). Precedente dominante do TST: mesmo com gratificação acima de 40%, se o empregado não tem autonomia real, é devido o controle de jornada e o pagamento de horas extras.

***

<!-- [MÓDULO: 2] [SUBTEMA: jornada-noturna] [TIPO: norma] -->

### 2.7 Trabalho Noturno

Regulado pelo art. 73 da CLT:

- **Período noturno:** Das **22h** às **5h** (trabalhadores urbanos);
- **Adicional noturno:** **20%** sobre o valor da hora diurna;
- **Hora noturna reduzida:** Cada hora trabalhada no período noturno equivale a **52 minutos e 30 segundos** (art. 73, §1º CLT), o que significa que em 8 horas-relógio o empregado cumpre 9 horas e 8 minutos de jornada computada;
- O empregado que inicia a jornada antes das 22h e prolonga após esse horário faz jus ao adicional nas horas efetivamente trabalhadas após 22h;
- A **prorrogação** da jornada noturna (além das 5h) mantém o adicional de 20% nas horas além das 5h até o encerramento da jornada.

***

<!-- [MÓDULO: 2] [SUBTEMA: jornada-desconexao-digital] [TIPO: norma-jurisprudencia] -->

### 2.8 Direito à Desconexão Digital

O **direito à desconexão** não possui regulamentação legal específica no Brasil até março de 2026, mas é reconhecido pela doutrina e jurisprudência trabalhista como **corolário do direito ao lazer** (art. 7º, IV CF/88) e da **proteção à saúde** (art. 7º, XXII CF/88).

**Tendências jurisprudenciais:**

1. **Cobrança de metas via WhatsApp fora do horário:** O TST tem reconhecido dano moral quando há cobrança sistêmica e invasiva, com ameaças de sanção — ver seção 2.4 (caso Telefônica Brasil);
2. **Mensagens "urgentes" eventuais:** Não configuram, por si sós, violação ao direito de desconexão; o critério é a **habitualidade e a coercitividade**;
3. **Grupos de WhatsApp corporativos:** A simples participação não gera obrigação de resposta fora do horário; o empregador não pode punir empregado por não responder mensagens fora do expediente.

**Boas práticas para o RH:**

- Inserir no código de conduta/política interna a vedação de cobranças por WhatsApp fora do horário de trabalho;
- Definir política de "silêncio digital" em feriados, fins de semana e férias;
- Treinamento de lideranças sobre o tema (vincula-se à prevenção de assédio — Lei 14.457/2022).

***

<!-- [MÓDULO: 2] [SUBTEMA: jornada-tabela-adicionais] [TIPO: referencia] -->

### 2.9 Tabela de Adicionais Trabalhistas

| Adicional | Percentual mínimo legal | Base de cálculo | Base legal |
| :-- | :-- | :-- | :-- |
| Hora extra (dias úteis) | **50%** | Hora normal | Art. 59 CLT; art. 7º, XVI CF/88 |
| Hora extra (DSR/feriado) | **100%** | Hora normal | OJ 394 SDI-1 TST |
| Noturno (urbano) | **20%** | Hora diurna | Art. 73 CLT |
| Insalubridade — grau mínimo | **10%** sobre salário mínimo | Salário mínimo nacional | Art. 192 CLT; NR-15 |
| Insalubridade — grau médio | **20%** sobre salário mínimo | Salário mínimo nacional | Art. 192 CLT; NR-15 |
| Insalubridade — grau máximo | **40%** sobre salário mínimo | Salário mínimo nacional | Art. 192 CLT; NR-15 |
| Periculosidade | **30%** sobre salário base | Salário contratual (sem adicional de insalubridade) | Art. 193 CLT; NR-16 |
| Sobreaviso | **1/3** da hora normal | Salário hora normal | Art. 244, §2º CLT |
| Prontidão | **2/3** da hora normal | Salário hora normal | Art. 244, §3º CLT |

> **Nota:** Insalubridade e periculosidade não se acumulam; o empregado opta pelo mais favorável (Súmula 191 TST). CCTs podem prever adicionais superiores.

***

## PARTE 3 — ASSÉDIO MORAL E SEXUAL NO TRABALHO

<!-- [MÓDULO: 2] [SUBTEMA: assedio-lei-14457-cipaa] [TIPO: norma] -->

### 3.1 Lei 14.457/2022 — CIPA passa a ser CIPAA

A **Lei 14.457/2022** (Programa Emprega + Mulheres) transformou a CIPA (Comissão Interna de Prevenção de Acidentes) em **CIPAA — Comissão Interna de Prevenção de Acidentes e de Assédio**, ampliando seu escopo para incluir prevenção e combate ao assédio sexual e outras formas de violência no trabalho.

**Empresas obrigadas a ter CIPA/CIPAA (NR-5):**

- Empresas com **20 ou mais empregados** em atividades de maior risco (conforme Quadro I da NR-5);
- Para outras atividades: conforme o número de empregados estipulado no Quadro II da NR-5;
- Nos setores de serviços (agências, imobiliárias, escritórios): obrigatoriedade a partir de diferentes faixas — verificar Quadros I e II da NR-5.

**Novas obrigações impostas pela Lei 14.457/2022 (art. 23) para empresas com CIPA:**

1. **Código de conduta:** Adoção de regras claras contra assédio sexual e outras formas de violência, com ampla divulgação a todos os empregados;
2. **Canal formal de denúncias:** Procedimentos definidos para recebimento, acompanhamento e apuração de denúncias, com **garantia de anonimato** e sigilo ao denunciante;
3. **Sanções administrativas:** Aplicação de medidas disciplinares aos responsáveis, sem prejuízo de procedimentos judiciais e penais;
4. **Inclusão do tema na CIPAA:** Os temas de prevenção devem integrar o escopo permanente das atividades da comissão;
5. **Capacitação anual obrigatória:** Ações de sensibilização para todos os níveis hierárquicos sobre assédio, violência, igualdade e diversidade.

***

<!-- [MÓDULO: 2] [SUBTEMA: assedio-canal-denuncias] [TIPO: norma] -->

### 3.2 Canal de Denúncias — Obrigações e Estrutura

O **canal de denúncias** é obrigatório para empresas com CIPA (art. 23, II, Lei 14.457/2022) e deve atender aos seguintes requisitos mínimos:

**Requisitos legais:**

- **Anonimato garantido:** O denunciante pode optar por não se identificar; a empresa não pode obrigá-lo à identificação como condição de recebimento da denúncia;
- **Sigilo absoluto:** Vedado o compartilhamento da identidade do denunciante com o investigado ou com terceiros não envolvidos na apuração;
- **Procedimento definido:** Fluxo documentado de recebimento → triagem → investigação → decisão → comunicação → arquivo;
- **Prazo de resposta:** Inexistência de prazo legal expresso; recomenda-se até 30 dias para a conclusão da apuração inicial (best practice de compliance);
- **Proteção ao denunciante:** Vedação de retaliação; qualquer medida adversa ao empregado após denúncia pode ser interpretada como retaliação — presunção de assédio moral (⚠️ ANALOGIA — tendência doutrinária).

**Canais aceitos:**

- Plataforma digital de terceiro (whistleblowing SaaS);
- E-mail exclusivo gerido por área independente (jurídico externo ou ouvidoria);
- Linha telefônica 0800;
- Caixa postal física com chave mantida por RH ou jurídico.

> **Atenção para pequenas agências e imobiliárias com CIPA:** A ausência de canal estruturado é infração à NR-5 e à Lei 14.457/2022, passível de autuação pelo Auditor Fiscal do Trabalho. Pequenas empresas podem usar formulários digitais simples (Google Forms com acesso restrito ao RH sênior), desde que garantam o anonimato.

***

<!-- [MÓDULO: 2] [SUBTEMA: assedio-tipos-moral] [TIPO: doutrina-norma] -->

### 3.3 Tipos de Assédio Moral — Conceito e Exemplos Setoriais

O assédio moral trabalhista, embora sem definição legal específica na CLT, é caracterizado pela doutrina (Godinho Delgado, *Curso de Direito do Trabalho*, 23ª ed.; Marie-France Hirigoyen) como **conduta abusiva, repetitiva, que cause dano psicológico, atente contra a dignidade ou integridade do empregado e deteriore o ambiente de trabalho**.

**Modalidades:**

**1. Assédio Vertical Descendente (superior → subordinado):**
Situação mais comum; o superior hierárquico pratica atos abusivos contra o subordinado.

*Exemplos em agências de marketing:*

- Diretor criativo que humilha publicamente designers em reuniões de review, comparando trabalhos de forma vexatória;
- Gestor que envia mensagens após meia-noite exigindo retrabalho imediato sob ameaça de demissão;
- Chefe que atribui metas impossíveis sistematicamente para justificar demissão por justa causa.

*Exemplos em imobiliárias:*

- Supervisor que expõe o corretor com baixo desempenho em ranking público com comentários depreciativos;
- Gerente que priva o corretor de leads bons como forma de pressão.

**2. Assédio Vertical Ascendente (subordinado → superior):**
Subordinados praticam atos abusivos contra o superior.

*Exemplos:*

- Equipe que sabotar sistematicamente as iniciativas do novo gestor;
- Subordinados que fazem campanha difamatória interna contra o supervisor por redes sociais internas.

**3. Assédio Horizontal (entre pares):**
Cometido entre colegas do mesmo nível hierárquico.

*Exemplos em clínicas:*

- Médicos sênior que ignoram sistematicamente o médico recém-admitido em reuniões;
- Equipe de enfermagem que exclui empregada de grupos de WhatsApp da equipe.

**4. Assédio Organizacional (institucional):**
A própria empresa, por sua estrutura e política de gestão, cria um ambiente de terror psicológico.

*Exemplos em escritórios jurídicos e agências:*

- Sistema de metas impossíveis, ranking público dos "piores" colaboradores, política de "last place out" periódica;
- Cultura de disponibilidade 24/7 normalizada pela gestão sênior;
- Cobrança sistemática via grupos de WhatsApp fora do expediente, com registro de quem não respondeu.

***

<!-- [MÓDULO: 2] [SUBTEMA: assedio-sexual] [TIPO: norma-penal] -->

### 3.4 Assédio Sexual — Tipificação Penal e Responsabilidade do Empregador

O assédio sexual no ambiente de trabalho é **crime** tipificado no art. 216-A do Código Penal, incluído pela Lei 10.224/2001 e com pena majorada pela Lei 13.718/2018:

```
Art. 216-A CP: Constranger alguém com o intuito de obter vantagem ou 
favorecimento sexual, prevalecendo-se o agente da sua condição de 
superior hierárquico ou ascendência inerentes ao exercício de emprego, 
cargo ou função.
Pena: detenção de 1 a 2 anos.
Parágrafo único: A pena é aumentada em até 1/3 se a vítima é menor de 18 anos.
§ 2º: A pena é aumentada em 1/3 a 2/3 nas hipóteses do § 1º do art. 226.
```

**Modalidades de assédio sexual reconhecidas:**

- *Quid pro quo* (chantagem sexual): condicionamento de benefício ou manutenção do emprego à concessão sexual;
- *Ambiental* (por intimidação): criação de ambiente de trabalho hostil, intimidador, com piadas, imagens ou condutas de conotação sexual.

**Responsabilidade do empregador:**

- **Civil:** Responsabilidade subjetiva com culpa in vigilando e culpa in eligendo; o empregador responde quando tinha ciência ou deveria ter ciência da conduta e não adotou medidas preventivas ou repressivas (art. 932, III CC; art. 186 CC);
- **Trabalhista:** Condenação em danos morais (art. 223-G CLT; STF — ADI 6050);
- **Solidariedade:** Em casos de terceirização, o tomador de serviços pode ser responsabilizado solidariamente se o assédio ocorreu nas suas dependências.

> **Obrigação positiva do empregador:** Após a Lei 14.457/2022, a ausência de canal de denúncias, capacitação e código de conduta pode ser utilizada como elemento de culpa in omitendo para responsabilizar a empresa mesmo quando o agressor é um colega (horizontal) e não um superior.

***

<!-- [MÓDULO: 2] [SUBTEMA: assedio-ambiente-digital] [TIPO: norma-jurisprudencia] -->

### 3.5 Assédio no Ambiente Digital

O assédio moral e sexual não requer presencialidade. Mensagens digitais, reuniões por videoconferência e grupos corporativos de WhatsApp são ambientes propícios e reconhecidos pela jurisprudência como locais de prática de assédio.

**Formas de assédio digital mais comuns em empresas de serviços:**


| Conduta | Tipo | Consequência jurídica |
| :-- | :-- | :-- |
| Mensagens de cobranças abusivas via WhatsApp fora do horário | Assédio moral organizacional | Dano moral + possível reconhecimento de sobreaviso |
| Exposição de empregado em grupo corporativo por baixo desempenho | Assédio moral vertical descendente | Dano moral — TST Almaviva (ver 3.10) |
| Envio de imagens, memes ou vídeos de conteúdo sexual para colegas | Assédio sexual ambiental | Crime (art. 216-A CP) + dano moral |
| Exclusão de empregado de grupos de trabalho como punição | Assédio moral horizontal/vertical | Dano moral |
| Humilhação em reunião de videoconferência com múltiplos participantes | Assédio moral vertical | Dano moral agravado (público) |
| Envio de áudios agressivos via WhatsApp | Assédio moral | Dano moral; áudios são prova lícita (TRT3 — ver 3.10) |

**Provas digitais:**

- Prints de tela, histórico de WhatsApp/Telegram, e-mails e gravações de videochamadas são admitidos como **prova lícita** na Justiça do Trabalho, desde que obtidos pelo próprio participante da conversa (não por terceiro — art. 5º, XII CF/88);
- A parte que participou da conversa pode juntá-la ao processo sem configurar violação ao sigilo das comunicações.

***

<!-- [MÓDULO: 2] [SUBTEMA: assedio-responsabilidade-empregador] [TIPO: norma-doutrina] -->

### 3.6 Responsabilidade Civil do Empregador — Subjetiva ou Objetiva?

A questão da natureza da responsabilidade civil do empregador por assédio é tema de debate na doutrina e jurisprudência:

**Posição majoritária do TST — Responsabilidade subjetiva com inversão do ônus:**

- O empregador responde quando age com **culpa in vigilando** (não fiscalizou) ou **culpa in eligendo** (escolheu mal o preposto);
- Invertida a perspectiva prática: cabe ao **empregador provar** que adotou todas as medidas de prevenção e repressão exigíveis, não à vítima provar a omissão da empresa;
- A ausência de canal de denúncias, de capacitação (Lei 14.457/2022) e de código de conduta é elemento que facilita a responsabilização.

**Casos de responsabilidade objetiva:**

- Quando o assédio é praticado pelo próprio empregador/sócio (pessoa física);
- Atividades de risco especial que envolvam assédio estrutural (ex.: telemarketing com metas abusivas sistêmicas).

**Doutrina:** Vólia Bomfim (*Direito do Trabalho*, 19ª ed.): "A responsabilidade do empregador por atos de assédio praticados por seus prepostos é de natureza subjetiva, mas a culpa pode ser presumida quando a empresa falha no dever de vigilância e de implementação de políticas preventivas."

***

<!-- [MÓDULO: 2] [SUBTEMA: assedio-danos-morais-223g] [TIPO: norma-jurisprudencia] -->

### 3.7 Danos Morais Trabalhistas — Art. 223-G CLT e STF (ADI 6050)

O art. 223-G da CLT, introduzido pela Reforma Trabalhista (2017), fixou parâmetros e tetos para indenização por dano extrapatrimonial:

**Parâmetros de fixação (art. 223-G, caput CLT):**
Natureza do bem jurídico tutelado; intensidade do sofrimento ou humilhação; possibilidade de superação física ou psicológica; reflexos pessoais e sociais da ação ou omissão; extensão e duração dos efeitos da ofensa; situação socioeconômica das partes; grau de dolo ou culpa; ocorrência de retratação espontânea; esforço para minimização da ofensa; colaboração da vítima; e grau de publicidade da ofensa.

**Classificação e tetos originais (art. 223-G, §1º CLT):**


| Gravidade | Teto original (por ofensa) |
| :-- | :-- |
| Ofensa de natureza **leve** | Até 3 últimos salários contratuais |
| Ofensa de natureza **média** | Até 5 últimos salários contratuais |
| Ofensa de natureza **grave** | Até 20 últimos salários contratuais |
| Ofensa de natureza **gravíssima** | Até 50 últimos salários contratuais |

**Decisão do STF — ADI 6050 (e ADIs 5870, 6069, 6082) — Acórdão publicado em 18/08/2023:**

O STF, por maioria, decidiu que:

> *"Os critérios de quantificação de reparação por dano extrapatrimonial previstos no art. 223-G, caput e §1º, da CLT deverão ser observados pelo julgador como critérios orientativos de fundamentação da decisão judicial. É constitucional, porém, o arbitramento judicial do dano em valores superiores aos limites máximos dispostos nos incisos I a IV do §1º do art. 223-G, quando consideradas as circunstâncias do caso concreto e
<span style="display:none">[^1][^10][^11][^12][^13][^14][^15][^16][^17][^18][^19][^2][^20][^21][^22][^23][^24][^25][^26][^27][^28][^29][^3][^30][^31][^32][^33][^34][^35][^36][^37][^38][^39][^4][^40][^41][^42][^5][^6][^7][^8][^9]</span>

<div align="center">⁂</div>

[^1]: https://www.hmgcadvogados.com.br/teletrabalho-e-controle-de-jornada-analise-da-lei-no-14-442-2022-e-gestao-de-passivos/

[^2]: https://www.planalto.gov.br/ccivil_03/_ato2019-2022/2022/lei/l14442.htm

[^3]: https://paixaoeditores.com/norma-aplicavel-no-teletrabalho-lei-14-442-2022/

[^4]: https://basis.trt2.jus.br/bitstream/handle/123456789/15090/martins_adalberto_consideracoes_teletrabalho_reforma.pdf?sequence=4\&isAllowed=y

[^5]: https://metalurgicoscarlosbarbosa.com.br/entenda-as-mudancas-da-lei-14-442-22-e-o-que-isso-impacta-o-teletrabalho/

[^6]: https://www.aliant.com.br/conteudos/nova-lei-14-457-exige-a-implantacao-do-canal-de-denuncias-em-empresas-com-cipa/

[^7]: https://www.migalhas.com.br/quentes/388828/stf-indenizacao-por-danos-morais-pode-superar-teto-da-clt

[^8]: https://juslaboris.tst.jus.br/handle/20.500.12178/213975

[^9]: https://juslaboris.tst.jus.br/bitstream/handle/20.500.12178/213384/2022_martins_adalberto_consideracoes_teletrabalho.pdf?sequence=1

[^10]: https://canaldedenuncias.com.br/nova-lei-14-457-exige-a-implantacao-do-canal-de-denuncias-em-empresas-com-cipa/

[^11]: https://revistaft.com.br/limitador-do-dano-moral-em-seu-artigo-223-g-da-clt-analise-e-a-perspectiva-de-majoracao-judicial/

[^12]: https://basis.trt2.jus.br/bitstream/handle/123456789/17228/ribeiro_viviane_assedio_moral_novo.pdf?sequence=1\&isAllowed=y

[^13]: https://revistas.unaerp.br/cbpcc/article/download/2847/2026/9235

[^14]: https://blog.bcompliance.com.br/2025/08/15/canal-de-denuncias-lei-14457-2022/

[^15]: https://boletimjuridico.ufms.br/stf-indenizacao-por-danos-morais-pode-ultrapassar-tabelamento-da-clt/

[^16]: https://www.tst.jus.br/-/nova-redacao-da-sumula-428-reconhece-sobreaviso-em-escala-com-celular

[^17]: https://www.tst.jus.br/-/analista-que-ficava-com-celular-e-notebook-de-banco-durante-a-folga-receberá-por-horas-de-sobreaviso

[^18]: https://www.csjt.jus.br/web/csjt/-/resposta-a-mensagens-de-whatsapp-apos-jornada-nao-caracteriza-sobreaviso

[^19]: https://www.trt4.jus.br/portais/escola/modulos/noticias/426468

[^20]: https://wagner.adv.br/strongtst-nova-redaccedilatildeo-da-suacutemula-428-reconhece-sobreaviso-em-escala-com-celularstrong/

[^21]: https://convergenciadigital.com.br/carreira/justia-do-trabalho-admite-mensagens-pelo-whatsapp-como-prova-de-assdio/

[^22]: https://www.ciadeestagios.com.br/conteudos-para-rh/lei-do-home-office-conheca-as-regras/

[^23]: https://portal.trt12.jus.br/noticias/tst-reviu-jurisprudencia-sobre-regime-de-sobreaviso-com-uso-de-celular

[^24]: https://www.trabalholegal.com.br/single-post/estagiarios-e-aprendizes-a-possibilidade-de-teletrabalho-e-o-cuidado-na-hora-da-contratação

[^25]: https://conexaotrabalho.portaldaindustria.com.br/noticias/detalhe/trabalhista/-geral/tst-nao-configura-sobreaviso-o-simples-uso-de-celular-pelo-empregado/

[^26]: https://portal.trt3.jus.br/internet/conheca-o-trt/comunicacao/noticias-juridicas/justica-do-trabalho-considera-registro-de-conversas-em-whatsapp-meio-de-prova-licito-para-apuracao-de-falso-testemunho

[^27]: https://www.nube.com.br/blog/2024/09/23/estagio-em-home-office-o-que-diz-a-lei

[^28]: https://www.lexml.gov.br/urn/urn:lex:br:tribunal.superior.trabalho:sumula:2012;428

[^29]: https://www.tst.jus.br/-/cobranca-de-metas-por-whatsapp-fora-do-expediente-extrapola-poder-do-empregador

[^30]: https://portal.trt3.jus.br/internet/jurisprudencia/repercussao-geral-e-controle-concentrado-adi-adc-e-adpf-stf/downloads/adi-6050-acordao.pdf

[^31]: https://www.anamatra.org.br/imprensa/anamatra-na-midia/34027-stf-dois-votos-para-que-teto-em-indenizacoes-trabalhistas-seja-exemplificativo

[^32]: https://site.conpedi.org.br/publicacoes/06n3kw94/12ck6wm3/g24F1BlDG7d00oY3.pdf

[^33]: https://www.observatoriotrabalhistadostf.com/post/adi-6050-reparação-integral-dignidade-humana-e-o-dano-extrapatrimonial-nas-relações-de-trabalho

[^34]: https://conexaotrabalho.portaldaindustria.com.br/noticias/detalhe/trabalhista/-geral/3-turmatst-reafirma-possibilidade-da-adocao-da-jornada-12x36-por-acordo-individual/

[^35]: https://buscadordizerodireito.com.br/jurisprudencia/11849/o-tabelamento-das-indenizacoes-trabalhistas-previsto-na-clt-devera-ser-observado-pelo-julgador-como-criterio-orientador-isso-nao-impede-contudo-a-fixacao-de-condenacao-em-quantia-superior-desde-que-devidamente-motivada

[^36]: https://www.migalhas.com.br/quentes/389428/stf-valida-adocao-de-jornada-12-36-por-acordo-individual

[^37]: https://www.tst.jus.br/-/supervisora-será-indenizada-por-assédio-de-gestores-em-grupo-corporativo-de-whatsapp 

[^38]: https://cj.estrategia.com/portal/constitucionalidade-jornada-12x36/

[^39]: https://portal.trt3.jus.br/internet/conheca-o-trt/comunicacao/noticias-juridicas/nj-trabalhador-nao-consegue-indenizacao-por-publicacao-de-ranking-de-produtividade-e-acionamento-por-whatsapp

[^40]: https://ww2.trt2.jus.br/noticias/noticias/noticia/supremo-tribunal-federal-publica-acordao-que-confirma-validade-da-jornada-12x36-por-acordo-individual-escrito

[^41]: https://convergenciadigital.com.br/carreira/tst-condena-telefnica-por-cobrar-metas-fora-do-expediente-via-whatsapp/

[^42]: https://www.guiatrabalhista.com.br/tematicas/Jornada-12-x-36-reforma-trabalhista.htm


</content>
