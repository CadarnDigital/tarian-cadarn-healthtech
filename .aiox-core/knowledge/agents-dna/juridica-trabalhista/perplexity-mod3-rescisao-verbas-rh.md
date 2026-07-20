---
source_file: perplexity-mod3-rescisao-verbas-rh.md
converted_at: 2026-03-25
original_extension: md
processor: Echo (aiox-m2m-etl)
extraction_quality: full
domain: Rescisão, Verbas Trabalhistas, eSocial e Compliance RH
source_type: perplexity-deep-research
source_tool: Perplexity Pro (Deep Research)
agent_target: juridica-trabalhista
squad: squad-cadarn-juridica
module: 3
module_title: Rescisão, Verbas, Obrigações Acessórias e Compliance RH
---

<content>


# Você é um pesquisador especialista em Direito do Trabalho brasileiro, com foco em rescisão contratual, verbas trabalhistas e gestão prática de RH para

empresas de serviços. Sua tarefa é produzir um módulo exaustivo e atualizado (base: março de 2026) sobre rescisão, verbas, obrigações acessórias e
compliance trabalhista operacional.

Contexto de uso: Este documento será processado por um pipeline automatizado (M2M + RAG). O chunking é feito por headers Markdown (\#\# e \#\#\#). Os metadados
em HTML comment são parseados por regex antes do chunking e funcionam como tags de classificação semântica — mantenha o formato exato. Output
obrigatório: Markdown puro, sem exceções. O documento será carregado como base de conhecimento de um agente Claude Code (CLI) utilizado por equipes de RH
de empresas de serviços premium (agências de marketing, imobiliárias, clínicas de estética, escritórios de advocacia) em capitais brasileiras (foco
Vitória/ES).

  <!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 3] [TEMA: rescisao-verbas-rh-compliance] -->
Cubra obrigatoriamente:

1. **Modalidades de Rescisão — Completo**
    - Sem justa causa (iniciativa do empregador)
    - Por justa causa (art. 482 CLT) — as 13 hipóteses com exemplos práticos para agências/imobiliárias
    - Pedido de demissão (iniciativa do empregado)
    - Acordo mútuo (art. 484-A CLT, Reforma Trabalhista) — como funciona, verbas, FGTS 20%
    - Rescisão indireta (art. 483 CLT) — "justa causa do empregador"
    - Culpa recíproca (art. 484 CLT)
    - Término de contrato por prazo determinado
    - Rescisão durante experiência (art. 479-480 CLT)
    - Morte do empregado / empregador pessoa física
    - Para cada modalidade: quais verbas são devidas e quais não são
2. **Tabela completa de verbas rescisórias por modalidade**
    - Colunas: Verba | Sem justa causa | Justa causa | Pedido demissão | Acordo mútuo | Rescisão indireta
    - Verbas: saldo de salário, aviso prévio (trabalhado/indenizado), 13º proporcional, férias vencidas + 1/3, férias proporcionais + 1/3, FGTS (saldo +
multa), seguro-desemprego
    - Fórmulas de cálculo para cada verba
3. **FGTS — Detalhamento completo**
    - Depósito mensal 8% (2% para menor aprendiz)
    - Multa rescisória: 40% (sem justa causa / rescisão indireta) vs 20% (acordo mútuo) vs 0% (justa causa / pedido demissão)
    - Saque: hipóteses legais (demissão sem justa causa, acordo mútuo, aposentadoria, doença grave, FGTS aniversário)
    - FGTS Digital — novo sistema de recolhimento via Pix
    - Prazo de recolhimento: até dia 20 do mês seguinte
4. **Aviso Prévio**
    - Aviso prévio trabalhado vs indenizado
    - Proporcional (Lei 12.506/2011): 30 dias + 3 dias por ano de serviço, até 90 dias
    - Tabela de proporcionalidade (1 ano = 33 dias, 2 anos = 36 dias, ... 20+ anos = 90 dias)
    - Redução de jornada: 2h/dia ou 7 dias corridos (escolha do empregado)
    - Aviso prévio no acordo mútuo: metade (15 dias mínimo)
5. **Prazos e Procedimentos de Rescisão**
    - Prazo único de 10 dias para pagamento (art. 477, §6º CLT — Reforma Trabalhista)
    - Multa por atraso: salário do empregado (art. 477, §8º CLT)
    - Homologação: NÃO é mais obrigatória no sindicato (Reforma Trabalhista aboliu, exceto se previsto em norma coletiva)
    - Documentos obrigatórios: TRCT, Termo de Quitação, chave de conectividade FGTS, guias de seguro-desemprego
    - CTPS digital — anotação automática via eSocial
6. **Estágio — Rescisão e Particularidades**
    - Estágio NÃO gera vínculo (se regular) — sem verbas rescisórias CLT
    - Recesso remunerado proporcional (30 dias/ano, proporcional se < 12 meses)
    - Quando estágio irregular vira CLT: desvio de função, ausência de supervisor, excesso de carga
    - Seguro obrigatório contra acidentes pessoais
7. **eSocial e Obrigações Acessórias — Guia Prático**
    - eSocial: eventos de admissão (S-2200), afastamento (S-2230), desligamento (S-2299)
    - Prazos por evento: admissão até dia anterior ao início, desligamento até 10 dias
    - DIRF (extinta em 2024 — substituída por EFD-Reinf + DCTF-Web)
    - RAIS (substituída pelo eSocial desde 2019)
    - CAGED (substituído pelo eSocial desde 2020)
    - DCTFWeb: substituiu a GFIP, prazo até dia 15 do mês seguinte
    - Multas por descumprimento de obrigações acessórias
8. **Compliance Trabalhista — Programa Prático para PMEs**
    - Código de conduta — temas obrigatórios: assédio, discriminação, uso de dados, redes sociais
    - Política de home office / teletrabalho
    - Política de uso de equipamentos e BYOD
    - Canal de denúncias (obrigatório Lei 14.457/2022 para empresas com CIPA)
    - Treinamentos obrigatórios: CIPA, NRs aplicáveis, assédio (anual)
    - Exames médicos: admissional, periódico, demissional, mudança de função, retorno ao trabalho
    - NR-17 (ergonomia) para escritórios e home office
    - Férias: fracionamento em até 3 períodos (Reforma), nenhum inferior a 5 dias corridos, um deles com mínimo 14 dias
    - Calendário mensal de obrigações do RH (tabela mês a mês)
9. **Checklist operacional — Admissão**
    - Documentos obrigatórios do empregado
    - Registro no eSocial (S-2200) até véspera do início
    - Exame admissional (ASO)
    - Contrato de trabalho / aditivo de teletrabalho
    - Integração: código de conduta, políticas internas, CIPA
10. **Checklist operacional — Demissão**
- Carta de comunicação (empregador) ou pedido formal (empregado)
- Cálculo de verbas rescisórias
- Pagamento em até 10 dias
- Evento S-2299 no eSocial
- Entrega de documentos: TRCT, guias seguro-desemprego, chave FGTS
- Exame demissional
- Baixa na CTPS digital (automática via eSocial)

Regras de integridade:

- Cite CLT artigo, lei e número para TODA regra
- Se uma regra mudou com a Reforma Trabalhista (2017), documente antes vs depois
- Se não encontrar fonte verificável: "não encontrado com fonte confiável"
- Doutrina: pode citar Godinho Delgado, Sérgio Pinto Martins, Vólia Bomfim se obra existir
- Use HTML comments: <!-- [MÓDULO: 3] [SUBTEMA: nome] [TIPO: tipo] -->
- Chunks entre 300-800 palavras por seção \#\#/\#\#\#
- Formato: Markdown puro, headers \#\# e \#\#\#, tabelas extensivas

Aqui está o módulo completo, construído com base nas informações verificadas de fontes governamentais e especializadas atualizadas até março de 2026.

***

<!-- [VERSÃO: 1.0] [DATA_GERAÇÃO: 2026-03] [VALIDADE_ESTIMADA: 2026-09] [MÓDULO: 3] [TEMA: rescisao-verbas-rh-compliance] -->

# Módulo 3 — Rescisão Contratual, Verbas Trabalhistas e Compliance de RH

