---
material: corpus-ia-saude-suplementar
anexo: B
titulo: "Glossário de Saúde Suplementar — Dicionário de Sobrevivência"
fontes: [health-dossie-mesa-gpt, health-dossie-gemini-brasil, health-dossie-estrategico-ia-backoffice-es, health-personas-bpo-gemini, health-concorrentes-bpo-gemini, health-estrategia-oferta-gemini, divergencias-metricas-saude-suplementar]
gerado_em: 2026-06-27
---

# Anexo B — Glossário de Saúde Suplementar

> **O que é este anexo e para que serve.** Os três dossiês de campo registrados na biblioteca em 2026-06-27 trazem, cada um, um "dicionário de sobrevivência" — sinal de que o domínio do vocabulário nativo é o **primeiro filtro de credibilidade** na mesa da saúde suplementar [fonte: health-dossie-gemini-brasil]. Este glossário consolida esses dicionários e os termos já desenvolvidos ao longo dos Capítulos 1 a 6, num único índice pesquisável. Cada verbete traz uma **definição curta**, o **impacto no back-office** e, quando o termo é desenvolvido em narrativa, o **capítulo de referência**. Os números aparecem com seu recorte; divergências entre fontes foram reconciliadas em [fonte: divergencias-metricas-saude-suplementar]. As definições consolidam [fonte: health-dossie-mesa-gpt | fonte: health-dossie-gemini-brasil | fonte: health-dossie-estrategico-ia-backoffice-es]; números específicos citam a fonte na linha.

---

## 1. Regulação e assistência

- **ANS — Agência Nacional de Saúde Suplementar.** Autarquia federal que regula as operadoras: registra beneficiários, define cobertura, contratação, movimentação cadastral, reajuste de planos individuais e o padrão de troca de dados (TISS). É balizador severo e gerador de custo de adaptação. *Ver Cap. 1.*
- **Susep — Superintendência de Seguros Privados.** Regula o canal de distribuição (corretores e corretoras). O setor vive sob dupla regulação: ANS no produto, Susep no canal. *Ver Cap. 1.*
- **Rol da ANS.** Lista mínima e obrigatória de consultas, exames, cirurgias e tratamentos que as operadoras devem cobrir. É a régua mínima que orienta as discussões de autorização e negativa.
- **DUT — Diretrizes de Utilização.** Critérios clínicos específicos que condicionam a cobertura obrigatória de um item do Rol. Se a indicação do paciente não preenche a DUT, a fatura é recusada — campo minado para clínica e faturamento [fonte: health-dossie-gemini-brasil].
- **RN 309 — Pool de risco.** Agrupamento de contratos PME para reajuste único; impacta a previsibilidade e exige auditoria técnica para contestar índices. *Ver Cap. 6.*
- **RN 593.** Norma que define inadimplência e cancelamento: o cancelamento por falta de pagamento exige, em regra, ao menos **duas mensalidades não pagas** e notificação prévia [fonte: health-dossie-mesa-gpt]. *Ver Cap. 1, §8.*
- **RN 623/2024.** Em vigor desde julho de 2025, exige agilidade, rastreabilidade e clareza no atendimento ao beneficiário: protocolo, acompanhamento on-line, resposta conclusiva em prazo (5 dias úteis em regra; 10 para internação eletiva) e negativa por escrito [fonte: health-dossie-mesa-gpt]. *Ver Cap. 1, §8.*
- **Consulta Pública 170.** Aberta pela ANS em abril de 2026 para rever a contratualização operadora-prestador; propõe vedar glosa de procedimento previamente autorizado e obrigar o pagamento do valor incontroverso [fonte: health-dossie-mesa-gpt]. *Ver Cap. 1, §8.*
- **Judicialização.** Pacientes recorrem ao Judiciário para obrigar cobertura de tratamentos de alto custo ou fora do Rol. Rompe a previsibilidade atuarial, infla a sinistralidade e endurece autorizações seguintes [fonte: health-dossie-gemini-brasil]. *Ver Cap. 1, §8.*
- **NIP — Notificação de Investigação Preliminar.** Instrumento da ANS para reclamações de beneficiário; cerca de 80% das NIPs são assistenciais (ligadas a acesso à cobertura) [fonte: health-dossie-mesa-gpt].
- **IGR — Índice Geral de Reclamações.** Reclamações por 100 mil beneficiários; caiu de 60,2 (2024) para 51,5 (2025), indicando melhora formal num ambiente ainda exigente [fonte: health-dossie-mesa-gpt].

---

## 2. Faturamento e codificação

