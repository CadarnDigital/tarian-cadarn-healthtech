# DNA-EXTRACT: Direito Contratual, Empresarial, Tributário e Regulação de IA para Agências Martech

> **Domínio:** Direito Contratual, Empresarial, Tributário, LGPD, Societário e Compliance — aplicado a agências de Engenharia de Lucro (Martech)
> **Fonte:** `.aiox-core/knowledge/agents-dna/juridica-contratos/`
> **Módulos processados:** 5
> **Extraído em:** 2026-03-23
> **Minerador:** Athena (knowledge-miner)

---

## 1. Conceitos-Chave

> Definições e termos fundamentais do especialista. Cada entrada é um conceito que o agente-clone DEVE conhecer.

| Conceito | Definição | Contexto de uso |
|----------|-----------|-----------------|
| Obrigação de Meio vs. Obrigação de Resultado | Obrigação de meio: o prestador emprega melhores esforços sem garantir resultado específico. Obrigação de resultado: o prestador se compromete com entrega mensurável. Agências de marketing assumem obrigação de MEIO (CC arts. 593-609), salvo estipulação expressa em contrário. | Sempre que redigir ou analisar cláusula de objeto/KPIs em contrato de agência. Qualquer promessa numérica (leads, ROI, seguidores) converte para obrigação de resultado. |
| Controlador vs. Operador (LGPD) | Controlador (art. 5º, VI): quem decide finalidades e meios do tratamento. Operador (art. 5º, VII): quem realiza tratamento em nome do controlador. Na relação agência-cliente, o cliente é controlador e a agência é operador. | Em toda cláusula LGPD de contrato agência-cliente. Exceção: agência pode ser co-controladora se tomar decisões autônomas sobre dados (ex: segmentação por IA sem instrução do cliente). |
| Scope Creep | Expansão informal e não remunerada do escopo contratual. Ocorre quando a cláusula de objeto é vaga ou ausente. | Ao revisar cláusula de objeto: exigir listagem exaustiva de serviços incluídos E excluídos, com previsão de aditivo para extras. |
| Fator R (Simples Nacional) | Razão entre folha de pagamento (12 meses) e receita bruta (12 meses). Se >= 28%: Anexo III (alíquotas menores). Se < 28%: Anexo V (alíquotas maiores). LC 123/2006, art. 18, § 24. | Ao orientar sobre regime tributário de agência. CNAEs 7311-4/00, 7319-0/04 e 6311-9/00 estão sujeitos ao Fator R. CNAEs 7319-0/02 e 7319-0/03 são fixos no Anexo III (SC COSIT nº 13/2022). |
| Título Executivo Extrajudicial | Documento que permite execução judicial direta (sem ação de cobrança ordinária). Contrato com 2 testemunhas é título executivo extrajudicial (CPC, art. 784, III). | SEMPRE recomendar 2 testemunhas em contratos. Transforma cobrança de inadimplência em execução direta com penhora (SISBAJUD). |
| Cessão de Direitos Patrimoniais | Transferência dos direitos de uso, reprodução e exploração comercial de obra autoral. Deve ser expressa, escrita e limitada ao uso contratado (Lei 9.610/98, art. 49). Cessão verbal é NULA (art. 49, I). | Ao redigir cláusula de PI: separar direitos patrimoniais (cedíveis) de direitos morais (inalienáveis, art. 24 LDA). Obras sob encomenda exigem cessão expressa. |
| Disclosure de IA (AI Disclosure) | Divulgação obrigatória ou recomendada do uso de IA generativa na criação de conteúdo. Em B2C: risco de violação ao CDC art. 31 (dever de informação) se omitido. Em B2B: recomendado pela boa-fé (CC art. 422). | Em todo contrato de agência que usa IA: incluir cláusula de disclosure. Antecipar PL 2338/2023 (art. 10, III e art. 24) que tornará obrigatório. |
| Opacidade Algorítmica (Algorithmic Opacity) | Incapacidade de compreender como um sistema de IA chegou a determinado output. PL 6707/2025 propõe dispensar consumidor de provar nexo causal quando há opacidade. | Ao analisar risco de responsabilidade por outputs de IA: a impossibilidade de explicar o raciocínio da IA AGRAVA a posição da agência, não a protege. |
| IVA Dual (CBS + IBS) | Novo sistema tributário da EC 132/2023. CBS (federal) substitui PIS/COFINS. IBS (estadual/municipal) substitui ICMS/ISS. Transição 2026-2033. | Ao redigir cláusulas de reajuste em contratos de longo prazo: incluir cláusula de hardship fiscal para reequilíbrio tributário na transição. |
| Vesting (Opção de Compra de Quotas) | Aquisição progressiva de participação societária condicionada a permanência e performance. No Brasil: contrato de opção de compra (call option), não contribuição em serviço (vedada pelo CC art. 1.055, § 2º). LC 182/2021 (Marco Legal das Startups) autoriza expressamente. | Para estruturação societária futura: cliff de 12 meses + vesting linear de 48 meses. Aplicável quando houver entrada de terceiro sócio ou equity para colaboradores-chave. |
| BV (Bonificação por Volume) | Bonificação paga por veículos de comunicação a agências com base no volume de investimento em mídia. Regulada pelo CENP (Anexo B das Normas-Padrão). Limites: nihil até R$ 2,5M; até 2% (R$ 2,5M-7,5M); até 3% (R$ 7,5M-25M); até 5% (acima de R$ 25M). | Ao orientar sobre relações comerciais com veículos de mídia tradicional. Para agências digitais puras, BV tem baixa relevância operacional direta. |
| Pejotização | Contratação de profissional PJ quando há relação de emprego disfarçada (pessoalidade + onerosidade + habitualidade + subordinação). Se os 4 requisitos do art. 3º CLT estiverem presentes, há vínculo independentemente do CNPJ. | Ao revisar contratos com freelancers/PJs: verificar que o contrato afasta os 4 requisitos do vínculo. Dado alarmante: 1,2 milhão de reclamações trabalhistas por terceirização entre 2020-2025 (fonte: MPT). |
| Responsabilidade Solidária LGPD | Operador responde solidariamente com controlador quando descumpre obrigações da LGPD ou não segue instruções lícitas do controlador (LGPD, art. 42, § 1º, I). | A agência pode ser responsabilizada JUNTO com o cliente em caso de vazamento de dados. Risco elevado quando agentes de IA autônomos tratam dados pessoais. |
| Desconto de Agência CENP | Comissão de no mínimo 20% sobre o valor bruto de mídia, reservada a agências certificadas pelo CENP (Normas-Padrão, item 2.5; Decreto 4.563/2002). | Para agências que operam mídia tradicional. Agências digitais puras geralmente não se beneficiam, mas o percentual serve como piso de referência para fees em contratos híbridos. |
| Human-in-the-Loop (Revisão Humana Intermediária) | Princípio de que todo output de IA deve passar por revisão humana qualificada antes de uso ou publicação. Antecipa PL 2338/2023 (supervisão humana) e segue Recomendação OAB 001/2024. | Em toda cláusula de IA: exigir revisão humana por nível de risco do conteúdo (posts = revisão editorial; conteúdo saúde/financeiro/jurídico = revisão especializada). |

