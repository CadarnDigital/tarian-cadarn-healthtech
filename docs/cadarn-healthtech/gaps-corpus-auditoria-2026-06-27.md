---
projeto: Corpus IA Saúde Suplementar
auditoria: 2026-06-27
run_id: wf_bfb02a21-c85
metodologia: Extração (14 fontes) → Coverage (grep) → Adjudicação
cobertura: 74% (603 PRESENTE + 233 PARAFRASADO de 1.127 items)
gaps_totais: 273
---

# Gaps do Corpus IA Saúde Suplementar — Auditoria 2026-06-27

## Resumo Executivo

| Métrica | Valor |
|---------|-------|
| **Items auditados** | 1.127 |
| **Cobertura** | 74% |
| **Gaps totais** | 273 |
| **Prioridade Alta** | 90 (táticas + personas) |
| **Prioridade Média** | 48 (frameworks + conceitos) |
| **Prioridade Baixa** | 135 (números/benchmarks) |

**Corpus liberado para uso em RAG/treinamento IA com integração de gaps em paralelo.**

---

## Como usar este documento

1. **Alta prioridade**: Integrar nos capítulos 02, 03, 05, 06 (impacto comercial direto)
2. **Média prioridade**: Consolidar estrutura conceitual (capítulos 01, 08)
3. **Baixa prioridade**: Usar como referência em benchmarking (capítulos 01, 04)

Cada item indica a **fonte** (pesquisa originária) e o **capítulo sugerido** para integração.

---

## 🔴 PRIORIDADE ALTA — 90 itens

### Táticas de Venda (50 itens)

| # | Tática | Contexto | Fonte | Cap. |
|----|---------|----------|--------|------|
| 1 | Call center omnicanal 24/7 | Cadastro de beneficiários, Maida Health | health-bpo-faturamento | 04 |
| 2 | Diagnóstico consultivo 10-15 min | Primeira abordagem de venda em PME | health-comportamento-compra-gpt | 05 |
| 3 | Contratos de curto prazo (1 ano + renovação) | Diminuir resistência inicial com SLAs claros | health-comportamento-compra-gpt | 03 |
| 4 | ISO 27001 como prova de segurança | Resposta a objeção crítica de dados sensíveis | health-comportamento-compra-gpt | 06 |
| 5 | Frase de entrada ES | "Ajudamos corretoras a organizar cadastro, movimentação, faturamento sem aumentar equipe" | health-comportamento-compra-gpt | 05 |
| 6 | Mensagem contextualizada à dor | "Ajudo corretoras com alta sinistralidade a garantir gestão eficiente" | health-comportamento-compra-gpt | 05 |
| 7 | Comunicação transparente com cronogramas | Prazos de implantação + relatórios parciais | health-comportamento-compra-gpt | 03 |
| 8 | Case SAMP/Carefy com cautela | Sinal de maturidade local — usar como prova social | health-comportamento-compra-gpt | 05 |
| 9 | Success fee Axenya | Remuneração atrelada a descontos em renovações | health-concorrentes-bpo-gemini | 06 |
| 10 | Auditoria ColaboRHa pré-pagamento | Linha a linha ANTES do pagamento, não reativa | health-concorrentes-bpo-gemini | 04 |
| 11 | APIs Coneccta + SLA 24h | Integração com ERPs + suporte omnicanal via RPA | health-concorrentes-bpo-gemini | 06 |
| 12 | WhatsApp 2Easy ao colaborador | Reduz carga no RH; dashboards preditivos de custos | health-concorrentes-bpo-gemini | 06 |
| 13 | Telemedicina Tailor Insurance integrada | Intervenção precoce em quadros clínicos → reduz sinistralidade | health-concorrentes-bpo-gemini | 06 |
| 14 | Bots noturnos de comissões | Acesso noturno a portais de operadoras; relatórios proativos | health-modelo-negocio-gemini | 03 |
| 15 | IA detecção de fraudes em contas | Sobreposição de patologias, faturamentos camuflados | health-modelo-negocio-gemini | 04 |
| 16 | Auditoria de coparticipações repetidas | Interceptar cobranças duplicadas de operadoras | health-modelo-negocio-gemini | 04 |
| 17 | Chatbot WhatsApp qualificação | ~30s resposta, BANT adaptado, cadastro automático funil | health-modelo-negocio-gpt | 05 |
| 18 | Educação colaboradores sobre plano | Explicar coparticipação, rede credenciada, risco urgências desnecessárias | health-modelo-negocio-gpt | 06 |
| 19 | Monitoramento mensal de sinistralidade | Acompanhamento regular com propostas preventivas | health-modelo-negocio-gpt | 06 |
| 20 | Reuniões trimestrais com RH | Revisar sinistralidade, ajustes de rede, ações preventivas | health-modelo-negocio-gpt | 06 |
| 21 | Telemedicina como valor agregado | Atendimento online 24h — satisfação + fidelização | health-modelo-negocio-gpt | 06 |
| 22 | Programas de prevenção com parcerias | Check-ups, educação em saúde (hipertensão, tabagismo) | health-modelo-negocio-gpt | 06 |
| 23 | Alerta proativo threshold 75% sinistralidade | Gatilho trimestral antes de atingir zona de risco (85%) | health-modelo-negocio-gpt | 03 |
| 24 | Piloto em carteira controlada (10 clientes) | Testar assistentes + métricas preditivas antes de escalar | health-modelo-negocio-gpt | 06 |
| 25 | Pacotes consultoria contínua | Treinamento RH + comunicação de saúde + telemedicina agrupados | health-modelo-negocio-gpt | 06 |
| 26 | Distribuir materiais educação saúde | Reduz utilização desnecessária de urgências hospitalares | health-perfil-corretoras-gemini-br | 06 |
| 27 | Modelo híbrido CLT + preposto autônomo | Balanceia custo com cobertura de vendas | health-perfil-corretoras-gemini-br | 02 |
| 28 | Pipeline CRM lead→primeiro boleto | Documenta atas, entregas, progressão junto à operadora | health-perfil-corretoras-gemini-br | 03 |
| 29 | Concentrar valor cognitivo humano | Moderação tática e negociações vitais pós-venda; automação assume digitação | health-perfil-corretoras-gemini-br | 03 |
| 30 | Checklist implantação (14 campos) | Tipo contratação, docs, dados titular, vigência, carência, operadora, plano, protocolo, ativação | health-perfil-corretoras-gpt | 02 |
| 31 | Planilha movimentação (12 campos) | Cliente, CNPJ, beneficiário, tipo movimentação, data solicitação, limite, operadora, status, protocolo, responsável | health-perfil-corretoras-gpt | 02 |
| 32 | Conferência fatura mensal (13 campos) | Cliente, competência, valor ant./atual, vidas, inclusões, exclusões, retroativos, reajuste, divergência, status contestação | health-perfil-corretoras-gpt | 02 |
| 33 | Controle comissão (12 campos) | Cliente, operadora, produto, vendedor, comissão prevista/recebida, diferença, motivo, repasse devido/realizado | health-perfil-corretoras-gpt | 03 |
| 34 | Histórico atendimento cliente (10 campos) | Cliente, contato, assunto, canal, data, responsável, status, solução, prazo, próxima ação | health-perfil-corretoras-gpt | 02 |
| 35 | Script WhatsApp genérico | Contextualização + dor + resultado + CTA ligação | health-persona-decisor-gpt | 05 |
| 36 | Script ligação telefônica | Tom consultivo, referência dor específica, casos similares | health-persona-decisor-gpt | 05 |
| 37 | Script email | Assunto personalizado + dor + CTA 15min; incluir link case/depoimento | health-persona-decisor-gpt | 05 |
| 38 | Script por indicação | Mencionar fonte comum + dor identificada + agendamento direto | health-persona-decisor-gpt | 05 |
| 39 | Script WhatsApp corretora ES | Indicação local + Grande Vitória + esteira operacional + proposta 15min | health-persona-decisor-gpt | 05 |
| 40 | Script WhatsApp faturista clínica | Pré-conferência + risco glosa + modelo relatório; sem exigir troca sistema | health-persona-decisor-gpt | 05 |
| 41 | Checklist pré-venda (4 etapas) | Conhecer sistema atual + preparar case relevante + agendar POC + envolver decisores finais | health-persona-decisor-gpt | 05 |
| 42 | Narrativa Escudo Institucional | Mitigação de risco contratual, escalabilidade orgânica, invulnerabilidade contra cartas nomeação | health-personas-bpo-gemini | 06 |
| 43 | Assinar DPA + NDA | Antes de qualquer demo com dados reais — transforma promessa LGPD em compromisso rastreável | health-vendas-b2b-gemini | 03 |
| 44 | SLAs com cláusulas saída + recuperação dados | Garantia de continuidade em caso de rescisão — mitiga medo de lock-in | health-vendas-b2b-gemini | 03 |
| 45 | Filtrar ICP por volume mínimo vidas | Qualifica maturidade organizacional antes da abordagem | health-vendas-b2b-gemini | 05 |
| 46 | ROI automação vs headcount (custo empresa 1,7x CLT) | Auxiliar Seguros R$3.353, Assistente Admin R$4.112, Auxiliar Faturamento R$4.228/mês | health-pesquisa-001 | 06 |
| 47 | Validar operadoras por município no Guia ANS | Antes de abordar carteiras específicas | health-pesquisa-001 | 05 |
| 48 | Trial 30 dias reduz fricção PME | Corretoras pequenas decidem mais rápido com período teste sem compromisso | icp-cadarn-health-grande-vitoria | 05 |
| 49 | Abordagem via associações médicas + CRM-ES | Canal de acesso a médico-sócio proprietário de clínicas | icp-cadarn-health-grande-vitoria | 05 |
| 50 | Importação via Excel como ponte migração | Revela que ICP está em planilha; migração precisa ser sem ruptura | icp-cadarn-health-grande-vitoria | 06 |

