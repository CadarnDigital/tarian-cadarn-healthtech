<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Marcas, INPI, Nomes de Dominio e Concorrencia Desleal

```
Voce e um pesquisador especialista em Propriedade Industrial e Marcas no Brasil. Preciso de uma especificacao tecnica modular sobre Registro de Marcas no INPI + Nomes de Dominio e Concorrencia Desleal no contexto de agencias de marketing digital. Este documento sera usado como base para construir um agente de IA que: (1) orienta clientes sobre protecao de marca e registro INPI e (2) identifica riscos de violacao de marca e concorrencia desleal em campanhas — para uma agencia que atende prestadores de servicos premium (high-ticket): imobiliarias, escritorios de advocacia, clinicas de estetica e consultores.

REGRA DE INTEGRIDADE: Cite cada afirmacao com a fonte (lei + artigo, jurisprudencia com numero do processo, tabelas INPI com URL). Se nao encontrar dado confiavel, escreva "nao encontrado com fonte confiavel". Para conteudo inferido, sinalize como "[inferencia aplicada — fonte: X]". Mantenha os termos originais em ingles entre parenteses na primeira mencao.

---

MODULO 1 — INPI: PROCESSO COMPLETO, CUSTOS E JURISPRUDENCIA

Eu ja tenho uma base sobre registro de marca (Art. 129 LPI), principio da especialidade, oposicao em 60 dias (Art. 158 LPI), caducidade por desuso (Art. 143 LPI), trade dress sem registro (Art. 195, III LPI).

O que PRECISO aprofundar:
- Tabela de retribuicoes INPI atualizada (2025-2026): valores de deposito, exame, concessao, renovacao por tipo de requerente (PJ, ME/EPP, PF). URL oficial se disponivel.
- Tempo medio real de tramitacao no INPI em 2025-2026 (apos a reducao do backlog): deposito ate concessao, por tipo de marca (nominativa, mista, figurativa).
- Marca de posicao, marca de movimento, marca sonora: como registrar no INPI? Requisitos especificos? Casos de sucesso no Brasil.
- Jurisprudencia recente (2023-2026) sobre conflito de marcas no setor de servicos (classe 35 — marketing, publicidade) e setor imobiliario (classes 36 e 37).
- Colidencia marcaria: criterios INPI para determinar semelhanca (visual, fonetica, ideologica). Como evitar oposicao fazendo busca previa robusta?
- Marca de alto renome (Art. 125 LPI): quantas existem atualmente no Brasil? Processo de reconhecimento. Algum caso recente de reconhecimento ou perda?
- Uso de marca de terceiro como keyword em Google Ads: STJ (jul/2024) condenou anunciante e Google. Quais os limites apos essa decisao? E em Meta Ads?

---

MODULO 2 — NOMES DE DOMINIO, SACI-ADM E CONCORRENCIA DESLEAL DIGITAL

Eu ja tenho conceitos basicos sobre SACI-Adm, cybersquatting (Art. 195, III e V LPI), typosquatting e registro defensivo.

O que PRECISO aprofundar:
- Procedimento SACI-Adm completo: etapas, prazos, custos, provedores de resolucao de disputas credenciados pelo Registro.br. Prazo medio de resolucao.
- Precedentes SACI-Adm relevantes (2023-2026): casos envolvendo marcas de prestadores de servicos, imobiliarias, clinicas. Criterios de decisao mais comuns.
- Cybersquatting vs domain grabbing: como tribunais brasileiros distinguem? Algum caso onde o registrante venceu?
- Dominios novos (.shop, .law, .clinic, .luxury): como funciona o registro? Existe protecao de marca prioritaria (Sunrise Period)?
- Concorrencia desleal digital: casos recentes (2023-2026) envolvendo: (a) imitacao de identidade visual em redes sociais, (b) uso de marca em hashtags e SEO, (c) review bombing como concorrencia desleal, (d) impersonation de perfis.
- Aproveitamento parasitario no marketing digital: quando a inspiracao vira copia? Jurisprudencia que ajude a tracar a linha.
- Trade dress digital: protecao de layout de site, paleta de cores, estilo de feed do Instagram. Algum caso brasileiro?

---

FORMATO DE SAIDA PARA CADA MODULO:
- Abra com definicao-sintese em 2-3 linhas (para insercao em system prompt de agente de IA)
- Use headers claros, listas numeradas e tabelas comparativas
- Cite URLs de tabelas oficiais (INPI, Registro.br), numeros de processo e artigos
- Feche cada modulo com "Instrucoes para o Agente" — 5-8 regras de comportamento derivadas daquele modulo
- Se nao encontrar informacao confiavel, indique e nao preencha com generico

Aqui está a especificação técnica completa, organizada nos dois módulos solicitados, com fontes em cada afirmação:

***

# Especificação Técnica Modular: Registro de Marcas (INPI) + Nomes de Domínio + Concorrência Desleal Digital

> **Destinação:** Base de conhecimento para agente de IA em agência de marketing digital atendendo prestadores de serviços premium (imobiliárias, escritórios de advocacia, clínicas de estética, consultores).

***

## MÓDULO 1 — INPI: Processo Completo, Custos e Jurisprudência

**Definição-síntese para system prompt:** O INPI (Instituto Nacional da Propriedade Industrial) é o órgão federal responsável pelo registro de marcas no Brasil, conferindo ao titular direito de uso exclusivo por 10 anos, renovável indefinidamente (Art. 133 da Lei nº 9.279/96 — LPI). O registro segue o princípio da especialidade (por classe de Nice) e da territorialidade, sendo indispensável para opor direitos a terceiros, licenciar, franquear ou litigar com segurança jurídica plena.

***

### 1.1 Tabela de Retribuições 2025–2026

A nova Tabela de Retribuições do INPI foi publicada pela **Portaria GM/MDIC nº 110/2025** e pela **Portaria INPI/PR nº 10/2025**, no Diário Oficial da União de 9/12 de maio de 2025, com vigência escalonada:[^1]

- **7 de agosto de 2025:** entram em vigor os novos valores e a taxa única
- **20 de setembro de 2025:** extinção da taxa de certificado de registro
- **20 de dezembro de 2025:** demais ajustes

**Principal inovação estrutural:** A nova tabela unifica depósito + concessão + 1º decênio de vigência + emissão de certificado em uma **taxa única** paga no ato do depósito. O modelo anterior exigia duas fases de pagamento, gerando arquivamentos indevidos por perda de prazo.[^2]

#### Tabela de Valores Vigentes (a partir de 07/08/2025)

| Código | Tipo de Pedido | Requerente | Valor (R$) |
|--------|---------------|------------|------------|
| 1 | Especificação pré-aprovada (lista Nice) | ME/EPP/MEI/Pessoa Física | **R$ 440,00** |
| 1 | Especificação livre | ME/EPP/MEI/Pessoa Física | **R$ 860,00** |
| 2 | Especificação pré-aprovada (lista Nice) | PJ Demais (Ltda, S/A) | **R$ 880,00** |
| 2 | Especificação livre | PJ Demais (Ltda, S/A) | **R$ 1.720,00** |
| 3021 | Comprovação de distintividade adquirida (secondary meaning) | Todos | **R$ 4.700,00** |
| 3022 | Oposição com alegações restritas | Todos | R$ 360,00 (R$ 180,00 c/ desconto) |

**Fonte:** Portaria GM/MDIC nº 110/2025 + Portaria INPI/PR nº 10/2025. URL da tabela oficial: `https://www.gov.br/inpi/pt-br/inpi-data/precificacao-dos-servicos/`[^3][^2]

