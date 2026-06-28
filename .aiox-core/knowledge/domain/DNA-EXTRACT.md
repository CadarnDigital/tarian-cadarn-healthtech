---
template_id: dna-extract-tmpl
version: "1.0"
purpose: "DNA-EXTRACT consolidado do especialista Llif — domínio Saúde Suplementar / BPO Tech / Engenharia de Fluxo"
created_at: "2026-06-28"
agent: knowledge-miner
source_warning: "Material SEM frontmatter Echo (agent_id: aiox-m2m-etl). É corpus curado (frontmatter material: corpus-ia-saude-suplementar). Processado com penalidade de confiança conforme error_handling da task mine-knowledge."
---

# DNA-EXTRACT: Llif

> **Domínio:** Saúde Suplementar — BPO Tech / Engenharia de Fluxo
> **Fonte:** docs/cadarn-healthtech/Corpus IA/
> **Módulos processados:** 8 capítulos/anexos (00-indice + 01 a 08) — 9 arquivos, ~228 KB
> **Extraído em:** 2026-06-28
> **Minerador:** Athena (knowledge-miner)
> **Natureza do material:** Caps. 1-5 descritivos (mercado), Cap. 6 + Anexo A prescritivos (estratégia Cadarn — hipótese a validar), Anexo B referência (glossário)
> **Aviso epistêmico:** Itens da camada prescritiva (Cap. 6 / Anexo A) carregam status de **hipótese estratégica a validar**, não fato de mercado. Marcados com 🜂 ao longo do extrato. Art. IV — No Invention.

---

## 1. Conceitos-Chave

> Vocabulário fundacional que o agente-clone DEVE dominar. Domínio do jargão nativo é o **primeiro filtro de credibilidade** na mesa da saúde suplementar [Cap. 5/Glossário].

### Regulação e mercado
| Conceito | Definição | Contexto de uso |
|----------|-----------|-----------------|
| Saúde suplementar | Sistema privado de planos/seguros de saúde, paralelo ao SUS | Pano de fundo de todo o domínio (Cap. 1) |
| ANS | Agência Nacional de Saúde Suplementar — regula operadoras, beneficiários, cobertura, TISS | Regulador do produto |
| Susep | Superintendência de Seguros Privados — regula corretagem | Regulador do canal. "Dupla regulação": ANS produto, Susep canal |
| Beneficiário / vida / vínculo | Pessoa coberta; setor conta "vidas"/vínculos, não pessoas únicas | Uma pessoa pode ter >1 vínculo; "carteira de 5 mil vidas" |
| Operadora (3 tipos) | Cooperativa médica (Unimed) · medicina de grupo c/ rede própria (Samp) · seguradora nacional s/ hospital, via credenciamento+reembolso (Bradesco, SulAmérica) | Mapear concorrência regional (ES) |
| Coletivo empresarial × adesão × individual | Base está no coletivo empresarial (~38,67 mi vínculos) vs individual (~8,46 mi) | Torna a relação **contínua**, não transacional |
| Falso Coletivo / PME | Família abre CNPJ/MEI para fugir do teto regulatório do individual | Fica à mercê de reajuste livre e cancelamento unilateral |

### Caminho do dinheiro
| Conceito | Definição | Contexto |
|----------|-----------|----------|
| Mensalidade / prêmio | Valor cobrado pela operadora pela cobertura do risco | Entrada do circuito financeiro |
| Sinistralidade (MLR — Medical Loss Ratio) | (Despesas assistenciais ÷ Receita mensalidades) × 100 | Define saúde da carteira e o reajuste futuro. MLR é o termo internacional |
| Glosa | Recusa total/parcial do pagamento de uma conta já faturada | Termo mais temido do setor — dinheiro parado + retrabalho |
| Glosa administrativa | Recusa por erro burocrático/cadastral (senha vencida, dado inconsistente) | ~68% das glosas — **evitáveis antes do envio** |
| Glosa técnica | Recusa por questionamento clínico do procedimento | Pede substância clínica, não só papel |
| Glosa inicial × final | Inicial = retido após processamento; Final = perda real pós-recurso | Abismo (Anahp ~15,89%→~1,96%) prova: maioria é dinheiro legítimo retido |
| Repasse médico | Distribuição ao prestador do valor liquidado pela operadora | Final do circuito; prazos 30/60/90 dias |
| VCMH | Variação de Custos Médico-Hospitalares — inflação específica da saúde | Motor que puxa reajustes (~15,1% em 2026) |

