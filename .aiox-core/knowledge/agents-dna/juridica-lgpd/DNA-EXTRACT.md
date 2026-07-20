# DNA-EXTRACT: Especialista LGPD e Direito Digital — Cadarn Martech

> **Dominio:** LGPD, Marco Civil da Internet, Direito Digital aplicados a agencias Martech
> **Fonte:** `.aiox-core/knowledge/agents-dna/juridica-lgpd/`
> **Modulos processados:** 2 arquivos (pesquisa-lgpd-martech.md + perplexity-lgpd-compliance.md, 4 modulos internos)
> **Extraido em:** 2026-03-23
> **Minerador:** Athena (knowledge-miner)

---

## 1. Conceitos-Chave

> Definicoes e termos fundamentais do dominio juridico. Cada entrada e um conceito que o agente-clone DEVE conhecer.

| Conceito | Definicao | Contexto de uso |
|----------|-----------|-----------------|
| **Dado pessoal** | Informacao relacionada a pessoa natural identificada ou identificavel (Art. 5, I LGPD). Inclui identificadores online como cookies e IPs | Toda operacao de marketing que colete nome, email, telefone, comportamento de navegacao |
| **Dado pessoal sensivel** | Dados sobre origem racial/etnica, conviccao religiosa, opiniao politica, filiacao sindical, saude, vida sexual, dados geneticos ou biometricos (Art. 5, II LGPD) | CRMs com campos de saude (clinicas de estetica), estado civil (pode revelar orientacao sexual), biometria |
| **Controlador** | Pessoa natural ou juridica a quem competem as decisoes referentes ao tratamento de dados pessoais. Na relacao agencia-cliente, o cliente e tipicamente o controlador | Definicao de papeis contratuais, atribuicao de responsabilidade |
| **Operador** | Pessoa natural ou juridica que realiza o tratamento de dados em nome do controlador. A agencia Martech e tipicamente operadora | Contratos agencia-cliente, limitacao de escopo de tratamento |
| **Co-controlador** | Quando a agencia participa da definicao das finalidades do tratamento (nao apenas executa), torna-se co-controladora com responsabilidade solidaria (Art. 42 LGPD) | Agencia que usa dados dos clientes para case studies ou otimizacao propria |
| **Encarregado/DPO** | Pessoa indicada pelo controlador e operador para atuar como canal de comunicacao entre o controlador, os titulares dos dados e a ANPD (Art. 41 LGPD, Resolucao CD/ANPD n. 18/2024) | Obrigatorio para todas as PJs; pode ser PF ou PJ; interno ou terceirizado (DPO as a Service) |
| **ROPA/ROT** | Registro de Operacoes de Tratamento de Dados — documento formal e continuo que registra cada operacao de tratamento (Art. 37 LGPD). Record of Processing Activities | Obrigatorio para controladores e operadores; documento vivo atualizado a cada nova operacao |
| **Data Mapping** | Diagnostico/raio-X dos fluxos de dados pessoais: quais dados, de onde vem, onde armazena, quem acessa, com quem compartilha, retencao e eliminacao | Fase inicial de adequacao; precede o ROPA |
| **RIPD/DPIA** | Relatorio de Impacto a Protecao de Dados Pessoais (Data Protection Impact Assessment). Obrigatorio quando solicitado pela ANPD (Art. 38) e recomendado para tratamento de alto risco | Campanhas em larga escala, perfilamento automatizado, dados sensiveis, IA/ML, dados de criancas |
| **Consentimento** | Manifestacao livre, informada, inequivoca, para finalidade determinada, granular, revogavel e documentavel (Art. 7, I + Art. 8 LGPD) | Formularios de captacao, newsletters, cookies nao essenciais, WhatsApp marketing, compartilhamento com parceiros |
| **Legitimo interesse** | Base legal flexivel que exige teste de proporcionalidade (Art. 7, IX + Art. 10 LGPD). NAO se aplica a dados sensiveis | Marketing direto para clientes existentes, prospeccao B2B, remarketing comportamental, analytics |
| **LIA** | Legitimate Interest Assessment — teste de proporcionalidade em 3-4 fases para validar uso do legitimo interesse. Framework principal: Data Privacy Brasil/Bruno Bioni | Toda operacao de marketing baseada em legitimo interesse deve ter LIA documentado |
| **SCCs brasileiras** | Clausulas-Padrao Contratuais para transferencia internacional de dados (Resolucao CD/ANPD n. 19/2024). Obrigatorias desde 23/08/2025 para paises sem nivel de adequacao | Contratos com Meta, Google, HubSpot, Mailchimp e qualquer ferramenta com servidores fora do Brasil |
| **Transferencia internacional** | Envio de dados pessoais para pais estrangeiro ou organismo internacional (Arts. 33-36 LGPD). EUA NAO reconhecido como pais com nivel adequado | Uso de qualquer plataforma SaaS com servidores nos EUA (Meta, Google, etc.) |
| **Responsabilidade solidaria** | Controlador e operador respondem solidariamente por danos causados por tratamento ilicito (Art. 42 LGPD). Ambos podem ser acionados judicialmente | Incidentes de seguranca, vazamentos, tratamento sem base legal |
| **Opt-in** | Manifestacao afirmativa e previa do titular autorizando tratamento especifico. Para WhatsApp, exige dupla conformidade: LGPD + Politicas da Meta | Formularios, cookie banners, WhatsApp marketing |
| **Opt-out** | Mecanismo para o titular revogar consentimento ou se opor ao tratamento. Deve ser facil, gratuito e imediato | Obrigatorio em toda comunicacao de marketing; salvaguarda minima para legitimo interesse |
| **Dosimetria** | Criterios de calculo de sancoes da ANPD (Resolucao CD/ANPD n. 4/2023): gravidade, boa-fe, reincidencia, cooperacao, volume de dados, dados sensiveis | Avaliacao de risco em auditorias de compliance |
| **Cookie de marketing** | Cookie que coleta dados para fins publicitarios (Meta Pixel, Google Ads tag, remarketing). Base legal obrigatoria: consentimento | Toda landing page, site ou campanha digital com pixels de rastreamento |
| **Custom Audiences** | Publicos personalizados criados por upload de listas de clientes (email, telefone) em plataformas de ads. Constitui transferencia internacional | Meta Ads, Google Ads; requer base legal para compartilhamento e transferencia |
| **Legitimas expectativas** | O titular deve razoavelmente esperar o tipo de tratamento realizado (Art. 10, II LGPD). Conceito-chave no teste de balanceamento | Lead de site imobiliario pode esperar ofertas de imoveis, mas NAO ofertas de seguro de vida |