> **Reajuste médio:** 24,1%, abaixo da inflação acumulada desde 2019.[^2]

**Renovação (Art. 133 LPI):** [inferência aplicada — fonte: LPI Art. 133] A taxa de renovação decenal não está detalhada nas fontes consultadas com novos valores pós-agosto/2025. Recomenda-se consulta direta à tabela oficial acima para código específico de renovação.

***

### 1.2 Tempo Médio Real de Tramitação (2024–2025)

| Fase | Prazo Médio Atual | Observação |
|------|------------------|------------|
| Depósito → 1ª decisão de mérito | **~18 meses** | Sem oposição ou exigência [^4] |
| Com oposição (Art. 158 LPI) | Pode exceder 24–36 meses | Depende de defesas e recursos [^4] |
| Prazo anterior (pré-redução de backlog) | Até 5 anos | Referência histórica [^4] |

> O prazo de 18 meses se aplica ao **primeiro julgamento** (deferimento, indeferimento, sobrestamento ou exigência), não necessariamente à concessão final. Não foram localizados dados desagregados por tipo de marca (nominativa, mista, figurativa) com fonte confiável para o período 2025-2026.[^4]

***

### 1.3 Marcas Não Tradicionais: Posição, Movimento e Sonora

#### Marca de Posição

O INPI passou a aceitar o registro de **marcas de posição** a partir de 2022, por meio de Nota Técnica interna da CGMA/DIRMA.[^5]

