# Radar — Memória Persistente

Agente: Radar (Especialista GMN)
Squad: Cadarn Comercial (Healtech)
Versão: 1.1
Criado (réplica/reescopo): 2026-07-19
Origem: réplica reescopada do Radar da Cadarn Martech (_AIOX_Manager/squads/cadarn-comercial/agents/radar.md, v1.1, criado 2026-06-01)

---

## Decisões Validadas

### Configuração do Agente
- **DNA escolhido:** Luciano Arthur (Escola de SEO) — mesmo DNA da réplica original, selecionado após pesquisa de especialistas BR (2026-06-01, sessão Martech). Alternativas consideradas e descartadas naquela sessão: Tiago Nogueira (MÉDIO), Lucas Cruz (MÉDIO). Não repesquisado nesta réplica.
- **Squad:** Cadarn Comercial (não Marketing) — objetivo principal é atrair lead, não construir presença/branding. Mesmo racional da réplica original.
- **Reutilizável:** sim, mas com escopo mais estreito que a versão Martech — apenas para clientes Healtech do segmento "dono/gestor de clínica ou consultório pequeno" com presença física de atendimento. Corretora de plano de saúde (B2B) e faturamento hospitalar/BPO ficam FORA do escopo: não dependem de busca local "perto de mim" para captar cliente [fonte: squads/cadarn-comercial/squad.yaml, bloco `icp.segments`].

### Restrições Permanentes (não negociáveis — herdadas idênticas, fatos universais de GMN)
- **LSA (Local Service Ads):** NÃO disponível no Brasil em 2026. Confirmado por múltiplas fontes (pesquisa original Martech, 2026-06-01). Nunca recomendar.
- **Q&A API:** descontinuada em 03/11/2025. Agora operada por Gemini AI com base nas informações do perfil GMN. Adaptar estratégia para otimizar Descrição + Serviços como fonte para o Gemini.
- **Reviews incentivadas:** proibido por TOS Google. Não recomendar pagamento, desconto ou qualquer benefício em troca de review.
- **Keyword no nome:** injetar palavras-chave no nome da empresa viola TOS → risco de suspensão.

### Dados Técnicos Validados (herdados idênticos — universais de GMN, não mudam por segmento)
- **50+ reviews:** aumento de 266% nas chances de aparição no Local Pack.
- **Área de atendimento SAB:** máximo 20 regiões. Campo não impacta ranking diretamente (Whitespark).
- **Performance Max:** mínimo 5 localizações para "local actions", 10 para "store visits" — inviável para profissional autônomo ou consultório único (1 SAB/1 Storefront).
- **KPI primário:** ligações diretas (não views/impressões).

### Resolvido em 2026-07-19 (pesquisa dedicada de saúde)
Pesquisa `docs/biblioteca/pesquisas/_inbox/2026-07-19_gmn-google-meu-negocio-clinicas-saude-brasil.md` (Atlas, natureza externa, 15 fontes) fechou as lacunas de v1.0. Resumo do que mudou no agente:

- **Categoria médica no GMN:** o Google oferece categorias específicas por especialidade (ex.: "Clínica médica", "Psicologia", "Odontologia", "Alergista", "Audiologista", "Quiropraxista", "Clínico geral") — deixou de ser exemplo ilustrativo genérico e passou a ser lista real, mantendo sinalização de que o peso algorítmico diferenciado não é confirmado por fonte oficial do Google.
- **CRM não é exigido pelo Google:** o processo de verificação de perfil GMN é o mecanismo padrão (vídeo/cartão-postal/telefone/e-mail) — não há evidência de exigência de CRM pelo Google. A exigência de exibir CRM/RQE é do CFM, fora do escopo do Google. Antes essa distinção não estava clara no agente.
- **Reviews e LGPD:** o risco real de vazamento de dado sensível (LGPD Art. 11) está na RESPOSTA PÚBLICA da clínica ao review (se citar diagnóstico/procedimento), não no post do paciente sobre si mesmo. Protocolo de resposta a review negativa revisado para nunca detalhar caso clínico.
- **CFM:** a Resolução 1.974/2011 foi REVOGADA e substituída pela Resolução 2.336/2023 (vigente desde março/2024) — liberou fotos antes/depois com contexto educativo, imagem de paciente anônima, preços, depoimentos sóbrios; mantém proibição de promessa de resultado; exige CRM/RQE visível em perfis públicos. Bloco novo adicionado ao agente ("Publicidade Médica — CFM").
- **Agendamento:** GMN integra agendamento via "Reservar com o Google" por provedores terceiros; Doctoralia confirmada como parceira ativa no Brasil para o segmento saúde. Bloco novo adicionado ao agente ("Agendamento Integrado").
- **YMYL/E-E-A-T:** saúde é YMYL clássico no Google, exige E-E-A-T mais forte — mas peso algorítmico específico no Local Pack é inferência de agências de SEO, sem confirmação de fonte primária do Google. Bloco novo adicionado ao agente.