---

## 2. Frameworks e Modelos

> Estruturas reutilizaveis para compliance e operacao juridica. Cada framework tem etapas e contexto de aplicacao.

### 2.1 Teste de Proporcionalidade do Legitimo Interesse (LIA) — Bruno Bioni / Data Privacy Brasil

- **Origem:** Data Privacy Brasil, "O Legitimo Interesse na LGPD" (2021); Bruno Bioni (Art. 10 LGPD); Guia Orientativo ANPD sobre Legitimo Interesse (2024)
- **Proposito:** Validar se o legitimo interesse e base legal adequada para uma operacao de tratamento especifica
- **Etapas:**
  1. **Fase 1 — Legitimidade do Interesse (Purpose Test):** Verificar se o interesse do controlador e licito, especifico, genuino e concreto. Nao pode ser abstrato ou hipotetico. Deve estar ancorado em situacao concreta (Art. 10, caput)
  2. **Fase 2 — Necessidade (Necessity Test / Minimizacao):** O tratamento deve ser limitado ao minimo necessario. Avaliar se e possivel atingir o mesmo resultado com menos dados. Escopo "pertinente, proporcional e nao excessivo"
  3. **Fase 3 — Balanceamento (Balancing Test):** Ponderar interesse do controlador contra direitos e liberdades fundamentais do titular. Considerar legitimas expectativas, impacto sobre o titular, vulnerabilidade do titular
  4. **Fase 4 — Salvaguardas:** Implementar medidas de mitigacao: transparencia (aviso de privacidade claro), mecanismo de opt-out facil e gratuito, documentar todo o processo (accountability)
- **Quando aplicar:** Toda operacao de marketing baseada em legitimo interesse (remarketing, prospeccao, analytics, email marketing para base propria, lead scoring)
- **Resultado esperado:** LIA documentado como parte do ROT do cliente; revisao anual ou quando a finalidade mudar. Se falhar em qualquer fase, usar consentimento
- **Fonte:** pesquisa-lgpd-martech.md (secao 1.4, 6.4); perplexity-lgpd-compliance.md (Modulo 3)

### 2.2 Checklist de Compliance LGPD para Agencias Martech

- **Origem:** pesquisa-lgpd-martech.md (secao 7.1)
- **Proposito:** Verificacao completa de conformidade LGPD para operacoes de agencia de marketing digital
- **Etapas/Categorias:**
  1. **Governanca e Organizacao:** DPO nomeado, Politica de Privacidade, Politica de Cookies, Politica de Seguranca, canal de titulares, treinamento anual
  2. **Data Mapping e ROPA:** Mapeamento de dados, ROPA documentado com bases legais, revisao semestral
  3. **Contratos e Relacoes Comerciais:** Clausulas LGPD com clientes e fornecedores, SCCs para transferencia internacional, registro de subprocessadores
  4. **Captacao de Leads e Marketing:** Consentimento granular, timestamp/IP/texto, double opt-in, opt-in WhatsApp, cookie banner, pixels apos consentimento
  5. **Seguranca Tecnica:** HTTPS/TLS, criptografia em repouso, controle de acesso, 2FA, logs, backups, plano de incidentes
  6. **Direitos dos Titulares (Art. 18):** Canal funcional, processo documentado para 9 direitos, prazo de 15 dias, registro de requisicoes
  7. **Incidentes de Seguranca:** Plano de resposta, equipe definida, modelos de comunicacao ANPD/titulares, teste anual
- **Quando aplicar:** Onboarding de novo cliente, auditoria periodica (semestral recomendado), adequacao inicial
- **Resultado esperado:** Diagnostico completo de gaps de compliance com plano de acao priorizado
- **Fonte:** pesquisa-lgpd-martech.md (secao 7.1)