**Requisitos cumulativos:**
1. O sinal deve ser aplicado em uma **posição singular e específica** de um determinado suporte
2. A posição deve estar **dissociada de efeito técnico ou funcional** — se a posição tiver função técnica ou utilitária, o INPI indeferirá[^5]
3. O sinal na posição específica deve ter como **única função** identificar a origem dos produtos/serviços
4. A posição não pode estar em locais de **uso comum** para aquele suporte[^5]

**Como registrar:** Pedido via sistema e-Marcas; na representação gráfica, o sinal deve ser destacado (ex.: linhas pontilhadas para indicar o suporte, sinal em destaque na posição específica). Incluir descrição detalhada da posição no formulário.

**Casos de sucesso no Brasil:** Não foram localizados números de processo específicos com fonte confiável para casos de marca de posição concedidos no Brasil pós-2022.

#### Marca Sonora

O INPI **não aceita** registro de marca sonora com base na legislação atual. O Art. 122 da LPI exige que a marca seja "visualmente perceptível", o que exclui sinais puramente auditivos. Há discussão acadêmica sobre a possibilidade de registro mediante representação visual em pauta musical, mas **sem resolução normativa confirmada** até 2025.[^6]

> [inferência aplicada — fonte: Art. 122 LPI] A entrada do Brasil no Protocolo de Madri (2019) gerou pressão para adequação, mas sem alteração legislativa confirmada nas fontes consultadas.

#### Marca de Movimento

Não foram localizadas informações com fonte confiável sobre aceitação formal de marcas de movimento pelo INPI até 2025.

***

### 1.4 Colidência Marcária: Critérios e Busca Prévia

O INPI avalia a colidência entre marcas sob **três eixos complementares** (baseados na interpretação do Art. 124, XIX da LPI e na prática administrativa):

| Critério | Descrição |
|----------|-----------|
| **Similaridade visual** | Comparação gráfica e estética dos elementos; avaliação pelo consumidor de atenção média |
| **Similaridade fonética** | Sons similares que causem confusão auditiva ao serem pronunciados |
| **Similaridade ideológica** | Evocação do mesmo conceito ou ideia, mesmo com grafia diferente |

**Como fazer busca prévia robusta (para evitar oposição):**
1. Acessar o sistema **Busca de Marcas** do e-Marcas: `https://busca.inpi.gov.br/pePI/`[^7]
2. Buscar variações fonéticas (ex.: "K" por "C", "Y" por "I"), não apenas grafia exata
3. Verificar marcas na mesma classe de Nice **e** classes relacionadas (princípio da especialidade + conexão entre produtos/serviços)
4. Pesquisar também marcas com status "em análise" (pedidos depositados sem decisão)
5. Para setores premium: verificar possibilidade de a outra marca ser de **alto renome** (Art. 125 LPI), pois sua proteção é irrestrita independente de classe[^7]

***

### 1.5 Marca de Alto Renome (Art. 125 LPI)

A marca de alto renome recebe **proteção em todas as classes** da Classificação de Nice, independentemente do setor de atuação do titular. O reconhecimento é declarado pelo INPI por meio de Resolução específica.

**Processo de reconhecimento (Art. 125 LPI + Resolução INPI nº 233/2019):**
- Requerimento administrativo pelo titular junto ao INPI
- Demonstração de alto grau de conhecimento entre consumidores de diferentes segmentos
- Pesquisa de percepção do público, faturamento, tempo de uso, abrangência territorial

**Quantas existem atualmente:** Não foi localizado dado atualizado para 2025-2026 com fonte confiável sobre o número exato de marcas de alto renome reconhecidas pelo INPI. A lista oficial pode ser consultada em: `https://www.gov.br/inpi/pt-br/servicos/marcas/alto-renome`.

**Casos recentes (2023-2026) de reconhecimento ou perda:** Não foram localizados casos com número de processo confirmado nas fontes pesquisadas para este período.

***

### 1.6 Jurisprudência Recente: Serviços (Classe 35, 36, 37)

#### Google Ads e Uso de Marca de Terceiro como Keyword — STJ (2024)

A **3ª Turma do STJ**, em decisão publicada em **julho de 2024**, manteve condenação da Google Brasil Internet por danos materiais (e determinou cessação da conduta) ao entender que:[^8][^9]