<!-- [MÓDULO: 3] [SUBTEMA: indice] [TIPO: navegacao] -->
> **Base legal consolidada:** CLT (Decreto-Lei 5.452/1943), Lei 13.467/2017 (Reforma Trabalhista), Lei 12.506/2011 (Aviso Prévio Proporcional), Lei 14.438/2022 (FGTS Digital), Lei 14.457/2022 (CIPA/Canal de Denúncias), eSocial MOS S-1.3 (consolidado NO S-1.3/05-2025).
> **Contexto de aplicação:** Empresas de serviços premium (agências de marketing, imobiliárias, clínicas de estética, escritórios de advocacia) em capitais brasileiras, com foco em Vitória/ES.
> **Aviso:** Este documento não substitui assessoria jurídica especializada. Consulte advogado trabalhista para casos concretos.

***

## 1. Modalidades de Rescisão Contratual

<!-- [MÓDULO: 3] [SUBTEMA: modalidades-rescisao] [TIPO: conceitual-legal] -->

### 1.1 Rescisão Sem Justa Causa (Iniciativa do Empregador)

<!-- [MÓDULO: 3] [SUBTEMA: sem-justa-causa] [TIPO: legal-operacional] -->
A rescisão sem justa causa é o término do contrato por iniciativa unilateral do empregador, sem que o empregado tenha praticado falta grave. Regulada pelo art. 477 da CLT, é a modalidade mais onerosa para o empregador.

**Verbas devidas:**

- Saldo de salário dos dias trabalhados no mês
- Aviso prévio (trabalhado ou indenizado), com proporcionalidade pela Lei 12.506/2011
- 13º salário proporcional (art. 7º, VIII, CF/88; art. 1º, Lei 4.090/1962)
- Férias vencidas + 1/3 constitucional (art. 7º, XVII, CF/88)
- Férias proporcionais + 1/3 (art. 146, parágrafo único, CLT)
- FGTS: saldo depositado + multa de **40%** sobre o saldo total da conta vinculada (art. 18, §1º, Lei 8.036/1990)
- Seguro-desemprego (Lei 7.998/1990 e Lei 13.134/2015)

**O que NÃO é devido:**

- Multa por não concessão de aviso prévio pelo empregado (essa multa é do empregado, não do empregador)

**Prazo de pagamento:** Até **10 dias corridos** contados do término do contrato (art. 477, §6º, CLT — redação dada pela Lei 13.467/2017). Antes da Reforma, o prazo era de 1 dia útil (aviso trabalhado) ou 10 dias (aviso indenizado).

***

### 1.2 Rescisão por Justa Causa (Iniciativa do Empregador)

<!-- [MÓDULO: 3] [SUBTEMA: justa-causa-empregador] [TIPO: legal-operacional] -->
A justa causa exige fato grave, tipificado em lei, atual e proporcional à punição. Prevista no art. 482 da CLT, que elenca **13 hipóteses** (alíneas "a" a "m"). Exige imediatidade, singularidade punitiva e proporcionalidade.

**As 13 hipóteses do art. 482 CLT com exemplos para serviços premium:**


| Alínea | Hipótese | Exemplo Prático (Agências/Imobiliárias/Clínicas) |
| :-- | :-- | :-- |
| a | Ato de improbidade | Funcionário de imobiliária adultera contrato de locação para receber comissão indevida |
| b | Incontinência de conduta ou mau procedimento | Atendente de clínica de estética assedia pacientes verbalmente de forma reiterada |
| c | Negociação habitual por conta própria ou alheia sem permissão | Corretor de imóveis capta clientes da imobiliária para negócio próprio paralelo |
| d | Condenação criminal transitada em julgado sem suspensão da pena | Colaborador de agência de marketing condenado por crime de fraude |
| e | Desídia no desempenho das funções | Designer acumula 5+ entregas atrasadas sem justificativa, após 2 advertências formais |
| f | Embriaguez habitual ou em serviço | Recepcionista de clínica chega alcoolizada ao trabalho em múltiplas ocasiões documentadas |
| g | Violação de segredo da empresa | Social media vaza estratégias de campanha para concorrente |
| h | Ato de indisciplina ou insubordinação | Atendente se recusa reiteradamente a usar uniforme obrigatório previsto no regimento interno |
| i | Abandono de emprego | Colaborador ausente por mais de 30 dias sem justificativa (TST: presunção de abandono após 30 faltas) |
| j | Ato lesivo à honra e boa fama praticado no serviço | Advogado ofende colega perante clientes do escritório |
| k | Ato lesivo à honra fora do serviço contra o empregador ou seus superiores | Publicação em redes sociais depreciando o escritório de advocacia empregador |
| l | Prática constante de jogos de azar | Não usual em serviços premium, mas aplicável em princípio |
| m | Perda da habilitação profissional por conduta dolosa | Advogado suspenso pela OAB por conduta dolosa; corretor com CRECI cassado por fraude |

> **Atenção para agências digitais:** A alínea "g" (violação de segredo) é especialmente relevante — é essencial incluir cláusula de confidencialidade no contrato e no código de conduta.

**Verbas devidas na justa causa:**

- Saldo de salário ✅
- Férias vencidas + 1/3 ✅ (art. 146, CLT — direito adquirido, imune à justa causa)
- **Não são devidos:** aviso prévio, 13º proporcional, férias proporcionais, multa de 40% FGTS, saque do FGTS, seguro-desemprego

**Procedimento recomendado (controle de prova):**

1. Sindicância interna documentada
2. Advertência prévia (salvo falta gravíssima)
3. Carta de demissão com fundamentação expressa no art. 482 e alínea aplicável
4. Testemunhas e documentação da falta

***

### 1.3 Pedido de Demissão (Iniciativa do Empregado)

<!-- [MÓDULO: 3] [SUBTEMA: pedido-demissao] [TIPO: legal-operacional] -->
O pedido de demissão é o ato unilateral do empregado que deseja encerrar o contrato. Deve ser formalizado por escrito. O empregado deve cumprir ou indenizar o aviso prévio (art. 487, §2º, CLT).

**Verbas devidas:**

- Saldo de salário ✅
- 13º salário proporcional ✅
- Férias vencidas + 1/3 ✅
- Férias proporcionais + 1/3 ✅
- Aviso prévio trabalhado (ou desconto se não cumprido) ✅/❌

**Não são devidos:**

- Multa de 40% sobre o FGTS ❌
- Saque do FGTS (salvo hipóteses específicas) ❌
- Seguro-desemprego ❌

> **Antes da Reforma (até 11/11/2017):** empregado com mais de 1 ano precisava de assistência sindical na homologação. **Após a Reforma:** homologação sindical **não é mais obrigatória** (art. 477, §1º, CLT).

***

### 1.4 Acordo Mútuo — Art. 484-A CLT (Reforma Trabalhista)

<!-- [MÓDULO: 3] [SUBTEMA: acordo-mutuo-484a] [TIPO: legal-operacional] -->
Introduzido pela Lei 13.467/2017, o acordo mútuo permite que empregado e empregador encerrem o contrato de forma consensual, com verbas intermediárias — nem tão oneroso quanto a demissão sem justa causa, nem tão restritivo quanto o pedido de demissão.

**Como funciona:**

- Deve ser formalizado por escrito, com assinatura de ambas as partes (recomenda-se duas testemunhas)
- Não pode haver vício de consentimento (coação, fraude ou erro) — risco de nulidade e reconhecimento de dispensa sem justa causa pela Justiça do Trabalho
- Não há forma especial exigida, mas o TRCT deve indicar expressamente a modalidade "acordo mútuo — art. 484-A"

**Verbas devidas no acordo mútuo:**


| Verba | Acordo Mútuo |
| :-- | :-- |
| Saldo de salário | 100% |
| Aviso prévio indenizado | 50% (metade) |
| 13º proporcional | 100% |
| Férias vencidas + 1/3 | 100% |
| Férias proporcionais + 1/3 | 100% |
| Multa FGTS | 20% (metade dos 40%) |
| Saque FGTS | Até 80% do saldo |
| Seguro-desemprego | ❌ NÃO tem direito |