- **TISS — Troca de Informação em Saúde Suplementar.** Padrão obrigatório da ANS para a troca eletrônica de dados entre prestador e operadora; é a "gramática operacional" do setor (autorizar, cobrar, devolver demonstrativo, recorrer). Versão de referência citada: Maio/2026. *Ver Caps. 1 e 4.*
- **TISS 4.01.** Versão do padrão TISS citada como referência nas arquiteturas de produto. *Ver Cap. 6.*
- **TUSS — Terminologia Unificada da Saúde Suplementar.** Tabela de códigos que nomeia procedimentos, materiais, taxas e medicamentos dentro do TISS. Código TUSS incorreto ou incompatível com o CID-10 é causa primária de glosa. *Ver Cap. 4.*
- **XML.** Formato estruturado em que o lote de faturamento é empacotado e transmitido. Uma tag fora do lugar derruba o lote inteiro no validador da operadora. *Ver Cap. 4.*
- **Guia.** Documento que descreve o atendimento. Tipos principais: **Consulta**, **SP/SADT** (Serviço de Apoio Diagnóstico e Terapêutico — exames e terapias ambulatoriais) e **Honorários Médicos**. *Ver Cap. 4.*
- **Lote.** Pacote de guias empacotado num único arquivo XML e enviado de uma vez à operadora, respeitando o cronograma de fechamento de cada uma. *Ver Cap. 4.*
- **PEP — Prontuário Eletrônico do Paciente.** Sistema onde o médico registra evolução clínica, materiais e dosagens. A dor central do faturista é que o PEP frequentemente **não se comunica com o módulo de faturamento**, obrigando a "garimpar" laudos para transformar texto em código TUSS [fonte: health-dossie-gemini-brasil]. *Ver Cap. 4.*
- **Ciclo de Receita (RCM — Revenue Cycle Management).** Conjunto integral de etapas que transforma o atendimento em dinheiro recebido: pré-autorização, elegibilidade, registro, codificação, auditoria, transmissão, recebimento, análise de glosas e conciliação. *Ver Caps. 4 e 5.*
- **Demonstrativo de Retorno (de repasse).** Relatório em que a operadora informa, item a item, o que aceitou pagar e o que glosou. *Ver Caps. 1 e 4.*
- **Validador TISS.** Ferramenta que confere a estrutura do XML antes do envio (credenciamento, *hash*, carteirinha, CBO, códigos), bloqueando erros "no berço". *Ver Cap. 4.*
- **CBO — Código Brasileiro de Ocupações.** Identifica a especialidade do profissional; incompatibilidade gera glosa. **CBHPM** é a tabela de referência de valores de procedimentos. *Ver Cap. 4.*
- **OPME — Órteses, Próteses e Materiais Especiais.** Materiais implantados ou usados em cirurgias; exigem anexo próprio no TISS e são dos pontos mais delicados de autorização e auditoria. *Ver Caps. 4 e 6.*
- **Elegibilidade.** Verificação de que o beneficiário tem direitos contratuais válidos naquele momento ("esse paciente está ativo e coberto para isto?") antes de atender ou faturar. *Ver Cap. 4.*
- **Autorização prévia / senha.** Permissão da operadora para realizar um procedimento. Sem ela não se atende; mal documentada, vira discussão na conta depois.

---

## 3. Financeiro e fluxo de caixa