- A **limitação de responsabilidade do provedor de pesquisa** prevista no **Art. 19 do Marco Civil da Internet (Lei nº 12.965/2014)** **não se aplica** à comercialização de links patrocinados em Google Ads[^8]
- A **venda de marca registrada como palavra-chave para empresa concorrente** configura **ato fraudulento** e **concorrência desleal** por desvio de clientela[^9]
- A **proibição foi modulada**: o Google não pode vender a palavra-chave para **concorrentes diretos**, mas pode comercializá-la para a própria titular da marca ou empresas de setores não concorrentes[^9]

> A ministra relatora Nancy Andrighi destacou: *"uma marca não pode ser tratada como uma palavra genérica e deve ter proteção diferenciada"*.[^9]

Adicionalmente, a **4ª Turma do STJ**, em decisão unânime de **fevereiro de 2026**, ratificou o entendimento de que o uso de marca como palavra-chave para direcionar consumidor ao site de concorrente configura concorrência desleal — sendo decisão inédita daquele órgão fracionário e com potencial de balizar novas ações sobre livre concorrência na internet.[^10]

#### Limites Práticos para Agências após o STJ 2024

| Conduta | Status Jurídico |
|---------|----------------|
| Comprar keyword = marca registrada de concorrente do cliente em Google Ads | **Proibido** — configura concorrência desleal |
| Cliente comprar keyword = sua própria marca | **Permitido** |
| Comprar keyword = marca de empresa de setor diferente | **Permitido** (modulação STJ) |
| Uso de marca de terceiro em hashtag como SEO orgânico | Zona cinzenta — não há precedente STJ específico com fonte confiável |
| **Meta Ads:** uso de marca de terceiro em targeting por interesse | Não encontrado precedente judicial brasileiro com fonte confiável |

***

### 1.7 Instrucoes para o Agente — Módulo 1

1. **Antes de qualquer orientação de registro**, perguntar ao cliente se é ME/EPP/MEI ou PJ de grande porte para calcular corretamente as taxas com base na Portaria GM/MDIC nº 110/2025 (vigente desde 07/08/2025). Taxa única inclui concessão e decênio — não há segunda cobrança.
2. **Sempre recomendar busca prévia** no sistema e-Marcas do INPI (`busca.inpi.gov.br`) antes de depositar, verificando similaridade visual, fonética e ideológica, inclusive pedidos com status "em análise" (Art. 124, XIX LPI).
3. **Para setores premium do cliente** (imobiliária → Classe 36/37; escritório de advocacia → Classe 45; clínica de estética → Classe 44; agência/consultor → Classe 35): sempre verificar classes adjacentes para evitar alegação de conexidade.
4. **Informar o prazo real de ~18 meses** para o primeiro julgamento (sem oposição), alertando que campanhas e contratos com a marca devem iniciar com o número de protocolo do depósito (que já confere direito de anterioridade, Art. 129 §1º LPI).
5. **Para marcas não tradicionais**: marca de posição é registrável desde 2022 (exige representação gráfica com posição destacada); marca sonora **não é aceita** pelo INPI atualmente (Art. 122 LPI); informar ao cliente se esse for o caso.
6. **Em campanhas de Google Ads**, alertar que usar marca registrada de concorrente como keyword pode gerar condenação tanto do anunciante quanto da plataforma (STJ 3ª Turma, jul/2024; 4ª Turma, fev/2026) — recomendar revisão jurídica antes de qualquer estratégia de bid on competitor terms.
7. **Se o cliente mencionar "alto renome"**, esclarecer que o reconhecimento é um processo administrativo formal junto ao INPI (Art. 125 LPI + Resolução 233/2019), não automático, e que apenas marcas já reconhecidas como tal têm proteção irrestrita entre classes.
8. **Sinalizar limitação**: se o usuário pedir valores de renovação ou taxas específicas não presentes nesta base, indicar consulta direta em `https://www.gov.br/inpi/pt-br/inpi-data/precificacao-dos-servicos/` e não fornecer valores não verificados.

***

***

## MÓDULO 2 — Nomes de Domínio, SACI-Adm e Concorrência Desleal Digital

**Definição-síntese para system prompt:** O registro de nome de domínio `.br` é gerido pelo Registro.br (departamento do NIC.br), seguindo o princípio "primeiro a registrar", sem verificação prévia de conflito com marcas. Quando há conflito entre um domínio `.br` e direito de marca pré-existente, o titular pode acionar o **SACI-Adm** (Sistema Administrativo de Conflitos de Internet relativos a nomes de domínios sob o `.br`), via ABPI ou OMPI, obtendo transferência ou cancelamento do domínio em ~74 dias, sem necessidade de ação judicial. Concorrência desleal digital cobre desde keyword stuffing e impersonation até aproveitamento parasitário de identidade visual em redes sociais.