> **Fonte verificada:** Art. 484-A, §§1º e 2º, CLT.[^1][^2]

**Aviso prévio no acordo mútuo:** O art. 484-A, §1º, prevê que o aviso prévio, se indenizado, corresponde à metade. Se trabalhado, não há previsão expressa de redução — doutrina majoritária entende que pode ser negociado entre as partes.

***

### 1.5 Rescisão Indireta — Art. 483 CLT

<!-- [MÓDULO: 3] [SUBTEMA: rescisao-indireta-483] [TIPO: legal-operacional] -->
A rescisão indireta é a "justa causa do empregador" — o empregado rescinde o contrato por culpa grave do empregador, com direito a todas as verbas da dispensa sem justa causa.

**Hipóteses do art. 483 CLT:**


| Alínea | Hipótese | Exemplo Prático |
| :-- | :-- | :-- |
| a | Serviços superiores às forças / vedados por lei | Agência exige horas extras habituais sem pagamento |
| b | Tratado com rigor excessivo | Diretor humilha publicamente o colaborador em reuniões |
| c | Perigo manifesto de mal considerável | Clínica não fornece EPI para procedimentos com risco biológico |
| d | Descumprimento das obrigações contratuais | Empregador não paga salário por 3+ meses consecutivos |
| e | Ato lesivo à honra e boa fama | Empregador divulga falsos dados sobre o empregado para clientes |
| f | Ofensas físicas | Sócio agride fisicamente colaborador |
| g | Redução do trabalho em peça ou tarefa | Não usual em serviços premium |

**Verbas devidas:** Idênticas à rescisão sem justa causa: saldo + aviso prévio integral + 13º + férias vencidas/proporcionais + multa 40% FGTS + seguro-desemprego.

**Procedimento:** O empregado pode pleitear a rescisão indireta diretamente na Justiça do Trabalho ou, em casos urgentes (ex: não pagamento de salário), pedir rescisão sem necessidade de aguardar decisão judicial — posição majoritária do TST (OJ 13, SDI-1).

***

### 1.6 Culpa Recíproca — Art. 484 CLT

<!-- [MÓDULO: 3] [SUBTEMA: culpa-reciproca-484] [TIPO: legal-operacional] -->
Ocorre quando tanto o empregado quanto o empregador praticam atos que justificariam, isoladamente, a rescisão. Prevista no art. 484 CLT, reconhecida judicialmente.

**Verbas devidas (50% das verbas da dispensa sem justa causa):**

- Aviso prévio: 50%
- Multa FGTS: 20% (metade dos 40%)
- 13º proporcional: 50%
- Férias proporcionais + 1/3: 50%
- Férias vencidas + 1/3: 100% (direito adquirido)
- Seguro-desemprego: não reconhecido administrativamente; possível via ação judicial

***

### 1.7 Término de Contrato por Prazo Determinado

<!-- [MÓDULO: 3] [SUBTEMA: contrato-prazo-determinado] [TIPO: legal-operacional] -->
Contratos a prazo determinado (art. 443 CLT) têm prazo máximo de 2 anos, com possibilidade de uma prorrogação. Incluem: contrato por obra certa (Lei 2.959/1956), contrato de experiência (art. 443, §2º, "c", CLT) e contrato de safra.

**Verbas ao término natural do prazo:**

- Saldo de salário ✅
- 13º proporcional ✅
- Férias proporcionais + 1/3 ✅
- Férias vencidas + 1/3 (se aplicável) ✅
- FGTS depositado (sem multa) ✅
- Aviso prévio: **não devido** ao término natural ❌
- Multa de 40% FGTS: **não devida** ❌
- Seguro-desemprego: **não devido** ❌

**Se o empregador rescindir antes do prazo:** Devido indenização de metade dos salários a que teria direito até o fim do contrato (art. 479 CLT) + verbas acima.

***

### 1.8 Rescisão Durante o Contrato de Experiência

<!-- [MÓDULO: 3] [SUBTEMA: rescisao-experiencia-479-480] [TIPO: legal-operacional] -->
O contrato de experiência é espécie de contrato a prazo determinado (art. 443, §2º, "c", CLT), com prazo máximo de **90 dias** (podendo ser prorrogado uma vez, desde que não ultrapasse 90 dias no total).

**Rescisão antecipada pelo empregador (art. 479 CLT):**

- Indenização equivalente à metade dos salários a que o empregado teria direito até o fim do prazo
- Exemplo: empregado com salário de R\$ 3.000, dispensado 30 dias antes do fim do contrato de experiência → indenização = R\$ 1.500 (metade de R\$ 3.000)
- Demais verbas da rescisão sem justa causa são devidas

**Rescisão antecipada pelo empregado (art. 480 CLT):**

- Empregado fica sujeito a pagar indenização ao empregador pelos prejuízos que causar (difícil de executar na prática)
- Na prática, raramente aplicada

**Término natural do contrato de experiência:**

- Verbas: saldo + 13º proporcional + férias proporcionais + 1/3 + FGTS depositado
- **Sem** aviso prévio, sem multa de 40%, sem seguro-desemprego

***

### 1.9 Morte do Empregado e do Empregador Pessoa Física

<!-- [MÓDULO: 3] [SUBTEMA: morte-empregado-empregador] [TIPO: legal-operacional] -->
**Morte do empregado (art. 477, §2º, CLT):**

- O contrato se extingue automaticamente
- Verbas são devidas aos dependentes habilitados perante o INSS ou, na falta, aos herdeiros legais (art. 1º, Lei 6.858/1980)
- Verbas devidas: saldo de salário, 13º proporcional, férias vencidas + 1/3, férias proporcionais + 1/3, FGTS + multa de 40% (art. 20, V, Lei 8.036/1990), seguro de vida (se previsto) e saldo FGTS para dependentes
- **Seguro-desemprego:** não aplicável
- **PIS/PASEP:** saldo disponível para dependentes

**Morte do empregador pessoa física (art. 483, §2º, CLT):**

- Empregado pode rescindir o contrato, caso a morte acarrete transformação na empresa que torne impossível a continuação do vínculo
- Verbas equivalentes às da rescisão sem justa causa
- Se os herdeiros continuam a atividade e mantêm o empregado, o contrato prossegue normalmente

***

## 2. Tabela Completa de Verbas Rescisórias por Modalidade

<!-- [MÓDULO: 3] [SUBTEMA: tabela-verbas-rescisórias] [TIPO: referencia-tabela] -->

### 2.1 Tabela Geral de Verbas

| Verba | Sem Justa Causa | Justa Causa | Pedido Demissão | Acordo Mútuo (484-A) | Rescisão Indireta | Culpa Recíproca | Término Experiência |
| :-- | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| Saldo de salário | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 100% |
| Aviso prévio (trabalhado ou indenizado) | ✅ 100% | ❌ | ✅ (empregado cumpre ou desconta) | ✅ 50% | ✅ 100% | ✅ 50% | ❌ |
| 13º proporcional | ✅ 100% | ❌ | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 50% | ✅ 100% |
| Férias vencidas + 1/3 | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 100% |
| Férias proporcionais + 1/3 | ✅ 100% | ❌ | ✅ 100% | ✅ 100% | ✅ 100% | ✅ 50% | ✅ 100% |
| FGTS saldo depositado | ✅ (saldo) | ✅ (saldo, sem saque) | ✅ (saldo, sem saque) | ✅ (saque 80%) | ✅ (saque 100%) | ✅ (saque) | ✅ (saldo) |
| Multa FGTS | ✅ **40%** | ❌ 0% | ❌ 0% | ✅ **20%** | ✅ **40%** | ✅ **20%** | ❌ 0% |
| Seguro-desemprego | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ (controverso) | ❌ |
| Indenização art. 479 | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ (se antecipada) |

> **Base legal:** Arts. 477, 479, 480, 482, 483, 484, 484-A da CLT; art. 18, §1º, Lei 8.036/1990; art. 3º, Lei 7.998/1990.

***

### 2.2 Fórmulas de Cálculo por Verba

<!-- [MÓDULO: 3] [SUBTEMA: formulas-calculo-verbas] [TIPO: referencia-calculo] -->
**Saldo de salário:**