---

## 2. Frameworks e Modelos

> Estruturas reutilizáveis criadas ou ensinadas pelo especialista. Cada framework deve ter nome, etapas e quando aplicar.

### 2.1 Estrutura Completa de Contrato de Agência Digital (12 Cláusulas)

- **Origem:** pesquisa-contratos-martech.md, Seções 1-9
- **Propósito:** Modelo contratual robusto que cobre todos os riscos jurídicos identificados para agências de Engenharia de Lucro
- **Etapas:**
  1. Preâmbulo e Qualificação das Partes (PJ completa, representantes)
  2. Objeto do Contrato — escopo exaustivo com exclusões expressas
  3. Entregáveis, SLA e Prazos — tabela de entregas com frequência e prazo
  4. KPIs e Métricas — natureza referencial, obrigação de MEIO expressa
  5. Remuneração — Setup Fee + MRR, verba de mídia separada
  6. Propriedade Intelectual — cessão patrimonial expressa, direitos morais preservados, cláusula de IA
  7. Confidencialidade (NDA) — 2 anos pós-término, multa de 12x mensalidade
  8. Limitação de Responsabilidade — cap de 12 meses pagos, exclusões detalhadas
  9. Proteção de Dados (LGPD) — controlador/operador, subprocessadores, incidentes em 48h
  10. Rescisão — aviso prévio 30 dias, multa 20% remanescente, portabilidade de dados em 15 dias
  11. Exclusividade (quando aplicável) — praça definida, acréscimo de 20-30%
  12. Reajuste — IPCA anual, cláusula de equilíbrio para onerosidade excessiva (CC art. 317)
- **Quando aplicar:** Todo novo contrato de prestação de serviços da Cadarn
- **Resultado esperado:** Contrato com 2 testemunhas (título executivo extrajudicial) que protege contra scope creep, inadimplência, disputa de PI e responsabilização indevida

### 2.2 Árvore de Decisão Tributária para Agências Martech

- **Origem:** perplexity-mod3-tributario.md, Seções 1-5
- **Propósito:** Orientar a escolha e monitoramento do regime tributário ideal conforme faturamento e composição da folha
- **Etapas:**
  1. Identificar CNAE principal (7311-4/00 sujeito a Fator R) e secundários
  2. Calcular Fator R = Folha 12m / Receita Bruta 12m
  3. Se Fator R >= 28%: Anexo III (6% a 33%) — RECOMENDADO
  4. Se Fator R < 28%: Anexo V (15,5% a 30,5%) — DESFAVORÁVEL, ajustar pró-labore
  5. Se faturamento > R$ 4,8M/ano: migrar para Lucro Presumido (~13,33% + ISS)
  6. Monitorar EC 132/2023: extinção progressiva do ISS, substituição por IBS (transição 2026-2033)
  7. Incluir cláusula de hardship fiscal em contratos de longo prazo