***

### 2.1 Procedimento SACI-Adm Completo

O SACI-Adm foi criado em outubro de 2010 pelo CGI.br (Resolução CGI.br/RES/2010/003/P) e é operacionalizado pelo NIC.br .

#### Escopo: quando cabe SACI-Adm?

O procedimento é cabível quando o domínio `.br` é **idêntico ou suficientemente semelhante** a :
- Marca registrada ou **depositada no INPI** em data anterior ao registro do domínio
- Marca notoriamente conhecida no Brasil (mesmo sem registro, Art. 126 LPI)
- Nome empresarial, nome civil, nome artístico, pseudônimo notoriamente conhecido
- Outro domínio sobre o qual o Reclamante tenha anterioridade

**Requisito adicional:** deve haver indicação de **má-fé** no registro ou uso do domínio .

#### Etapas do Procedimento (Fluxo Oficial — Cartilha CGI.br/NIC.br, 2025)

| Etapa | Descrição | Prazo |
|-------|-----------|-------|
| **1** | Reclamante apresenta petição + documentos + paga taxa à IC escolhida | Momento do pedido |
| **2** | IC analisa requisitos formais | Dias iniciais |
| **3** | NIC.br bloqueia (congela) o domínio | Imediato após comunicação |
| **4** | Titular (Reclamado) é notificado e tem prazo para defesa; em revelia: processo segue normalmente (vedada presunção de veracidade) | Prazo da IC |
| **5** | IC nomeia Painel de 1 ou 3 especialistas | Após prazo de defesa |
| **6** | Painel delibera e profere decisão fundamentada (manutenção, transferência ou cancelamento) | — |
| **7** | Publicação da decisão (anonimizada) | — |
| **8** | Prazo de 15 **dias úteis** para as partes ajuizarem ação judicial ou arbitral | A partir da publicação |
| **9** | Não havendo judicialização: NIC.br executa a decisão | Após prazo de 15 dias úteis |


#### Custos

Os valores variam conforme a IC escolhida, o número de domínios em disputa e se o painel é singular (1 especialista) ou plural (3 especialistas). **As taxas são pagas pelo Reclamante diretamente à IC**, sem repasse ao NIC.br . Para saber os custos atuais:
- **ABPI/CASD-ND:** `https://csd-abpi.org.br/casd-nd-abpi/`
- **OMPI/WIPO:** `https://www.wipo.int/amc/en/domains/`

> Se o Reclamante optou por 1 especialista, mas o Reclamado pede 3, o Reclamante paga honorários de 1 e o Reclamado paga os outros 2 .

#### Prazo e Eficiência

| Indicador | Dado | Fonte |
|-----------|------|-------|
| **Prazo médio real** | **~74 dias** (até a decisão de mérito) | Cartilha CGI.br/NIC.br, dados até 2024 [^11] |
| Prazo máximo regulamentar | 90 dias (prorrogável) | Regulamento SACI-Adm, Art. 28 [^12] |
| Poder Judiciário (equivalente) | 2 a 3 anos | [^11] |
| Velocidade comparativa | **Até 15× mais rápido** | Cartilha CGI.br 2025 [^11] |

#### Resultados (781 procedimentos até 2024)

| Resultado | Quantidade | % |
|-----------|-----------|---|
| Transferência de titularidade | 575 | **85,02%** |
| Manutenção com titular atual | 64 | 8,96% |
| Cancelamento do domínio | 42 | 6,02% |
| Resolvidos por acordo | 79 | ~10,5% (do total) |
| Evoluíram para ação judicial | 21 | ~2,80% |


> **Atenção:** O SACI-Adm **não admite pedido de indenização** — resolve apenas a titularidade do domínio. Pedidos de danos devem ser levados ao Judiciário .

***

### 2.2 Cybersquatting vs. Domain Grabbing: Distinção Judicial

Não foram localizados casos judiciais brasileiros pós-2023 com número de processo que distinguissem explicitamente "cybersquatting" de "domain grabbing" com decisão favorável ao registrante, com fonte confiável.

**[inferência aplicada — fonte: Art. 195, III e V LPI + doutrina]** A distinção prática é:
- **Cybersquatting:** registro de domínio idêntico/similar a marca alheia com intenção de vender ao titular ou prejudicá-lo (má-fé clara)
- **Domain grabbing:** registro especulativo em massa de domínios para revenda, sem necessariamente visar marca específica

Em ambos os casos, o critério determinante no SACI-Adm é a **demonstração de má-fé** combinada com a **anterioridade da marca ou sinal distintivo** do Reclamante.