```
Saldo = (Salário Mensal ÷ 30) × Dias trabalhados no mês da rescisão
```

**13º salário proporcional (art. 3º, Lei 4.090/1962):**

```
13º Prop. = (Salário Mensal ÷ 12) × Meses trabalhados no ano
```

> Fração ≥ 15 dias = 1 mês completo. Fração < 15 dias = desprezada.

**Férias proporcionais + 1/3:**

```
Férias Prop. = (Salário Mensal ÷ 12) × Meses do período aquisitivo incompleto
Adicional 1/3 = Férias Prop. × 1/3
```

> Base: art. 146, parágrafo único, CLT. Mesma regra de fração de 15 dias.

**Férias vencidas + 1/3:**

```
Férias Vencidas = Salário Mensal × (Dias de férias não gozadas ÷ 30)
Adicional 1/3 = Férias Vencidas × 1/3
```

> Se gozadas parcialmente (ex: 15 dias gozados de 30 devidos): calcular sobre 15 dias restantes.

**Aviso prévio indenizado (sem proporcionalidade):**

```
AP Indenizado = (Salário Mensal ÷ 30) × Dias de Aviso Prévio
```

> Para o aviso proporcional, vide Seção 4 deste módulo.

**Multa FGTS (40%):**

```
Multa = Saldo Total FGTS (todos os depósitos + rendimentos) × 0,40
```

> Para acordo mútuo: × 0,20. O saldo total é consultado no FGTS Digital ou portal Caixa Econômica Federal.

***

## 3. FGTS — Detalhamento Completo

<!-- [MÓDULO: 3] [SUBTEMA: fgts-completo] [TIPO: legal-operacional] -->

### 3.1 Depósito Mensal

<!-- [MÓDULO: 3] [SUBTEMA: fgts-deposito-mensal] [TIPO: legal-operacional] -->
O FGTS é regido pela Lei 8.036/1990. O empregador deve depositar mensalmente o equivalente a **8% da remuneração bruta** do empregado em conta vinculada na Caixa Econômica Federal. Para o **menor aprendiz**, a alíquota é de **2%** (art. 15, §7º, Lei 8.036/1990).

**Base de cálculo:** Inclui salário, horas extras habituais, adicionais (noturno, de insalubridade, de periculosidade), gratificações habituais e 13º salário. Exclui indenizações e benefícios não salariais (art. 457, §2º, CLT — Reforma Trabalhista).

**Prazo de recolhimento:** Até o **dia 20 do mês seguinte** à competência, ou o dia útil anterior quando o dia 20 cair em dia não útil (art. 15, §4º, Lei 8.036/1990, com redação dada pela Lei 14.438/2022).[^3]

> **Antes da Reforma/FGTS Digital:** Prazo era até o dia 7 do mês seguinte. A Lei 14.438/2022 alterou para dia 20.

***

### 3.2 Multa Rescisória

<!-- [MÓDULO: 3] [SUBTEMA: fgts-multa-rescisoria] [TIPO: legal-operacional] -->
| Modalidade | Multa FGTS | Base Legal |
| :-- | :--: | :-- |
| Dispensa sem justa causa | **40%** | Art. 18, §1º, Lei 8.036/1990 |
| Rescisão indireta | **40%** | Art. 18, §1º + art. 483 CLT |
| Culpa recíproca | **20%** | Art. 18, §2º, Lei 8.036/1990 |
| Acordo mútuo | **20%** | Art. 484-A, §1º, II, CLT |
| Justa causa (empregador) | **0%** | Art. 18, caput, Lei 8.036/1990 |
| Pedido de demissão | **0%** | Art. 18, caput, Lei 8.036/1990 |
| Término natural de contrato | **0%** | Art. 18, caput, Lei 8.036/1990 |

> **Nota:** A multa de 40% tem um componente adicional de **10%** recolhido ao Governo Federal como contribuição social (art. 1º, LC 110/2001), totalizando 50% sobre o saldo FGTS nos casos de dispensa sem justa causa. O FGTS Digital unificou o recolhimento de ambos os componentes.

***

### 3.3 Hipóteses de Saque do FGTS

<!-- [MÓDULO: 3] [SUBTEMA: fgts-saque-hipoteses] [TIPO: referencia] -->
| Hipótese | Base Legal | Percentual de Saque |
| :-- | :-- | :--: |
| Dispensa sem justa causa | Art. 20, I, Lei 8.036/1990 | 100% |
| Acordo mútuo (art. 484-A CLT) | Art. 20, I-A, Lei 8.036/1990 | Até 80% |
| Rescisão indireta | Art. 20, I, Lei 8.036/1990 | 100% |
| Aposentadoria | Art. 20, III, Lei 8.036/1990 | 100% |
| Doença grave (neoplasia maligna, HIV, etc.) | Art. 20, XI, Lei 8.036/1990 | 100% |
| Falecimento do trabalhador | Art. 20, V, Lei 8.036/1990 | 100% (dependentes) |
| FGTS Aniversário (opt-in) | Art. 20-C, Lei 8.036/1990 | % variável por faixa |
| Conta inativa por 3 anos (extinção da empresa) | Art. 20, II, Lei 8.036/1990 | 100% |
| Financiamento habitacional (SFH) | Art. 20, V, Lei 8.036/1990 | Parcial |
| Desastre natural / estado de calamidade | Art. 20-A, Lei 8.036/1990 | Variável |

> **Atenção FGTS Aniversário:** O trabalhador que aderiu ao saque-aniversário **perde o direito ao saque total** em caso de demissão sem justa causa, podendo sacar apenas a parcela aniversário. Para manter o saque integral rescisório, deve cancelar a opção com **25 meses de antecedência** (regra vigente pós-Resolução CCFGTS 971/2021).

***

### 3.4 FGTS Digital — Novo Sistema de Recolhimento

<!-- [MÓDULO: 3] [SUBTEMA: fgts-digital-sistema] [TIPO: operacional-tecnico] -->
O FGTS Digital é o sistema que substituiu o SEFIP/GFIP para fins de recolhimento do FGTS, operando de forma integrada ao eSocial. Implantado gradualmente desde março de 2023, está vigente para todos os empregadores.

**Principais características (situação em março de 2026):**

- **Pagamento exclusivo via Pix** — a Resolução BCB nº 503/2025 (publicada em 18/09/2025) restabeleceu o recolhimento via Pix **sem limite de valor por transação** para guias do FGTS Digital, permitindo pagamento integral em uma única operação[^4]
- Emissão de Guia de Recolhimento do FGTS Digital (GFD) pelo portal `fgts.digital.gov.br`
- Integração automática com o eSocial: folha processada no eSocial gera automaticamente a GFD
- **Tipos de guias:** mensal, rescisória, parcelamento e consignado

**Prazos no FGTS Digital:**


| Tipo de Recolhimento | Prazo | Observação |
| :-- | :-- | :-- |
| FGTS mensal | Dia 20 do mês seguinte | Antecipa se não for dia útil |
| FGTS rescisório | 10 dias corridos após desligamento | Inclui multa 40% ou 20% |

> **Base legal:** Lei 14.438/2022; IN SIT nº 10/2025 (Nota Orientativa).[^4][^3]

***

## 4. Aviso Prévio

<!-- [MÓDULO: 3] [SUBTEMA: aviso-previo-completo] [TIPO: legal-operacional] -->

### 4.1 Aviso Prévio Trabalhado vs. Indenizado

<!-- [MÓDULO: 3] [SUBTEMA: aviso-previo-modalidades] [TIPO: legal-operacional] -->
O aviso prévio é regulado pelos arts. 487 a 491 da CLT e pelo art. 7º, XXI, CF/88. Tem por finalidade comunicar com antecedência o término do contrato, permitindo que a outra parte se prepare.

**Aviso prévio trabalhado:**

- O empregado continua prestando serviços durante o período de aviso
- O empregador pode conceder ao empregado a **redução de 2 horas diárias** na jornada ou a opção de **faltar 7 dias corridos** ao final do aviso (art. 488, parágrafo único, CLT) — escolha do **empregado**
- O salário do período de aviso integra a remuneração para todos os efeitos (FGTS, férias, 13º)