- **Glosa.** Recusa, total ou parcial, do pagamento de uma conta já faturada. É o termo mais temido do setor: significa dinheiro parado, retrabalho e caixa pressionado. *Ver Caps. 1 e 4.*
- **Glosa administrativa.** Recusa por erro burocrático ou cadastral (assinatura ausente, guia incompleta, senha vencida, dado inconsistente). A assistência pode ter sido correta, mas o back-office errou a trilha de prova. Cerca de **68% das glosas são administrativas — evitáveis antes do envio** [fonte: health-dossie-gemini-brasil]. *Ver Cap. 4.*
- **Glosa técnica.** Recusa em que a operadora questiona clinicamente o procedimento (inadequado, desnecessário, mal respaldado). Pede substância clínica, não só papel correto. *Ver Cap. 4.*
- **Glosa inicial × glosa final (contábil).** A inicial é o valor retido logo após o processamento; a final é o que de fato se perde depois dos recursos. O abismo entre elas é revelador: nos grandes hospitais (Anahp), ~15,89% inicial contra ~1,96% final — prova de que a maior parte da glosa é dinheiro legítimo retido temporariamente. No setor inteiro (Painel ANS), ~7,31% inicial e ~7,14% final [fonte: divergencias-metricas-saude-suplementar]. *Ver Cap. 4.*
- **Recurso de glosa.** Contestação técnica enviada à operadora para reaver o pagamento recusado. Tem dois inimigos: o prazo recursal exíguo e a complexidade técnica. *Ver Cap. 4.*
- **PMR — Prazo Médio de Recebimento.** Dias entre faturar e receber da operadora. Nos grandes hospitais piorou de 66,6 para 78,5 dias entre o 3T/2024 e o 3T/2025 [fonte: health-dossie-gemini-brasil]. *Ver Cap. 4.*
- **PMP — Prazo Médio de Pagamento.** Dias que o prestador tem para pagar fornecedores e equipe (~46 dias). *Ver Cap. 4.*
- **Gap de caixa.** Descompasso PMR − PMP; passou de ~19 para ~32 dias, forçando o prestador a bancar a operação com capital próprio ou crédito [fonte: health-dossie-gemini-brasil]. *Ver Cap. 4.*
- **DSO — Days Sales Outstanding.** Indicador equivalente ao PMR: número médio de dias entre o atendimento e o recebimento. *Ver Cap. 1.*
- **Repasse médico.** Distribuição ao médico/prestador do valor liquidado pela operadora. Quando a operadora glosa ou atrasa, o dono da clínica decide entre adiantar com capital próprio ou arriscar a fuga do corpo clínico. *Ver Caps. 1 e 4.*
- **Split de pagamento.** Fracionamento de um mesmo recebimento entre vários destinatários (médicos de uma clínica de *coworking*). *Ver Cap. 4.*
- **Índice combinado.** Relação entre despesas totais e receitas de uma operadora; situou-se em ~95,3%, margem de manobra mínima [fonte: health-dossie-gemini-brasil]. *Ver Cap. 1.*
- **Mensalidade / prêmio.** Valor cobrado pela operadora pela cobertura do risco; a entrada do "caminho do dinheiro". *Ver Cap. 1.*
- **Coparticipação / fator moderador.** Mecanismos (coparticipação, franquia) que fazem parte do custo de uso recair sobre o beneficiário, inibindo o uso desnecessário e blindando a sinistralidade. *Ver Cap. 1.*
- **Inadimplência.** Não é atraso simples: configura-se quando a mensalidade anterior segue sem pagamento depois do vencimento da próxima (RN 593) [fonte: health-dossie-mesa-gpt].

---

## 4. Seguros, preços e gestão de carteira

- **Sinistralidade (MLR — Medical Loss Ratio).** Razão entre despesas assistenciais e receita com mensalidades. Faixa saudável: abaixo de 70-75%; equilíbrio: 85-89%; acima disso, reajustes punitivos. Setor em ~81,7% (2025) [fonte: health-dossie-mesa-gpt]. *Ver Cap. 1.*
- **VCMH — Variação de Custos Médico-Hospitalares.** Inflação específica da saúde (novas tecnologias, medicamentos, câmbio, envelhecimento); ~15,1% em 2026, contra IPCA de um dígito. *Ver Cap. 1.*
- **Beneficiário / vida / vínculo.** Pessoa coberta. O setor conta "vidas" (vínculos), não pessoas únicas — uma pessoa pode ter mais de um vínculo. *Ver Cap. 1.*
- **Movimentação cadastral.** Inclusões, exclusões e alterações de vidas na base da operadora; o atraso aqui é a raiz comum da glosa de elegibilidade e da cobrança indevida (o "Insight de Ouro" do Cap. 6). *Ver Caps. 2 e 6.*
- **SIB — Sistema de Informações de Beneficiários.** Base de beneficiários da ANS; exige atualização constante, e atrasos geram cobrança de "vidas indevidas". *Ver Cap. 6.*
- **DPS / DLP — Declaração de Saúde / Doenças Preexistentes.** Gargalo de digitação braçal e risco crítico de compliance e LGPD.
- **Coletivo empresarial × adesão × individual.** A base está no coletivo empresarial (~38,67 mi de vínculos) e não no individual (~8,46 mi) — o que torna a relação contínua, não transacional. *Ver Cap. 1.*
- **Falso Coletivo / PME.** Famílias abrem CNPJ (MEI) para contratar plano empresarial e fugir do teto regulatório do individual; ficam à mercê de reajustes livres e cancelamentos unilaterais [fonte: health-dossie-gemini-brasil]. *Ver Cap. 1.*
- **Agrupamento de contratos (regra dos < 30 vidas).** Reajuste de contratos coletivos pequenos; sistematicamente acima dos grandes — **14,24% em 2025** (era 17,85% em 2023) [fonte: divergencias-metricas-saude-suplementar]. *Ver Cap. 6.*
- **Regra 5/50.** 5% dos beneficiários de um contrato (crônicos/oncológicos) concentram ~50% dos custos da apólice. Revelá-la dá ao corretor inteligência para a renovação. *Ver Caps. 5 e 6.*
- **Carteira / churn / carta de nomeação.** Carteira é o conjunto de clientes ativos da corretora; churn é a perda; a carta de nomeação formaliza a troca de corretora. No corporativo, o churn é operacional (exaustão com o suporte), não de preço. *Ver Caps. 3 e 5.*

