# Metodologia Pedro Sobral — Meta Ads: Documento de Referência Técnico para Agente de IA

> **Escopo e integridade:** Este documento cobre exclusivamente conteúdo público — blog pedrosobral.com.br, canal YouTube Canal Subido (@pedrosobral), posts do LinkedIn e Instagram públicos, e entrevistas/palestras abertas (Hotmart FIRE, podcasts). Todo trecho baseado em transcrições de lives ou materiais de estudo derivados de conteúdo público está sinalizado com [inferência aplicada — fonte: título + URL]. Afirmações sem fonte pública confirmável estão marcadas como _não encontrado com fonte pública confiável_.

***

## Definição-Síntese (adequada para uso em system prompt)

Pedro Sobral é o criador da Comunidade Subido, maior comunidade de gestores de tráfego pago do Brasil, e referência pública em Meta Ads estratégico. Sua metodologia organiza campanhas em três tipos (audiência, captação, vendas), segmenta públicos por hierarquia de aquecimento (quente → frio), e prescreve otimização baseada em uma única métrica principal por objetivo. A filosofia central é que **o gestor estratégico entende negócios e pessoas — não apenas aperta botões** — e que consistência de execução supera qualquer perfeição de plano.

***

## MÓDULO 1 — ESTRUTURA DE CAMPANHAS

> **Definição-síntese para system prompt:** A metodologia Sobral organiza o tráfego Meta Ads em três tipos de campanha sequenciais (Audiência → Captação → Vendas), com nomenclatura padronizada por tags, estrutura de testes isolados e uma distinção operacional clara entre campanha CONTINUA (tráfego aprovado, com exclusões hierárquicas) e campanha TESTE (sem exclusões, variando apenas uma variável por vez).

### 1.1 Os 3 Tipos de Campanha

Sobral ensina publicamente que toda operação de tráfego Meta Ads pode ser enquadrada em três categorias funcionais:[^1][^2]

| Tipo | Função estratégica | Objetivos Meta Ads compatíveis | Quando usar |
|---|---|---|---|
| **Audiência** | Atrai, filtra e aquece público qualificado; prepara para compra futura | Reconhecimento, Tráfego, Engajamento, Visualizações de vídeo, Cadastros | Sempre que o negócio ainda não tem base de reengajamento; antes ou em paralelo com captação |
| **Captação de Leads** | Coleta contatos (e-mail, WhatsApp, telefone) para nutrição | Cadastros (leads), Engajamento (mensagens), Formulário instantâneo | Quando existe oferta de entrada (conteúdo, diagnóstico, agendamento) |
| **Vendas** | Maximiza conversões dentro do ROAS previsto | Vendas (com pixel), Engajamento (WhatsApp/Direct), Tráfego (sem pixel — uso não recomendado) | Com pixel instalado e evento de conversão configurado; base de dados sólida |

**Estratégias derivadas dos 3 tipos** [inferência aplicada — fonte: transcrição de lives públicas, passeidireto.com/arquivo/101323691/lives-pedro-sobral]:
- Audiência → Leads quentes → Vendas (funil clássico)
- Audiência → Venda direta (para ofertas de baixo atrito)
- Captação direta para público frio (com oferta irresistível)
- Reengajamento → Vendas (para bases existentes)

### 1.2 Organização de Conjuntos de Anúncios (Ad Sets)

A lógica de separação de ad sets na metodologia Sobral segue o princípio de que **públicos maiores consomem verba de públicos menores quando coexistem na mesma campanha** [inferência aplicada — fonte: transcrição de lives públicas, passeidireto.com/arquivo/101323691/lives-pedro-sobral]:

- **4 a 6 ad sets por campanha** como estrutura padrão[^3]
- A Meta recomendava 6 anúncios por ad set; com Andrômeda (2025-2026), a recomendação migrou para **8 a 15 criativos conceitualmente distintos** por ad set[^4]
- Públicos de qualidade diferente devem ser separados em **campanhas distintas** — não apenas conjuntos diferentes
- Ad sets de remarketing (públicos quentes) têm verba forçada via ABO ou campanha isolada, para não serem esmagados por públicos frios em CBO
- A separação de posicionamento (feed vs. Stories vs. Reels) só se justifica quando os criativos forem **genuinamente diferentes** por formato — caso contrário, o posicionamento Advantage+ performa melhor[^4]

### 1.3 Padrão de Nomenclatura de Campanhas

[inferência aplicada — fonte: transcrição de live pública sobre nomenclatura, passeidireto.com/arquivo/101323691/lives-pedro-sobral e studocu.com/pt-br/document/…/2-2-comunidade-sobral-como-criar-e-organizar-publicos/40748131]

**Tags principais obrigatórias:**
- `[CONTINUA]` — campanha ativa com públicos testados e aprovados, com exclusões hierárquicas
- `[TESTE]` — campanha experimental sem exclusões entre públicos

**Estrutura do nome:**
```
[TIPO] [OBJETIVO] [EVENTO/PRODUTO] [POSICIONAMENTO] [NÍVEL DE AQUECIMENTO]
```

**Exemplos concretos da metodologia:**
- `[CONTINUA] [CONVERSÃO] [9SDI] [VIDEO] Verbo To Be`
- `[TESTE] [CONVERSÃO] [EBOOK] [MOBILE] Ninja Públicos`

**Nomenclatura de conjuntos de anúncios:** numeração sequencial (00, 01, 02…) refletindo a hierarquia de aquecimento — 00 é o público mais quente, números maiores indicam públicos mais frios.

**Nomenclatura de anúncios:** identifica criativo, formato e variável testada.

> **Diferença operacional crítica:**
> - **Campanha CONTINUA**: Múltiplos públicos já testados; cada conjunto exclui todos os mais quentes acima dele na hierarquia; é a campanha "mestre" em operação.
> - **Campanha TESTE Ninja** (públicos): varia apenas o público, sem exclusões entre conjuntos — para descobrir quais públicos performam melhor em paralelo.
> - **Campanha TESTE Boladão** (criativos): mantém o mesmo público em todos os conjuntos, variando apenas 1 variável criativa (copy, headline ou imagem) — mínimo 3, máximo 6 anúncios. Se um teste supera a CONTINUA, ela é substituída.

### 1.4 ABO vs. CBO — Posição Pública de Sobral