**Aviso prévio indenizado:**

- O empregador ou empregado opta pelo pagamento em espécie, sem prestação de serviços
- O valor equivale aos dias de aviso prévio calculados sobre a remuneração do empregado
- O período de aviso indenizado **conta como tempo de serviço** para fins de FGTS e período aquisitivo de férias (Súmula 305 TST; art. 487, §1º, CLT)

**Aviso prévio dado pelo empregado:**

- Deve cumprir integralmente (sem redução de jornada a seu favor)
- Se não cumprir, o empregador pode descontar os dias não trabalhados da rescisão (art. 487, §2º, CLT)

***

### 4.2 Aviso Prévio Proporcional — Lei 12.506/2011

<!-- [MÓDULO: 3] [SUBTEMA: aviso-previo-proporcional] [TIPO: referencia-tabela] -->
A Lei 12.506/2011 regulamentou o art. 7º, XXI, CF/88, estabelecendo a proporcionalidade do aviso prévio: **30 dias base + 3 dias por ano de serviço completo**, até o máximo de **90 dias** no total.[^5][^6]

**Tabela de aviso prévio proporcional:**


| Tempo de Serviço na Empresa | Dias de Aviso Prévio |
| :-- | :--: |
| Até 1 ano (menos de 1 ano completo) | 30 dias |
| 1 ano completo até menos de 2 anos | 33 dias |
| 2 anos completos até menos de 3 anos | 36 dias |
| 3 anos completos até menos de 4 anos | 39 dias |
| 4 anos completos até menos de 5 anos | 42 dias |
| 5 anos completos até menos de 6 anos | 45 dias |
| 6 anos completos até menos de 7 anos | 48 dias |
| 7 anos completos até menos de 8 anos | 51 dias |
| 8 anos completos até menos de 9 anos | 54 dias |
| 9 anos completos até menos de 10 anos | 57 dias |
| 10 anos completos até menos de 11 anos | 60 dias |
| 11 anos completos até menos de 12 anos | 63 dias |
| 12 anos completos até menos de 13 anos | 66 dias |
| 13 anos completos até menos de 14 anos | 69 dias |
| 14 anos completos até menos de 15 anos | 72 dias |
| 15 anos completos até menos de 16 anos | 75 dias |
| 16 anos completos até menos de 17 anos | 78 dias |
| 17 anos completos até menos de 18 anos | 81 dias |
| 18 anos completos até menos de 19 anos | 84 dias |
| 19 anos completos até menos de 20 anos | 87 dias |
| 20 anos completos ou mais | **90 dias** (máximo) |

> **Atenção:** A Lei 12.506/2011 fala em "ano completado". A contagem começa no 2º ano — um empregado com 1 ano e 1 dia tem direito a 33 dias. Para o empregado que pede demissão, o TST (OJ 14, SDI-1) entende que a proporcionalidade também se aplica.

**Aviso prévio no acordo mútuo:** Metade dos dias calculados pela tabela acima (mínimo de 15 dias), nos termos do art. 484-A, §1º, I, CLT.

***

## 5. Prazos e Procedimentos de Rescisão

<!-- [MÓDULO: 3] [SUBTEMA: prazos-procedimentos-rescisao] [TIPO: operacional] -->

### 5.1 Prazo de Pagamento e Multa por Atraso

<!-- [MÓDULO: 3] [SUBTEMA: prazo-pagamento-multa-atraso] [TIPO: legal-operacional] -->
**Antes da Reforma Trabalhista (até 11/11/2017):**

- Aviso prévio trabalhado: pagamento até **1 dia útil** após o último dia de trabalho
- Aviso indenizado ou dispensa imediata: pagamento em até **10 dias** corridos

**Após a Reforma Trabalhista (Lei 13.467/2017 — vigente):**

- Prazo único: **10 dias corridos** a partir da data de rescisão do contrato (art. 477, §6º, CLT)
- Aplica-se a todas as modalidades

**Multa por descumprimento do prazo (art. 477, §8º, CLT):**

- Equivalente a **1 salário mensal do empregado** (referente ao último salário)
- Aplica-se ao empregador; se o empregado deu causa ao atraso (ex: não comparecer para assinar), a multa não é devida

***

### 5.2 Homologação da Rescisão

<!-- [MÓDULO: 3] [SUBTEMA: homologacao-rescisao] [TIPO: legal-historico] -->
**Antes da Reforma (até 11/11/2017):**

- Empregados com mais de 1 ano de empresa deviam ter a rescisão homologada no **Sindicato da categoria** ou na **Delegacia Regional do Trabalho (DRT)**, sob pena de nulidade
- Exigência do art. 477, §1º, CLT (revogado pela Lei 13.467/2017)

**Após a Reforma (vigente desde 11/11/2017):**

- **Homologação sindical NÃO é mais obrigatória** (art. 477, §1º, CLT revogado)
- Exceção: se previsto em **norma coletiva** (CCT ou ACT), a homologação pode ser exigida pelo instrumento coletivo
- Recomenda-se que o TRCT seja assinado por advogado ou contador responsável pelo DP para fins de prova

***

### 5.3 Documentos Obrigatórios na Rescisão

<!-- [MÓDULO: 3] [SUBTEMA: documentos-rescisao] [TIPO: operacional-checklist] -->
| Documento | Obrigatoriedade | Observação |
| :-- | :--: | :-- |
| TRCT — Termo de Rescisão do Contrato de Trabalho | Obrigatório | Art. 477, §2º, CLT; modelo padrão MTE |
| Termo de Quitação (recibo) | Obrigatório | Assinado pelo empregado; prova do pagamento |
| Chave de Conectividade FGTS | Obrigatório | Gerada no FGTS Digital; permite ao empregado movimentar a conta |
| Guias do Seguro-Desemprego (SD/CD) | Obrigatório (quando cabível) | Formulário SD — Comunicação de Dispensa |
| Comunicação de Dispensa para Seguro-Desemprego | Obrigatório (quando cabível) | Emitida via portal Emprega Brasil |
| ASO Demissional | Obrigatório (ver exceções na NR-7) | Dispensável se exame periódico < 135 dias; clínica de estética: sempre realizar |
| Baixa na CTPS Digital | Automática via eSocial (S-2299) | Não é mais necessária anotação manual na CTPS física |

> **CTPS Digital:** Com o eSocial, a baixa no emprego é registrada automaticamente quando o evento S-2299 é processado. O empregado não precisa mais apresentar a CTPS física para anotação. Base: art. 29, §3º, CLT (redação dada pela Lei 13.874/2019).

***

## 6. Estágio — Rescisão e Particularidades

<!-- [MÓDULO: 3] [SUBTEMA: estagio-rescisao] [TIPO: legal-operacional] -->

### 6.1 Estágio Regular — Ausência de Vínculo CLT

<!-- [MÓDULO: 3] [SUBTEMA: estagio-regular] [TIPO: legal-conceitual] -->
O estágio regular é regido pela **Lei 11.788/2008** (Lei do Estágio) e **não gera vínculo empregatício** com a concedente, desde que cumpridos todos os requisitos legais. Consequentemente, não há verbas rescisórias nos termos da CLT.

**Requisitos para o estágio ser regular (art. 3º, Lei 11.788/2008):**

1. Matrícula e frequência regular em instituição de ensino
2. Celebração de **Termo de Compromisso de Estágio (TCE)** entre estagiário, concedente e instituição de ensino
3. Existência de **Plano de Atividades** compatível com o currículo escolar
4. Indicação de **supervisor na concedente** (com formação ou experiência profissional na área)
5. Designação de **orientador** pela instituição de ensino
6. Carga horária: máximo **6 horas/dia e 30 horas/semanais** (exceto para estágios que façam parte da grade de ensino regular)

**Ao encerramento do estágio, são devidos:**

- **Recesso remunerado:** 30 dias por 12 meses de estágio (proporcional se período < 12 meses) — art. 13, Lei 11.788/2008; deve ser concedido preferencialmente durante as férias escolares
- **Bolsa proporcional** pelos dias trabalhados no mês de encerramento
- **Seguro obrigatório contra acidentes pessoais** durante todo o período (art. 9º, IV, Lei 11.788/2008)