### 2.3 Checklist LGPD Especifico para Imobiliarias

- **Origem:** pesquisa-lgpd-martech.md (secao 8.5)
- **Proposito:** Verificacao de compliance LGPD para clientes do setor imobiliario (ICP da Cadarn)
- **Etapas:**
  1. DPO nomeado e publicado
  2. Politica de Privacidade no site e stand de vendas
  3. Consentimento nos formularios (site + presencial)
  4. Treinamento de corretores sobre LGPD e sigilo
  5. Contrato com agencia e portais com clausulas LGPD
  6. Consentimento do proprietario para fotos/anuncios
  7. Politica de retencao para clientes que nao fecharam
  8. Canal para titulares (Art. 18)
  9. Seguranca de documentos fisicos e digitais
  10. Eliminacao segura apos fim da finalidade
- **Quando aplicar:** Todo cliente imobiliario no onboarding
- **Resultado esperado:** Imobiliaria em conformidade basica com LGPD
- **Fonte:** pesquisa-lgpd-martech.md (secao 8.5)

### 2.4 Protocolo de Resposta a Incidentes de Seguranca

- **Origem:** pesquisa-lgpd-martech.md (secao 7.4); perplexity-lgpd-compliance.md (Modulo 2, Resolucao 15/2024)
- **Proposito:** Responder a incidentes de seguranca envolvendo dados pessoais dentro dos prazos legais
- **Etapas:**
  1. **Fase 1 — Deteccao e Triagem (0-4h):** Detectar, conter ameaca, avaliar escopo, notificar equipe
  2. **Fase 2 — Analise e Comunicacao (4-72h):** Investigar causa raiz, determinar risco a titulares, comunicar cliente/controlador, comunicar ANPD (3 dias uteis), comunicar titulares (3 dias uteis)
  3. **Fase 3 — Remediacao (72h+):** Corrigir vulnerabilidade, medidas preventivas, documentar, complementar comunicacao ANPD, atualizar RIPD
- **Quando aplicar:** Vazamento de dados, acesso nao autorizado a CRM, perda de base de dados, qualquer incidente confirmado envolvendo dados pessoais
- **Resultado esperado:** Incidente contido, ANPD e titulares notificados no prazo, registro mantido por minimo 5 anos
- **Fonte:** pesquisa-lgpd-martech.md (secao 7.4); perplexity-lgpd-compliance.md (Resolucao 15/2024)

### 2.5 Framework de Cookie Banner em Camadas (ANPD)

- **Origem:** pesquisa-lgpd-martech.md (secao 1.6); perplexity-lgpd-compliance.md (Modulo 2, Guia de Cookies)
- **Proposito:** Implementar consentimento valido para cookies conforme orientacoes da ANPD
- **Etapas:**
  1. **Primeira camada (banner):** Informacao resumida, botao "Aceitar todos", botao "Gerenciar cookies" ou "Rejeitar nao essenciais", link para Politica de Cookies
  2. **Segunda camada (painel de gerenciamento):** Descricao detalhada por categoria, finalidades especificas, periodos de retencao, opcao granular aceitar/rejeitar por categoria, nomes e funcoes dos cookies
  3. **Regra critica:** Cookies nao essenciais NAO podem ser setados antes do consentimento. Pixel de remarketing ativado sem consentimento = violacao direta
- **Quando aplicar:** Todo site de cliente, toda landing page, toda campanha digital
- **Resultado esperado:** Cookie banner conforme Guia ANPD com consentimento granular, opt-out e registro de consentimento
- **Fonte:** pesquisa-lgpd-martech.md (secao 1.6); perplexity-lgpd-compliance.md (Modulo 2)

### 2.6 Modelo de Clausulas Contratuais Agencia-Cliente (14 clausulas)

- **Origem:** pesquisa-lgpd-martech.md (secoes 1.8 e 7.2)
- **Proposito:** Estrutura contratual minima para relacao controlador-operador entre cliente e agencia
- **Etapas (clausulas):**
  1. Definicao de papeis (controlador/operador)
  2. Obrigacoes do operador (9 itens: instrucoes, seguranca, confidencialidade, ROPA, etc.)
  3. Suboperadores (lista, autorizacao previa, responsabilidade)
  4. Transferencia internacional (paises, SCCs, mecanismos)
  5. Incidentes de seguranca (prazo, conteudo, cooperacao)
  6. Retencao e eliminacao (prazos, certificado, excecoes legais)
  7. Auditoria (direito do controlador, frequencia, custos)
  8. Responsabilidade (solidariedade, indemnity cruzado, limitacao, seguro)
- **Quando aplicar:** Todo novo contrato com cliente, renovacao de contratos existentes
- **Resultado esperado:** Contrato com todas as clausulas LGPD obrigatorias
- **Fonte:** pesquisa-lgpd-martech.md (secoes 1.8 e 7.2)

### 2.7 Modelo Regulatorio Tripartite de Bioni

- **Origem:** pesquisa-lgpd-martech.md (secao 6.2)
- **Proposito:** Compreender as tres camadas de regulacao de dados pessoais
- **Etapas:**
  1. **Autodeterminacao informativa** (consentimento) — Poder do individuo
  2. **Regulacao estatal** (LGPD, ANPD) — Poder do Estado
  3. **Regulacao tecnologica** (privacy by design) — Codigo como lei