---

## 5. Tecnologia e automação de back-office

- **BPO — Business Process Outsourcing.** Terceirização de uma função inteira (aqui, o ciclo de receita ou o cadastro) para um fornecedor especializado. *Ver Cap. 4.*
- **OCR — Reconhecimento Óptico de Caracteres.** Leitura automática de documentos fotografados (RG, guias). Base da automação de cadastro. *Ver Caps. 4 e 6.*
- **RPA — Robotic Process Automation.** Robôs que executam tarefas repetitivas (preencher portais). *Ver Caps. 4 e 6.*
- **RAG — Retrieval-Augmented Generation.** IA que responde consultando uma base de conhecimento (manuais de operadora, regras ANS) — usada para compliance e defesa de glosa. *Ver Cap. 6.*
- **LLM / Claude Vision / Playwright.** LLM é o modelo de linguagem; Claude Vision (Haiku 4.5) é o motor de OCR recomendado; Playwright é a ferramenta de automação de navegador usada como RPA. *Ver Cap. 6.*
- **Human-in-the-loop.** Humano no circuito de validação — confere o que a IA extraiu antes de injetar no sistema. *Ver Cap. 6.*
- **Prompt Caching.** Técnica que barateia o custo de tokens ao processar volumes de documentos/faturas. *Ver Cap. 6.*
- **LGPD — Lei Geral de Proteção de Dados.** Rege o tratamento de dados pessoais; sensibilidade máxima na saúde (CPF, declaração de saúde, doenças). Segurança de nível bancário é ponto de partida irrevogável da negociação. *Ver Caps. 4, 5 e 6.*

---

## 6. Termos próprios da jogada Cadarn (prescritivo — ver Cap. 6)

> Os termos abaixo são da camada **prescritiva** (a estratégia da Cadarn), não fatos de mercado; têm status de hipótese a validar [fonte: health-estrategia-oferta-gemini].

- **BPO Tech.** Usar a própria IA como vantagem competitiva para prestar cadastro e faturamento mais rápido, barato e preciso — escalando sem multiplicar a equipe.
- **Efeito Espelho das Ineficiências.** A dor de uma ponta (glosa no hospital) é o reflexo da dor da outra (cobrança indevida na corretora).
- **Insight de Ouro.** A raiz comum de quase toda glosa administrativa e de toda cobrança indevida é a mesma: assimetria de dados cadastrais e lentidão na atualização das vidas.
- **Trio da Eficiência Operacional.** A oferta encadeada: Onboarding (entrada) → Conciliação (manutenção) → Sinistralidade (retenção).
- **Glosa Zero.** Bandeira da pré-auditoria que impede o "nascimento" da glosa antes do envio.
- **Crossover.** A mesma base tecnológica vendida de dois jeitos: "Auditor Médico/Defensor de Receita" para a clínica; "Integrador/Previsor Atuarial" para a corretora. *Ver Cap. 5.*
- **Cavalo de Troia.** Processo de entrada de menor atrito e maior dor (conciliação de comissões na corretora; raio-X de glosas no hospital).
- **Diagnóstico de Eficiência Operacional.** A oferta de entrada: auditoria gratuita dos últimos 30-90 dias que expõe "quantos reais a empresa perdeu", abrindo para Success Fee ou assinatura.
- **Success Fee.** Honorário percentual atrelado ao resultado (glosa recuperada, divergência identificada).
- **Fator R.** Mecanismo tributário do Simples (folha ≥ 28% da receita migra do Anexo V ao III, reduzindo imposto). A automação deve contornar o Fator R via realocação, concentração de folha ou escala — nunca corte cego. *Ver Caps. 3 e 6.*
- **Wizard of Oz / Design Partner.** Método de validar um produto operando o "motor" manualmente nos bastidores antes de automatizá-lo (*Wizard of Oz*), com um parceiro que cede dados reais (*Design Partner*).

---

> **Nota de uso (treinar IA).** Este glossário é índice de referência, não substitui a narrativa: cada termo é desenvolvido em contexto no capítulo indicado. Quando duas fontes divergem sobre um número (glosa, reajuste, beneficiários), a reconciliação está em [fonte: divergencias-metricas-saude-suplementar], e o material apresenta o recorte de cada uma sem fundi-las (Art. IV — No Invention).