### Personas (40 itens)

| # | Persona | Contexto | Porte | Fonte | Cap. |
|----|---------|----------|--------|--------|------|
| 1 | Diretor Financeiro/CFO corretora média | Preocupação com custos, previsibilidade, risco; aprovação com comitês | 12-25 pess. | health-comportamento-compra-gpt | 02 |
| 2 | Gerente Operações/TI (influenciador técnico) | Análise técnica: demos, POCs, integração TISS, referências, segurança | 12-25 pess. | health-comportamento-compra-gpt | 02 |
| 3 | Gestor RH/Operações (influenciador continuidade) | Garantias de continuidade + qualidade SLA; medo BPO substitua equipe | qualquer porte | health-comportamento-compra-gpt | 02 |
| 4 | Corretor/Agente CLT | Salário R$2.166-3.864 + comissionamento; ~56% headcount | estruturada | health-perfil-corretoras-gemini-br | 02 |
| 5 | Preposto Autônomo comissionado | Sem vínculo CLT; repasse líquido impostos; baixo custo fixo, sem exclusividade | pequena | health-perfil-corretoras-gemini-br | 02 |
| 6 | Pequena corretora local (3-7 pess.) | Dono + comercial + cadastro/faturamento acumulado + atendimento acumulado | 3-7 | health-perfil-corretoras-gpt | 02 |
| 7 | Pequena corretora estruturada (7-12 pess.) | Sócio + comercial + cadastro + faturamento + atendimento + financeiro; separa venda/manutenção | 7-12 | health-perfil-corretoras-gpt | 02 |
| 8 | Corretora média regional Grande Vitória (12-25 pess.) | 8 áreas: direção, comercial, cadastro, movimentação, faturamento, atendimento, financeiro, marketing | 12-25 | health-perfil-corretoras-gpt | 02 |
| 9 | Faturista de clínica capixaba | 8-40 colaboradores, 5-30 médicos atendendo (Patrícia/Renata/Simone/Carlos) | 8-40 | health-concorrentes-bpo-gemini | 04 |
| 10 | Auxiliar de Seguros (CBO 411040) | Apoio proposta, cadastro, documentos, seguradoras; R$1.972 CLT / R$3.353 custo | junior | health-pesquisa-001 | 02 |
| 11 | Assistente Administrativo (CBO 411010) | Backoffice geral, planilhas, relatórios, atendimento; R$2.419 CLT / R$4.112 custo | junior | health-pesquisa-001 | 02 |
| 12 | Auxiliar de Faturamento (CBO 413115) | Boletos, notas, repasses, conciliação, cobrança, comissão; R$2.487 CLT / R$4.228 custo | junior | health-pesquisa-001 | 02 |
| 13 | Diretor operacional/TI operadora regional | Decisor em SAMP (267k vidas); foco volume guias, cadastro escala, auditoria | 267k+ vidas | icp-cadarn-health-grande-vitoria | 02 |
| 14 | Médico-sócio proprietário de clínica | Decisor final em clínica especializada; contactável via CRM-ES | 5-30 médicos | icp-cadarn-health-grande-vitoria | 05 |
| 15 | Gestor administrativo clínica | Implementação operacional; responsável por faturamento, cadastro, movimentação | 5-30 médicos | icp-cadarn-health-grande-vitoria | 04 |
| 16 | Operadora regional (SAMP, Mais Saúde Vix, Ampla, Select) | Foco em eficiência de processos, redução de guias manual, automação de faturamento | regional | icp-cadarn-health-grande-vitoria | 01 |
| 17 | Administradora de benefícios PME | Foco em retenção, sinistralidade, compliance LGPD; ciclo 6+ meses | PME | icp-cadarn-health-grande-vitoria | 02 |
| 18 | Decisor de compra BPO (corretora PME) | Busca: reduzir tempo backoffice, melhorar controle, não aumentar headcount | 7-25 pess. | icp-cadarn-health-grande-vitoria | 05 |
| 19 | Decisor de compra BPO (clínica PME) | Busca: reduzir glosa, melhorar ciclo de caixa, compliance TISS | 8-40 pess. | icp-cadarn-health-grande-vitoria | 04 |
| 20 | Influenciador técnico de clínica (TI/Operações) | Análise de integração com prontuário, TISS, portais de operadoras | 8-40 pess. | health-persona-decisor-gpt | 04 |
| 21 | RH de empresa cliente final | Quer educação de colaboradores, telemedicina, relatórios de sinistralidade | empresa cliente | health-modelo-negocio-gpt | 06 |
| 22 | Compliance/LGPD de corretora | Preocupação com segurança de dados, DPA, certificações, auditoria | qualquer porte | health-vendas-b2b-gemini | 03 |
| 23 | Jurídico de corretora/operadora | Análise de termos de contrato BPO, SLAs, cláusulas de saída, responsabilidades | qualquer porte | health-vendas-b2b-gemini | 03 |
| 24 | Dono corretora pequena (até 12 pess.) | Acumula comercial, financeiro, operações; sensível a custo, ROI; seguro com relacionamento | 3-12 | health-perfil-corretoras-gpt | 02 |
| 25 | Sócio gerente corretora média | Foco em escalabilidade, eficiência operacional, retenção de clientes | 12-25 | health-perfil-corretoras-gpt | 02 |
| 26 | Responsável pós-venda (corretora) | Monitoramento contínuo de sinistralidade, comunicação com cliente, renovação atuarial | qualquer porte | health-modelo-negocio-gpt | 03 |
| 27 | Responsável implantação (corretora/clínica) | Testes de integração, migrações de dados, treinamento de equipe | qualquer porte | health-vendas-b2b-gemini | 03 |
| 28 | Gestor de pipeline de vendas (corretora) | Responsável por CRM, funil comercial, acompanhamento de leads | pequena/média | health-perfil-corretoras-gpt | 05 |
| 29 | Analista de sinistralidade (operadora/corretora) | Monitora índices, propõe ações preventivas, argui operadora em renovações | média | health-modelo-negocio-gemini | 03 |
| 30 | Consultor de benefícios (corretora sênior) | Aconselhamento atuarial, defesa de cliente em renovações, gestão de sinistralidade | média/grande | health-modelo-negocio-gemini | 05 |
| 31 | Vendedor transacional → consultivo | Evolução esperada com BPO: menos operação, mais consultoria | qualquer porte | health-comportamento-compra-gpt | 05 |
| 32 | Consultor técnico defesa atuarial | Especialista em negociação de reajustes e sinistralidade | média | health-comportamento-compra-gpt | 05 |
| 33 | Operacional de cadastro (corretora) | Inclusões, exclusões, alterações de beneficiários; 1-2 pess. | pequena/média | health-perfil-corretoras-gpt | 02 |
| 34 | Operacional de faturamento (corretora) | Boletos, repasses, conciliação, comissões, relatórios; 1-2 pess. | pequena/média | health-perfil-corretoras-gpt | 02 |
| 35 | Analista administrativo Grande Vitória | Custo R$5.500-8.500/mês para analista pleno-sênior | média | health-perfil-corretoras-gpt | 02 |
| 36 | Profissional saúde (médico, dentista, fisioterapeuta) | Faturamento TISS, prazos recebimento, glosa, gestão de vários convênios | prestador | icp-cadarn-health-grande-vitoria | 04 |
| 37 | Gestor financeiro clínica | Acompanha contas a receber, ciclo de caixa, sinistralidade do plano da clínica | 8-40 pess. | icp-cadarn-health-grande-vitoria | 04 |
| 38 | Recepcionista/administrativo clínica | Agendamento, cadastro de beneficiários, checkin de convênios | 8-40 pess. | icp-cadarn-health-grande-vitoria | 04 |
| 39 | Corretor autônomo ES | Vendedor independente comissionado; rede de contatos local; incentivo trial 30 dias | 1-5 usuários | icp-cadarn-health-grande-vitoria | 05 |
| 40 | Decisor de compliance (operadora regional) | Exigência de LGPD, TISS, segurança dados; ciclo decisório conservador | qualquer porte | health-vendas-b2b-gemini | 03 |