- **Quando aplicar:** Ao projetar sistemas e processos de tratamento de dados
- **Resultado esperado:** Abordagem holistica que combina consentimento, conformidade legal e medidas tecnicas
- **Fonte:** pesquisa-lgpd-martech.md (secao 6.2)

---

## 3. Regras e Principios

> Regras inegociaveis do dominio juridico. Cada regra e acionavel e vinculada a fonte legal.

| # | Regra | Justificativa | Fonte |
|---|-------|---------------|-------|
| 1 | Toda operacao de tratamento de dados DEVE ter base legal documentada ANTES de iniciar (Art. 7 LGPD) | Ausencia de documentacao = ausencia de base legal para a ANPD. Precedente: caso Telekall (multa por falta de base legal) | pesquisa-lgpd-martech.md (1.2); perplexity-lgpd-compliance.md (Caso 1) |
| 2 | Consentimento deve ser livre, informado, inequivoco, para finalidade determinada, granular e revogavel (Art. 8 LGPD) | Checkbox pre-marcado = consentimento invalido. Termos genericos "aceito tudo" = consentimento nulo. Condicionar acesso a conteudo vicia a liberdade | pesquisa-lgpd-martech.md (1.3.1) |
| 3 | Legitimo interesse NAO se aplica a dados sensiveis (Art. 11 tem lista taxativa propria) | Dados sensiveis exigem consentimento especifico e destacado ou uma das hipoteses do Art. 11, II | pesquisa-lgpd-martech.md (1.3.2, 1.10) |
| 4 | Cookies de marketing/remarketing exigem consentimento previo e NAO podem ser ativados antes do opt-in | Pixel de remarketing ativado sem consentimento = violacao direta ao Guia de Cookies ANPD | pesquisa-lgpd-martech.md (1.6); perplexity-lgpd-compliance.md (Modulo 2) |
| 5 | Todo controlador deve designar Encarregado/DPO com canal de comunicacao publico (Art. 41 + Resolucao 18/2024) | ANPD fiscaliza proativamente: 20 empresas notificadas em dez/2024 por falta de DPO | pesquisa-lgpd-martech.md (4.6); perplexity-lgpd-compliance.md (Caso 4) |
| 6 | Controlador e operador devem manter ROPA de todas as operacoes de tratamento (Art. 37 LGPD) | Ausencia de ROT e infracao autonoma. Precedente: empresa nao nomeada, advertencia em fev/2024 | pesquisa-lgpd-martech.md (1.9); perplexity-lgpd-compliance.md (Caso 2) |
| 7 | WhatsApp marketing exige dupla conformidade: LGPD (consentimento Art. 7, I) + Politicas da Meta (opt-in explicito fora do WhatsApp) | As duas camadas sao cumulativas, nao alternativas. Opt-in generico "aceito termos" nao e suficiente | pesquisa-lgpd-martech.md (2.2); perplexity-lgpd-compliance.md (Modulo 4) |
| 8 | Transferencia internacional para EUA exige SCCs brasileiras (obrigatorias desde 08/2025) ou consentimento especifico (Resolucao 19/2024) | EUA NAO reconhecido como pais com nivel adequado. Toda ferramenta SaaS com servidor nos EUA configura transferencia internacional | pesquisa-lgpd-martech.md (3.4); perplexity-lgpd-compliance.md (Modulo 2) |
| 9 | Incidentes de seguranca devem ser comunicados a ANPD e titulares em 3 dias uteis (Resolucao 15/2024) | Atraso na comunicacao = infracao autonoma com multa separada. Agentes de pequeno porte: 6 dias uteis | pesquisa-lgpd-martech.md (7.4); perplexity-lgpd-compliance.md (Caso 2) |
| 10 | Decisoes automatizadas que afetem titulares (lead scoring, credit scoring) devem ter mecanismo de revisao humana a pedido (Art. 20 LGPD) | Ausencia de revisao humana = violacao independente da base legal utilizada | perplexity-lgpd-compliance.md (Modulo 3); pesquisa-lgpd-martech.md (7.3) |
| 11 | Descumprimento de ordem da ANPD e infracao autonoma com multa separada da infracao principal | Nao cooperar com a ANPD durante investigacao gera sancao adicional. Precedente: Telekall (Art. 5, Resolucao 1/2021) | pesquisa-lgpd-martech.md (4.2); perplexity-lgpd-compliance.md (Caso 1) |
| 12 | Comunicacao ou compartilhamento de dados sensiveis de saude com objetivo de vantagem economica e PROIBIDA (Art. 11, §3 LGPD) | Excecao apenas para prestacao de servicos de saude, assistencia farmaceutica e assistencia a saude | pesquisa-lgpd-martech.md (1.10) |
| 13 | Politica de Privacidade deve conter 13 itens minimos obrigatorios (Arts. 6, VI e 9 LGPD) | Identificacao controlador, DPO, dados coletados, finalidades, bases legais, compartilhamento, transferencia internacional, retencao, direitos, seguranca, cookies, alteracoes, vigencia | pesquisa-lgpd-martech.md (1.7) |
| 14 | Conteudo impulsionado/pago tem presuncao de responsabilidade da plataforma E da agencia criadora (decisao STF Jun/2025) | Art. 19 do Marco Civil declarado parcialmente inconstitucional. Agencia tem responsabilidade direta pelo conteudo que cria e impulsiona | pesquisa-lgpd-martech.md (5.1) |
| 15 | Registros de acesso a aplicacoes devem ser mantidos por minimo 6 meses (Art. 15, Marco Civil). Registros de consentimento: enquanto durar tratamento + 5 anos (prescricao) | Obrigacao legal de retencao que deve ser observada mesmo apos opt-out do titular | pesquisa-lgpd-martech.md (5.3) |
| 16 | Opt-out deve ser respeitado imediatamente, sem mensagens de confirmacao tipo "tem certeza?" | Respeito imediato e obrigatorio. Segregar listas por tipo de consentimento (transacional vs marketing) | pesquisa-lgpd-martech.md (2.4) |
| 17 | DPO nao deve exercer funcoes que envolvam decisoes estrategicas sobre tratamento de dados (conflito de interesses) | Exemplo: Diretor de Marketing nao deve ser DPO — conflito entre maximizar uso de dados e protege-los | pesquisa-lgpd-martech.md (4.6); perplexity-lgpd-compliance.md (Modulo 2) |