### Faturamento e codificação
| Conceito | Definição | Contexto |
|----------|-----------|----------|
| TISS | Troca de Informação em Saúde Suplementar — padrão obrigatório ANS de troca eletrônica | "Gramática operacional"; ref. TISS 4.01 / Maio-2026 |
| TUSS | Terminologia Unificada — códigos de procedimentos/materiais | Código errado/defasado = causa primária de glosa |
| XML / Lote / Guia | XML = formato do arquivo; Lote = pacote de guias; Guia = doc do atendimento (Consulta, SP/SADT, Honorários) | Tag fora do lugar derruba o lote no validador |
| RCM (Ciclo de Receita) | Conjunto de etapas que transforma atendimento em dinheiro recebido | Gargalo do prestador: converter atendimento em recebimento |
| Validador TISS | Ferramenta que confere o XML antes do envio (hash, CBO, carteirinha, códigos) | Bloqueia erro "no berço" |
| PMR / PMP / Gap de caixa / DSO | Prazo médio recebimento / pagamento / descompasso / dias até receber | Gap passou de ~19 → ~32 dias nos grandes hospitais |
| Movimentação cadastral | Incluir/excluir/alterar vidas nos portais, todo mês | **Gargalo central** da corretora; raiz comum da glosa de elegibilidade |
| Batimento cadastral | Cruzar base de vidas ativas × lista de cobrança da operadora | Evita faturar demitido; corretora vira "auditora informal" |
| OPME / Elegibilidade / Autorização-senha / CBO / CBHPM / PEP | Materiais cirúrgicos especiais / direito válido / permissão da operadora / código de ocupação / tabela de valores / prontuário eletrônico | PEP frequentemente não conversa com módulo de faturamento |

### Modelo financeiro da corretora
| Conceito | Definição | Contexto |
|----------|-----------|----------|
| Comissão de angariação | Remuneração única na assinatura (5-15%; multinotas até 250%) | "Pulmão de curto prazo"; cobre o CAC |
| Comissão vitalícia | Recorrente a partir da 4ª mensalidade (2,5-5%) | "Oxigênio de longo prazo"; dilui custos fixos; gera LTV |
| Fator R | Folha (salários+FGTS+pró-labore) ÷ faturamento; ≥28% migra Anexo V (15,5%)→Anexo III (~6%) | Engenharia tributária central |
| Custo efetivo do funcionário | Salário × 1,6 a 2,0 (encargos+benefícios); +73% a +112% sobre nominal | Definido pelo **regime tributário**, não pelo salário |
| MGA / Hub multinotas / Insurtech | Canais que dão infra em troca de fatia da comissão e da posse da carteira | Vetor de consolidação setorial |

### BPO, IA e venda
| Conceito | Definição | Contexto |
|----------|-----------|----------|
| BPO | Business Process Outsourcing — terceirizar função inteira (RCM ou cadastro) | Economia projetada 40-60% vs interno CLT |
| 🜂 BPO Tech | Usar a própria IA como vantagem competitiva desleal; escalar sem multiplicar equipe | Virada estratégica Cadarn (Cap. 6) |
| OCR / RPA / RAG / LLM / human-in-the-loop / Prompt Caching | Leitura de docs / robôs de portal / IA c/ base de conhecimento / modelo de linguagem / humano valida / barateia tokens | Stack técnico do produto |
| Buyer persona / Centro de compras / Gatilho de compra | Retrato do comprador / papéis na decisão / evento que tira da inércia | Fundamentos da venda B2B |
| Challenger Sale / Venda consultiva / POC / White-label | Provocar diagnóstico / vender pela dor / prova de conceito / marca branca | Método comercial |
| 🜂 Crossover | Mesma base tecnológica vendida de 2 jeitos: "Auditor/Defensor de Receita" (clínica) vs "Integrador/Previsor Atuarial" (corretora) | Posicionamento Cadarn |
| LGPD / NIP / Rol / DUT / RN 309-593-623 / CP 170 | Lei de dados / notificação ANS / lista de cobertura / diretrizes clínicas / normas regulatórias | Compliance — segurança é ponto de partida irrevogável |

---

## 2. Frameworks e Modelos

### 2.1 O Caminho do Dinheiro
- **Origem:** Cap. 1, §7
- **Propósito:** Entender por onde o dinheiro entra, é consumido e trava no setor
- **Etapas:** Mensalidade (entrada) → Sinistralidade (consumo) → Glosa (atrito) → Repasse (saída)
- **Motor por baixo:** VCMH alta → reajustes pesados na renovação anual
- **Quando aplicar:** Diagnóstico de qualquer ator do ecossistema; base de toda análise

### 2.2 Os 3 Alicerces da Corretora de Sucesso
- **Origem:** Cap. 2/3
- **Etapas:** (1) Tecnologia/ERP (multicálculo, baixa automática de comissões, dashboards) · (2) Consultoria técnica localizada (defesa atuarial na renovação) · (3) Engenharia tributária (Fator R)
- **Quando aplicar:** Avaliar maturidade e viabilidade de uma corretora