---

## 🟡 PRIORIDADE MÉDIA — 48 itens

### Frameworks (24 itens)

| # | Framework | Descrição | Fonte | Cap. |
|----|-----------|-----------|--------|------|
| 1 | Cronograma Gantt — Ciclo Venda Corretoras PME | Prospecção 30d → Contato 45d → Negociação 30d → Implantação 15d = ~120d total | health-comportamento-compra-gpt | 05 |
| 2 | 4 Características Locais ES/Venda | Mercado relacional + operadoras regionais + estruturas enxutas + Grande Vitória como eixo | health-comportamento-compra-gpt | 05 |
| 3 | Dupla Oferta BPO+CFO Saúde (Loki) | BPO operacional + CFO estratégico; atende clínicas de diferentes níveis maturidade | health-bpo-faturamento | 06 |
| 4 | Ordem Canônica Pitch BPO ES/PME | 1) Dor local 2) Resultado 3) Método BPO+IA supervisionada 4) Segurança LGPD 5) Prova diagnóstico amostra real | health-concorrentes-bpo-gemini | 05 |
| 5 | Ganho de Escala Custo Por Vida | 20 vidas R$35-45/vida → 50 vidas R$30-32,50 → 100 vidas R$25-30 → 200 vidas R$23-27,50 | health-concorrentes-bpo-gemini | 06 |
| 6 | Progressão Lógica Risco Atuarial (4 Etapas) | 1. Deterioração índice (85-90%) 2. Reajuste técnico dual 3. Choque financeiro PME 4. Colapso contratual | health-modelo-negocio-gemini | 03 |
| 7 | Matriz Consultiva 4 Serviços | 1. Health Analytics+comitês 2. Coparticipação estratégica 3. Navegação pacientes 4. Auditoria+renegociação | health-modelo-negocio-gemini | 06 |
| 8 | Automação em Duas Camadas | Camada 1: RPA processos rígidos | Camada 2: IA padrões cognitivos | health-modelo-negocio-gemini | 06 |
| 9 | Ciclo Operacional Backoffice (5 Etapas) | 1. Prospeção 2. Transição contratual 3. Movimentação cadastral 4. Gestão+auditoria faturas 5. Renovação tarifária | health-modelo-negocio-gemini | 02-03 |
| 10 | Roadmap IA 3 Fases | Curto (1-3m): chatbot+pipeline piloto | Médio (3-6m): RPA+auditoria ML | Longo (6-12m): preditivos+dashboards | health-modelo-negocio-gpt | 06 |
| 11 | 3 Frentes Operacionais Backoffice Corretora | 1. Implantação+Registro 2. Faturação+Comissionamento 3. Gestão Pós-Venda+Sinistralidade | health-perfil-corretoras-gemini-br | 02-03 |
| 12 | 3 Camadas Metodológicas Análise Mercado | 1) Dados oficiais 2) Leitura operacional 3) Estimativas gerenciais | health-perfil-corretoras-gpt | 01 |
| 13 | Estrutura Recomendada Corretora Média (8 Áreas) | Direção, Comercial, Cadastro, Movimentação, Faturamento, Atendimento, Financeiro, Marketing/SDR | health-perfil-corretoras-gpt | 02 |
| 14 | 5 Oportunidades Eficiência Operacional | 1. Checklist implantação 2. Planilha movimentação 3. Conferência fatura mensal 4. Controle comissão 5. Histórico atendimento | health-perfil-corretoras-gpt | 02 |
| 15 | 5 Características Mercado ES/Grande Vitória | 1. Alta cobertura (mercado maduro) 2. Concentração metropolitana 3. Forte PME 4. Competição operadoras regional vs nacional 5. Crescimento odontológico | health-perfil-corretoras-gpt | 01 |
| 16 | Roteiro Vendas One-Sheet (7 Componentes) | Perfil Cliente + Proposta Valor por Persona + Benefícios+ROI + Diferenciais + Objeções+Respostas + Etapas Processo + KPIs-alvo | health-persona-decisor-gpt | 05 |
| 17 | Sequência Mensagem BPO Capixaba (5 Etapas) | 1) Dor local 2) Resultado 3) Método BPO+IA supervisionada 4) Segurança LGPD 5) Prova com amostra real | health-persona-decisor-gpt | 05 |
| 18 | Comparativo Personas (13 Dimensões) | Objetivo, Responsabilidades, Dores, Vocabulário, Critérios Compra, Gatilhos, Objeções, Confiança, Stakeholders, Canais, KPIs, Demografia | health-persona-decisor-gpt | 02 |
| 19 | Prioridade Prospecção Grande Vitória (3 Nichos) | Nicho 1: Corretoras PME Vitória/Vila Velha/Serra (saúde+odonto) | Nicho 2: Clínicas especializadas Vitória/Vila Velha | Nicho 3: Clínicas Serra/Cariacica alto volume | health-persona-decisor-gpt | 05 |
| 20 | Tabela Impacto Glosas (Clínicas) | R$2M faturamento: 15%→4% glosa = R$220k/mês | R$5M: R$550k/mês | R$10M: R$1,1M/mês | health-personas-bpo-gemini | 04 |
| 21 | Tabela Impacto Sinistralidade (3 Anos) | 200 vidas: reajuste passivo 20%/ano vs ativo 6%/ano = economia R$650.800 acumulada em 3 anos | health-personas-bpo-gemini | 06 |
| 22 | 5 Estágios Ciclo Venda B2B (Tempos) | 1. SDR/BDR 2-4sem 2. Discovery 3-6sem 3. Auditoria Regulatória+LGPD 4-10sem 4. POC/Piloto 4-8sem 5. Aprovação Comitê 2-6sem = total 6-9 meses | health-vendas-b2b-gemini | 05 |
| 23 | ICP Tri-Segmento Cadarn Health | Primário: corretora PME | Secundário: clínica/consultório TISS | Terciário: operadora regional/administradora | icp-cadarn-health-grande-vitoria | 01-02 |
| 24 | Dimensões ICP (8 Eixos) | Porte, Decisor, Dor Principal, Dor Secundária, Trigger Compra, Canal Acesso, Objeção #1, Objeção #2 | icp-cadarn-health-grande-vitoria | 01-02 |