---

## 4. Anti-Patterns

> Erros, praticas ruins e armadilhas que o agente deve identificar e bloquear.

| # | Anti-Pattern | Por que e ruim | O que fazer em vez |
|---|-------------|----------------|---------------------|
| 1 | **Checkbox pre-marcado em formulario** | Consentimento invalido — nao e "inequivoco" (Art. 8 LGPD) | Checkbox desmarcado com texto claro e especifico para cada finalidade |
| 2 | **Termos genericos "aceito tudo"** | Consentimento nulo — autorizacoes genericas sao nulas (Art. 8, §4 LGPD) | Consentimento granular com checkboxes separados por finalidade (email, WhatsApp, parceiros) |
| 3 | **Condicionar acesso a conteudo ao consentimento para marketing (hard-gating)** | Vicia a liberdade do consentimento — nao e "livre" | Soft-gating permitido; consentimento para marketing deve ser opcional e separado |
| 4 | **Usar legitimo interesse como "base legal coringa"** | Falha nos testes de necessidade e balanceamento; ANPD exige LIA documentado | Aplicar LIA em 3-4 fases para cada operacao; se falhar em qualquer fase, usar consentimento |
| 5 | **Ativar pixels de remarketing antes do consentimento do visitante** | Violacao direta ao Guia de Cookies ANPD. Erro mais comum de agencias | Cookie banner com opt-in ativo; pixels carregados apenas apos consentimento para cookies de marketing |
| 6 | **Cookie banner com dark pattern** (botao "aceitar" em destaque, "rejeitar" escondido) | Nao atende ao requisito de consentimento livre, informado e inequivoco (Art. 8 LGPD) | Opcao de recusa tao acessivel quanto a de aceite; design neutro |
| 7 | **Listas de leads compradas ou alugadas** | Altissimo risco — sem consentimento documentado do titular, sem base legal valida | Bloquear automaticamente. Construir base organica com consentimento proprio |
| 8 | **Enviar WhatsApp marketing sem opt-in especifico para WhatsApp** | Viola LGPD + Politicas da Meta. Risco de banimento da conta WABA | Opt-in separado e especifico: "Aceito receber comunicacoes via WhatsApp" |
| 9 | **Compartilhar dados com plataformas internacionais sem clausula de transferencia** | Violacao a Resolucao 19/2024 (SCCs obrigatorias desde 08/2025) | Incorporar SCCs brasileiras nos contratos; documentar transferencia no ROPA |
| 10 | **Agencia sem definicao contratual de papeis (controlador/operador)** | Gera corresponsabilidade solidaria indefinida (Art. 42 LGPD) | Contrato com clausula explicita de papeis, finalidades, bases legais e limites |
| 11 | **DPO com conflito de interesses** (ex: Diretor de Marketing como DPO) | Conflito entre maximizar uso de dados e protege-los; viola Resolucao 18/2024 | DPO independente, sem subordinacao a quem decide finalidades de tratamento |
| 12 | **Nao cooperar com a ANPD durante investigacao** | Infracao autonoma com multa separada. Precedente: Telekall | Cooperacao total e imediata; jamais recomendar ao cliente ignorar solicitacao da ANPD |
| 13 | **Lookalike audiences sem consentimento** | Titular nao tem relacao com controlador; dados compartilhados com terceiro; volume amplo — todos fatores contra no balanceamento | Consentimento explicito; ou nao aprovar sem analise juridica especifica do cliente |
| 14 | **Email marketing sem link de opt-out em cada disparo** | Viola salvaguarda minima do legitimo interesse; impossibilita revogacao de consentimento | Opt-out funcional em toda comunicacao; finalidade compativel com opt-in original |
| 15 | **Review gating** (direcionar so clientes satisfeitos para Google) | Manipulacao de avaliacoes: viola diretrizes Google (risco de suspensao perfil) + Art. 37 CDC (publicidade enganosa) | Solicitar avaliacoes de forma generica para todos; responder todas (positivas e negativas) |
| 16 | **Usar legitimo interesse para cookies de publicidade sem teste de balanceamento** | Guia ANPD Cookies recomenda consentimento; legitimo interesse "nem sempre podera ser utilizado" para cookies publicitarios | Consentimento como base legal para cookies de marketing; LI apenas para cookies analiticos com LIA documentado |
| 17 | **Tratar dados de criancas sem salvaguardas especificas (Art. 14 LGPD)** | Zona de risco critico — ANPD agiu cautelarmente em 24-48h no caso Meta por esse motivo | Verificacao de idade em formularios; conformidade Art. 14 antes de qualquer aprovacao |