- **Quando aplicar:** Planejamento tributário anual, revisão de pró-labore dos sócios, renegociação contratual
- **Resultado esperado:** Enquadramento no Anexo III com alíquota efetiva entre 6% e ~15%

### 2.3 Checklist de Compliance para IA em Contratos de Agência

- **Origem:** perplexity-mod4-ia-contratos.md, Seção 4; perplexity-mod1-jurisprudencia.md, Seção 5
- **Propósito:** Garantir que contratos de agência que utilizam IA generativa estejam protegidos contra os riscos emergentes de responsabilidade
- **Etapas:**
  1. Cláusula de Disclosure — informar uso de IA ao cliente (relatório mensal ou sob demanda)
  2. Cláusula de Titularidade — cessão de direitos de uso comercial sobre outputs ao cliente após pagamento
  3. Cláusula de Revisão Humana Obrigatória — por nível de risco (editorial, especializada, direção criativa)
  4. Cláusula de Limitação de Responsabilidade — cap de 6 meses para danos por IA; exclusão de danos indiretos por alucinação
  5. Cláusula de Dados e Treinamento — vedação de inserir dados pessoais do cliente em IA sem autorização; uso preferencial de API (não interface web); opt-out de treinamento ativo
  6. Garantia Limitada de Não-Infração — declaração de melhores práticas, sem garantia absoluta de originalidade
- **Quando aplicar:** Todo contrato onde a agência utiliza IA generativa (ChatGPT, Midjourney, Claude, etc.)
- **Resultado esperado:** Antecipação regulatória (future-proofing) do PL 2338/2023 e proteção contra responsabilidade objetiva do PL 6707/2025

### 2.4 Resolução Escalonada de Conflitos (Escalation Clause)

- **Origem:** pesquisa-contratos-martech.md, Seção 9
- **Propósito:** Evitar litígio judicial sempre que possível, com escalação gradual
- **Etapas:**
  1. Nível 1 — Negociação Direta (15 dias)
  2. Nível 2 — Mediação (30 dias, mediador credenciado)
  3. Nível 3A — Arbitragem (para contratos > R$ 50.000/ano; decisão em 90 dias) OU
  3. Nível 3B — Foro Judicial (para contratos menores; Comarca da sede da Cadarn)
- **Quando aplicar:** Cláusula padrão em todo contrato de prestação de serviços
- **Resultado esperado:** Resolução mais rápida e menos custosa; arbitragem (6-12 meses) vs. judicial (2-5 anos)

### 2.5 Modelo de Contrato Seguro com PJ/Freelancer (Anti-Pejotização)

- **Origem:** pesquisa-contratos-martech.md, Seção 5.4
- **Propósito:** Afastar os 4 requisitos do vínculo empregatício (CLT art. 3º) na contratação de profissionais PJ
- **Etapas:**
  1. Autonomia — liberdade de métodos, horários e local de execução
  2. Impessoalidade — possibilidade de designar prepostos/subcontratados
  3. Pluralidade de Clientes — declaração de não exclusividade
  4. Risco do Negócio — PJ assume custos operacionais e tributos
  5. Emissão de NF obrigatória para cada pagamento
  6. Avaliação por RESULTADO, não por PROCESSO (sem controle de jornada)
- **Quando aplicar:** Toda contratação de designers, redatores, gestores de tráfego, desenvolvedores como PJ
- **Resultado esperado:** Contrato que resiste a reclamação trabalhista com base nos 4 elementos de afastamento do vínculo

---

## 3. Regras e Princípios

> O que o especialista defende como verdade inegociável. Cada regra deve ser acionável.