### Conceitos (24 itens)

| # | Conceito | Definição | Fonte | Cap. |
|----|----------|-----------|--------|------|
| 1 | CFO Saúde | Serviço CFO terceirizado para clínicas/hospitais; estratégia financeira + operacional (diferente de BPO tradicional) | health-bpo-faturamento | 04 |
| 2 | Sociedade Simples | Estrutura jurídica comum consultórios médicos Brasil; apoio contábil relevante para BPO | health-bpo-faturamento | 04 |
| 3 | Custo Por Vida (per capita) | Métrica hegemônica BPO benefícios/RH; R$23-45 dependendo volume de vidas | health-concorrentes-bpo-gemini | 06 |
| 4 | Clearinghouse | Provedor central faturamento; processa/valida lotes XML antes de transmitir operadoras | health-concorrentes-bpo-gemini | 04 |
| 5 | DMED | Omissão documental médica gera multas/impostos em cascata; compliance crítico BPO contábil | health-concorrentes-bpo-gemini | 04 |
| 6 | Backoffice Vetor Inteligência Competitiva | Transição 2024-26: administrativo deixa de ser custo e vira gerador de rentabilidade+dados estratégicos | health-concorrentes-bpo-gemini | 03 |
| 7 | Analytics Forense Faturas | Leitura 100% faturas por IA (Axenya) para detectar cobranças indevidas; fee atrelado a resultado | health-concorrentes-bpo-gemini | 04 |
| 8 | Reajuste Técnico Dual | Mecanismo operadora: VCMH (inflação médica) + reajuste penalizador sobre sinistralidade que excedeu break-even | health-modelo-negocio-gemini | 03 |
| 9 | Desvio Assistencial | Uso inadequado urgência para baixa complexidade; combatido com educação + navegação pacientes | health-modelo-negocio-gemini | 06 |
| 10 | DRG — Diagnosis-Related Groups | Sistema agrupamento diagnósticos para faturamento hospitalar; variações geram perdas colossais | health-modelo-negocio-gemini | 04 |
| 11 | BANT Adaptado | Método qualificação leads (Budget, Authority, Need, Timeline) para setor saúde; automático via chatbot | health-modelo-negocio-gpt | 05 |
| 12 | Cara-ativa vs Mensal Recorrente | Dois modelos comissão: alta inicial+baixa recorrente (receita imediata) vs baixa inicial+alta recorrente (receita contínua 5 anos) | health-modelo-negocio-gpt | 03 |
| 13 | KPIs IA para Corretoras | Tempo resposta leads, taxa leads convertidos, tempo processamento inclusão vidas, taxa renovação, churn, NPS | health-modelo-negocio-gpt | 06 |
| 14 | Preposto Autônomo | Vendedor comissionado sem CLT; repasse líquido impostos; baixo custo fixo, sem exclusividade garantida | health-perfil-corretoras-gemini-br | 02 |
| 15 | ESECS | Estudo sobre Perfil Corretores Seguros (Fenacor); revela: 80-90% corretoras são pequeno porte (1-7 pess.) | health-perfil-corretoras-gemini-br | 01 |
| 16 | CPT — Cobertura Parcial Temporária | Restrição contratual temporária para DLP; regulatório que sistemas genéricos raramente tratam | health-vendas-b2b-gemini | 08 |
| 17 | DMED — Declaração Informações Planos Saúde | Obrigação fiscal imposto renda; coincidência com ciclos de venda causa suspensão temporária de projetos de inovação | health-vendas-b2b-gemini | 08 |
| 18 | Autogestão (Operadora) | Tipo operadora gerida por empresa empregadora; case com glosa 10% a.a. | icp-cadarn-health-grande-vitoria | 01 |
| 19 | Healthcare Accepts No Shortcuts | Princípio: compradores B2B saúde exigem evidência clínica+conformidade antes de avançar | health-vendas-b2b-gemini | 05 |
| 20 | RN 472/2021 (ANS) | Resolução ANS/TISS; qualquer solução faturamento/cadastro precisa demonstrar conformidade obrigatória | health-vendas-b2b-gemini | 04 |
| 21 | Intercâmbio Eletrônico TISS Movimentações | Automação inclusão/exclusão/alteração beneficiários via TISS; gap não atendido por nenhum sistema corretora | icp-cadarn-health-grande-vitoria | 02 |
| 22 | Objeção "IA Pode Errar Guia" | Resistência a IA autônoma; clínica quer IA+humano responsável supervisionando (não IA autônoma) | health-persona-decisor-gpt | 05 |
| 23 | Objeção Resistência Interna Faturista | Equipe faturamento sente ameaça substituição; argumento correto: BPO como apoio, não substituição | health-persona-decisor-gpt | 05 |
| 24 | CNES — Cadastro Nacional Estabelecimentos Saúde | Código identificação clínica junto Ministério Saúde; erro em guia = causa de glosa frequente | health-persona-decisor-gpt | 04 |