---

## 5. Taticas Acionaveis

> Do/don't com contexto de aplicacao, separadas por categoria.

### Categoria: Captacao de Leads e Formularios

| Tatica | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Implementar consentimento granular com checkboxes separados | DO | Todo formulario de captacao (landing page, pop-up, formulario de contato) | Checkboxes separados para: email marketing, WhatsApp, compartilhamento com parceiros. Desmarcados por padrao |
| Registrar timestamp, IP, user agent e texto do consentimento | DO | Toda coleta de consentimento | Armazenar versao do texto aceito + logs para auditoria. Onus da prova e do controlador (Art. 8, §2) |
| Implementar double opt-in para email marketing | DO | Toda inscricao em listas de email | Nao obrigatorio por lei, mas pratica mais segura para demonstrar consentimento valido |
| Coletar apenas dados estritamente necessarios | DO | Todo formulario | Principio da minimizacao (Art. 6, III). Para proposta comercial: email + nome, NAO CPF |
| Link para Politica de Privacidade acessivel ANTES do envio do formulario | DO | Todo formulario | Titular deve ter acesso a informacoes antes de consentir |
| Condicionar acesso total ao consentimento para marketing | DON'T | Qualquer formulario com conteudo valioso | Vicia liberdade do consentimento. Soft-gating ok, hard-gating problematico |

### Categoria: Cookies e Pixels

| Tatica | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Carregar pixels/tags apenas APOS consentimento para cookies de marketing | DO | Todo site com Meta Pixel, Google Ads, TikTok Pixel, etc. | Cookies nao essenciais NAO podem ser setados antes do consentimento |
| Separar Politica de Cookies da Politica de Privacidade | DO | Todo site de cliente | ANPD recomenda documento separado, acessivel de forma destacada |
| Usar Consent Mode (Meta/Google) quando usuario nao consente | DO | Campanhas de trafego pago | Permite operar com dados limitados sem violar consentimento |
| Ativar Google Analytics sem consentimento alegando "necessario" | DON'T | Sites com analytics | Analytics = cookie analitico; requer ao menos legitimo interesse com LIA, ou consentimento |

### Categoria: WhatsApp Business API

| Tatica | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Obter opt-in especifico fora do WhatsApp para marketing | DO | Todo uso de WhatsApp Business API para campanhas | Checkbox especifico: "Aceito receber comunicacoes via WhatsApp". Metodos: formulario web, SMS, presencial, chatbot |
| Incluir opt-out em toda mensagem de marketing | DO | Todo template de marketing | Ex: "Responda SAIR para cancelar". Respeitar imediatamente |
| Segregar listas por tipo de consentimento (transacional vs marketing) | DO | Gestao de contatos WABA | Evitar enviar marketing para quem so consentiu transacional |
| Adicionar numeros de lista comprada ao WhatsApp | DON'T | Nunca | Viola LGPD + Politicas Meta. Risco de banimento WABA |
| Enviar marketing na janela de sessao sem consentimento previo | DON'T | Conversas iniciadas pelo usuario | Janela de sessao nao implica consentimento para marketing |

### Categoria: Contratos e Relacoes Comerciais

| Tatica | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Verificar se cliente possui DPO designado antes de assinar contrato | DO | Onboarding de todo novo cliente | Se nao possui, incluir clausula de obrigacao com prazo de adequacao |
| Incorporar SCCs brasileiras em contratos com processadores internacionais | DO | Todo contrato envolvendo Meta, Google, HubSpot, Mailchimp, etc. | Obrigatorio desde 08/2025 (Resolucao 19/2024) |
| Incluir clausula de LIA como representacao do cliente | DO | Contratos onde marketing usa legitimo interesse | Cliente declara que realizou LIA e resultado foi favoravel |
| Declarar lista de suboperadores no contrato | DO | Todo contrato agencia-cliente | Lista de ferramentas SaaS usadas (Meta, Google, HubSpot, Supabase), com autorizacao previa |
| Assinar contrato sem definicao de papeis controlador/operador | DON'T | Nunca | Gera corresponsabilidade indefinida |

### Categoria: Trafego Pago e Remarketing

| Tatica | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Documentar base legal para Custom Audiences | DO | Toda campanha com upload de listas | Consentimento especifico ou legitimo interesse com LIA. Dados enviados em hash = ainda e transferencia internacional |
| Observar principio da nao discriminacao em Lookalike Audiences (Art. 6, IX) | DO | Toda campanha com publicos semelhantes | Nao usar lookalikes baseados em dados que gerem discriminacao ilicita |
| Informar uso de remarketing na Politica de Privacidade | DO | Todo site que use remarketing | Transparencia obrigatoria + opcao de opt-out |
| Aprovar campanha de remarketing via lookalike sem consentimento | DON'T | Maioria dos cenarios | Titular nao tem relacao com controlador; compartilhamento com terceiro; risco alto no balanceamento |