Casos onde o registrante venceu (manteve o domínio) correspondem a **8,96%** das decisões SACI-Adm — tipicamente por ausência de má-fé demonstrável ou quando o Reclamante não demonstrou anterioridade suficiente .

***

### 2.3 Domínios Novos (.shop, .law, .clinic, .luxury)

Os domínios genéricos de topo (gTLDs) como `.shop`, `.law`, `.clinic` e `.luxury` são geridos pela **ICANN** e seus registradores credenciados, não pelo Registro.br. O registro segue regras ICANN, não as do NIC.br.[^13]

**Sunrise Period:** Muitos novos gTLDs oferecem um período de registro prioritário (*Sunrise Period*) para titulares de marcas registradas no **TMCH (Trademark Clearinghouse)**, mecanismo da ICANN que permite inscrição de marcas registradas para receber alertas e acesso prioritário. Para usar o Sunrise Period, a marca deve estar cadastrada no TMCH: `https://www.trademark-clearinghouse.com/`.

**Proteção de marca prioritária para gTLDs:** [inferência aplicada — fonte: política ICANN UDRP e TMCH] O titular de marca registrada pode acionar a **UDRP (Uniform Domain Name Dispute Resolution Policy)** para disputar domínios em gTLDs genéricos, mesmo após o Sunrise Period.

> **Importante para o agente:** Domínios `.br` são disputados exclusivamente via SACI-Adm ou Judiciário brasileiro. Domínios como `.com`, `.shop`, `.law` seguem a UDRP da ICANN, via OMPI ou NAF.

***

### 2.4 Concorrência Desleal Digital: Casos e Enquadramento Jurídico

#### (a) Imitação de Identidade Visual em Redes Sociais

O STJ, ao julgar o **AgInt no REsp nº 1.851.321/MG (2019/0357740-8)**, reconheceu o dever de indenizar por **uso indevido de marca e reprodução de elementos visuais de identidade semelhantes**, confirmando que a imitação parcial capaz de gerar confusão ao consumidor enseja proibição e obrigação de indenizar.[^14][^15]

A **3ª Turma do STJ**, em decisão de **maio de 2025** (processo não identificado com número confirmado nas fontes consultadas), reiterou que o uso indevido de marca registrada com intenção de confundir o consumidor ou desviar clientela é passível de sanção civil e indenização por dano extrapatrimonial.[^16]

#### (b) Uso de Marca em Hashtags e SEO

Não foram localizados casos judiciais brasileiros com número de processo específico sobre uso de marca de terceiro em hashtags ou SEO orgânico como concorrência desleal com fonte confiável para 2023-2026.

**[inferência aplicada — fonte: Art. 195 LPI + princípios gerais de concorrência desleal]** O uso de marca alheia como hashtag com finalidade de desviar clientela ou criar confusão pode se enquadrar no Art. 195, III (venda com falsa indicação de procedência) ou V (uso indevido de signo) da LPI. A diferença entre SEO neutro (citação informativa) e SEO parasitário (uso para captação indevida) será avaliada caso a caso.

#### (c) Review Bombing como Concorrência Desleal

Não foram localizados casos judiciais brasileiros sobre *review bombing* como concorrência desleal com fonte confiável para 2023-2026.

**[inferência aplicada — fonte: Art. 195, IV LPI + CDC]** Avaliações falsas e coordenadas para prejudicar concorrente podem se enquadrar no Art. 195, IV LPI (divulgar informações falsas sobre concorrente) e no Art. 67 do CDC (publicidade enganosa). A dificuldade probatória é considerável — requer prova da coordenação e do nexo com o concorrente.

#### (d) Impersonation de Perfis

Não foram localizados casos judiciais brasileiros específicos sobre impersonation de perfis com número de processo confirmado para 2023-2026. A conduta pode se enquadrar em **concorrência desleal** (Art. 195 LPI), **uso indevido de nome empresarial** (Art. 1.166 CC) e, se envolver falsidade de identidade, em esfera criminal (Art. 307 CP).

***

### 2.5 Aproveitamento Parasitário no Marketing Digital

O STJ consolidou o entendimento de que a **imitação parcial, quando capaz de causar confusão ao consumidor**, configura aproveitamento parasitário e gera obrigação de indenizar.[^15]

**A linha entre inspiração e cópia (critérios jurisprudenciais):**