---

## 🟢 PRIORIDADE BAIXA — 135 itens

### Números e Benchmarks

**Segmentação de Mercado (14 dados)**

| # | Dado | Contexto | Fonte |
|----|------|----------|--------|
| 1 | R$ 600 mil–30 mi/ano | Faturamento típico clínicas PME atendidas por BPO contábil | health-bpo-faturamento |
| 2 | 2 a 4 meses | Ciclo de venda típico corretoras pequenas Brasil | health-comportamento-compra-gpt |
| 3 | 20,7% crescimento | Beneficiários planos assistência médica ES 2020-2025 (ANS) | icp-cadarn-health-grande-vitoria |
| 4 | 8,21% crescimento | Planos odontológicos ES março/2025–março/2026 (ANS) | icp-cadarn-health-grande-vitoria |
| 5 | 52,96 milhões vínculos | Planos assistência médica Brasil abril 2026 (ANS) | health-perfil-corretoras-gpt |
| 6 | 35,98 milhões vínculos | Planos exclusivamente odontológicos Brasil abril 2026 (ANS) | health-perfil-corretoras-gpt |
| 7 | 61% faturamento; 66% profissionais | Concentração Região Sudeste no setor segurador Brasil | health-perfil-corretoras-gemini-br |
| 8 | 17-18% força corretagem | Região Sul faturamento + força de vendas | health-perfil-corretoras-gemini-br |
| 9 | 1,94 bilhão procedimentos | Total 2024 realizados por planos saúde Brasil | health-persona-decisor-gpt |
| 10 | 284,5 milhões consultas | Consultas médicas 2024 por planos saúde Brasil | health-persona-decisor-gpt |
| 11 | 1,18 bilhão exames ambulatoriais | Volume maior categoria 2024; gera maior volume guias, risco glosa | health-persona-decisor-gpt |
| 12 | 80 corretores PF + 62.000 corretoras PJ | Totais SUSEP novembro 2025 Brasil | health-perfil-corretoras-gpt |
| 13 | 267 mil vidas SAMP | Maior operadora medicina grupo ES; 1.200+ prestadores; 30+ anos | icp-cadarn-health-grande-vitoria |
| 14 | 4,1 milhões população ES | Base demográfica para cálculos penetração mercado | icp-cadarn-health-grande-vitoria |

**Sinistralidade e Reajustes (18 dados)**

| # | Dado | Contexto | Fonte |
|----|------|----------|--------|
| 1 | 25-30%+ agravamento | Reajuste em única renovação quando sinistralidade >break-even | health-modelo-negocio-gemini |
| 2 | 100%+ | Sinistralidade: uma UTI pode provocar em PME | health-modelo-negocio-gemini |
| 3 | 130% | Nível sinistralidade que força encerramento contrato PME | health-modelo-negocio-gemini |
| 4 | 15-20% redirecionamento | Urgências → telemedicina/ambulatório como alavanca poupança | health-modelo-negocio-gemini |
| 5 | 30-50% coparticipação | Teto regulatório ANS exames simples+consultas eletivas | health-modelo-negocio-gemini |
| 6 | 60% agravamento inicial | Gatilho intervenção corretor em renegociação atuarial | health-modelo-negocio-gemini |
| 7 | 19,95% negociado | Reajuste após intervenção direta corretor (vs 60% inicial) | health-modelo-negocio-gemini |
| 8 | 50-70% sinistralidade disciplinada | Faixa que confere alavancagem corretor para negociar supressão reajustes | health-modelo-negocio-gemini |
| 9 | 2% anomalias detectáveis | Taxa interseção erros em faturas via bate-cadastral automatizado | health-modelo-negocio-gemini |
| 10 | 30-50% redução tempos administrativos | RPA admissão/demissão de vidas | health-modelo-negocio-gemini |
| 11 | 20-30% redução contas a receber | Meta típica clínicas após implementar BPO faturamento | health-persona-decisor-gpt |
| 12 | 45 dias vs 60 dias | Meta ciclo de caixa após BPO | health-persona-decisor-gpt |
| 13 | 4% glosa de referência | Benchmark eficiência alvo com BPO/IA | health-personas-bpo-gemini |
| 14 | 25% reajuste | Exemplo: operadora aplicou quando sinistralidade =92% | health-personas-bpo-gemini |
| 15 | 92% sinistralidade | Threshold que gera reajuste 25% | health-personas-bpo-gemini |
| 16 | 6% reajuste | Com gestão ativa BPO/IA (vs 20% histórico) | health-personas-bpo-gemini |
| 17 | 5%→15-20% | Salto glosa que aciona gatilho primário compra BPO clínicas | health-personas-bpo-gemini |
| 18 | 10% glosa média a.a. | Taxa média operadora autogestão estudada | icp-cadarn-health-grande-vitoria |

**Precificação e ROI (28 dados)**