### Categoria: IA e Decisoes Automatizadas

| Tatica | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Documentar base legal, finalidade e mecanismo de revisao humana para projetos de IA | DO | Chatbots, lead scoring, personalizacao por algoritmo | Art. 20 LGPD exige revisao humana a pedido do titular. Risco regulatorio elevado (regulamentacao em tramitacao) |
| Verificar base legal de plataformas contratadas para uso de IA | DO | Campanhas que usem IA generativa com dados de usuarios | Precedente: ANPD suspendeu Meta por uso de dados para treinar IA sem base legal adequada |
| Implantar lead scoring sem mecanismo de revisao humana | DON'T | Qualquer sistema de decisao automatizada | Violacao do Art. 20 LGPD, independente da base legal |

### Categoria: Setor Imobiliario

| Tatica | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Obter consentimento do proprietario para fotos internas e tours virtuais | DO | Todo anuncio imobiliario com fotos/videos internos | Fotos internas podem revelar informacoes pessoais (objetos, decoracao) |
| Treinar corretores sobre LGPD e sigilo de dados | DO | Todo cliente imobiliario | Corretores acessam CPF, RG, renda, score — dados altamente sensiveis na pratica |
| Verificar ToS de portais imobiliarios sobre propriedade de leads | DO | Anuncios em ZAP, VivaReal, OLX | Leads gerados no portal: verificar de quem sao os dados e quem e controlador |
| Usar dados de financiamento (score, renda) para remarketing | DON'T | Nunca | Dados financeiros com tratamento diferenciado; alto risco de danos morais |

---

## 6. Metricas e Benchmarks

> Numeros de referencia citados nas fontes. Incluir contexto para nao serem aplicados fora de escopo.

| Metrica | Valor/Range | Contexto | Fonte |
|---------|-------------|----------|-------|
| Multa maxima LGPD | 2% do faturamento bruto, limitada a R$ 50 milhoes por infracao | Multa simples ou diaria; teto absoluto de R$ 50M por infracao | pesquisa-lgpd-martech.md (9.1) |
| Primeira multa ANPD (Telekall) | R$ 14.400 (2x R$ 7.200) | Microempresa de telemarketing; 2% do faturamento | perplexity-lgpd-compliance.md (Caso 1) |
| Multa diaria caso Meta/IA | R$ 50.000/dia por descumprimento de medida cautelar | Aplicada por medida preventiva, nao como sancao definitiva | perplexity-lgpd-compliance.md (Caso 3) |
| Prazo comunicacao incidente a ANPD | 3 dias uteis (agentes regulares); 6 dias uteis (pequeno porte) | A partir da data de conhecimento do incidente. Resolucao 15/2024 | pesquisa-lgpd-martech.md (7.4) |
| Prazo retencao registros de acesso (Marco Civil) | 6 meses | Registros de acesso a aplicacoes (Art. 15, Marco Civil) | pesquisa-lgpd-martech.md (5.3) |
| Prazo retencao registros de conexao (Marco Civil) | 1 ano | Registros de conexao — provedores de acesso (Art. 13, Marco Civil) | pesquisa-lgpd-martech.md (5.3) |
| Prazo retencao registros de consentimento | Duracao do tratamento + 5 anos (prescricao civil) | Onus da prova do consentimento e do controlador | pesquisa-lgpd-martech.md (5.3) |
| Prazo retencao registro de incidente | Minimo 5 anos | Registro completo do incidente e resposta | pesquisa-lgpd-martech.md (7.4) |
| Prazo para incorporacao SCCs brasileiras | 12 meses apos publicacao (encerrou em 23/08/2025) | Resolucao 19/2024; obrigatorio para transferencias para paises sem adequacao | pesquisa-lgpd-martech.md (3.4) |
| Desconto para pagamento sem recurso | 25% | Previsto no precedente Telekall; pagamento imediato sem recurso | perplexity-lgpd-compliance.md (Caso 1, Dosimetria) |
| Classificacao de infracoes — faixa de multa leve | Ate 1% do faturamento | Infracoes de menor potencial ofensivo | pesquisa-lgpd-martech.md (4.5) |
| Classificacao de infracoes — faixa de multa media | 1% a 1,5% do faturamento | Infracoes com potencial ofensivo moderado | pesquisa-lgpd-martech.md (4.5) |
| Classificacao de infracoes — faixa de multa grave | 1,5% a 2% do faturamento | Infracoes com alto potencial ofensivo | pesquisa-lgpd-martech.md (4.5) |
| Suspensao de banco de dados | Ate 6 meses, prorrogavel | Sancao para infracoes graves | pesquisa-lgpd-martech.md (9.1) |
| Mensagens gratuitas WhatsApp API (Service) | 1.000/mes por conta WABA | Respostas a mensagens iniciadas pelo cliente | perplexity-lgpd-compliance.md (Modulo 4) |
| Retencao GA4 configuravel | 2 ou 14 meses | Opcao de configuracao no Google Analytics 4 | pesquisa-lgpd-martech.md (3.2) |
| Prazo resposta a titulares (recomendado) | 15 dias | Nao ha prazo legal fixo, mas 15 dias e pratica recomendada | pesquisa-lgpd-martech.md (7.1) |
| Multa FTC por review gating (referencia internacional) | Ate US$ 51.744 por violacao | EUA, 2024 — referencia comparativa para praticas enganosas de avaliacoes | pesquisa-lgpd-martech.md (3.5) |
| Empresas fiscalizadas ANPD (dez/2024) | 20 empresas simultaneamente | Fiscalizacao proativa por falta de DPO e canal de comunicacao | perplexity-lgpd-compliance.md (Caso 4) |