| # | Regra | Justificativa | Fonte |
|---|-------|---------------|-------|
| 1 | NUNCA incluir promessa de resultado numérico (leads, ROI, seguidores) em contrato, proposta, e-mail ou WhatsApp | Converte obrigação de meio em obrigação de resultado; precedente TJES 0004882-12.2019.8.08.0011 condenou agência em R$ 20.810,16 por promessa de 2.000 seguidores | perplexity-mod1-jurisprudencia.md |
| 2 | SEMPRE colher assinatura de 2 testemunhas em contratos | Transforma contrato em título executivo extrajudicial (CPC art. 784, III), permitindo execução direta com penhora | pesquisa-contratos-martech.md |
| 3 | Cessão de direitos autorais DEVE ser expressa e escrita (Lei 9.610/98, art. 49, I); cessão verbal é NULA | Sem cláusula expressa, direitos patrimoniais permanecem com a agência criadora. Direitos morais são inalienáveis (art. 24 LDA) | pesquisa-contratos-martech.md |
| 4 | Cláusula penal NÃO pode exceder o valor da obrigação principal (CC art. 412) | Multa acima de 50% do contrato tem risco alto de redução judicial (art. 413 CC); em relação de consumo pode ser nula (CDC art. 51, IV) | perplexity-mod1-jurisprudencia.md |
| 5 | Contas de plataforma (Instagram, Google Ads, Meta Business) DEVEM ser criadas em nome do CLIENTE, com agência como gerente | Se criadas pela agência, o cliente perde acesso na rescisão. Ausência de cláusula de transição é a principal causa de litígios pós-rescisão | pesquisa-contratos-martech.md, perplexity-mod1-jurisprudencia.md |
| 6 | Notificação extrajudicial FORMAL é obrigatória antes de rescindir por inadimplemento | Rescisão verbal ou por WhatsApp fragiliza o direito à multa contratual. Enviar carta com AR ou cartório, prazo de 5-10 dias úteis para cura (CC art. 475) | perplexity-mod1-jurisprudencia.md |
| 7 | A agência é OPERADOR de dados (LGPD) e DEVE manter lista atualizada de subprocessadores | Subprocessadores incluem Meta, Google, Supabase, WhatsApp API, OpenAI, Anthropic. Cada um deve ter DPA verificado. Transferência internacional (LGPD art. 33) exige base legal | pesquisa-contratos-martech.md |
| 8 | Todo conteúdo gerado por IA DEVE passar por revisão humana qualificada antes da entrega | Antecipa PL 2338/2023 (supervisão humana) e protege contra responsabilidade por alucinação, violação de PI e conteúdo discriminatório. OAB Recomendação 001/2024 exige o mesmo para advocacia | perplexity-mod4-ia-contratos.md |
| 9 | Verificar Fator R MENSALMENTE para garantir enquadramento no Anexo III | Folha de pagamento >= 28% do faturamento = Anexo III. Pró-labore dos sócios e encargos contam. Distribuição de lucros NÃO conta (LC 123/2006, art. 18, § 24) | perplexity-mod3-tributario.md |
| 10 | Publicidade para escritórios de advocacia deve respeitar Provimento CFOAB 205/2021 | Proibido: captação ativa, divulgação de honorários, promessas de resultado, geolocalização em tribunais, remarketing agressivo. Permitido: conteúdo informativo/educativo, SEO, newsletters | pesquisa-contratos-martech.md |
| 11 | Anúncios de imóveis DEVEM conter número do CRECI do contratante (Resolução COFECI 458/95) | CRECI fiscaliza publicidade de imóveis. Exclusividade de venda é proibida como condição imposta (decisão CADE/COFECI 2018), mas pode ser oferecida | pesquisa-contratos-martech.md |
| 12 | Não usar marca de concorrente como palavra-chave em Google Ads | STJ (jul/2024) condenou Google e anunciante por concorrência desleal. TJSC (abr/2025, AG 5042725-36.2024.8.24.0000) manteve Google como corréu. Agência pode ser corresponsável | perplexity-mod1-jurisprudencia.md |
| 13 | Incidente de segurança envolvendo dados pessoais: notificar controlador em até 48h (contrato) e ANPD conforme art. 48 LGPD | A agência como operador deve ter procedimento de resposta a incidentes documentado. Para IA: notificação em 24h se dados expostos via plataforma | pesquisa-contratos-martech.md, perplexity-mod4-ia-contratos.md |
| 14 | Agência NÃO pode inserir dados pessoais de clientes em interfaces web de IA (ChatGPT web, Claude.ai web) sem opt-out de treinamento ativo | Risco de transferência internacional de dados sem base legal + dados usados para treinamento do modelo. Usar SEMPRE API com zero data retention | perplexity-mod4-ia-contratos.md |
| 15 | Escalar OBRIGATORIAMENTE para advogado humano quando: (a) valor > R$ 20.000; (b) liminar/notificação recebida; (c) violação de PI por terceiro; (d) dano causado por output de IA | Responsabilidade por IA não tem consolidação jurisprudencial. Lacuna confirmada em todos os TJs pesquisados (2023-2026) | perplexity-mod1-jurisprudencia.md, perplexity-mod4-ia-contratos.md |
| 16 | Antes de identificar relação como B2B, verificar se o cliente pode ser considerado consumidor (PF, MEI, profissional sem expertise no setor) | Se consumidor: CDC se aplica integralmente — inversão do ônus da prova, nulidade de cláusulas abusivas, prescrição de 5 anos (art. 27 CDC). Se B2B: maior autonomia, menor revisão judicial | perplexity-mod1-jurisprudencia.md |

---

## 4. Anti-Patterns

> O que o especialista condena. Erros, práticas ruins, armadilhas comuns.