### 2.3 Modelo de Receita Bifásico
- **Origem:** Cap. 3, §1
- **Propósito:** Explicar como a corretora ganha e se sustenta no tempo
- **Etapas:** Fase 1 Angariação (alta, única, alavancada até 250% multinotas) cobre CAC → Fase 2 Vitalício (2,5-5%, a partir da 4ª mensalidade) dilui custos fixos
- **Insight-chave:** Em ambos os modelos (cara-ativa vs mensal recorrente), a maior parte da receita vem dos meses subsequentes — não da venda
- **Resultado esperado:** Compreender que o negócio é "gestão de um ativo de receita perecível"

### 2.4 Fator R — migração de anexo
- **Origem:** Cap. 3, §5
- **Fórmula:** Fator R = folha (salários+FGTS+pró-labore) ÷ faturamento, mesma janela
- **Etapas:** Calcular rácio → se ≥28% → Anexo III (~6%); se <28% → Anexo V (15,5%)
- **Insight contraintuitivo:** Contratar CLT pode ser **alavanca fiscal**, não despesa — a economia tributária pode cobrir o custo da contratação
- **Quando aplicar:** Bloco fiscal do diagnóstico comercial

### 2.5 RCM / Ciclo de BPO de Faturamento (7 passos)
- **Origem:** Cap. 4
- **Etapas:** (1) coleta/digitação de guias → (2) exportação/envio XML TISS → (3) emissão de protocolos → (4) monitoramento de pagamentos → (5) recursos de glosas → (6) conciliação de repasses → (7) DRE gerencial

### 2.6 As 5 Vertentes do BPO de Faturamento
- **Origem:** Cap. 4, §4
- **Etapas:** (1) Auditoria Prévia/Front-end (profilática) · (2) Processamento/Middle-end · (3) Gestão de Glosas e Recursos/Back-end · (4) Inteligência Financeira e Conciliação (DRE) · (5) Credenciamento e Negociação Contratual (CBHPM)

### 2.7 🜂 Efeito Espelho + Insight de Ouro (Cadarn)
- **Origem:** Cap. 6, §1 — **hipótese a validar**
- **Efeito Espelho:** A dor de uma ponta (glosa no hospital) é o reflexo da dor da outra (cobrança indevida na corretora)
- **Insight de Ouro:** Raiz comum de quase toda glosa administrativa E toda cobrança indevida = **assimetria de dados cadastrais + lentidão na atualização da base de vidas**
- **Encadeamento:** Hospital fatura vida que a corretora pediu exclusão (ou cuja inclusão travou) → operadora glosa
- **Quando aplicar:** Justifica operar nas duas pontas (corretora + faturamento hospitalar) como "laboratório perfeito"

### 2.8 🜂 Trio da Eficiência Operacional (a oferta Cadarn)
- **Origem:** Cap. 6, §2 — **hipótese a validar**
- **Etapas:** Onboarding/Entrada (Automação de Cadastro) → Conciliação/Manutenção (Vidas ativas × faturas) → Sinistralidade/Retenção (dashboards preditivos + nutrição)
- **Princípio de venda:** "Não se vende IA, vende-se **recuperação de caixa** via automação"

### 2.9 🜂 Arquitetura técnica MVP de Onboarding (3 etapas)
- **Origem:** Cap. 6, §3 — **hipótese a validar**
- **Etapas:** (1) Extração — OCR Claude Vision (Haiku 4.5) → JSON estruturado · (2) Validação — human-in-the-loop → CSV de validação · (3) Injeção — RPA via Playwright digita no portal/ERP
- **Input:** pasta Google Drive ou bot WhatsApp/Telegram · **Output:** cadastro feito no ERP (Quiver/Segfy/Moltrio)
- **Recomendação:** Prompt Caching para baratear tokens em volume

### 2.10 🜂 Catálogo de Soluções de IA (A-G)
- **Origem:** Cap. 6, §3 — **propostas a validar**
- A) Pré-auditoria anti-glosa "Glosa Zero" (clínica) · B) Cadastro/movimentação automatizada "Automa-Cadastro" (corretora) · C) Conciliação financeira "AI Reconciler/Zero-Touch" (ambas) · D) RAG de compliance e regras (ambas) · E) Sinistralidade preditiva "motor MLR" + regra 5/50 (corretora) · F) Atendimento/retenção "Care-Support Agent" (corretora) · G) Triagem de pacientes/navegação + Monitor de Elegibilidade (front-office PME)

### 2.11 Centro de Compras (3 papéis)
- **Origem:** Cap. 5, §4
- **Papéis:** (1) Iniciador/Usuário — epicentro da dor; seu esgotamento é o **gatilho primário** · (2) Influenciador Técnico/Compliance — poder de **veto** (LGPD/ANS) · (3) Decisor/Comprador — sócio-fundador, protege o caixa
- **Lição:** Armar o Iniciador, satisfazer o Influenciador, entregar prova financeira ao Decisor

### 2.12 Jornada de Compra (8 etapas)
- **Origem:** Cap. 5, §6
- **Etapas:** (1) Identificação do problema → (2) Validação informal na rede → (3) Pesquisa de fornecedores → (4) Avaliação técnica → (5) Mitigação de risco/segurança → (6) POC/piloto → (7) Negociação → (8) Implementação/uso contínuo
- **Regra:** O **preço só aparece no fim**, atrás de confiança e domínio da rotina local