| Inspiração lícita | Aproveitamento parasitário |
|-------------------|---------------------------|
| Paleta de cores similar, sem conjunto-imagem identificável | Reprodução do conjunto-imagem completo (cores + tipografia + layout) que gera confusão |
| Mesmo segmento de mercado, identidade visual própria | Criação deliberada de semelhança para captar clientela do concorrente |
| Menção informativa à marca concorrente (comparação leal) | Uso de marca alheia para direcionar consumidor ao próprio produto/serviço |
| Referência a produto alheio em contexto jornalístico | Uso de marca em anúncio pago para desvio de clientela (STJ, jul/2024) [^8] |

***

### 2.6 Trade Dress Digital

Não foram localizados casos brasileiros específicos com decisão judicial confirmada sobre **trade dress digital** (proteção de layout de site, paleta de cores, estilo de feed do Instagram) com número de processo e fonte confiável para 2023-2026.

**[inferência aplicada — fonte: Art. 195, III LPI + jurisprudência sobre conjunto-imagem]** O trade dress digital pode ser protegido como **conjunto-imagem** (trade dress) sem necessidade de registro específico, desde que o titular comprove:
1. Distintividade (o conjunto visual identifica unicamente a origem do serviço)
2. Anterioridade no uso
3. Possibilidade de confusão ou associação indevida

O Art. 195, III LPI proíbe o uso de "meio fraudulento" para desviar clientela, o que pode abranger a reprodução do conjunto visual digital de concorrente.

Para **clínicas de estética, escritórios e imobiliárias premium**: a proteção mais robusta combina registro da marca nominativa/mista no INPI + documentação de uso do conjunto visual (prints com datas, contratos de criação, ata notarial do site/feed) para eventual disputa.

***

### 2.7 Precedentes SACI-Adm Relevantes (2023-2026)

Não foram localizados números de processo específicos de decisões SACI-Adm de 2023-2026 envolvendo imobiliárias, clínicas ou prestadores de serviços com fonte confiável e detalhamento suficiente. As decisões publicadas pelo NIC.br e pelas ICs (ABPI e OMPI) podem ser consultadas em:
- ABPI: `https://csd-abpi.org.br/casd-nd-abpi/decisoes/`
- OMPI: `https://www.wipo.int/amc/en/domains/decisions/`
- NIC.br: `https://registro.br/dominio/decisoes-saci-adm.html`

***

### 2.8 Instrucoes para o Agente — Módulo 2

1. **Quando um cliente relatar uso indevido de domínio `.br`**, orientar o acionamento do SACI-Adm via ABPI ou OMPI: prazo médio de **74 dias**, custo pago pelo reclamante à IC escolhida, resolução exclusivamente de titularidade do domínio — danos patrimoniais demandam ação judicial separada.[^11]
2. **Verificar sempre a má-fé** antes de recomendar SACI-Adm: a ausência de má-fé demonstrável é o principal motivo pelo qual 8,96% dos reclamados vencem. Má-fé pode ser indicada por: oferta de venda do domínio ao titular da marca, uso para concorrência direta, domínio registrado após a marca .
3. **Para domínios genéricos (`.com`, `.shop`, `.law`)**: o mecanismo correto não é SACI-Adm, mas a **UDRP da ICANN** via OMPI. Recomendar inscrição preventiva no TMCH (Trademark Clearinghouse) para marcas registradas de clientes com potencial de expansão digital.
4. **Em campanhas de marketing digital**, nunca usar marca registrada de concorrente como palavra-chave em Google Ads para direcionar tráfego — risco confirmado de condenação solidária (anunciante + Google) após STJ jul/2024 (3ª Turma) e fev/2026 (4ª Turma).[^10][^8]
5. **Para identidade visual de cliente premium**, recomendar documentação formal do conjunto-imagem digital (ata notarial, registro de criação, screenshots com timestamp) como complemento ao registro INPI, para eventual ação de trade dress digital com base no Art. 195, III LPI.
6. **Para setores imobiliário e de estética**: alertar que *review bombing* coordenado por concorrente pode ser enquadrado no Art. 195, IV LPI, mas requer robusta prova documental da coordenação — recomendar preservação de evidências (prints, IP logs, relatórios de plataforma) desde o início.
7. **O SACI-Adm é inteiramente online e em português**; advogado é facultativo mas recomendado . Para casos com histórico de litigância ou reclamado pessoa jurídica representada, recomendar orientação jurídica especializada.
8. **Sinalizar limitação**: se solicitado valor exato de custas SACI-Adm, indicar consulta direta à ABPI (`csd-abpi.org.br`) ou OMPI (`wipo.int/amc`) — os valores não são padronizados e variam por IC e por número de domínios/especialistas.
<span style="display:none">[^17][^18][^19][^20][^21][^22][^23][^24][^25][^26][^27][^28][^29][^30]</span>