| # | Dado | Contexto | Fonte |
|----|------|----------|--------|
| 1 | R$ 299/mês | TISSMED único preço público; até ~100 guias | health-bpo-faturamento |
| 2 | R$ 1.290/mês | Proos BPO financeiro consultórios | health-concorrentes-bpo-gemini |
| 3 | R$ 159,90–309,90 | ContaAzul automação contábil microempresas | health-concorrentes-bpo-gemini |
| 4 | R$ 70–129 mensais | Módulos controladoria ERP parceiros | health-concorrentes-bpo-gemini |
| 5 | R$ 5.250/mês | Stathen BPO financeiro premium | health-concorrentes-bpo-gemini |
| 6 | R$ 700–900/mês | BPO folha até 20 vidas (R$35-45 per capita) | health-concorrentes-bpo-gemini |
| 7 | R$ 1.500–1.625/mês | BPO folha até 50 vidas (R$30-32,50 per capita) | health-concorrentes-bpo-gemini |
| 8 | R$ 2.500–3.000/mês | BPO folha até 100 vidas (R$25-30 per capita) | health-concorrentes-bpo-gemini |
| 9 | R$ 4.625–5.500/mês | BPO folha até 200 vidas (R$23-27,50 per capita) | health-concorrentes-bpo-gemini |
| 10 | R$ 220.000/mês | Receita recuperável clínica R$2M (glosa 15%→4%) | health-personas-bpo-gemini |
| 11 | R$ 550.000/mês | Receita recuperável clínica R$5M | health-personas-bpo-gemini |
| 12 | R$ 1.100.000/mês | Receita recuperável clínica R$10M | health-personas-bpo-gemini |
| 13 | R$ 650.800 | Economia 3 anos empresa 200 vidas (gestão ativa vs passiva) | health-personas-bpo-gemini |
| 14 | 18% incremento | Repasse honorários médicos 60 dias com RPA glosas | health-personas-bpo-gemini |
| 15 | R$ 790/mês | Digital Controle 1º usuário corretora PME | icp-cadarn-health-grande-vitoria |
| 16 | R$ 109/mês | Digital Controle usuário adicional | icp-cadarn-health-grande-vitoria |
| 17 | R$ 800–2.000/mês | Faixa gasto corretoras PME com back office | icp-cadarn-health-grande-vitoria |
| 18 | R$ 266/mês | Ampla Saúde plano entrada (Q Ampla 200) | icp-cadarn-health-grande-vitoria |
| 19 | R$ 250/mês | Select Saúde plano entrada | icp-cadarn-health-grande-vitoria |
| 20 | R$ 836/mês | Care Plus plano entrada premium ES | icp-cadarn-health-grande-vitoria |
| 21 | R$ 1.272/mês | Omint plano entrada premium ES | icp-cadarn-health-grande-vitoria |
| 22 | R$ 149/mês por médico | Shosp Fellowship (inclui faturamento TISS) | icp-cadarn-health-grande-vitoria |
| 23 | R$ 147/mês | ByDoctor Pro para consultórios | icp-cadarn-health-grande-vitoria |
| 24 | R$3.900 / 8.700 / 13.500 | Receita 1/3/5 anos modelo alta inicial (15%) + baixa recorrente (2%) | health-modelo-negocio-gpt |
| 25 | R$5.300 / 14.900 / 24.500 | Receita 1/3/5 anos modelo baixa inicial (5%) + alta recorrente (4%) | health-modelo-negocio-gpt |
| 26 | R$ 20k–200k/mês | Faturamento ICP Primário (corretora PME) | icp-cadarn-health-grande-vitoria |
| 27 | R$ 30k–300k/mês | Faturamento ICP Secundário (clínica PME com convênios) | icp-cadarn-health-grande-vitoria |
| 28 | 15% inicial + 2% mensal | Exemplo estrutura comissão: R$500 plano = R$75 + R$10/mês | health-modelo-negocio-gpt |

**Custo de Mão de Obra (23 dados)**

| # | Dado | Contexto | Fonte |
|----|------|----------|--------|
| 1 | R$ 1.730 | Piso salarial CCT Sincor-ES 2026 | health-perfil-corretoras-gemini-gv |
| 2 | R$ 1.930 | Salário demais funcionários CCT Sincor-ES 2026 | health-perfil-corretoras-gemini-gv |
| 3 | R$ 48/dia | Ticket Alimentação CCT Sincor-ES 2026 | health-perfil-corretoras-gemini-gv |
| 4 | R$ 1.824 | Mediana auxiliar administrativo Vitória (CAGED mai/2025–abr/2026) | health-perfil-corretoras-gpt |
| 5 | R$ 2.110 | Mediana auxiliar faturamento Vitória (CAGED) | health-perfil-corretoras-gpt |
| 6 | R$ 1.800–2.200 salário | Auxiliar administrativo/cadastro júnior Grande Vitória; R$3.100–4.200 custo | health-perfil-corretoras-gpt |
| 7 | R$ 3.200–4.800 salário | Analista operacional Grande Vitória; R$5.500–8.500 custo | health-perfil-corretoras-gpt |
| 8 | R$ 11.000–16.000/mês | Custo backoffice pequena/média em crescimento (3 pess.) Grande Vitória | health-perfil-corretoras-gpt |
| 9 | R$ 16.000–25.000/mês | Custo backoffice média regional (4-5 pess.) Grande Vitória | health-perfil-corretoras-gpt |
| 10 | R$ 25.000–45.000/mês | Custo backoffice média madura (6-9 pess.) Grande Vitória | health-perfil-corretoras-gpt |
| 11 | R$ 1.840–2.417 | Assistente Implantação/Registro (CLT) | health-perfil-corretoras-gemini-br |
| 12 | R$ 3.000–5.016 | Analista Faturação/Backoffice (CLT) | health-perfil-corretoras-gemini-br |
| 13 | R$ 2.166–3.864 | Corretor/Agente CLT componente fixo | health-perfil-corretoras-gemini-br |
| 14 | R$ 1.972 | Auxiliar Seguros (CBO 411040) salário médio CLT | health-pesquisa-001 |
| 15 | R$ 3.353 | Auxiliar Seguros custo empresa (~1,7x CLT) | health-pesquisa-001 |
| 16 | R$ 2.419 | Assistente Administrativo (CBO 411010) salário médio CLT | health-pesquisa-001 |
| 17 | R$ 4.112 | Assistente Administrativo custo empresa | health-pesquisa-001 |
| 18 | R$ 2.487 | Auxiliar Faturamento (CBO 413115) salário médio CLT | health-pesquisa-001 |
| 19 | R$ 4.228 | Auxiliar Faturamento custo empresa | health-pesquisa-001 |
| 20 | R$ 7,6k–8,4k/mês | Custo equipe mínima: 1 cadastro + 1 faturamento/financeiro | health-pesquisa-001 |
| 21 | R$ 500 mil anuais | Receita bruta limite corretores individuais | health-perfil-corretoras-gemini-br |
| 22 | R$ 50 | Anuênio CCT Sincor-ES (tempo de casa) | health-perfil-corretoras-gpt |
| 23 | R$ 13,21% | Reajuste médio 2023 carteiras maiores empresariais (ANS) | health-modelo-negocio-gpt |