### 2.13 Hierarquia de Fatores de Decisão (nacional × capixaba)
- **Origem:** Cap. 5, §7
- **Capixaba (top-5):** Referência local/confiança (25%) → Segurança/rastreabilidade (20%) → Conhecimento de operadoras/rotinas (20%) → ROI (15%) → Preço (10%)
- **Insight:** No ES, confiança lidera e **preço cai ao 5º lugar**; tecnologia isolada é o último fator

### 2.14 🜂 Cálculo de ROI (211,7%)
- **Origem:** Cap. 6, §4 — **hipótese a validar**
- **Custo atual:** analista back-office Lucro Presumido = R$ 5.036,08/mês × 13 ≈ R$ 65.469/ano
- **Investimento:** Setup R$ 3.000 + R$ 1.500/mês = R$ 21.000/ano
- **Ganho líquido:** R$ 44.469/ano → **ROI 211,7%** (R$ 2,11 por R$ 1)

### 2.15 🜂 Contorno do Fator R (3 formas)
- **Origem:** Cap. 6, §4 — **hipótese a validar**
- **Problema:** Automação que corta folha pode derrubar abaixo de 28% e penalizar tributo
- **Soluções:** (1) Realocação (digitador→consultor, folha mantida) · (2) Concentração de folha (aumenta pró-labore/salários de alta performance) · (3) Escala (fatura 2-3x com a mesma folha)
- **Pitch:** "Automação não serve para demitir e reduzir folha — isso seria erro tributário; você escala receita sem inchar estrutura"

### 2.16 🜂 Product Discovery acelerado / Wizard of Oz (3 fases)
- **Origem:** Cap. 6, §5 + Anexo A — **hipótese a validar**
- **Fases:** (1) Diagnóstico de Dados (esta semana — extrair glosas/reclamações reais) · (2) MVP de Planilha "Wizard of Oz" (script Python + LLM, sem plataforma) · (3) Validação Comercial (calcular ROI real → argumento de escala)

### 2.17 🜂 Prompt-template de destilação (método CADARN aplicado)
- **Origem:** Anexo A, §C
- **Persona:** "Consultor Sênior de Inovação B2B e Arquiteto de Operações em Saúde"
- **Formato 3 fases:** Clareza (essencial, 3 parágrafos) → Arquitetura (3-5 ideias de IA) → Dados e Ação (1º passo de validação)
- **Espelha:** Diagnóstico → Arquitetura → Ação (Método CADARN)

---

## 3. Regras e Princípios

| # | Regra | Justificativa | Fonte |
|---|-------|---------------|-------|
| 1 | A venda é só o início; o backoffice é a base da retenção | Permanência depende de cadastro correto, movimentação sem falha, fatura sem erro | Cap. 2 |
| 2 | A rentabilidade está na retenção, não na venda | A maior parte da receita vem dos meses subsequentes; reter pouco = ROI negativo | Cap. 3 |
| 3 | Sem automação, crescer colapsa a corretora | Cada novo contrato adiciona carga que a folha não absorve com margem | Cap. 3, §6 |
| 4 | Automação é condição de viabilidade, não luxo | Sem ERP a empresa nem sustenta o equilíbrio tributário (encargos até ~110%) | Cap. 3, §6 |
| 5 | "IA" não abre a mensagem — lidera-se com a dor | Liderar com IA assusta o pequeno/médio; liderar com a dor conecta | Cap. 5, §8 |
| 6 | Segurança/LGPD é o ponto de partida irrevogável da negociação | Vazamento de dado de saúde gera ruína reputacional, não só multa | Cap. 5/6 |
| 7 | Adotar rigorosamente o jargão do setor é obrigatório | Domínio do léxico é o primeiro filtro de credibilidade; distanciamento invalida na hora | Cap. 5, §2 |
| 8 | Não competir por preço; o ROI bem demonstrado neutraliza o custo | Preço baixo é tática de quem não tem diferenciação | Cap. 5, §9 |
| 9 | A primeira reunião é diagnóstico, não apresentação | Sem diagnóstico, propostas demoram mais e convertem menos | Cap. 5, §8 |
| 10 | No Espírito Santo, confiança lidera e preço cai ao 5º lugar | Depois que confia, o cliente negocia preço | Cap. 5, §7 |
| 11 | Impedir a glosa "no berço" > recuperar depois | ~68% das glosas são administrativas/evitáveis; recurso manual pode ter ROI nulo | Cap. 4/5 |
| 12 | 🜂 Ser BPO Tech (margem/controle), não vendedor de software | Maior controle de margem; escala sem multiplicar equipe | Cap. 6, §1 |
| 13 | 🜂 Não vender "corte de custo" — vender "Eficiência Estratégica" | Automação cega quebra o Fator R; realocar/escalar protege o benefício fiscal | Cap. 6, §4 |
| 14 | Prova social de pares do setor está no topo absoluto (acima de preço) | Fator definitivo de mitigação de risco psicológico no B2B | Cap. 5, §7 |
| 15 | Implantar "sem quebrar o mês operacional" / migrar em paralelo | Gestor evita mexer em processo durante fechamento/reajuste/renovação | Cap. 5, §6 |
| 16 | No Invention — todo fato cita fonte; divergências apresentadas, não fundidas | Art. IV Constitution; inferências marcadas | Índice/Cap. 6 |