***

### 6.2 Quando o Estágio Vira CLT

<!-- [MÓDULO: 3] [SUBTEMA: estagio-irregular-clt] [TIPO: legal-risco] -->
O estágio **irregular** é equiparado ao emprego comum, gerando reconhecimento de vínculo empregatício e todas as verbas trabalhistas retroativas. Situações de risco:


| Irregularidade | Consequência | Exemplo em Agências/Imobiliárias |
| :-- | :-- | :-- |
| Desvio de função | Vínculo CLT | Estagiário de marketing atuando como vendedor pleno sem supervisão pedagógica |
| Ausência de supervisor na concedente | Vínculo CLT | Agência sem funcionário designado como supervisor de estágio |
| Ausência de Plano de Atividades | Vínculo CLT | TCE sem descrição das atividades pedagógicas |
| Matrícula desatualizada / aluno formado | Vínculo CLT | Estagiário que se formou mas continua na empresa sem conversão para CLT |
| Carga horária acima do limite | Vínculo CLT | Estagiário trabalhando 8h/dia (acima das 6h permitidas) |
| Ausência de TCE válido | Vínculo CLT | Contrato assinado apenas entre empresa e estagiário, sem participação da IES |

> **Risco para escritórios de advocacia:** O estágio jurídico supervisionado pela OAB tem regras específicas (Provimento 144/2011 OAB). A prática de atos processuais sem a devida supervisão pode caracterizar tanto irregularidade ética quanto trabalhista.

***

## 7. eSocial e Obrigações Acessórias — Guia Prático

<!-- [MÓDULO: 3] [SUBTEMA: esocial-obrigacoes-acessorias] [TIPO: operacional-tecnico] -->

### 7.1 Eventos Trabalhistas no eSocial

<!-- [MÓDULO: 3] [SUBTEMA: esocial-eventos-principais] [TIPO: operacional-tecnico] -->
| Evento | Código | Descrição | Prazo |
| :-- | :-- | :-- | :-- |
| Admissão | S-2200 | Cadastramento inicial do empregado | Até o dia **anterior** ao início das atividades |
| Admissão (simplificada) | S-2190 | Para empresas com folha simplificada | Até o dia anterior ao início |
| Afastamento temporário | S-2230 | Licenças, afastamentos INSS | Até o **décimo dia** corrido do afastamento |
| Desligamento | S-2299 | Rescisão contratual | Até **10 dias corridos** contados da data do desligamento, excluído o dia do desligamento [^7][^8] |
| Alteração de dados cadastrais | S-2205 | Mudança de cargo, salário, jornada | Antes do processamento da folha |
| Folha de pagamento | S-1200 | Remuneração mensal | Até o dia 7 do mês seguinte (fechamento da folha eSocial) |
| Férias | S-2230 | Afastamento por férias | Antes do início das férias |

> **Prazo S-2299:** De acordo com o MOS S-1.3 (consolidado até NO S-1.3/05-2025), o prazo é de 10 dias corridos a partir da data do desligamento, excluindo o próprio dia do desligamento. Se o prazo vencer em dia não útil, deve ser antecipado para o dia útil anterior.[^7][^9]

***

### 7.2 Obrigações Extintas e Suas Substituições

<!-- [MÓDULO: 3] [SUBTEMA: obrigacoes-extintas-substituicoes] [TIPO: historico-tecnico] -->
| Obrigação Extinta | Substituída por | Vigência da Substituição |
| :-- | :-- | :-- |
| RAIS (Relação Anual de Informações Sociais) | eSocial (automático) | Desde 2019 (grandes empresas); 2020 (demais) |
| CAGED (Cadastro Geral de Empregados e Desempregados) | eSocial (eventos S-2200, S-2299) | Desde Janeiro/2020 |
| DIRF (Declaração de Imposto de Renda Retido na Fonte) | EFD-Reinf + DCTF-Web | A partir do ano-calendário 2024 (entrega 2025) |
| GFIP/SEFIP (Guia de Recolhimento FGTS e Previdência) | eSocial + DCTFWeb + FGTS Digital | Progressivo 2019-2025 |
| DCTF convencional (PGD) | DCTFWeb | IN RFB 2.237/2024 — extinção a partir jan/2025 |


***

### 7.3 DCTFWeb — Declaração de Débitos e Créditos Tributários Federais

<!-- [MÓDULO: 3] [SUBTEMA: dctfweb-obrigacoes] [TIPO: operacional-tecnico] -->
A DCTFWeb substituiu a GFIP como instrumento de confissão de dívida previdenciária e constituição do crédito tributário federal. Desde janeiro de 2025, também incorporou os tributos antes declarados na DCTF convencional (IN RFB 2.237/2024).[^10][^11]

**Prazos de entrega:**[^12]


| Tipo | Prazo |
| :-- | :-- |
| DCTFWeb mensal | Até o **15º dia útil** do mês seguinte aos fatos geradores |
| DCTFWeb rescisória (diária/eventual) | Até o **dia do pagamento** da rescisão contratual |
| DCTFWeb anual (imunes/isentas) | Até o 15º dia útil de janeiro do ano seguinte |

> **Atenção:** Há atualizações recentes nos prazos da DCTFWeb. Consulte sempre o Manual de Orientação da DCTFWeb e as Instruções Normativas vigentes, pois o prazo mensal pode variar conforme normas supervenientes.[^13][^11]

***

### 7.4 Multas por Descumprimento de Obrigações Acessórias

<!-- [MÓDULO: 3] [SUBTEMA: multas-obrigacoes-acessorias] [TIPO: referencia-legal] -->
| Obrigação | Infração | Multa |
| :-- | :-- | :-- |
| eSocial — não envio de S-2200 | Admissão sem registro | R\$ 402,53 a R\$ 805,06 por empregado (art. 47, CLT) |
| eSocial — atraso no S-2299 | Desligamento fora do prazo | Sujeito a autuação fiscal (Portaria MTE 1.195/2010, adaptada ao eSocial) |
| FGTS Digital — recolhimento em atraso | Não pagamento no prazo | Multa diária + encargos (art. 22, Lei 8.036/1990) — atualização TR + 3% a.a. + multa 10% |
| DCTFWeb — não entrega | Omissão | R\$ 500,00/mês (para empresas enquadradas no Simples) ou R\$ 1.000,00/mês (demais) — IN RFB 2.237/2024 |
| TRCT — não fornecimento | Prazo art. 477 CLT | R\$ 170,00 a R\$ 340,00 por empregado (portaria MTE) |
| Registro de empregado — ausência | Art. 47 CLT | R\$ 3.000,00 por empregado não registrado (MPE: R\$ 800,00) |


***

## 8. Compliance Trabalhista — Programa Prático para PMEs

<!-- [MÓDULO: 3] [SUBTEMA: compliance-trabalhista-pme] [TIPO: operacional-estratégico] -->

### 8.1 Código de Conduta e Políticas Obrigatórias

<!-- [MÓDULO: 3] [SUBTEMA: codigo-conduta-politicas] [TIPO: operacional] -->
O código de conduta não tem forma legal obrigatória única, mas sua ausência representa risco em processos de assédio e discriminação. Para empresas com CIPA, a Lei 14.457/2022 tornou obrigatórios os mecanismos de prevenção.[^14][^15]

**Temas obrigatórios no código de conduta:**

- **Assédio moral e sexual:** definições, exemplos, procedimentos de denúncia; referência à Lei 9.029/1995, arts. 216-A e 223-A a 223-G CLT
- **Discriminação:** raça, gênero, orientação sexual, deficiência, religião — Lei 9.029/1995, art. 1º; Lei 9.459/1997
- **Uso de dados e LGPD:** tratamento de dados de empregados, clientes e parceiros — Lei 13.709/2018
- **Redes sociais e imagem corporativa:** proibição de divulgação de informações confidenciais, regras para menção ao empregador
- **Conflito de interesses:** vedação de atividades concorrentes durante o vínculo (cláusula de não concorrência deve ser inserida no contrato — art. 444, CLT)
- **Integridade e propina:** Lei 12.846/2013 (Lei Anticorrupção) para empresas com relacionamento com poder público

***