**Glosas, Faturamento e Operação (28 dados)**

| # | Dado | Contexto | Fonte |
|----|------|----------|--------|
| 1 | ~100 guias/mês | Limite volume TISSMED R$299/mês | health-bpo-faturamento |
| 2 | <5% | Meta glosa MAC Finance SLA declarado | health-bpo-faturamento |
| 3 | 3%-7% | Perdas receita mensal atribuídas erros faturamento | icp-cadarn-health-grande-vitoria |
| 4 | R$ 80.000/mês | Exemplo clínica fatura com planos | icp-cadarn-health-grande-vitoria |
| 5 | R$ 9.600/mês | Glosas evitáveis clínica R$80k/mês (12% de 80k) | icp-cadarn-health-grande-vitoria |
| 6 | Abaixo de 1% | Taxa glosa ideal segundo mercado | icp-cadarn-health-grande-vitoria |
| 7 | R$ 932,15/beneficiário/ano | Prejuízo operadora autogestão com glosa 10% | icp-cadarn-health-grande-vitoria |
| 8 | R$ 184,8 milhões/5 anos | Perdas totais operadora autogestão glosa 10% | icp-cadarn-health-grande-vitoria |
| 9 | 10-20% faturas | Percentual a auditar para recuperar cobranças indevidas | health-modelo-negocio-gpt |
| 10 | 5-20% custos errados | ML pode recuperar em faturas mensais | health-modelo-negocio-gpt |
| 11 | 30-50% redução tempo | Backoffice (movimentação + conferência faturas) com automação | health-modelo-negocio-gpt |
| 12 | 60%→85% retenção | Impacto receita recorrente crescimento substancial | health-modelo-negocio-gpt |
| 13 | ~600.000 guias/mês | Volume processado operadora grande antes IA (Maida Health) | icp-cadarn-health-grande-vitoria |
| 14 | 50–500 guias/mês | Volume estimado clínica PME com convênio [INFERÊNCIA] | icp-cadarn-health-grande-vitoria |
| 15 | 9 milhões vidas | Maida Health impactadas | icp-cadarn-health-grande-vitoria |
| 16 | R$ 8 bilhões | Maida Health faturamento sob gestão | icp-cadarn-health-grande-vitoria |
| 17 | 8 milhões processos/ano | Maida Health regulação assistencial | icp-cadarn-health-grande-vitoria |
| 18 | 45→6 profissionais | Redução equipe análise operadora 600k guias/mês após BPO Maida | icp-cadarn-health-grande-vitoria |
| 19 | 90% redução retrabalho | Benchmark promessa BPO corretoras/clínicas | health-persona-decisor-gpt |
| 20 | 3 dias úteis/mês | Tempo equipe administrativa fazendo batimento Excel | health-personas-bpo-gemini |
| 21 | 15 dias úteis | Prazo legal montar/enviar recurso glosa | health-personas-bpo-gemini |
| 22 | 40 convênios distintos | Cenário complexidade clínica que torna inviável manter equipe atualizada | health-personas-bpo-gemini |
| 23 | 1-5 usuários ativos | Porte típico corretora PME cliente Digital Controle/Approvita | icp-cadarn-health-grande-vitoria |
| 24 | <5 minutos resposta | Tempo resposta lead que dobra taxa conversão | health-modelo-negocio-gpt |
| 25 | até 9x melhoria | Conversão com atendimento ultra-rápido leads | health-modelo-negocio-gpt |
| 26 | 5-8 interações | Necessárias antes de proposta formal B2B saúde | icp-cadarn-health-grande-vitoria |
| 27 | 89% casos | B2B saúde incluem demonstração+validação antes decisão | icp-cadarn-health-grande-vitoria |
| 28 | 1,1-2,5% | Taxa conversão lead→venda B2B saúde | icp-cadarn-health-grande-vitoria |

**Perfil de Corretoras e Força de Trabalho (18 dados)**

| # | Dado | Contexto | Fonte |
|----|------|----------|--------|
| 1 | 12% | Corretoras com 8-17 funcionários (ESECS 2024) | health-perfil-corretoras-gpt |
| 2 | 2% | Corretoras com 18-25 funcionários (ESECS 2024) | health-perfil-corretoras-gpt |
| 3 | 3% | Corretoras com >25 funcionários (ESECS 2024) | health-perfil-corretoras-gpt |
| 4 | ~50% | Corretoras com plano de sucessão | health-perfil-corretoras-gemini-br |
| 5 | 51,5% | Trabalhadores formais Brasil com ensino médio como máximo | health-perfil-corretoras-gemini-br |
| 6 | 53,3% | Colaboradores setor seguros+saúde suplementar com ensino superior | health-perfil-corretoras-gemini-br |
| 7 | ~56% headcount | Corretores/Agentes CLT em corretoras estruturadas | health-perfil-corretoras-gemini-br |
| 8 | 80-90% | Percentual corretoras pequeno porte (1-7 pess.) segundo ESECS | health-perfil-corretoras-gemini-br |
| 9 | 2.051 | Profissionais+empresas corretagem ES (PF+PJ, Fenacor/SUSEP 2025) | health-perfil-corretoras-gpt |
| 10 | 1.160 | Total empresas CNAE 6622-3/00 ES (Econodata) | health-pesquisa-001 |
| 11 | 710 | Corretoras PJ registradas ES (Sincor-ES/SUSEP 2026) | health-pesquisa-001 |
| 12 | 70-75% | Concentração 710 corretoras capixabas em Grande Vitória | health-pesquisa-001 |
| 13 | 70.699 | Empresas CNAE 6622-3/00 Brasil (Econodata) — TAM nacional | icp-cadarn-health-grande-vitoria |
| 14 | 147.783 | Corretores SUSEP ativos Brasil novembro/2025 | icp-cadarn-health-grande-vitoria |
| 15 | 200–400 | Estimativa corretoras ES com foco saúde [INFERÊNCIA] | icp-cadarn-health-grande-vitoria |
| 16 | 35–55 anos | Faixa etária personas corretora (perfil geral nacional) | health-persona-decisor-gpt |
| 17 | 35–50 anos | Faixa etária personas corretora (perfil capixaba) | health-persona-decisor-gpt |
| 18 | 2-15 médicos | Porte ICP Secundário clínica/consultório com TISS | icp-cadarn-health-grande-vitoria |

**Mercado e Concorrência (22 dados)**