### Ainda sinalizado como [INFERÊNCIA — não verificada] após a pesquisa de 2026-07-19
A pesquisa foi explícita sobre o que NÃO conseguiu confirmar. Estes pontos permanecem marcados no corpo do agente e NÃO foram promovidos a fato:
1. Se atributos como "aceita novos pacientes" / "convênio aceito" são exclusivos de categorias de saúde no GMN ou padrão mais amplo disponível a outras categorias.
2. Existência de resolução do CFM tratando especificamente de "avaliações/reviews no Google" como tema autônomo (existe só aplicação geral do Código de Ética Médica + LGPD por interpretação de mercado).
3. Se a exigência de identificação CRM/RQE do CFM se aplica formalmente ao campo de Descrição/Posts do GMN especificamente (inferência razoável, não confirmada em texto da resolução).
4. Peso algorítmico diferenciado e mensurável de E-E-A-T/YMYL dentro do Local Pack/Maps especificamente para categoria de saúde (existe para busca orgânica geral; para Local Pack é inferência de agências de SEO médico).
5. Lista completa e oficial de provedores de agendamento disponíveis no Brasil além da Doctoralia (Cloudia, Trinks, SimplyBook.me mencionados com menor grau de confirmação).
6. Tratamento algorítmico diferenciado para categoria GMN específica de saúde além do princípio geral de categorização (categoria específica > genérica).

---

## Sessões Relevantes

### 2026-06-01 — Criação do Agente Original (Cadarn Martech)
- Emrys + Fabiano definiram escopo, nome (Radar), squad e DNA para o mercado imobiliário.
- Pesquisas base: 4 arquivos lidos de fonte externa (Google Meu Negócio).
- Biblioteca Martech: 2 pesquisas Atlas salvas em `docs/biblioteca/pesquisas/_inbox/` (repositório _AIOX_Manager) —
  `2026-06-01_especialistas-google-meu-negocio-seo-local-brasil.md` e
  `2026-06-01_luciano-arthur-escola-seo-metodologia-gmn.md`.
- Fontes externas: Escola de SEO Luciano Arthur, Escola do Sobral (Google Ads — tangencial), Whitespark Local SEO survey.

### 2026-07-19 — Réplica e Reescopo para Healtech
- Decisão de Fabiano: replicar o Radar da Martech para o Healtech, trocando o avatar de
  "corretor de imóveis / imobiliária" para "dono/gestor de clínica ou consultório pequeno"
  — um dos 4 segmentos reais do ICP Healtech, o único com presença física local relevante
  para GMN (corretora de plano de saúde B2B e faturamento hospitalar/BPO não dependem de
  busca local).
  [fonte: squads/cadarn-comercial/squad.yaml deste repositório, blocos `icp.segments` e
  `upgrades.note`]
- Núcleo técnico de GMN (trinômio de ranqueamento, checklist 25 itens, TOS de reviews, Q&A
  via Gemini, métricas, integração com Google Ads) copiado IDÊNTICO — metodologia validada e
  universal, não muda entre segmentos.
- Exemplos, scripts e templates de descrição/posts adaptados para o contexto de clínica/
  consultório. Categorias GMN de saúde sinalizadas como inferência não verificada (ver seção
  acima) — não copiadas como fato validado.
- Pesquisas-fonte originais NÃO foram copiadas para este repositório (Healtech ainda não
  tem Biblioteca Cadarn própria) — permanecem no repositório Martech (_AIOX_Manager). Se
  necessário aprofundar, consultar aquele repositório ou reexecutar pesquisa via Atlas
  (@analyst) neste Tarian.
- Arquivos gerados: `squads/cadarn-comercial/agents/radar.md` (agente completo) e este
  arquivo de memória.

### 2026-07-19 — Pesquisa Dedicada de Saúde Incorporada (v1.0 → v1.1)
- Atlas (@analyst) concluiu pesquisa dedicada sobre o que MUDA em GMN especificamente
  para clínicas/consultórios de saúde no Brasil (categoria médica, CRM, LGPD em
  reviews, CFM 2.336/2023, agendamento via Doctoralia, YMYL/E-E-A-T), com 15 fontes,
  natureza externa. Arquivo: `docs/biblioteca/pesquisas/_inbox/2026-07-19_gmn-google
  -meu-negocio-clinicas-saude-brasil.md`.
- Todas as lacunas sinalizadas `[INFERÊNCIA — não verificada]` na criação do agente
  (2026-07-19, mesmo dia) foram revisadas: parte foi resolvida com fato confirmado
  pela pesquisa, parte permanece sinalizada como inferência porque a própria pesquisa
  não encontrou fonte primária que confirmasse (ver seções "Resolvido em 2026-07-19"
  e "Ainda sinalizado como inferência" acima).
- Agente atualizado para v1.1 com 3 blocos novos ("Publicidade Médica — CFM",
  "Agendamento Integrado — Reservar com o Google", "YMYL/E-E-A-T"), bloco de
  Categorias reescrito com nomes reais e elegibilidade/verificação, seção de Reviews
  revisada com o ponto de risco de LGPD na resposta pública, e anti-patterns novos
  (LGPD Art. 11, promessa de resultado CFM, foto antes/depois sem contexto, exposição
  de paciente identificado).
- Núcleo técnico universal de GMN (trinômio, checklist 25 itens, TOS de reviews,
  Q&A via Gemini, métricas, integração com Google Ads, LSA indisponível) permaneceu
  intocado — a pesquisa não tocou nesses pontos, que já estavam validados.

---

## Clientes Atendidos

*(vazio — preencher ao usar o agente pela primeira vez com um cliente específico)*

---

*Memória mantida por: Emrys (Regência) + Fabiano | Severidade de dados: Alta — dados de configuração técnica*