---

## 7. Vocabulario Signature

> Termos e expressoes que definem a voz do agente juridico LGPD. Essencial para voice_dna do agente-clone.

### Termos que SEMPRE usa
- **Titular** — A pessoa natural a quem se referem os dados pessoais
- **Controlador** — Quem decide sobre o tratamento; na relacao agencia-cliente, tipicamente o cliente
- **Operador** — Quem executa o tratamento em nome do controlador; tipicamente a agencia
- **Base legal** — Hipotese do Art. 7 (ou Art. 11 para sensiveis) que fundamenta o tratamento
- **Consentimento granular** — Consentimento separado por finalidade, nao generico
- **Finalidade** — Proposito especifico e declarado do tratamento de dados
- **Minimizacao** — Principio de coletar apenas o estritamente necessario
- **Transparencia** — Dever de informar o titular de forma clara e acessivel
- **Accountability** — Principio de responsabilizacao e prestacao de contas
- **LIA** — Legitimate Interest Assessment; teste de proporcionalidade obrigatorio para legitimo interesse
- **ROPA/ROT** — Registro de Operacoes de Tratamento; documento formal obrigatorio
- **RIPD/DPIA** — Relatorio de Impacto; obrigatorio para tratamento de alto risco
- **SCCs** — Clausulas-Padrao Contratuais para transferencia internacional
- **DPO/Encarregado** — Responsavel pelo canal de comunicacao entre controlador, titulares e ANPD
- **Opt-in / Opt-out** — Mecanismos de entrada e saida de consentimento
- **Tratamento** — Qualquer operacao realizada com dados pessoais (coleta, armazenamento, uso, compartilhamento, eliminacao)
- **Incidente de seguranca** — Evento que comprometa confidencialidade, integridade ou disponibilidade de dados pessoais
- **Dosimetria** — Criterios de calculo e graduacao de sancoes

### Expressoes recorrentes
- "Base legal documentada ANTES de iniciar o tratamento"
- "Consentimento livre, informado e inequivoco"
- "Teste de proporcionalidade em 4 fases"
- "Legitimas expectativas do titular"
- "Responsabilidade solidaria entre controlador e operador"
- "Dupla conformidade: LGPD + Politicas da Meta"
- "Onus da prova do consentimento e do controlador"
- "Dados minimos necessarios para a finalidade"
- "Transferencia internacional de dados"
- "Clausulas-padrao contratuais brasileiras"
- "Infracao autonoma com multa separada"
- "Zona de risco critico"
- "Alerta bloqueador"
- "Fiscalizacao proativa da ANPD"

### Termos que NUNCA usa (ou condena)
- **"Aceito tudo"** — Consentimento generico invalido; condena terminantemente
- **"Base legal residual"** — Bioni critica uso do legitimo interesse como "base para tudo que nao encaixa em outro lugar"
- **"Dado anonimizado = liberdade total"** — Anonimizacao real e dificil; pseudonimizacao nao exime da LGPD
- **"E so colocar nos termos"** — Termos de uso nao substituem consentimento valido; transparencia nao e conformidade
- **"Review gating"** — Pratica condenada; manipulacao de avaliacoes

### Metaforas e analogias frequentes
- **"Raio-X da empresa"** — Data mapping como diagnostico completo dos fluxos de dados
- **"Documento vivo"** — ROPA como registro continuo, atualizado a cada nova operacao (diferente do data mapping, que e "foto")
- **"Fadiga de consentimento"** — Volume de solicitacoes torna o consentimento mecanico (conceito de Bioni)
- **"Ilusao de controle"** — Consentimento cria falsa sensacao de que o titular controla seus dados (conceito de Bioni)
- **"Consentimento como legitimacao"** — Empresas usam consentimento para "lavar" praticas questionaveis (conceito de Bioni)
- **"Duas camadas cumulativas"** — LGPD + Politicas da Meta para WhatsApp (nao alternativas)

---

## Metadados de Extracao

```yaml
extraction_stats:
  total_files_processed: 2
  total_lines_analyzed: 1920
  concepts_extracted: 21
  frameworks_extracted: 7
  rules_extracted: 17
  anti_patterns_extracted: 17
  tactics_extracted: 32
  metrics_extracted: 18
  vocabulary_terms: 34
  dedup_removals: 12
  confidence_score: "92%"
```

---

_Extraido por Athena (knowledge-miner) v1.0 — 2026-03-23_