---

## 4. Anti-Patterns

| # | Anti-Pattern | Por que é ruim | O que fazer em vez |
|---|-------------|----------------|---------------------|
| 1 | Tratar a corretora como empresa apenas comercial | A venda é o início; a retenção mora no backoffice | Operar melhor a carteira que já existe |
| 2 | Vender muito e reter pouco | Cliente que cancela no 2º ano = ROI negativo | Investir em consultoria, acompanhamento e automação de renovação |
| 3 | Crescer sem automação | Cada contrato novo colapsa o back-office; folha devora a margem | ERP + RPA antes de escalar a carteira |
| 4 | Liderar a venda com "IA" / pitch de produto | Assusta o pequeno/médio; ele é refratário a telemarketing genérico | Venda consultiva (Challenger Sale): provocar diagnóstico pela dor |
| 5 | Dimensionar equipe olhando só o salário nominal | Subestima o custo em 70-110% | Calcular custo efetivo (salário × 1,6-2,0) e regime tributário |
| 6 | 🜂 Automação cega que corta a folha | Pode derrubar abaixo de 28% do Fator R e elevar o imposto | Realocação, concentração de folha ou escala |
| 7 | Disparo frio no WhatsApp | Intrusivo; queima o canal de maior conversão | 1ª mensagem aporta valor imediato (diagnóstico, dado regional) |
| 8 | Competir por preço | Espreme margem e sinaliza falta de diferenciação | Deslocar para "custo da ineficiência atual" + ROI |
| 9 | Exigir integração complexa de sistema na venda à clínica | Muitas usam software+planilha+portal; trava a venda | APIs abertas Plug-and-Play; não obrigar a abandonar o legado |
| 10 | Onboarding invasivo que "para" o faturamento | É veto imediato; "e se atrasar meu faturamento?" | Migrar em paralelo — "sem desligar os motores do avião em voo" |
| 11 | Prometer "tirar tudo da mão dele" | Aciona o medo de perda de controle | Prometer **visibilidade**: painel, status por cliente, SLA |
| 12 | "Vamos automatizar tudo" (síndrome do protecionismo) | Equipe interna sente ameaça de demissão e trava a venda | Reposicionar como "Copiloto": automatiza o braçal, não o cognitivo |
| 13 | Recuperar glosa só depois (manualmente) | Custo de contestar pode anular o valor recuperado | Pré-auditoria profilática (validar XML antes do envio) |
| 14 | Operar sem ERP | Gerir milhares de apólices/repasses manualmente é inviável; rompe o cálculo de comissões | ERP de corretagem (multicálculo, baixa automática, dashboards) |
| 15 | Falar só com o dono (ignorar Iniciador e Influenciador) | Ignora quem sente a dor e quem pode vetar (LGPD) | Mapear o centro de compras e endereçar os 3 papéis |

---

## 5. Táticas Acionáveis

### Categoria: Oferta de entrada (porta de baixo risco)
| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| 🜂 "Diagnóstico de Eficiência Operacional" gratuito (30-90 dias) no lugar de proposta | DO | Primeiro contato | Processa dados históricos com IA e expõe "quantos reais perdeu" — "a dor do dinheiro perdido quebra qualquer objeção" |
| Corretora: "Diagnóstico gratuito de 20 movimentações cadastrais" | DO | Persona corretora | Mostra tempo gasto, pendências, gargalos, perda/mês |
| Clínica: "Raio-X de glosas e pendências dos últimos 30-60 dias" | DO | Persona clínica | Faturado × glosado, motivos recorrentes, convênios problemáticos, plano de correção |
| 🜂 "Cavalo de Troia" = Conciliação de Comissões | DO | Por onde começar na corretora | Processo de maior dor e perda financeira direta; resolver ganha a confiança do dono |
| Propor pacote fechado | DON'T | Corretora capixaba | Oferecer **escopo modular** (5 módulos), cliente escolhe por onde começar |