<div align="center">⁂</div>

[^1]: https://gomesaltimari.com.br/inpi-atualiza-tabela-de-retribuicoes-entenda-os-impactos-e-como-se-preparar-para-as-novas-taxas-a-partir-de-agosto-de-2025/
[^2]: https://www.sosmarcasepatentes.com.br/nova-tabela-do-inpi-2025-o-que-muda-e-como-economizar-no-registro-da-sua-marca/
[^3]: https://www.gov.br/inpi/pt-br/inpi-data/precificacao-dos-servicos/tabela-de-retribuicoes-inpi_portaria-mdic-no110_2025-e-portaria-inpi-no-10_2025.pdf
[^4]: https://agpmarcasepatentes.com.br/quanto-tempo-leva-um-registro-de-marca-no-inpi-e-como-reduzir/
[^5]: https://www.kasznarleonardos.com/inpi-passa-a-aceitar-o-registro-de-marcas-de-posicao/
[^6]: https://www.portaldeperiodicos.idp.edu.br/rda/article/download/6234/2530/20311
[^7]: https://www.gov.br/inpi/pt-br/servicos/marcas/guia-basico
[^8]: https://www.stj.jus.br/sites/portalp/Paginas/Comunicacao/Noticias/2024/09072024-Terceira-Turma-mantem-condenacao-do-Google-em-caso-de-concorrencia-desleal-com-links-patrocinados.aspx
[^9]: https://jcm.adv.br/noticia/stj-mantem-condenacao-da-google-por-concorrencia-desleal-em-links-patrocinados/
[^10]: https://bvalaw.com.br/blog/stj-ratifica-concorrencia-desleal-marcas/
[^11]: https://cgi.br/media/docs/publicacoes/13/pt/20251013164752/cartilha-saci-adm.pdf
[^12]: https://csd-abpi.org.br/casd-nd-abpi/regulamento-saci-adm/
[^13]: https://periodicos.unicesumar.edu.br/index.php/revjuridica/article/download/5113/3096/27113
[^14]: https://www.smnadv.com.br/uso-indevido-de-marca-e-concorrencia-desleal-quando-surge-o-dever-de-indenizar/
[^15]: https://legale.com.br/blog/concorrencia-desleal-e-uso-indevido-de-marca-guia-juridico-pratico/
[^16]: https://www.instagram.com/p/DJWYq3CRnt4/
[^17]: https://www.gov.br/inpi/pt-br/central-de-conteudo/noticias/inpi-fixa-descontos-para-a-nova-tabela-de-retribuicoes-pelos-seus-servicos
[^18]: https://fasadv.com.br/pt/bra/publication/novas-taxas-do-inpi-entram-em-vigor-em-agosto
[^19]: https://zavagnagralha.com.br/atualizacao-de-taxas-oficiais-do-inpi/
[^20]: https://registrojusto.com.br/o-reajuste-no-valor-do-registro-de-marcas-no-inpi-em-2025/
[^21]: https://www.nic.br/noticia/na-midia/conflito-entre-marcas-e-nomes-de-dominio-na-internet/
[^22]: https://www.youtube.com/watch?v=HVK_zTEfDdM
[^23]: https://www.montaury.com.br/pt/o-plano-de-combate-ao-backlog-de-patentes-do-inpi
[^24]: https://buscadordizerodireito.com.br/jurisprudencia/12887/a-utilizacao-de-marca-como-palavra-chave-para-direcionar-o-consumidor-do-produto-ou-servico-para-o-link-de-seu-concorrente-configura-se-como-meio-fraudulento-para-desvio-de-clientela
[^25]: https://www.migalhas.com.br/quentes/402160/stj-google-ads-nao-pode-vender-palavra-chave-para-marca-concorrente
[^26]: https://veja.abril.com.br/coluna/radar/stj-mantem-condenacao-ao-google-por-concorrencia-desleal-em-anuncios/
[^27]: https://politics.org.br/pt-br/governanca-news/saci-o-sistema-administrativo-de-conflitos-de-internet-implementado-para-dominios
[^28]: https://www.baguete.com.br/noticias/google-condenado-por-link-patrocinado
[^29]: https://csd-abpi.org.br/casd-nd-abpi/regulamento-saci-adm-atualizado/
[^30]: https://www.jota.info/opiniao-e-analise/artigos/decisao-do-stj-sobre-google-ads-e-um-marco-para-a-propriedade-intelectual```