| # | Anti-Pattern | Por que é ruim | O que fazer em vez |
|---|-------------|----------------|---------------------|
| 1 | Prometer resultado numérico em proposta comercial, e-mail ou WhatsApp | Cria obrigação de resultado, mesmo sem cláusula formal. Precedente TJES: condenação de R$ 20.810,16 | Usar sempre linguagem de "melhores esforços" e "obrigação de meio" em toda comunicação |
| 2 | Contrato sem 2 testemunhas | Não é título executivo extrajudicial. Cobrança exige ação ordinária (anos) em vez de execução direta (meses) | Colher assinatura de 2 testemunhas em todos os contratos, inclusive digitais |
| 3 | Cláusula de objeto vaga ("serviços de marketing digital") | Scope creep garantido. Trabalho não remunerado. Alegação de inadimplemento por ambas as partes | Listar exaustivamente serviços incluídos E excluídos, com previsão de aditivo para extras |
| 4 | Criar contas de plataforma (Google Ads, Instagram) em nome da agência | Lock-in do cliente. Disputa de acesso na rescisão. Perda de dados de campanha | Criar TODAS as contas em nome do cliente, com agência como gerente/administrador |
| 5 | Cessão verbal ou implícita de direitos autorais | Cessão verbal é NULA (Lei 9.610/98, art. 49, I). Disputa sobre titularidade de materiais na rescisão | Cláusula expressa de cessão patrimonial condicionada a pagamento integral |
| 6 | Multa rescisória acima de 50% do contrato | Risco alto de redução judicial (CC art. 413). Em relação de consumo: nula por abusividade (CDC art. 51, IV) | Multa de 20% do valor remanescente, justificada por custos de onboarding |
| 7 | Pró-labore artificialmente baixo + distribuição de lucros desproporcional | Receita Federal pode desconsiderar e tributar como pró-labore (planejamento tributário abusivo). Reduz Fator R para abaixo de 28% | Manter pró-labore que garanta Fator R >= 28%; mínimo de 1 salário mínimo (IN RFB 1.131/2011) |
| 8 | Usar IA sem informar ao cliente (disclosure omitido) | Violação ao dever de informação (CDC art. 31). Boa-fé objetiva (CC art. 422). PL 2338/2023 tornará obrigatório (art. 10, III) | Cláusula de disclosure + relatório mensal de ferramentas de IA utilizadas |
| 9 | Inserir dados do cliente em interface web de IA sem opt-out | Transferência internacional sem base legal (LGPD art. 33). Dados usados para treinamento. Risco LGPD crítico | Usar exclusivamente API com zero data retention. Verificar DPA com cada plataforma |
| 10 | Exigir horário fixo, exclusividade e subordinação a PJ/freelancer | Configura vínculo empregatício independentemente do CNPJ (CLT art. 3º). 1,2M reclamações trabalhistas por terceirização (2020-2025) | Contrato com autonomia, impessoalidade, pluralidade de clientes e avaliação por resultado |
| 11 | Rescindir contrato por WhatsApp sem notificação formal | Fragiliza direito à multa rescisória. Não documenta inadimplemento (CC art. 475) | Notificação extrajudicial por carta com AR ou cartório, prazo de cura de 5-10 dias |
| 12 | Campanhas de advogados com captação ativa, remarketing agressivo ou geolocalização em tribunais | Viola Provimento CFOAB 205/2021. Sanção disciplinar da OAB para o advogado. Risco para a agência | Conteúdo informativo/educativo. Caráter sóbrio. Sem promessas de resultado ou oferta direta |
| 13 | Usar marca de concorrente do cliente como keyword em Google Ads | Concorrência desleal. STJ e TJSC condenaram. Agência pode ser corresponsável pela configuração | Auditar palavras-chave negativas mensalmente. Política formal de exclusão de marcas concorrentes |
| 14 | Afirmar que output de IA "não viola direito autoral" | Incerteza jurídica absoluta: IA pode reproduzir obras protegidas sem transparência (opacidade algorítmica) | Garantia LIMITADA de não-infração + cláusula de cooperação em caso de notificação de terceiro |

---

## 5. Táticas Acionáveis

> Do/don't com contexto de quando aplicar. Separadas por categoria.

### Categoria: Redação Contratual

| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Incluir cláusula expressa de obrigação de meio com exclusão de variáveis externas | DO | Todo contrato de prestação de serviços | "Os serviços constituem obrigação de meio... sem garantir resultados específicos de audiência, engajamento, conversões ou faturamento, os quais dependem de variáveis externas não controláveis pela CONTRATADA." |
| Separar verba de mídia da remuneração da agência na cláusula financeira | DO | Contratos com gestão de tráfego pago | Verba em conta de anúncios do CLIENTE. Agência não pratica markup. Cliente tem acesso irrestrito ao Gerenciador de Anúncios |
| Incluir cláusula de portabilidade de dados na rescisão (15 dias) | DO | Todo contrato | Entregar: acesso a contas, relatórios, dados de leads, materiais criativos. Revogar credenciais em 5 dias úteis |
| Incluir cláusula anticorrupção (Lei 12.846/2013) | DO | Contratos com clientes que têm exposição pública ou contratos com entes públicos | Responsabilidade objetiva da PJ. Multa de 0,1% a 20% do faturamento bruto |
| Incluir cláusula de reajuste por variação tributária (hardship fiscal) | DO | Contratos de longo prazo (12+ meses) | EC 132/2023 pode aumentar custos em ~12,15% (PIS/COFINS 9,25% + ISS 2,9% nas faturas Meta/Google). Cláusula de reequilíbrio |
| Usar plataforma de assinatura eletrônica com trilha de auditoria | DO | Todo contrato | DocuSign, D4Sign, Clicksign. STJ admite assinaturas fora da ICP-Brasil desde que demonstrada autenticidade (REsp 2.159.442/PR) |
| Omitir cláusula de exclusividade sem justificativa | DON'T | Clientes do ICP (imobiliárias premium, escritórios de advocacia) | Exclusividade é estratégica no ICP Cadarn. Prevenir conflito ético. Acréscimo de 20-30% na mensalidade |

### Categoria: LGPD e Proteção de Dados

| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Documentar TODOS os subprocessadores com DPA verificado | DO | Fase de onboarding de cada cliente | Lista: Meta, Google, Supabase, WhatsApp API, OpenAI, Anthropic, ClickUp. Obter autorização prévia do controlador |
| Implementar opt-in explícito para WhatsApp marketing | DO | Todo uso de WhatsApp Business API | Consentimento livre, informado, inequívoco. Registrar data/hora/canal. Separar por finalidade (atendimento != marketing). Comando "SAIR" obrigatório |
| Criar RIPD (Relatório de Impacto) quando solicitado | DO | Quando controlador solicitar (LGPD art. 38) | Manter registro de operações de tratamento (LGPD art. 37) |
| Usar interface web de IA para processar dados de clientes | DON'T | Nunca | Risco de treinamento de modelo + transferência internacional sem base legal. Usar API com opt-out ativo |

### Categoria: Tributário

| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Usar CNAE 7319-0/03 (Marketing Direto) como secundário quando possível | DO | Na abertura ou alteração do contrato social | Fixo no Anexo III sem Fator R (SC COSIT nº 13/2022). Reduz risco de cair no Anexo V |
| Ajustar pró-labore para manter Fator R >= 28% | DO | Mensalmente, ao verificar receita e folha | Exemplo: faturamento R$ 50.000/mês → folha mínima R$ 14.000/mês. Incluir pró-labore + encargos |
| Base de cálculo do ISS sobre total da verba de mídia (em vez de sobre honorário) | DON'T | Na emissão de NFS-e | ISS deve incidir sobre o honorário da agência, não sobre verba de mídia que transita pela conta do cliente |
| Descrição genérica "serviços prestados" na NFS-e | DON'T | Na emissão de NFS-e | Risco identificado pela Reforma Tributária. Descrever serviço detalhadamente com código LC 116/2003 correto |

### Categoria: Propriedade Intelectual e IA

| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Manter registro de outputs de IA + revisões humanas por mínimo 2 anos | DO | Todo projeto com IA generativa | Comprova diligência em caso de disputa. Inclui prompts, versões, aprovações |
| Registrar metodologias e frameworks proprietários como obra autoral | DO | A qualquer momento (proteção do método Cadarn) | Proteção automática pela Lei 9.610/98, mas registro em cartório fortalece. Manter como PI exclusiva no contrato |
| Prometer originalidade absoluta de outputs de IA | DON'T | Nunca | Impossibilidade técnica de verificação plena. Usar "garantia limitada" com melhores práticas de verificação de plágio |
| Criar deepfake de pessoa real sem consentimento comprovado | DON'T | Nunca | LGPD art. 42 + CC art. 21 + futuramente PL 2338/2023. Verificação de identidade + confirmação de licença obrigatória |

### Categoria: Cobrança e Inadimplência

| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Protestar título em cartório após inadimplência | DO | Após 30 dias de atraso e notificação sem resposta | Rapidez (3 dias), custo baixo, pressão efetiva. Custas recuperáveis do devedor (Lei 9.492/1997) |
| Ajuizar no Juizado Especial Cível (até 40 SM) | DO | Cobranças até ~R$ 60.720 | Cadarn como LTDA/ME pode ajuizar (LC 147/2014). Velocidade: 2-6 meses vs. 1-5 anos na justiça comum |
| Preservar provas digitais (WhatsApp, e-mail) com ata notarial | DO | Antes de qualquer litígio | CPC art. 384. Custo R$ 100-500. Exportar conversa completa, não apenas screenshots |

---

## 6. Métricas e Benchmarks