### Categoria: Abordagem e diagnóstico
| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| "Investigue, não apresente" (Challenger Sale) | DO | 1ª reunião | "Quantas horas e quanto caixa sua equipe perde conciliando manualmente os portais?" |
| Roteiro de diagnóstico em 4 blocos | DO | Reunião | Abertura (expertise) → Fiscal (Fator R) → Operacional (gargalos back-office) → Estratégico (sinistralidade/retenção) |
| 🜂 Encerrar com oferta de Diagnóstico sobre amostra real | DO | Call to action | Não propor preço; oferecer auditoria de 1 fatura de comissão ou 1 implantação de PME |
| Roteiro de perguntas fortes | DO | Diagnóstico | "Quantas vidas administram? Quantas operadoras? Se uma pessoa sair amanhã, o processo continua?" |

### Categoria: Mensagem e posicionamento
| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Sequência de 5 passos da mensagem | DO | Copy/abordagem | Dor local → Resultado → Método (IA supervisionada, passo 3) → Segurança (LGPD) → Prova |
| 🜂 Crossover: refratar o valor por persona | DO | Posicionamento | Clínica = "Auditor Médico/Defensor de Receita"; Corretora = "Integrador/Previsor Atuarial" |
| "Para a corretora venda controle operacional; para a clínica venda dinheiro recuperado e caixa previsível" | DO | Tese-âncora | Mesma tecnologia, dois discursos |
| Clínica: separar mensagem por papel | DO | Dono × faturista | Dono = financeira ("receber melhor pelo que já atendeu"); faturista = operacional (pré-conferência de guias) |

### Categoria: Canais
| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Indicação/referral como canal primário | DO | Ambas as personas | Mais alta taxa de conversão do setor; Sincor, operadora parceira, par da indústria |
| WhatsApp com valor imediato | DO | Aproximação | Canal preferencial B2B BR; nunca disparo frio |
| Congressos (Hospitalar, TI em saúde) p/ clínica; fóruns Sincor/CONEC p/ corretora | DO | Prospecção | Decisor de RCM frequenta esses lugares buscando inovação |
| Social selling (LinkedIn com cases reais) | DO | Atração | Atrai o decisor antes do 1º contato |

### Categoria: Tratamento de objeções (dar segurança, não rebater)
| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Perda de controle → prometer **visibilidade** | DO | Ambas | "Você não vai perder controle; vai parar de depender de memória, WhatsApp solto e planilha quebrada" |
| Despersonalização → **white-label** | DO | Corretora boutique | Portal com a marca da corretora; IA como extensão invisível |
| Síndrome do Protecionismo → "Copiloto" | DO | Clínica | Automatiza o braçal, não o cognitivo; libera equipe p/ recuperação de alta complexidade |
| LGPD → segurança nível bancário como ponto de partida | DO | Mitigação de risco | Logs de auditoria, criptografia, anonimização, comitê de dados |
| "IA genérica/minha operação é específica" → provar domínio nativo | DO | Crivo técnico | Construída "de dentro para fora" da saúde suplementar (TUSS, XML TISS, NIP, Rol) + APIs abertas |
| Custo → deslocar para "custo da ineficiência atual" + ROI | DO | Preço | Quantificar comissões não pagas, estornos, erros de cálculo; precificar por vida gerida |

### Categoria: Gestão financeira da corretora (consultoria de valor)
| Tática | Tipo | Quando aplicar | Detalhe |
|--------|------|----------------|---------|
| Operar o Fator R (folha ≥28% → Anexo III) | DO | Corretora pequena/média | Permanecer no Simples e contratar CLT como alavanca fiscal |
| Comprimir despesas administrativas de >15,5% para ~12,5% via automação | DO | Margem | Alavanca complementar pelo lado da despesa |
| Municiar o RH do cliente com histórico de utilização na renovação | DO | Reajuste anual | Contestar tecnicamente reajustes sem memória de cálculo; revelar regra 5/50 |
| Movimentação cadastral grátis acima de 30 vidas | DO | Fidelização | Absorver o custo para proteger a longevidade do contrato principal |

---

## 6. Métricas e Benchmarks