[inferência aplicada — fonte: artigo blog pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/como-fazer-testes-no-trafego-pago-e-melhorar-seus-resultados e live #362, youtube.com/watch?v=MBSws43QpeA]

| Modalidade | Quando usar segundo Sobral | Por que |
|---|---|---|
| **CBO** (Campaign Budget Optimization) | Padrão na maioria dos casos; escala; iniciantes | Meta otimiza distribuição de verba automaticamente; alinha com Advantage+ |
| **ABO** (Ad Set Budget Optimization) | Para forçar gasto em público específico que seria esmagado no CBO; remarketing; testes controlados de verba | Garante volume mínimo de entrega em públicos menores ou mais qualificados |

**Citação direta (blog público):** "Na campanha: a Meta distribui o dinheiro entre os conjuntos de forma otimizada. Recomendado para iniciantes e para a maioria dos casos."[^3]

Com Andrômeda (2025-2026), o CBO com fewer ad sets e mais criativos distintos tornou-se o padrão prescrito. ABO permanece válido quando:[^4]
1. O público de remarketing teria CPM muito alto competindo com públicos frios
2. É necessário forçar orçamento mínimo num conjunto específico
3. A campanha tem apenas 1-2 ad sets (diferença prática entre CBO e ABO fica irrelevante)

### 1.5 Metodologia de Testes

[inferência aplicada — fonte: passeidireto.com/arquivo/101323691/lives-pedro-sobral e pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/como-fazer-testes-no-trafego-pago-e-melhorar-seus-resultados][^3]

**Princípio fundamental:** "Cada centavo investido em tráfego pago é um teste. Não tem como realizar novos testes sem investir na fonte de tráfego."[^3]

**5 métodos de teste documentados publicamente:**

1. **Teste orgânico/com o carro andando** — campanha ativa sendo monitorada com ajustes regulares
2. **Teste Ninja de Públicos** — mesmos criativos, diferentes públicos em ad sets paralelos, sem exclusões entre si
3. **Teste Boladão de Criativos** — mesmo público, diferentes criativos; isolar 1 variável (copy, headline, imagem ou formato)
4. **Criativos dinâmicos com detalhamento** — múltiplos textos/títulos/imagens no mesmo anúncio; Meta testa automaticamente; analisar via "Elemento de criativo dinâmico"
5. **Teste A/B nativo da Meta** — uso esporádico; Sobral prefere testes manuais[^3]

**Frequência de otimização por elemento:**

| Elemento | Orçamento baixo | Orçamento alto |
|---|---|---|
| Orçamento/lance | A cada 2 dias | A cada 1 dia |
| Criativos | A cada 2–3 dias | A cada 2 dias |
| Públicos | A cada 4–7 dias | A cada 4 dias |
| Estrutura geral | A cada 7–28 dias | A cada 7–14 dias |

**Com Andrômeda/2026:** a recomendação de criativos migrou para **8 a 15 conceitos distintos** (não variações mínimas da mesma ideia) por ad set, diversificando formato (vídeo, carrossel, imagem), narrativa (dor, desejo, dilema, prova social), gancho (pergunta, contra-intuitivo, urgência, público implícito) e ângulo de abordagem.[^4]

### 1.6 Exemplo Aplicado: Imobiliária de Alto Padrão

Estrutura hipotética derivada dos princípios Sobral para imobiliária premium:

```
CAMPANHA 1: [CONTINUA] [CADASTROS] [IMOB-ALTO] [AUTO] Captação Leads
├── 00 — Envolvimento Instagram 7D (excluir nenhum)
├── 01 — Visitou Site 30D (excluir: 00)
├── 02 — Visualização 75% vídeo tour 30D (excluir: 00, 01)
├── 03 — Lookalike 1% clientes (excluir: 00, 01, 02)
└── 04 — Interesses: imóveis alto padrão + renda presumida alta (excluir: 00–03)

CAMPANHA 2: [CONTINUA] [ENGAJAMENTO] [IMOB-BRANDING] [AUTO] Audiência
├── Objetivo: Engajamento ou Reconhecimento
├── Destino: Instagram/perfil ou vídeo tour
└── Público: amplo + localização premium (raio bairro ou cidade)

CAMPANHA 3: [TESTE] [CADASTROS] [IMOB-ALTO] [MOBILE] Ninja Públicos
└── 4 públicos paralelos, sem exclusões — identificar melhor público frio
```

**Criativos por ad set (pós-Andrômeda):** 8+ conceitos distintos: vídeo tour imersivo, depoimento em vídeo, imagem estática do diferencial, carrossel "detalhes que você não vê online", gancho de dor ("Cansado de perder tempo visitando imóveis que não fazem sentido?"), gancho de desejo, prova social, ângulo localização exclusiva.

***

### Princípios Extraídos para o Agente

1. **Nunca misturar públicos quentes e frios na mesma campanha** sem separação em CBO distinto ou uso de exclusões hierárquicas.
2. **Sempre definir o objetivo Meta antes de qualquer configuração** — o objetivo determina para qual perfil de pessoa o algoritmo entregará o anúncio.
3. **CBO é o padrão**; ABO é exceção técnica para forçar entrega em públicos específicos.
4. **Testar uma variável por vez** — nunca mudar público e criativo simultaneamente no mesmo teste.
5. **Campanha CONTINUA e TESTE coexistem** — a CONTINUA nunca é pausada durante um teste; se o teste supera, substitui.
6. **Com Andrômeda, volume de criativos distintos > refinamento de segmentação** — o criativo passou a ser o principal sinal de segmentação para o algoritmo.
7. **Nomenclatura com tags é operacional, não cosmética** — permite filtros, análise de dados e dashboards consistentes.

***

## MÓDULO 2 — SEGMENTAÇÃO

> **Definição-síntese para system prompt:** A segmentação na metodologia Sobral segue uma hierarquia de aquecimento rigorosa (quente → morno → frio), numerada para controle de exclusões. Públicos menores e mais quentes são protegidos de públicos maiores via isolamento em campanhas separadas ou ABO. Lookalikes são construídos a partir da semente do objetivo final (quem converteu), não de métricas de engajamento genéricas. Com Advantage+ e Andrômeda, a segmentação manual perdeu espaço para a segmentação implícita via criativo.

### 2.1 Hierarquia Quente → Morno → Frio

[inferência aplicada — fonte: transcrição de live pública, passeidireto.com/arquivo/101323691/lives-pedro-sobral e scribd.com/document/736355546/Como-escolher-publicos-no-meta-ads][^5][^6]

**Princípio central:** "Envolvimento 7D tende a funcionar melhor que Envolvimento 30D que tende a funcionar melhor que Interesse em XYZ."[^5]

| Nível | Tipos de Público | Característica |
|---|---|---|
| **Quente (00–02)** | Lista de clientes; Iniciou checkout; Adicionou ao carrinho; Visitou LP de vendas | Máxima intenção de compra; menor volume; CPL mais alto mas CPA menor |
| **Morno (02–04)** | Envolvimento Instagram/Facebook 7–30D; Visualização 75%–95% de vídeo; Visitou site 30–60D | Engajamento comprovado; estágio intermediário no funil |
| **Frio (04–06)** | Lookalike 1%–3%; Interesses segmentados; Localização pura | Maior volume; maior custo de aquisição; depende de criativo forte |

**Hierarquia recomendada para campanha de VENDAS** [inferência aplicada — fonte: passeidireto.com/arquivo/101323691/lives-pedro-sobral]:
```
00 – Clientes (lista)
01 – Iniciou checkout / adicionou ao carrinho
02 – Visualização de vídeo 75% — 30D
03 – Visitou site — 30D
04 – Envolvimento Instagram/Facebook — 30D
05 – Lookalike 1% do objetivo (conversão)
06 – Interesses específicos
```

**Hierarquia recomendada para campanha de LEADS:**
```
00 – Lista clientes/compradores
01 – Visitou página de captura sem converter
02 – Visualização 75% — 30–60D
03 – Envolvimento 30D
04 – Lookalike 1% cadastros
05 – Interesses específicos
```

**Regra de ouro do erro de gestores iniciantes** (erro #6 identificado no blog público): "Focar só em público frio OU só em público quente. O segredo é balancear a distribuição de recursos entre públicos quentes e frios, priorizando quem já tem algum tipo de interação ou conhecimento da sua marca."[^1]

### 2.2 Lookalike Audiences (Públicos Semelhantes)

[inferência aplicada — fonte: passeidireto.com/arquivo/101323691/lives-pedro-sobral][^5]

**Porcentagens:** menores sempre performam melhor — 1% > 2% > 3%. Usar 3% apenas quando 1% é muito pequeno para entrega adequada (mercados com segmentação geográfica restrita).

**Sementes prioritárias (em ordem de qualidade):**
1. Público que **realizou o objetivo final da campanha** (comprou, converteu, agendou)
2. Lookalike de visualização de vídeo 95%
3. Lookalike de clientes (lista de e-mail/CRM)

**Regra de qualidade:** "Público foda = Lookalike foda. Público base ruim = Lookalike ruim." [inferência aplicada — fonte: passeidireto.com/arquivo/101323691/lives-pedro-sobral][^5]

**3 lookalikes recomendados para testar em paralelo:**
- LAL 1% do objetivo da campanha específica
- LAL 1% de view video 95%
- LAL 1% dos clientes

**Observação pós-Andrômeda** [inferência aplicada — fonte: live #362, youtube.com/watch?v=MBSws43QpeA]: Com Advantage+, o Lookalike manual perde relevância progressiva. A Meta usa públicos-semente como "sugestão", não como limite rígido. Para negócios locais ou produtos de nicho restrito, manter segmentação manual ainda é recomendado.

### 2.3 Custom Audiences (Públicos Personalizados) — Hierarquia de Qualidade

[inferência aplicada — fonte: passeidireto.com/arquivo/101323691/lives-pedro-sobral][^5]

A hierarquia de qualidade (do mais para o menos valioso):
1. **Lista de clientes pagantes** (CRM, CSV)
2. **Eventos no site** (compra, checkout, lead — via Pixel/CAPI)
3. **Visualização de vídeo 75%–95%** de conteúdos relevantes (ex.: tour de imóvel, vídeo de procedimento)
4. **Visitou site** (60D > 30D para negócios com ciclos longos de decisão)
5. **Envolvimento no Instagram/Facebook** (30D para campanhas ativas; 60–90D para remarketing de branding)
6. **Engajamento com formulário/lead ad** (quem abriu mas não submeteu)

### 2.4 Interesse vs. Lookalike vs. Advantage+ Audience

[inferência aplicada — fonte: live #362, youtube.com/watch?v=MBSws43QpeA; artigo blog como-fazer-testes, pedrosobral.com.br][^4][^3]

| Tipo | Posição de Sobral | Quando usar |
|---|---|---|
| **Interesses** | Ainda válidos como sugestão/input para algoritmo; perderam força como segmentação rígida com Andrômeda | Negócios locais; nichos muito específicos; quando Advantage+ vaza fora da região desejada |
| **Lookalike manual** | Útil como semente de qualidade; Advantage+ dilui a segmentação rígida | Audiências de alta qualidade (clientes premium); quando pixel tem muitos dados |
| **Advantage+ Audience** | Recomendado como padrão para escala; não recomendado para negócios locais restritos | Escala nacional; infoprodutos; e-commerce; quando criativo é forte e pixel tem histórico |

**Citação direta (live #362):** "Se você não está anunciando numa região extremamente específica e se essa campanha complementa uma estratégia maior, você pode utilizar o Público Advantage+. Se você é um negócio local que anuncia em determinados bairros, não usa campanha Advantage [pura]. Por quê? Porque o Advantage vai anunciar para pessoas fora da sua região."[^4]

**Citação sobre criativos como nova segmentação (live #362):** "Não é mais você que encontra o público certo. Quem encontra o público certo é o seu anúncio."[^4]

### 2.5 Exclusão de Públicos — Regras Anti-Sobreposição

[inferência aplicada — fonte: passeidireto.com/arquivo/101323691/lives-pedro-sobral][^5]

**Regra de numeração e exclusão:**
- Ao inserir um público novo na hierarquia, reestruturar todas as exclusões
- Conjuntos numerados 00, 01, 02… — cada conjunto exclui todos os de numeração menor
- Exemplo:
  - Conj. 00: Envolvimento 7D → sem exclusão
  - Conj. 01: Envolvimento 30D → **exclui Conj. 00**
  - Conj. 02: Visitou Site 30D → **exclui Conj. 00 e 01**
  - Conj. 03: Lookalike 1% → **exclui Conj. 00, 01 e 02**

**Por que excluir:** Sem exclusões, o algoritmo pode mostrar o mesmo anúncio de remarketing para alguém que já comprou, desperdiçando verba e poluindo o sinal de otimização.

**Campanha TESTE:** nunca tem exclusões entre conjuntos — o objetivo é descobrir qual público performa melhor em condições iguais, sem o viés das exclusões.

**Ferramenta Overlap:** Sobral menciona publicamente o uso de ferramentas de verificação de sobreposição de públicos (Audience Overlap) antes de criar a estrutura de exclusões.[^5]

### 2.6 Negócios Locais com Raio Geográfico Limitado

[inferência aplicada — fonte: blog pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/trafego-pago-para-clinicas-de-estetica e live #362, youtube.com/watch?v=MBSws43QpeA][^7][^4]

**Princípio de geolocalização:** "Públicos de locais muito específicos (CEPs, bairros, cidades) tendem a funcionar melhor sozinhos do que combinados com outra segmentação."[inferência aplicada — fonte: passeidireto.com/arquivo/101323691/lives-pedro-sobral][^5]

**Aplicação para clínica de estética avançada** (blog público, out 2025):[^7]
- Raio de até 10 km da clínica
- Demografias: mulheres 25–60 anos (testar masculino crescente)
- Público quente: envolvimento Instagram 30D + visitou site
- Campanhas recomendadas: Engajamento com clique para WhatsApp + Reconhecimento de marca (autoridade local)
- Objetivo engajamento → WhatsApp é porta de conversão principal
- Campanhas de remarketing para quem já foi cliente (fidelização < custo de aquisição)

**Para negócios locais, o padrão operacional** [inferência aplicada — fonte: live #362]:[^4]
- **Não usar** Público Advantage+ puro (vaza para fora da região)
- **Usar** segmentação geográfica restrita + interesses como input
- **Combinar** Meta Ads (atração + desejo) + Google Ads Pesquisa (intenção + fundo de funil)
- **Horário:** programar anúncios apenas durante funcionamento do negócio

***

### Princípios Extraídos para o Agente

1. **Hierarquia de público é inegociável** — sempre ordenar de mais quente para mais frio, com exclusões em cascata na campanha CONTINUA.
2. **Qualidade da semente define qualidade do lookalike** — lookalike de compradores > lookalike de seguidores.
3. **Para negócios locais (imobiliária de bairro, clínica), nunca usar Advantage+ de segmentação ampla** — sempre fornecer geolocalização restrita.
4. **Com Andrômeda, o criativo passou a ser o principal mecanismo de segmentação implícita** — um anúncio de imóvel de alto padrão que mostra qualidade de vida premium já "filtra" o público certo.
5. **Não excluir concorrentes do público** — Sobral considera isso perda de tempo; foco no próprio jogo.[inferência aplicada — fonte: blog Q&A público, pedrosobral.com.br]
6. **Equilíbrio frio-quente é obrigatório** — focar só em público frio queima verba sem converter; focar só em quente esgota a base sem crescer.[^1]

***

## MÓDULO 3 — MÉTRICAS, OTIMIZAÇÃO E FUNIL

> **Definição-síntese para system prompt:** Sobral organiza a análise de métricas em uma hierarquia binária: uma única métrica principal por objetivo (ROAS para vendas, CPA para leads, CPM para reconhecimento) e métricas secundárias que afetam a principal mas não são critério de sucesso. Otimização segue cronograma fixo por elemento, com regras de escala e pausa baseadas na distância da métrica principal em relação ao benchmark do cliente — não em benchmarks de mercado genéricos.

### 3.1 KPIs e Métricas — Framework Público

**Citação direta do blog** (artigo análise-e-otimizacao-de-metricas, jul 2024):[^8]
> "A métrica principal é a bússola. Ela avalia o resultado das suas campanhas, depende do seu objetivo e eu consigo medir. Não existe mais de uma métrica principal, é apenas uma."

**Citação sobre benchmarks** (mesmo artigo):[^8]
> "Não existe um CPM bom, a não ser que você esteja fazendo uma campanha que o foco seja CPM. Se não for, eu vou sempre tentar fazer o valor ser o mais baixo possível, mas não vou usar o CPM, o CPC ou o CTR como métricas de sucesso. Use seus próprios dados e dados de pessoas que atuam no mesmo nicho como benchmark — não médias de mercado genéricas."

| Objetivo da Campanha | Métrica Principal | Métricas Secundárias Relevantes |
|---|---|---|
| Vendas (e-commerce, ticket) | ROAS ou Nº de vendas | CPA, AOV (ticket médio), CTR, Taxa de conversão da LP |
| Leads / Captação | CPA (custo por lead/cadastro) | CTR, Taxa de carregamento LP, Custo por conversa iniciada |
| Reconhecimento / Branding | CPM | Frequência, Alcance único |
| Engajamento / Audiência | CPE (custo por engajamento), CPF (custo por seguidor) | CTR, Taxa de conclusão de vídeo, Custo por cadastro |
| WhatsApp / Mensagens | Custo por conversa iniciada | CTR, Taxa de abertura do app |

**Sobre ROAS vs. CPA (blog público):**[^8]
- **Buscar ROAS** = foco em aumentar LTV (Life Time Value); prioriza valor do ticket por venda
- **Buscar CPA** = foco em reduzir CAC (Custo de Aquisição de Cliente); prioriza volume de aquisições
- A escolha depende do modelo de negócio do cliente: "O que é melhor depende do que é mais importante para o cliente: ter mais lucro ou um ROI maior."[^8]

**Métricas que Sobral menciona como secundárias relevantes:**
- **CPM** — sinal de alcance e custo do inventário; CPM alto pode indicar segmentação muito restrita ou criativo rejeitado
- **CTR** — qualidade do gancho do anúncio; CTR baixo aponta para criativo fraco, não necessariamente para público errado
- **Frequência** — risco de fadiga criativa; anúncio visto muitas vezes sem conversão = saturação
- **Taxa de carregamento da página** — gargalo técnico entre clique e conversão

### 3.2 Regras para Pausar, Escalar e Matar Campanhas

[inferência aplicada — fonte: blog pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/como-fazer-testes-no-trafego-pago-e-melhorar-seus-resultados e blog como-escalar-o-resultado-das-suas-campanhas][^3]

**Para anúncios:**
- **Pausar** anúncios de baixo desempenho (métrica principal muito acima do CPA/ROAS ideal)
- **Não pausar** anúncios que contribuem com escala, mesmo que individualmente não sejam os melhores
- Ao pausar, sempre substituir por novo criativo — nunca deixar o ad set sem criativos suficientes
- Criar novas versões de anúncios que performam bem (ângulo diferente, não variação mínima)[^4]

**Para públicos:**
- **Não pausar** públicos com bons resultados
- **Modificar** públicos com alto CTR mas baixa conversão (tráfego não qualificado)
- **Ampliar** públicos com CPM elevado (segmentação muito estreita)
- **Pausar** públicos muito abaixo dos demais na mesma hierarquia
- Ao pausar, substituir por público de qualidade equivalente na hierarquia

**"Momento da filha caindo do penhasco"** [inferência aplicada — fonte: passeidireto.com/arquivo/101323691/lives-pedro-sobral]: expressão de Sobral para resultados catastroficamente ruins — quando isso acontece, otimização imediata sem esperar o ciclo normal. A maioria das otimizações, porém, segue cronograma fixo.

**Critério de escala:** campanha com ROAS/CPA dentro do ideal recebe aumento gradual de orçamento (20–30% por vez para não sair da fase de aprendizado)[inferência aplicada — fonte: artigo como-escalar blog].

### 3.3 Funil de Tráfego — TOFU, MOFU, BOFU

Sobral não utiliza explicitamente a terminologia TOFU/MOFU/BOFU em fontes públicas rastreadas. Ele organiza o funil implicitamente pelos 3 tipos de campanha e a palestra Hotmart FIRE 2024 descreve a estrutura funcional equivalente:[^9]

| Estágio Funcional | Campanha Correspondente | Objetivo Meta | Público |
|---|---|---|---|
| **Descoberta** (TOFU) | Audiência / Branding | Reconhecimento, Engajamento, Visualização | Frio → Lookalike → Interesse |
| **Aquecimento** (MOFU) | Audiência + Captação | Cadastros, Engajamento, Mensagens | Morno → Envolvimento 30D |
| **Conversão** (BOFU) | Vendas / Captação avançada | Vendas, Engajamento WhatsApp | Quente → Lista, Site, 7D |

**Distribuição de verba (Hotmart FIRE 2024):**
> "Se você tá começando, vai ser quase 100% pra descoberta. Não tô começando: 50/50 é um bom parâmetro. E depois com o passar do tempo você vai mudando — investe um pouquinho mais em quem não te conhece, um pouquinho menos em quem te conhece."[^9]

**Artigo blog clínica de estética (out 2025) sobre funil:**
> "No topo do funil, o público ainda não sabe de 'procedimentos' ou técnicas. Ele busca 'meu rosto inchado', 'minha pele flácida'. Na etapa de consideração, você pode introduzir o procedimento como meio para alcançar esse resultado."[^7]

### 3.4 Campanhas de Tráfego para WhatsApp

[inferência aplicada — fonte: artigo blog pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/trafego-pago-para-clinicas-de-estetica e blog métricas][^7][^8]

**Objetivo recomendado:** Engajamento (não Tráfego)

**Citação direta (blog métricas, jul 2024):**[^8]
> "Se o objetivo da campanha for tráfego, o usuário clica mas pode não abrir o WhatsApp. Teste o objetivo de engajamento: embora o custo por clique seja mais alto, muito mais pessoas que clicarem realmente vão iniciar a conversa."

**Estrutura de campanha WhatsApp para negócio local** (denominada "Campanha WAR" em material público)[inferência aplicada — fonte: passeidireto.com/arquivo/101323691/lives-pedro-sobral]:
- Segmentação: raio geográfico restrito + público quente/morno
- Horário: apenas durante funcionamento do negócio
- Destino: WhatsApp Business (não link externo)
- Copy de entrada: direta, com proposta de valor clara e CTA específico (ex.: "Quero saber sobre harmonização — me chama aqui")
- Métrica principal: Custo por conversa iniciada

**Copy de entrada para high-ticket** [inferência aplicada]: Sobral prescreve que o anúncio já deve funcionar como primeiro filtro de qualificação — "o anúncio é o primeiro filtro do lead".[^10]

### 3.5 Integração Tráfego Orgânico e Pago

**Citação direta (LinkedIn público, nov 2024):**[^11]
> "Abandone a mentalidade de quinta série. Tráfego pago e tráfego orgânico são coisas opostas? Esquece essa ideia rasa. Um 'impulsiona' o outro, simples assim. O tráfego orgânico constrói uma base sólida de confiança e autoridade, enquanto o tráfego pago permite que você amplifique rapidamente sua mensagem."

**Estrutura dos 6 pilares de distribuição de conteúdo (Hotmart FIRE 2024):**[^9]
1. **Validação** — métricas de custo por resultado (objetivo: custo mais barato por engajamento/seguidor)
2. **Seleção** — critério subjetivo de qualidade: "esse conteúdo me representa e atrai compradores do meu produto?"
3. **Descoberta** — anunciar para pessoas que ainda não conhecem (topo)
4. **Aquecimento** — reinvestir em quem já conhece para manter quente
5. **Variação** — variar formatos (vídeo, carrossel, imagem) E objetivos de campanha para atrair audiência heterogênea
6. **Diversificação** — criar conteúdos genuinamente novos, não variações do mesmo

**Citação sobre tráfego pago como limitado pelo orgânico** [inferência aplicada — fonte: Hotmart Cast, youtube.com/watch?v=Ib0UDLG4Oxs]:
> "Tráfego pago é limitado pelo orgânico: se você não tem uma base boa orgânica, não tá produzindo conteúdo, chega uma hora que você chega no teto e não consegue investir mais."

### 3.6 Estratégia para Negócios Locais

[inferência aplicada — fonte: blog trafego-pago-para-clinicas-de-estetica e live #362][^7][^4]

**3 pilares inegociáveis antes de tráfego pago:**
1. Atendimento de qualidade
2. Oferta clara e competitiva
3. Produto/serviço com qualidade comprovada

**Estrutura multicanal para negócio local:**

| Canal | Campanha | Objetivo | Público |
|---|---|---|---|
| **Meta Ads** | Engajamento → WhatsApp | Conversa iniciada | Raio 1–10km, público quente/morno |
| **Meta Ads** | Branding / Reconhecimento | CPM baixo, autoridade local | Raio estendido, frio |
| **Meta Ads** | Remarketing clientes | Fidelização / upsell | Lista clientes + visitou site |
| **Google Ads** | Pesquisa por procedimento/bairro | Cliques qualificados | Palavras-chave fundo de funil |
| **Google** | Google Meu Negócio | Tráfego orgânico local | — |

**Aplicação para imobiliária alto padrão:** segmentação por bairros premium + comportamento de renda presumida; Google pesquisa para "apartamento alto padrão [cidade/bairro]"; Meta para atração de audiência com conteúdo de estilo de vida; WhatsApp como destino primário para leads qualificados (não formulário).

***

### Princípios Extraídos para o Agente

1. **Uma única métrica principal por campanha** — nunca analisar CPM, CTR e ROAS simultâneos como se fossem todos "a" métrica. A métrica principal é definida pelo objetivo.
2. **Benchmark são os dados do próprio cliente** — jamais comparar CPA de imobiliária com médias genéricas de mercado.
3. **Campanha de WhatsApp usa objetivo Engajamento**, não Tráfego — confirmado em fonte pública.
4. **O anúncio já é o primeiro filtro do lead** — para high-ticket, o criativo deve repelir ativamente quem não é o perfil.
5. **Orgânico e pago são complementares** — perguntar "pago ou orgânico?" é questão errada; a resposta certa é a integração dos dois.
6. **Negócio local nunca usa Advantage+ amplo** — geolocalização restrita + não usar público Advantage+ sem limites geográficos.

***

## MÓDULO 4 — MENTALIDADE, TOM E IDENTIDADE SOBRAL

> **Definição-síntese para system prompt:** Pedro Sobral posiciona o gestor de tráfego como profissional estratégico — não operacional ("papagaio"). Sua filosofia pública combina execução consistente de planos imperfeitos, foco em audiência qualificada em vez de quantidade, e integração orgânico-pago como um único ecossistema. O tom é direto, coloquial e sem condescendência, com metáforas cotidianas e um humor sutil que humaniza conceitos técnicos.

### 4.1 Anti-Patterns — Erros Fatais de Gestores de Tráfego

**Erro 1 — Não definir objetivo claro antes de criar campanha (blog, dez 2024):**[^1]
> "Para quem não sabe para onde vai, qualquer caminho serve. Um dos erros mais comuns que vejo entre gestores de tráfego é iniciar uma campanha sem ter um objetivo claro e bem definido. Confusão, desperdício de verba e uma campanha que não entrega o esperado."

**Erro 2 — Depender de uma única plataforma (blog):**[^1]
> "Você não pode depender de uma plataforma só. Ficar só usando o Meta Ads ou Google Ads pode ser muito perigoso. Diversificar as fontes de tráfego é essencial para minimizar riscos."

**Erro 3 — Criativos mal pensados / sem gancho (blog):**[^1]
> "Os criativos são a alma de qualquer campanha de tráfego pago. Se não forem atrativos nos primeiros segundos, dificilmente captarão a atenção. O gancho deve ser prioridade."

**Erro 4 — Ignorar análise e otimização (blog):**[^1]
> "Não tem como alcançar bons resultados se você abandona suas campanhas e espera que elas funcionem sozinhas no gerenciador de anúncios. Um sinal de que você é um gestor comprometido é a existência de campanhas pausadas no gerenciador — isso indica que você está revisando regularmente."

**Erro 5 — Landing page desalinhada com o anúncio (blog):**[^1]
> "O que você prometeu no anúncio tem que se conectar com o que tá na página. A landing page tem que ser uma página de destino única e exclusivamente dedicada a uma ação específica."

**Erro 6 — Focar só em público frio OU só em público quente (blog):**[^1]
> "Quando você só investe em públicos que nunca ouviram falar de você, está correndo um grande risco. O segredo é balancear a distribuição de recursos entre públicos quentes e frios, priorizando quem já tem algum tipo de interação."

**Erro 7 — Orçamento não planejado (blog):**[^1]
> "Gastar dinheiro à toa é coisa de maluco. Entrar no gerenciador sem um plano definido é como navegar sem bússola."

**Anti-pattern do gestor "papagaio"** (scribd — material derivado de live pública):[^12]
> "Essa é a parte fácil da gestão de tráfego: ser um papagaio. Não a despreze por isso, mas 'gestor estratégico' não é só quem sabe os botões — é quem responde às grandes perguntas: Onde estou? Para onde vou? Por que vou?"

**Anti-pattern de análise ansiosa (blog métricas, jul 2024):**[^8]
> "O erro do gestor iniciante é analisar o CPM e se basear por alguém que disse que o CPM tinha que ser no máximo 15 reais. A verdade é que não existe um CPM bom, a não ser que seja sua métrica principal."

### 4.2 Crenças Nucleares Públicas

**Consistência como superpoder (Hotmart FIRE 2024 — transcrição integral):**[^9]
> "Um plano ruim bem executado vale mais do que um plano bom não executado."
> "Desde 2018 até hoje eu tinha um plano e eu resolvi não trair o meu plano. 300 semanas que eu peguei aquele plano que eu construí e que eu fiz esse plano acontecer. 300 semanas que eu foco em melhorar."

**Sobre ser "traidor de si mesmo" (Hotmart FIRE 2024):**[^9]
> "Você é um traidor. Você só não gosta de admitir porque você passa a vida inteira traindo seus planos — até os piores planos."

**Qualidade vs. quantidade de audiência (Hotmart FIRE 2024):**[^9]
> "Quando eu bati os meus 10.000 seguidores no Instagram eu falei: pronto, aqui tá o Meu Primeiro Milhão. Porque eu só preciso que 5% dessa galera — 500 pessoas — sejam loucas por mim e queiram pagar R$2.000 por um produto."

**Relação gestor/cliente — blog público:**[^13]
> "Além de executar as tarefas, o gestor de tráfego também é um conselheiro estratégico para o cliente, ajudando ele a entender o que está sendo feito com o dinheiro investido."

**3 tipos de gestor (LinkedIn, jul 2024):**[^14]
> "Existem três tipos de gestores de tráfego: Os estratégicos — respondem às grandes perguntas: Onde estou? Para onde vou? Por que vou? Os táticos — criam os planos que implementam a estratégia. Os operacionais — executam as táticas. Quanto mais estratégico o profissional, mais ele tende a ganhar."

**Sobre tráfego não ser sobre botões (live #362, nov 2025):**[^4]
> "O jogo muda do 'saber apertar o botão' para 'saber como pensar tráfego'. A pessoa fala assim: 'Ah, mas cadê a parte prática?' A gente tem aulas sobre isso. Para mim, o grande superpoder do gestor de tráfego é essa mudança."

### 4.3 Tom de Voz e Vocabulário Recorrente

**Termos de identidade:**
- **"Subidos" / "Subidas"** — apelido para a comunidade/alunos, derivado do apelido pessoal de Sobral. Usado em todas as comunicações[^2][^15]
- **"Gestor papagaio"** — gestor puramente operacional, que só aperta botões[^12]
- **"Gestor estratégico"** — profissional que entende o negócio do cliente e o funil completo[^14]
- **"Plano ruim"** — plano imperfeito mas executado; filosofia central de ação sem perfeccionismo[^9]
- **"Adversário Platônico"** — competir com alguém que não sabe que você está competindo com ele[^9]
- **"Meio puto"** — estado emocional de admiração + indignação que impulsiona crescimento[^9]
- **"Momento da filha caindo do penhasco"** — metáfora para crise que demanda otimização imediata[inferência aplicada — fonte: passeidireto.com]
- **"Teste Ninja"** e **"Teste Boladão"** — nomenclaturas para os dois tipos de teste[inferência aplicada — fonte: passeidireto.com]
- **"Mentalidade de quinta série"** — pensamento binário e simplista (ex.: "tráfego pago OU orgânico")[^11]
- **"Contrate um Subido"** — plataforma da Comunidade para contratar gestores formados[^2]

**Estilo de comunicação observável:**
- Tom direto, coloquial, sem distância técnica desnecessária
- Uso de humor situacional e metáforas cotidianas (CrossFit, semáforo, filha caindo do penhasco)
- Provoca o interlocutor com perguntas retóricas antes de entregar a resposta
- Usa repetição intencional de frases ("esse é o superpoder", "isso é o que eu tô dizendo")
- Mistura alta densidade técnica com narrativas pessoais (formato hibrido de aula + storytelling)
- Anti-pomposo: critica ativamente quem se vangloria de ser "estratégico" sem dominar o operacional[^12]

### 4.4 Frases-Síntese com Fonte

| Frase | Fonte |
|---|---|
| "Um plano ruim bem executado vale mais do que um plano bom não executado." | Palestra Hotmart FIRE 2024 — youtube.com/watch?v=0Xt3U_jy4TQ [^9] |
| "Tráfego não é sobre botões, é sobre entender pessoas." | [inferência aplicada — paráfrase amplamente atribuída; citação próxima: "o jogo muda do saber apertar o botão para saber como pensar tráfego" — live #362, youtube.com/watch?v=MBSws43QpeA][^4] |
| "Sua atuação vai muito além de simplesmente 'colocar anúncios por aí' e apertar botões. É um trabalho estratégico e técnico." | Blog pedrosobral.com.br — guia-completo-para-comecar [^2] |
| "Abandone a mentalidade de quinta série. Tráfego pago e orgânico são coisas opostas? Esquece essa ideia rasa." | LinkedIn público — activity-7259596489390260224 [^11] |
| "O objetivo não é criar a campanha perfeita. O que importa é saber o que fazer para reverter resultados ruins." | Blog pedrosobral.com.br — análise-e-otimização-de-métricas [^8] |
| "300 semanas que eu foco em melhorar." | Hotmart FIRE 2024 — youtube.com/watch?v=0Xt3U_jy4TQ [^9] |
| "Não é mais você que encontra o público certo. Quem encontra o público certo é o seu anúncio." | Live #362 — youtube.com/watch?v=MBSws43QpeA [^4] |
| "Anúncios não existem só pra gerar clique." | Post público Instagram — instagram.com/p/DOG9towjggX [^10] |
| "Se o seu lead imobiliário está caro, antes de culpar o tráfego pago, analise o processo comercial." | Post público Instagram — instagram.com/p/DOW8grikoHF [^16] |

### 4.5 Diferenciais Públicos vs. Outros Educadores de Tráfego

1. **300+ semanas de lives semanais públicas e gratuitas** (terças-feiras, 15h, canal Subido) — comprometimento de consistência incomum no mercado[^9][^4]

2. **"Ensinar demais nunca foi o problema — foi o diferencial"** (Growthcast, abr 2025): filosofia de entregar publicamente o que a maioria cobra, como estratégia de construção de audiência qualificada[^17]

3. **Foco em audiência qualificada, não em métricas de vaidade** — "5% de 10.000 seguidores loucos por você valem mais que 100.000 seguidores frios"[^9]

4. **Anti-fórmulas**: posiciona-se contra soluções universais ("não existe um CPM bom"); defende que o melhor benchmark é o próprio histórico do cliente[^8]

5. **Integração orgânico+pago como único ecossistema** — quando a maioria do mercado ensina os dois separados, Sobral defende que são complementares e indissociáveis[^11]

6. **Gestor como conselheiro estratégico** — não apenas executor técnico; responsabilidade inclui entender o processo comercial, a landing page, o atendimento e o produto[^2]

7. **Ecossistema completo (Comunidade Sobral + Contrate um Subido + Subido Ao Vivo)** — cria um mercado interno para os próprios alunos[^2]

***

### Princípios Extraídos para o Agente

1. **O agente deve se recusar a tomar decisões baseado em benchmarks genéricos de mercado** — sempre perguntar pelo CPA/ROAS atual e histórico do cliente específico.
2. **Ao identificar um resultado ruim, a primeira pergunta é sobre o funil completo** — antes de culpar o tráfego, verificar: a oferta é boa? A LP converte? O atendimento fecha? O produto entrega?[^8][^1]
3. **O agente não deve sugerir "só tráfego pago" nem "só orgânico"** — a resposta correta integra os dois como ecossistema.[^11]
4. **Consistência é mais valiosa que sofisticação** — um plano simples executado 300 semanas supera um plano perfeito nunca implementado.[^9]
5. **O criativo já é segmentação** — o agente deve avaliar se o anúncio "repele" ativamente os leads não qualificados, especialmente em high-ticket imobiliário e estética avançada.[^10][^4]
6. **Linguagem do agente deve refletir o tom Sobral**: direta, sem rodeios, com perguntas que forçam clareza antes de receitas prontas — nunca condescendente, sempre estratégica.

***

## Apêndice: Fontes Primárias Verificadas

| Fonte | URL | Tipo |
|---|---|---|
| Blog — 7 erros comuns em campanhas | pedrosobral.com.br/blog/c/introducao-ao-trafego-pago/os-7-erros-comuns-em-campanhas-de-trafego-pago-e-como-evita-los | Artigo blog público |
| Blog — Guia completo tráfego pago | pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/trafego-pago-o-guia-completo-para-comecar-e-ter-resultados-rapidos | Artigo blog público |
| Blog — Como fazer testes no tráfego pago | pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/como-fazer-testes-no-trafego-pago-e-melhorar-seus-resultados | Artigo blog público |
| Blog — Análise e otimização de métricas | pedrosobral.com.br/blog/c/introducao-ao-trafego-pago/analise-e-otimizacao-de-metricas-de-trafego-pago-na-pratica | Artigo blog público |
| Blog — Como ser gestor de tráfego bem pago | pedrosobral.com.br/blog/c/como-ser-um-gestor-de-trafego-pago/comoserumgestorbempago | Artigo blog público |
| Blog — Tráfego pago para clínicas de estética | pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/trafego-pago-para-clinicas-de-estetica | Artigo blog público |
| Palestra Hotmart FIRE 2024 | youtube.com/watch?v=0Xt3U_jy4TQ | Vídeo público Hotmart |
| Live #362 — Andrômeda, Advantage+, PMax | youtube.com/watch?v=MBSws43QpeA | Live pública Canal Subido |
| LinkedIn — Orgânico vs. Pago | linkedin.com/posts/sobral-pedro_abandone-a-mentalidade-de-quinta-série-activity-7259596489390260224 | Post LinkedIn público |
| LinkedIn — 3 tipos de gestores | linkedin.com/posts/sobral-pedro_existem-três-tipos-de-gestores-de-tráfego-activity-7218932418999644160 | Post LinkedIn público |
| Instagram — Lead imobiliário | instagram.com/p/DOW8grikoHF | Post Instagram público |
| Instagram — Anúncios como filtro | instagram.com/p/DOG9towjggX | Post Instagram público |
| Transcrição de lives públicas (Passeidireto) | passeidireto.com/arquivo/101323691/lives-pedro-sobral | Resumo de lives públicas |
| Growthcast (abr 2025) | youtube.com/watch?v=FR_DmUA84-8 | Podcast/entrevista pública |
| Papo Social Media (mai 2025) | youtube.com/watch?v=IfySTVTSyfI | Podcast/entrevista pública |

---

## References

1. [Os 7 erros comuns em campanhas de tráfego pago (e como ...](https://pedrosobral.com.br/blog/c/introducao-ao-trafego-pago/os-7-erros-comuns-em-campanhas-de-trafego-pago-e-como-evita-los) - Um dos erros mais comuns que vejo entre gestores de tráfego é iniciar uma campanha sem ter um objeti...

2. [Tráfego Pago: o guia completo para começar e ter resultados ...](https://pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/trafego-pago-o-guia-completo-para-comecar-e-ter-resultados-rapidos) - A gestão de tráfego é uma profissão muito procurada e rentável porque, pra começar, o gestor de tráf...

3. [Como fazer testes no tráfego pago e melhorar seus resultados | Blog](https://pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/como-fazer-testes-no-trafego-pago-e-melhorar-seus-resultados) - cjkslj

4. [Andromeda, Pmax e Advantage+ como usar a IA das ...](https://www.youtube.com/watch?v=MBSws43QpeA) - Como criar campanhas no Meta Ads em 2026 | Live #363. Canal Subido ... (Gestor de Tráfego) Pedro Sob...

5. [Grátis: Lives Pedro Sobral - Material Claro e Objetivo em ...](https://www.passeidireto.com/arquivo/101323691/lives-pedro-sobral) - Veja grátis o arquivo Lives Pedro Sobral enviado para a disciplina de Marketing Digital Categoria: R...

6. [Princípios de Segmentação no Meta Ads | PDF | Publicidade](https://pt.scribd.com/document/736355546/Como-escolher-publicos-no-meta-ads) - Este documento fornece 19 princípios sobre segmentação de anúncios no Meta Ads. Os princípios aborda...

7. [Tráfego pago para médicos: como usar anúncios online para ...](https://pedrosobral.com.br/blog/c/estrategias-de-trafego-pago/trafego-pago-para-medicos-como-usar-anuncios-online-para-lotar-a-agenda) - Leia esse post e aprenda como gestores de tráfego podem lotar a agenda de médicos usando as estratég...

8. [Análise e otimização de métricas de tráfego pago na prática | Blog](https://pedrosobral.com.br/blog/c/introducao-ao-trafego-pago/analise-e-otimizacao-de-metricas-de-trafego-pago-na-pratica) - Aprenda a dominar as métricas essenciais para avaliar e otimizar suas campanhas de marketing digital...

9. [PEDRO SOBRAL revela sua estratégia no MARKETING ...](https://www.youtube.com/watch?v=0Xt3U_jy4TQ) - Por quanto tempo você mantém as promessas que faz? No Hotmart FIRE 2024, Pedro Sobral revela como a ...

10. [Anúncios não existem só pra gerar clique.](https://www.instagram.com/p/DOG9towjggX/) - Pedro Sobral @pedrosobral · 3 passos simples pra QUALIFICAR um lead (antes da venda) o anúncio já é ...

11. [Abandone a mentalidade de quinta série. Vira e mexe ouço pessoas me… | Pedro Sobral | 14 comentários](https://pt.linkedin.com/posts/sobral-pedro_abandone-a-mentalidade-de-quinta-s%C3%A9rie-activity-7259596489390260224-uDRN) - Abandone a mentalidade de quinta série. Vira e mexe ouço pessoas me perguntando: “Ah, Pedro, tráfego...

12. [Gestao de Trafego Trafego Pago Pedro Sobral | PDF - Scribd](https://pt.scribd.com/document/1003094835/Gestao-de-Trafego-Trafego-Pago-Pedro-Sobral) - O documento é um guia sobre como prospectar, precificar e fechar contratos com clientes de gestão de...

13. [Como ser um gestor de tráfego muito bem pago | Blog - Subido](https://pedrosobral.com.br/blog/c/como-ser-um-gestor-de-trafego-pago/comoserumgestorbempago) - Eu tenho um artigo aqui no blog que também dá uma boa lista de dicas de como MANTER clientes sendo g...

14. [Pedro Sobral on LinkedIn: Existem três tipos de gestores de tráfego: 🎯 Os estratégicos: São os que… | 14 comments](https://pt.linkedin.com/posts/sobral-pedro_existem-tr%C3%AAs-tipos-de-gestores-de-tr%C3%A1fego-activity-7218932418999644160-UtYm) - Existem três tipos de gestores de tráfego: 🎯 Os estratégicos: São os que respondem às grandes pergun...

15. [Gestão de Tráfego com Pedro Sobral | Papo Social Media](https://www.youtube.com/watch?v=IfySTVTSyfI) - Presente do Papo Social Media! 🎁 Você ganhou 1 mês grátis para testar a mLabs. Aproveite: https://ml...

16. [Só a dica final já vale seu like nesse carrossel todo](https://www.instagram.com/p/DOW8grikoHF/) - Se o seu lead imobiliário está caro, antes de culpar o tráfego pago, analise o processo comercial. N...

17. [PEDRO SOBRAL revela qual é o PIOR ERRO dos empresários ao investir em TRÁFEGO PAGO](https://www.youtube.com/watch?v=FR_DmUA84-8) - APRENDA A CONSTRUIR UM TIME QUE GERA +6 DÍGITOS POR MÊS:
https://cp.growthmachine.com.br/curso-gesta...