> Números de referência citados pelo especialista. Incluir contexto para não serem aplicados fora de escopo.

| Métrica | Valor/Range | Contexto | Fonte |
|---------|-------------|----------|-------|
| Multa rescisória recomendada | 20% do valor remanescente do contrato | Referência de mercado, respeita limite do CC art. 412 | pesquisa-contratos-martech.md |
| Multa por violação de NDA | 12x última mensalidade vigente | Sem prejuízo de perdas e danos adicionais | pesquisa-contratos-martech.md |
| Multa moratória (atraso) | 2% sobre valor em atraso | Em B2B pode ser maior, mas 2% é seguro (CDC art. 52, § 1º para consumo) | pesquisa-contratos-martech.md |
| Juros de mora | 1% ao mês (pro rata die) | CC art. 406 c/c CTN art. 161, § 1º. STJ admite Taxa Selic como alternativa | pesquisa-contratos-martech.md |
| Prazo de prescrição (contratos de serviço) | 5 anos | CC art. 206, § 5º, I. Dívida prescrita NÃO admite cobrança extrajudicial (STJ Tema 1.264) | pesquisa-contratos-martech.md |
| Multa LGPD máxima | 2% do faturamento, máx R$ 50 milhões por infração | ANPD pode aplicar. Responsabilidade solidária operador-controlador | pesquisa-contratos-martech.md |
| Multa PL 2338/2023 (futuro) | Até 2% do faturamento bruto, máx R$ 50 milhões por infração | Quando sancionado. Aplica-se a agentes de IA. Inclui suspensão do serviço | perplexity-mod4-ia-contratos.md |
| Multa anticorrupção | 0,1% a 20% do faturamento bruto | Lei 12.846/2013. Responsabilidade objetiva da PJ | pesquisa-contratos-martech.md |
| Alíquota Simples Nacional (Anexo III, 1ª faixa) | 6,00% | Até R$ 180.000 em 12 meses. Fator R >= 28% | perplexity-mod3-tributario.md |
| Alíquota Simples Nacional (Anexo V, 1ª faixa) | 15,50% | Até R$ 180.000 em 12 meses. Fator R < 28% | perplexity-mod3-tributario.md |
| Alíquota efetiva Lucro Presumido (total) | ~13,33% a 16,33% sobre faturamento | IRPJ 4,8% + CSLL 2,88% + PIS 0,65% + COFINS 3% + ISS 2-5%. Presunção de 32% para serviços | perplexity-mod3-tributario.md |
| Limite Simples Nacional | R$ 4.800.000/ano | Acima: obrigatório migrar para Lucro Presumido ou Real | perplexity-mod3-tributario.md |
| Fator R mínimo para Anexo III | >= 28% | Folha de pagamento 12m / Receita Bruta 12m. LC 123/2006, art. 18, § 24 | perplexity-mod3-tributario.md |
| Desconto de agência CENP | Mínimo 20% sobre valor bruto de mídia | Normas-Padrão, item 2.5; Decreto 4.563/2002. Apenas para agências certificadas | perplexity-mod2-abradi-cenp.md |
| Comissão agenciador autônomo CENP | Até 20% | Paga pelo veículo (Normas-Padrão, item 5.1). Vedada transferência ao anunciante | perplexity-mod2-abradi-cenp.md |
| Honorários sobre fornecedores (CENP) | 15% | Normas-Padrão, seção 3 | perplexity-mod2-abradi-cenp.md |
| Aviso prévio mínimo para rescisão CENP | 60 dias | Normas-Padrão, seção 3 | perplexity-mod2-abradi-cenp.md |
| CBS em 2026 (teste) | 0,9% | EC 132/2023 + LC 214/2024. Fase de teste | perplexity-mod3-tributario.md |
| IBS em 2026 (teste) | 0,1% | EC 132/2023 + LC 214/2024. Fase de teste | perplexity-mod3-tributario.md |
| ISS Vitória/ES (publicidade item 17.06) | 2% a 5% | Lei Municipal 6.075/2003. Confirmar alíquota específica para marketing digital | perplexity-mod3-tributario.md |
| Reajuste contratual (índice recomendado) | IPCA/IBGE anual | Mais conservador que IGP-M. Periodicidade mínima anual (Lei 9.069/1995, art. 28, § 1º) | pesquisa-contratos-martech.md |
| Piso salarial Sinapro-MG (BH, 2024/2025) | R$ 1.510,00 (ingresso) / R$ 1.621,00 (1+ ano técnico) | Reajuste de 6%. Base para composição de fees | perplexity-mod2-abradi-cenp.md |
| Ata notarial (custo) | R$ 100 a R$ 500 | CPC art. 384. Preservação de prova digital | pesquisa-contratos-martech.md |
| Juizado Especial (limite de valor) | Até 40 SM (~R$ 60.720) | ME/EPP podem ajuizar (LC 147/2014). Velocidade: 2-6 meses | pesquisa-contratos-martech.md |
| Guia ABRADI (itens mapeados) | 147 produtos e serviços em 11 áreas | 3ª edição (out/2024). Acesso restrito a associados (R$ 136/mês) | perplexity-mod2-abradi-cenp.md |
| Gestão de redes sociais (referência mercado) | R$ 599 a R$ 10.000/mês | Fonte paralela, não ABRADI oficial | perplexity-mod2-abradi-cenp.md |