| # | Dado | Contexto | Fonte |
|----|------|----------|--------|
| 1 | 8,03% | Crescimento planos odontológicos ES abril/2025–abril/2026 (destaque nacional junto PI) | health-concorrentes-bpo-gemini |
| 2 | 30 municípios | Rede Unimed Sul Capixaba | health-pesquisa-001 |
| 3 | ANS 357391 | Registro ANS Unimed Vitória | health-pesquisa-001 |
| 4 | ANS 37071-1 | Registro ANS Uniodonto ES | health-pesquisa-001 |
| 5 | 30 anos | Tempo Coneccta no segmento seguros | health-concorrentes-bpo-gemini |
| 6 | 460 hospitais-clientes | ZG Soluções clientes | icp-cadarn-health-grande-vitoria |
| 7 | R$ 32 bilhões | ZG Soluções contas médicas analisadas | icp-cadarn-health-grande-vitoria |
| 8 | R$ 1 bilhão | ZG Soluções glosas recuperadas | icp-cadarn-health-grande-vitoria |
| 9 | 35.000+ usuários | Clínica nas Nuvens | icp-cadarn-health-grande-vitoria |
| 10 | 3.000+ clínicas / 20.000+ profissionais | Amplimed escala | icp-cadarn-health-grande-vitoria |
| 11 | 5.000+ profissionais | App Health usuários | icp-cadarn-health-grande-vitoria |
| 12 | 30 dias | Trial Approvita e Digital Controle | icp-cadarn-health-grande-vitoria |
| 13 | 890 operadoras | 667 médico-hospitalares + 223 odontológicas (ANS abr/2026) | icp-cadarn-health-grande-vitoria |
| 14 | ~16.748 vidas | Mais Saúde Vix operadora local menor ES | icp-cadarn-health-grande-vitoria |
| 15 | ~1,8 milhão | População Grande Vitória (~40% ES) | icp-cadarn-health-grande-vitoria |
| 16 | ~500–600 mil | Estimativa beneficiários Grande Vitória [INFERÊNCIA] | icp-cadarn-health-grande-vitoria |
| 17 | 3-7% taxa resposta | Campanhas multicanal qualificadas B2B saúde | icp-cadarn-health-grande-vitoria |
| 18 | R$ 17 bilhões | Déficit setor 2021-2023 (pós-pandemia) | health-vendas-b2b-gemini |
| 19 | 70-75% MLR | Break-even operadora (quando ultrapassa = reajustes insustentáveis) | health-vendas-b2b-gemini |
| 20 | até 40% | Automação aumenta taxa fechamento novos contratos | health-vendas-b2b-gemini |
| 21 | 2-4 semanas | Estágio SDR/BDR ciclo B2B saúde | health-vendas-b2b-gemini |
| 22 | 6-9 meses | Total ciclo venda B2B saúde (SDR+Discovery+Regulatória+POC+Comitê) | health-vendas-b2b-gemini |

---

## Mapa de Capítulos → Gaps Principais

| Capítulo | Gaps de Alta Prioridade | Gaps de Média Prioridade |
|----------|-------------------------|--------------------------|
| **01-mercado-saude-suplementar.md** | Nenhum (análise macro não é tática) | Características ES × Grande Vitória (5); ICP Tri-Segmento (1); ESECS e estrutura mercado (1) |
| **02-corretora-perfil-operacao.md** | Personas (14 itens): Corretoras locais, estruturadas, médias; Diretor financeiro, Gerente Ops/TI, Gestor RH (6) | Frameworks: Estrutura 8 Áreas (1), Oportunidades Eficiência (1); Conceitos: Preposto Autônomo (1); Ciclo Operacional (1) |
| **03-corretora-modelo-negocio.md** | Táticas: Diagnóstico consultivo (1), Modelo híbrido CLT+autônomo (1), Pipeline CRM (1), Concentrar valor cognitivo (1); Estrutura Reajustes (1) | Frameworks: Progressão Risco Atuarial (1), Reajuste Técnico Dual (1); Ciclo Operacional Backoffice (1); Roadmap IA 3 Fases (1) |
| **04-faturamento-saude-clinicas-bpo.md** | Táticas: Call center omnicanal 24/7 (1), Auditoria pré-pagamento ColaboRHa (1), IA detecção fraudes (1), Auditoria coparticipações (1), Checklist implantação/Planilha movimentação/Conferência fatura/Histórico atendimento (4 táticas operacionais) | Frameworks: Tabela Impacto Glosas (1); Conceitos: CFO Saúde, Sociedade Simples, DMED, Clearinghouse, Analytics Forense, DRG, CNES, RN 472/2021 TISS (8) |
| **05-decisor-jornada-compra.md** | Táticas: Entrada ES, Mensagem contextualizada, Comunicação transparente, Case SAMP (4); Scripts WhatsApp/Ligação/Email/Indicação/Específicos (6); Checklist pré-venda (1); Chatbot WhatsApp (1) | Frameworks: Cronograma Gantt, 4 Características ES, Sequência Mensagem 5 Etapas (3); Roteiro One-Sheet (1); Ciclo Venda B2B (1); BANT Adaptado; Healthcare No Shortcuts |
| **06-cadarn-modelo-oferta.md** | Táticas: APIs Coneccta, WhatsApp 2Easy, Telemedicina Tailor, Educação colaboradores, Monitoramento sinistralidade, Reuniões trimestrais, Programas prevenção, Alerta 75%, Piloto 10 clientes, Pacotes consultoria (10); Success fee Axenya (1); Trial 30 dias (1) | Frameworks: Dupla Oferta BPO+CFO (1), Matriz 4 Serviços (1), Automação Duas Camadas (1); Narrativa Escudo Institucional (1); Tabela Impacto Sinistralidade 3 Anos (1); Ganho Escala Per Capita (1) |
| **07-anexo-perguntas-estrategicas.md** | (Não aplicável — perguntas estratégicas já existem) | (Integrar perguntas sobre novos conceitos descobertos) |
| **08-anexo-glossario.md** | Nenhum (glossário é compilado, não original) | Conceitos: CPT, DMED Fiscal, Autogestão, Intercâmbio TISS, Objeções IA+Resistência Interna (5); Adicionar definições de todos os 24 conceitos de Média prioridade |

---

## Recomendação de Sequência de Integração

1. **Semana 1**: Capítulo 05 (táticas vendas + scripts) + 06 (modelo oferta)
2. **Semana 2**: Capítulo 02 (personas + estrutura) + 04 (operacional glosas)
3. **Semana 3**: Capítulo 03 (frameworks negócio) + 08 (glossário expandido)
4. **Semana 4**: Revisão + validação de dados com operações Cadarn ES

---

**Arquivo gerado:** 2026-06-27  
**Audit Run ID:** wf_bfb02a21-c85  
**Coverage:** 74% (603 PRESENTE + 233 PARAFRASADO de 1.127 items)  
**Status Corpus:** ✅ **LIBERADO PARA USO em RAG/Treinamento IA**