### 8.2 Política de Teletrabalho / Home Office

<!-- [MÓDULO: 3] [SUBTEMA: politica-teletrabalho] [TIPO: operacional-legal] -->
Após a Reforma Trabalhista (Lei 13.467/2017, arts. 75-A a 75-E CLT) e a regulamentação emergencial da pandemia (MP 927/2020, expirada), as regras de teletrabalho foram consolidadas pela **Lei 14.442/2022**.

**Requisitos formais do contrato de teletrabalho:**

- Previsão expressa no contrato individual ou aditivo contratual (art. 75-C, CLT)
- Indicação das atividades realizadas pelo empregado
- Definição sobre responsabilidade pelos equipamentos e infraestrutura (art. 75-D, CLT)
- Previsão de reversão ao trabalho presencial, com prazo de adaptação de **15 dias** (art. 75-C, §2º, CLT)

**Conteúdo mínimo da política de teletrabalho:**


| Item | Obrigatoriedade | Base Legal |
| :-- | :--: | :-- |
| Equipamentos fornecidos ou reembolso | Contratual | Art. 75-D, CLT |
| Jornada (controlada ou não) | Contratual | Art. 62, III, CLT |
| Ergonomia em home office | Orientação obrigatória | NR-17 (Portaria MTE 1.129/2017) |
| Assinatura de termo de ciência de ergonomia | Recomendado | NR-17; responsabilidade civil |
| Direito à desconexão | Boas práticas | Art. 6º, parágrafo único, CLT |
| Hipóteses de reversão | Contratual | Art. 75-C, §2º, CLT |


***

### 8.3 Canal de Denúncias (Lei 14.457/2022)

<!-- [MÓDULO: 3] [SUBTEMA: canal-denuncias-lei-14457] [TIPO: legal-operacional] -->
A Lei 14.457/2022 (Programa Emprega + Mulheres) alterou a CLT e tornou obrigatória a implementação de canal de denúncias para empresas com CIPA constituída. O prazo de adequação venceu em **21 de março de 2023**. Empresas ainda sem canal estão em situação irregular e sujeitas a autuações.[^15][^14]

**Requisitos do canal de denúncias:**

- Garantia de **anonimato e sigilo** ao denunciante
- Procedimentos definidos para recebimento, acompanhamento e apuração das denúncias
- Aplicação de sanções administrativas aos responsáveis identificados
- Atribuição à CIPA de acompanhar as questões relacionadas ao canal

**Capacitação obrigatória anual (art. 23-A, CLT, inserido pela Lei 14.457/2022):**

- Temas: assédio moral e sexual, violência, discriminação, igualdade e diversidade
- Acessível a todos os níveis hierárquicos
- Frequência mínima: **anual**

***

### 8.4 Exames Médicos Ocupacionais

<!-- [MÓDULO: 3] [SUBTEMA: exames-medicos] [TIPO: operacional-legal] -->
Regulados pela **NR-7 (PCMSO — Programa de Controle Médico de Saúde Ocupacional)**, os exames médicos ocupacionais são obrigatórios para todos os empregados regidos pela CLT.


| Tipo de Exame | Momento | Observação |
| :-- | :-- | :-- |
| Admissional | Antes do início das atividades | Obrigatório; o ASO deve preceder o início do trabalho |
| Periódico | Conforme tabela da NR-7 por faixa etária e risco | Anual para maiores de 45 anos (cargos administrativos) |
| Demissional | Antes da homologação da rescisão | Dispensável se periódico realizado há menos de 135 dias (NR-7); recomenda-se sempre realizar em clínicas de estética |
| Mudança de função | Antes da transferência de função | Obrigatório se nova função tem riscos diferentes |
| Retorno ao trabalho | No primeiro dia após afastamento ≥ 30 dias | Por doença, acidente, parto ou aborto |

> **Risco para clínicas de estética:** Por envolverem exposição a produtos químicos, radiação e agentes biológicos, os profissionais de estética devem ter PCMSO robusto, incluindo avaliação de agentes químicos (produtos de limpeza, tinturas, etc.) e biológicos (risco de contaminação).

***

### 8.5 Férias — Regras Após a Reforma Trabalhista

<!-- [MÓDULO: 3] [SUBTEMA: ferias-reforma] [TIPO: legal-operacional] -->
**Antes da Reforma:** Férias deviam ser concedidas em período único de 30 dias.

**Após a Reforma (art. 134, §§1º e 2º, CLT — Lei 13.467/2017):**

- Fracionamento em até **3 períodos** (desde que um deles seja de, no mínimo, **14 dias corridos**, e nenhum inferior a **5 dias corridos**)
- Fracionamento deve ser acordado com o empregado (não pode ser imposto unilateralmente pelo empregador)
- **Início das férias:** não pode coincidir com sábados, domingos, feriados ou dias que antecedem esses dias, se o empregado recebe salário semanal ou quinzenal (art. 135, CLT)

**Pagamento de férias:**

- Deve ser efetuado até **2 dias antes** do início do período de gozo (art. 145, CLT)
- Inclui o 1/3 constitucional

**Férias coletivas (art. 139 CLT):**

- Comunicação ao MTE com antecedência mínima de 15 dias
- Aviso aos empregados com antecedência mínima de 30 dias
- Comunicação ao sindicato da categoria

***

### 8.6 NR-17 — Ergonomia em Escritórios e Home Office

<!-- [MÓDULO: 3] [SUBTEMA: nr17-ergonomia] [TIPO: operacional-legal] -->
A **NR-17 (Portaria MTE 1.129/2017)** estabelece parâmetros mínimos para adaptação das condições de trabalho às características psicofisiológicas dos trabalhadores. Para escritórios e serviços premium, os principais itens são:

**Mobiliário e estação de trabalho:**

- Superfícies de trabalho com altura regulável (ou adequada ao trabalhador)
- Cadeiras com regulagem de altura, apoio de antebraço e encosto ajustável
- Suporte para os pés quando necessário

**Equipamentos (monitors, teclados):**

- Telas ajustáveis em altura, inclinação e rotação
- Teclados separados de monitores
- Mouse posicionado na mesma superfície do teclado

**Iluminação:** Nível mínimo de 500 lux para trabalho com leitura e escrita

**Aplicação ao home office:**

- A obrigação do empregador de orientar o empregado sobre ergonomia em home office é expressa (art. 75-E, CLT)
- Recomenda-se elaborar **checklist de ergonomia** para home office e colher assinatura do empregado

***

### 8.7 Calendário Mensal de Obrigações do RH

<!-- [MÓDULO: 3] [SUBTEMA: calendario-obrigacoes-rh] [TIPO: referencia-tabela] -->
| Dia Limite | Obrigação | Base Legal |
| :-- | :-- | :-- |
| Dia 7 | Pagamento de salário (salvo acordo/CCT diferente) | Art. 459, parágrafo único, CLT |
| Dia 7 | Fechamento/envio da folha de pagamento no eSocial (S-1200/S-1202) | MOS eSocial |
| Dia 20 | Recolhimento do FGTS mensal via FGTS Digital (Pix) | Lei 14.438/2022 |
| 15º dia útil | Transmissão da DCTFWeb mensal | IN RFB / Manual DCTFWeb |
| Dia 25 | Pagamento do INSS (contribuição previdenciária patronal + empregado) | Lei 8.212/1991 |
| Dia 30 | Envio EFD-Reinf (eventos mensais) | IN RFB 2.043/2021 |
| Antes do início | Envio do S-2200 (admissão) no eSocial | MOS eSocial |
| Até 10 dias | Envio do S-2299 (desligamento) no eSocial | MOS S-1.3 |
| Até 10 dias | Pagamento das verbas rescisórias | Art. 477, §6º, CLT |
| Até 10 dias | Recolhimento do FGTS rescisório + multa | Lei 14.438/2022 |
| 2 dias antes das férias | Pagamento antecipado das férias + 1/3 | Art. 145, CLT |
| Anual (jan/fev) | Entrega do informe de rendimentos ao empregado | IN RFB |
| Anual | Treinamento obrigatório CIPA/assédio (Lei 14.457/2022) | Lei 14.457/2022 |