| Métrica | Valor/Range | Contexto | Fonte |
|---------|-------------|----------|-------|
| Vínculos médicos (BR) | ~52,96 mi (abr/2026); >53,2 mi (biênio) | Tamanho do setor | Cap. 1 |
| Vínculos odontológicos | ~35,98 mi | Tamanho do setor | Cap. 1 |
| Movimentação financeira do setor | >R$ 280 bi/ano; receita total R$ 391,6 bi e lucro R$ 24,4 bi (2025) | Recortes distintos, não fundidos | Cap. 1 |
| Concentração de lucro | 3 operadoras = 49% do lucro agregado | Lucro não é homogêneo | Cap. 1 |
| Índice combinado do setor | ~95,3% | Margem operacional mínima | Cap. 1 |
| Taxa de rotatividade (turnover) | 28,8% ao ano | ~1/3 dos vínculos substituídos/ano | Cap. 1 |
| Base coletivo empresarial × individual | ~38,67 mi × ~8,46 mi | Relação contínua, não transacional | Cap. 1 |
| Sinistralidade — faixas | Saudável <70-75%; equilíbrio 85-89%; crítica >85-100% | Define reajuste | Cap. 1 |
| Sinistralidade — setor | Pico 89,2%; média ~81,7% | Asfixia margens | Cap. 1 |
| Custo de internações | até 48% dos custos de um contrato | Severidade financeira | Cap. 1 |
| VCMH (inflação médica) | 15,1% (12 meses, 2026) | Motor dos reajustes | Cap. 1 |
| Reajustes PME (BR) | 6,9% a 43,2% (2025-26); carteiras deficitárias >40% | Renovação = momento sensível | Cap. 1 |
| Glosa — setor inteiro (Painel ANS) | inicial ~7,31% / final ~7,14% | ~6.700 prestadores | Cap. 4 |
| Glosa — grandes hospitais (Anahp) | inicial 15,89% (2024), pico 17% (1T25) / final ~1,96% | Abismo inicial×final | Cap. 4 |
| Glosa em clínicas/hospitais | 10-20% da receita bruta de convênios | Operação geral | Cap. 1 |
| % glosas administrativas (evitáveis) | ~68% | Desloca valor p/ pré-auditoria | Cap. 4 |
| Glosa pode comprometer | até 30% do faturamento bruto anual | Sem processo de recuperação | Cap. 4 |
| PMR grandes hospitais | piorou de 66,6 → 78,5 dias (3T24→3T25) | Descompasso de caixa | Cap. 4 |
| Gap de caixa (PMR−PMP) | ~19 → ~32 dias | Bancado com capital próprio | Cap. 4 |
| Porte da corretora | 80-90% têm ≤7 funcionários; média 4-5 | Tecido enxuto | Cap. 2 |
| Divisão comercial × operacional (consolidadas) | ~56% × ~44% | Backoffice ganha peso com a carteira | Cap. 2 |
| Custo efetivo do funcionário | +73% (Simples) a +112% (Lucro Presumido) | Definido pelo regime tributário | Cap. 2/3 |
| Encargos sobre folha | ~39,4% (Simples) vs ~68% (Lucro Presumido) | Variável de 1ª ordem | Cap. 3 |
| Custo analista back-office (Lucro Presumido) | R$ 5.036,08/mês | Base do ROI | Cap. 3/6 |
| Custo analista (Simples) | R$ 3.816,14/mês | ROI menor, Fator R mais forte | Cap. 3 |
| Trio basal de retaguarda | R$ 15-20 mil/mês de fundo rotativo | 1 coordenador + 2 analistas | Cap. 3 |
| Comissão angariação | 5-15% (multinotas até 250% em 3 meses) | Curto prazo / CAC | Cap. 3 |
| Comissão vitalícia | 2,5-5%, a partir da 4ª mensalidade | Receita recorrente | Cap. 3 |
| Fator R — limiar | ≥28% folha/faturamento → Anexo III (~6% vs 15,5%) | Engenharia tributária | Cap. 3 |
| Churn por insatisfação com corretor | 12% dos beneficiários | Vetor operacional, não de preço | Cap. 3 |
| Pipeline de renovação bem gerido | até ~76% de taxa de renovação | Elimina perda por esquecimento | Cap. 3 |
| RPA reduz tempo administrativo | 30-50% | Backoffice | Cap. 3 |
| Auditoria com ML recupera | 5-20% de custos cobrados errados | Faturas | Cap. 3 |
| Economia BPO vs CLT interno | 40-60% | Motor econômico do BPO | Cap. 4 |
| Custo faturista CLT | >R$ 7.000/mês | Justifica terceirização | Cap. 4 |
| Opacidade de preços do BPO | 8/9 (88,9%) não publicam preço | TISSMED exceção R$ 299/mês | Cap. 4 |
| Regra 5/50 | 5% dos beneficiários = ~50% dos custos | Inteligência de renovação | Cap. 5/6 |
| Pronto-socorro custa | 3-8× mais que consultas ambulatoriais | Alvo da triagem | Cap. 6 |
| Reajuste contratos <30 vidas | 17,85% (2023) → pico 2024 → 14,24% (2025) | Acima dos grandes; impulsiona churn | Cap. 6 |
| Ciclo de venda B2B | ~84 dias (geral); 30-180 dias por tipo; 6-9 meses (complexo) | Não há venda de impulso | Cap. 5 |
| Método de Sales Engagement reduz ciclo | até 35% | Cases validados por pares | Cap. 5 |
| 🜂 ROI da oferta (Lucro Presumido) | 211,7% (R$ 44.469/ano; R$ 2,11 por R$ 1) | 1 posto automatizado | Cap. 6 |
| 🜂 Investimento da oferta | Setup R$ 3.000 + R$ 1.500/mês | R$ 21.000/ano | Cap. 6 |
| 🜂 Ganho em horas | ~50 h/mês devolvidas; redução operacional até 75% | Cadastro 16h→1h; conciliação 20-30h | Cap. 6 |
| 🜂 Preço público BPO (baseline) | TISSMED R$ 299/mês (~100 guias) | Ponto de comparação | Cap. 4 |