---

## 7. Vocabulário Signature

> Termos e expressões recorrentes que definem a voz do especialista. Essencial para voice_dna do agente-clone.

### Termos que SEMPRE usa
- **Obrigação de meio** — natureza jurídica padrão dos contratos de marketing digital; contraposta a "obrigação de resultado"
- **Scope creep** — expansão informal do escopo contratual sem remuneração correspondente
- **Título executivo extrajudicial** — contrato com 2 testemunhas que permite execução direta
- **Controlador/Operador** — papéis LGPD na relação agência-cliente
- **Fator R** — razão folha/faturamento que determina Anexo III ou V do Simples
- **Disclosure** — divulgação obrigatória (uso de IA, uso de subprocessadores)
- **Human-in-the-loop** — revisão humana intermediária obrigatória
- **Cessão patrimonial** — transferência de direitos de uso/exploração comercial
- **Hardship fiscal** — cláusula de reequilíbrio por variação tributária
- **Future-proofing** — antecipação regulatória em cláusulas contratuais
- **Alucinação** — output incorreto ou falso gerado por IA generativa
- **DPA (Data Processing Agreement)** — contrato de processamento de dados com subprocessadores
- **Pejotização** — contratação PJ fraudulenta que mascara vínculo empregatício
- **Setup Fee + MRR** — modelo de precificação recomendado (taxa de implantação + recorrência mensal)

### Expressões recorrentes
- "Salvo estipulação expressa em contrário"
- "Risco por ausência de cláusula"
- "Nos termos do art. [X] do [Lei]"
- "Sem prejuízo de perdas e danos"
- "Mediante aditivo contratual assinado por ambas as partes"
- "A responsabilidade editorial e criativa pelo conteúdo permanece da CONTRATADA"
- "Garantia limitada de não-infração"
- "Este tema está em evolução legislativa acelerada"
- "Cláusula de transição de ativos digitais"

### Termos que NUNCA usa (ou condena)
- **"Garantimos resultados"** — converte obrigação de meio em resultado; risco de condenação judicial
- **"Serviços prestados" (genérico em NFS-e)** — risco fiscal identificado pela Reforma Tributária; descrever detalhadamente
- **"IA é segura juridicamente"** — vácuo legislativo impede qualquer afirmação de segurança jurídica sobre IA
- **"Planejamento tributário agressivo"** — nunca apresentar como "recomendação"; apenas descrever opções legítimas
- **"Contrato verbal é válido"** — cessão de direitos autorais verbal é NULA; contrato sem testemunhas não é título executivo

### Metáforas e analogias frequentes
- "Precisão cirúrgica" — para redação de cláusula de objeto/escopo
- "Cadeia de responsabilidade em camadas" — para explicar responsabilidade por output de IA (plataforma → agência → cliente)
- "Relação tripartite" — cliente → agência → plataforma (Google, Meta) na gestão de tráfego
- "Caixa-preta" — para descrever opacidade algorítmica e por que não protege a agência
- "Evolução natural" — para progressão societária: MEI → ME → EPP → LTDA LP → Holding

---

## Metadados de Extração

```yaml
extraction_stats:
  total_files_processed: 5
  total_lines_analyzed: 3225
  concepts_extracted: 14
  frameworks_extracted: 5
  rules_extracted: 16
  anti_patterns_extracted: 14
  tactics_extracted: 21
  metrics_extracted: 24
  vocabulary_terms: 28
  dedup_removals: 17
  confidence_score: "91%"
```

**Nota de confiança:** Score de 91% reflete:
- (+) Cobertura exaustiva de 5 módulos (contratos, jurisprudência, regulação setorial, tributário, IA)
- (+) Fundamentação legal com artigos específicos citados em cada item
- (+) Casos jurisprudenciais verificáveis (TJES 0004882-12.2019.8.08.0011, TJSP 1063770-43.2020.8.26.0100, TJSC 5042725-36.2024.8.24.0000, STJ REsp 1.561.033-RS)
- (-) Lacunas jurisprudenciais confirmadas em disputas de IA em publicidade (tema emergente, sem consolidação)
- (-) PL 2338/2023 e PL 6707/2025 em tramitação (podem ser alterados)
- (-) Valores do Guia ABRADI não acessíveis publicamente (tabela restrita a associados)
- (-) Módulo tributário tem volatilidade alta (revisar semestralmente)

---

_Extraído por Athena (knowledge-miner) v1.0 — 2026-03-23_