> **Nota:** O calendário acima é base. Obrigações específicas por setor (ex: NRs aplicáveis à clínica de estética, PCMSO, PPRA/PGR) devem ser incluídas conforme o grau de risco da atividade.

***

## 9. Checklist Operacional — Admissão

<!-- [MÓDULO: 3] [SUBTEMA: checklist-admissao] [TIPO: operacional-checklist] -->

### 9.1 Documentos Obrigatórios do Empregado

<!-- [MÓDULO: 3] [SUBTEMA: admissao-documentos] [TIPO: checklist] -->
- [ ] RG (ou CNH, ou passaporte)
- [ ] CPF
- [ ] CTPS Digital (número do CPF, via eSocial — a CTPS física é opcional desde a Lei 13.874/2019)
- [ ] PIS/PASEP (número de inscrição — essencial para FGTS Digital)
- [ ] Comprovante de residência atualizado
- [ ] Certidão de nascimento ou casamento
- [ ] Comprovante de escolaridade (exigido para cargos específicos ou para aprendizagem)
- [ ] Certidão de nascimento dos filhos até 14 anos (para salário-família, se aplicável)
- [ ] Laudo médico de deficiência (para empregados PCD — Lei 8.213/1991, art. 93)
- [ ] Conta bancária (para depósito de salário)
- [ ] Foto 3x4 (se exigido internamente)

***

### 9.2 Procedimentos de Admissão

<!-- [MÓDULO: 3] [SUBTEMA: admissao-procedimentos] [TIPO: checklist] -->
- [ ] **Registro no eSocial (S-2200):** enviar até o dia **anterior** ao início das atividades — sem exceções (art. 13, Lei 13.874/2019; MOS eSocial)
- [ ] **Exame admissional (ASO):** realizado antes do início; o empregado só pode iniciar as atividades após o ASO com resultado "Apto"
- [ ] **Elaboração e assinatura do contrato de trabalho** (por prazo indeterminado, determinado ou de experiência)
    - Se teletrabalho: incluir aditivo de teletrabalho (art. 75-C, CLT) ou prever diretamente no contrato
    - Se cargo de confiança: prever gratificação e jornada (art. 62, II, CLT)
- [ ] **Abertura da conta FGTS** (automática via FGTS Digital com o envio do S-2200 e PIS/PASEP do empregado)
- [ ] **Cadastro no plano de saúde** (se oferecido pela empresa) — prazo conforme contrato com operadora
- [ ] **Integração inicial:** entregar e colher assinatura de ciência nos seguintes documentos:
    - [ ] Código de conduta / política interna
    - [ ] Regulamento interno
    - [ ] Política de teletrabalho (se aplicável)
    - [ ] Termo de uso de equipamentos e BYOD
    - [ ] Orientação de ergonomia (NR-17)
    - [ ] Políticas de LGPD aplicáveis ao cargo
- [ ] **Inclusão na CIPA** (se cargo elegível por função ou conforme CCT)
- [ ] **Registro no plano de benefícios** (VT, VR/VA, plano odontológico, etc.)
- [ ] **Cadastro no ponto eletrônico / sistema de controle de jornada** (se empresa com 20+ empregados — art. 74, §2º, CLT)

***

## 10. Checklist Operacional — Demissão

<!-- [MÓDULO: 3] [SUBTEMA: checklist-demissao] [TIPO: operacional-checklist] -->

### 10.1 Fase 1 — Formalização da Rescisão

<!-- [MÓDULO: 3] [SUBTEMA: demissao-fase1-formalizacao] [TIPO: checklist] -->
- [ ] **Carta de comunicação de dispensa** (se iniciativa do empregador): indicar a modalidade (sem justa causa, justa causa com art. 482 e alínea específica, acordo mútuo), data do desligamento e data de início do aviso prévio
- [ ] **Pedido de demissão formal** (se iniciativa do empregado): por escrito, com assinatura do empregado e testemunha
- [ ] **Acordo mútuo:** lavrar instrumento
<span style="display:none">[^16][^17][^18][^19][^20][^21][^22][^23][^24][^25][^26][^27][^28][^29][^30]</span>

<div align="center">⁂</div>

[^1]: https://www.csjt.jus.br/web/csjt/noticias3/-/asset_publisher/RPt2/content/id/6933354

[^2]: https://sindvig.org.br/acordo-mutuo-na-demissao/

[^3]: https://escolasuperioresn.com.br/fgts-digital-2026-guia-completo-funcionamento/

[^4]: https://www.gov.br/trabalho-e-emprego/pt-br/servicos/empregador/fgtsdigital/comunicados/banco-central-do-brasil-restabelece-o-recolhimento-do-fgts-digital-sem-limitacao-de-valor-por-transacao-pix

[^5]: https://www.kpmg.com.br/publicacoes/tax/Boletim_Legislacao_Fiscal_Mercado_Empreendedor/O_Aviso_Previo_Proporcional.pdf

[^6]: https://idealsoftwares.com.br/tabelas/tabela.php?id=250

[^7]: https://www.instagram.com/reel/DQUkqfXiXre/

[^8]: https://documentacao.senior.com.br/gestao-de-pessoas-hcm/esocial/leiautes/nao-periodicos/s-2299.htm

[^9]: https://suporte.dominioatendimento.com/central/faces/solucao.html?codigo=6862

[^10]: https://qive.com.br/blog/dctfweb

[^11]: https://www.metadados.com.br/blog/entenda-a-dctfweb

[^12]: https://www.e-auditoria.com.br/blog/dctfweb-o-que-e-quando-entregar-e-o-que-muda-com-o-fim-da-dctf-pgd/

[^13]: https://keevo.com.br/blog-ec/dctfweb-o-que-e/

[^14]: https://canaldedenuncias.com.br/nova-lei-14-457-exige-a-implantacao-do-canal-de-denuncias-em-empresas-com-cipa/

[^15]: https://blog.bcompliance.com.br/2025/08/15/canal-de-denuncias-lei-14457-2022/

[^16]: https://jrconttabilidade.com.br/noticias/tecnicas/2025/09/18/sit-orienta-empregadores-sobre-recolhimento-do-fgts-digital-em-fintechs-sujeitas-a-limite-do-pix.html

[^17]: https://fiscco.cnt.br/noticias/detalhes/31402/banco-central-do-brasil-restabelece-o-recolhimento-do-fgts-digital-sem-limitacao-de-valor-por-transacao-pix

[^18]: https://www.gov.br/trabalho-e-emprego/pt-br/servicos/empregador/fgtsdigital/comunicados/fgts-digital-todos-os-comunicados

[^19]: https://www.memoriaforense.com/produtos/direito-do-trabalho-resumido-2026-viisx/

[^20]: https://escolasuperioresn.com.br/fgts-digital-2026-o-que-mudou/

[^21]: https://pt.scribd.com/document/886387589/ADRIANO-Corrigido-06-07

[^22]: https://www.metadados.com.br/blog/fgts-digital

[^23]: https://www.ghc.com.br/portalrh/files/arq_ptg_6_1_1178.pdf

[^24]: https://www.gov.br/receitafederal/pt-br/assuntos/orientacao-tributaria/declaracoes-e-demonstrativos/DCTFWeb/arquivos/perguntas-e-respostas-dctfweb-2025-09-23.pdf

[^25]: https://www.gov.br/receitafederal/pt-br/centrais-de-conteudo/publicacoes/manuais/manual-dctfweb/manual-dctfweb-atualizacao-janeiro2025_versao_final.pdf

[^26]: https://ambitojuridico.com.br/acordo-trabalhista-da-direito-ao-seguro-desemprego/

[^27]: https://cidmed.med.br/web/canal-denuncias-cipa/

[^28]: https://www.youtube.com/watch?v=Shb-lJO5OSo

[^29]: https://cnm.org.br/comunicacao/noticias/contabilidade-nova-regra-de-entrega-da-dctfweb-para-prazo-fora-de-dia-util-e-fim-da-gfip

[^30]: https://nextbay.com.br/blogpost/lei-14-457-22-muda-clt-e-cipa-entenda-a-obrigatoriedade-do-canal-de-denuncias-no-ambiente-de-trabalh


</content>