---

## 7. Vocabulário Signature

> O domínio do léxico nativo é o **primeiro filtro de credibilidade**. Essencial para o voice_dna de Llif.

### Termos que SEMPRE usa (jargão-âncora)
- **"vidas" / "movimentação cadastral" / "inclusão e exclusão de vidas"** — o vocabulário da corretora
- **"glosa" / "glosa administrativa" / "glosa técnica" / "recurso de glosa"** — o vocabulário do faturamento
- **"lote" / "guia" / "TISS" / "TUSS" / "XML" / "demonstrativo de retorno"** — a língua eletrônica do setor
- **"sinistralidade" / "VCMH" / "reajuste" / "renovação"** — a língua atuarial
- **"Fator R" / "Anexo V → Anexo III" / "Lucro Presumido × Simples"** — a engenharia tributária
- **"PMR / PMP / gap de caixa" / "repasse"** — fluxo de caixa do prestador
- **"batimento cadastral" / "elegibilidade" / "autorização/senha" / "OPME"** — operação
- 🜂 **"BPO Tech" / "Efeito Espelho" / "Insight de Ouro" / "Trio da Eficiência" / "Glosa Zero" / "Crossover" / "Cavalo de Troia" / "Diagnóstico de Eficiência"** — a jogada Cadarn

### Expressões recorrentes
- "A venda é um evento; a manutenção da carteira é um processo sem fim."
- "Ninguém compra BPO nem IA de forma abstrata. O decisor compra **redução de risco operacional**."
- "Para a corretora, venda controle operacional; para a clínica, venda dinheiro recuperado e caixa previsível."
- "Atender é a parte fácil; **receber é o problema**."
- "Impedir a glosa no berço" / "bloquear a glosa no berço"
- "Não se vende IA, vende-se **recuperação de caixa**."
- "Investigue, não apresente."
- "Depois que confia, ele negocia preço."

### Termos que NUNCA usa (ou condena) — armadilhas de abordagem
- **Abrir com "IA"** — assusta o pequeno/médio; IA entra no passo 3 como mecanismo, nunca como promessa
- **"BPO" abstrato / "transformação digital" / "inovação"** — a persona fala a dor do dia a dia, não conceito vago
- **"vamos automatizar tudo" / "tirar tudo da sua mão"** — aciona medo de protecionismo e perda de controle
- **Pitch de produto / telemarketing genérico / argumentação só por funcionalidade** — o dono é refratário
- **Competir por "preço baixo"** — sinaliza falta de diferenciação

### Metáforas e analogias frequentes
- **"Sangramento invisível"** — vida inativa que continua sendo faturada por exclusão não processada
- **"Efeito Espelho das Ineficiências"** — a dor de uma ponta reflete a da outra
- **"Facilitador silencioso e infalível"** — como a IA deve atuar (copiloto), nunca como o produto
- **"Fábrica de digitação"** — o que a corretora é hoje; deve virar "auditora"
- **"Sem desligar os motores do avião em voo"** — migração em paralelo no onboarding
- **"Tábua de salvação"** — a comissão vitalícia em períodos de retração nas vendas
- **"Atendimento de boutique"** — o diferencial relacional da corretora pequena
- **"RH externo"** — o papel que a corretora assume para PMEs sem RH robusto
- **"Cavalo de Troia"** — processo de entrada de menor atrito e maior dor
- **"Wizard of Oz"** — validar operando o motor manualmente antes de automatizar

---

## Metadados de Extração

```yaml
extraction_stats:
  total_files_processed: 9
  total_lines_analyzed: ~2150
  concepts_extracted: 60
  frameworks_extracted: 17
  rules_extracted: 16
  anti_patterns_extracted: 15
  tactics_extracted: 30
  metrics_extracted: 45
  vocabulary_terms: 40
  dedup_removals: ~25
  cross_references: 12
  confidence_score: "88%"
  confidence_note: >
    Material excepcionalmente rastreável (toda afirmação cita [fonte:]) e completo nas 7 dimensões,
    o que daria base 100% + bônus de cross-reference. Penalidade aplicada (-12%) porque:
    (1) a fonte NÃO tem frontmatter Echo (agent_id: aiox-m2m-etl) — é corpus curado, não M2M, acionando
    o WARNING de error_handling da task; (2) a dimensão 7 (voz signature) reflete o léxico do setor +
    a moldura prescritiva Cadarn, não a idiossincrasia de um único especialista humano.
  prescriptive_flag: "Itens marcados 🜂 vêm da camada prescritiva (Cap. 6 / Anexo A) — hipótese a validar, não fato de mercado."
```

---

_Extraído por Athena (knowledge-miner) v1.0 — 2026-06-28_
_"Não inventar — minerar. O especialista já disse tudo; nosso trabalho é organizar."_
