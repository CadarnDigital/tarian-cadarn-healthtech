---
tipo: dossie-consolidado
origem: framework-cadarn-m2m/cadarn-martech/ (sem subpastas pesquisas/ e framework-antigo/)
criado_em: 2026-03-18
analista: Echo + Orion
total_documentos_analisados: 24
checksum_l1: "sha256:dd6526c0990ee7e18ae4fe538f42b3a0962880110013be9111c64d355a8037d3"
simhash_l2: null
---

> ⚠️ **HISTÓRICO — RELATÓRIO DE INTELIGÊNCIA (18/03/2026). Não é o dossiê doutrinário.**
> Este é o relatório de inteligência editorial (Echo + Orion) que analisou 24 documentos e gerou as
> recomendações que originaram o dossiê oficial. **NÃO confundir** com o framework vigente. A fonte
> única é o **dossiê v6.0** (`docs/negocio-cadarn/01-vigente/dossie-framework-cadarn-v6.md`). Mantido como genealogia.

# DOSSIE FRAMEWORK CADARN -- Consolidado para Revisao

## RELATORIO DE INTELIGENCIA

### Redundancias Identificadas

**GRUPO 1 -- Valores / Hexagono Moral (5 documentos sobrepostos)**

| Documento | Conteudo |
|-----------|----------|
| `codigo-cadarn-manifesto-ordem-valores.md` | 6 valores como "Ciclo de Ascensao" narrativo (Verdade, Arquitetura Evolutiva, Blindagem, Padrao Cirurgico, Autonomia, Pacto de Trincheira) |
| `bussola-valores-hexagono-moral.md` | 6 valores como taxonomia estruturada (Excelencia, Prudencia, Justica, Inovacao, Poder, Lealdade) com 5 topicos cada |
| `cadarn-valores.md` | Os mesmos 6 valores com dupla perspectiva (Mente do Arquiteto + Entrega da Realizadora) e mantras por valor |
| `arquitetura-moral-cadarn-hexagonal.md` | Mapeamento de como cada valor conecta a uma letra do C.A.D.A.R.N. |
| `roteiro-ciclo-engenharia-cadarn-valores.md` | Roteiro de video/apresentacao narrando os 6 valores como espiral ascendente |

**Nota editorial:** Todos falam da mesma coisa (os 6 valores Cadarn), mas com perspectivas diferentes. O `cadarn-valores.md` e o mais completo e maduro. O `bussola-valores-hexagono-moral.md` tem a taxonomia mais detalhada. O `manifesto-ordem-valores` e o mais narrativo/emocional. O `arquitetura-moral-cadarn-hexagonal.md` faz a ponte valores-metodo. O roteiro e instrumental (para video).

**GRUPO 2 -- Metodologia C.A.D.A.R.N. (5 documentos sobrepostos)**

| Documento | Conteudo |
|-----------|----------|
| `acronimo-metodo-cadarn.md` | Definicao pura do acronimo (6 letras, conceito e acao) |
| `excelente-escolha-fabiano.md` | Genese do acronimo C.A.D.A.R.N. + Motor Hexagonal SGC + nomenclatura + carrosseis |
| `protocolo-hexagonal-engenharia-receita.md` | Versao "para o cliente" do metodo (texto introdutorio do Playbook) |
| `6-pilares-engenharia-cadarn.md` | 6 pilares como doutrina comercial (para pitch/venda) |
| `briefing-estrategico-ogilvy-para-jp.md` | Briefing explicando a transicao do metodo 10P para o Hexagonal |

**Nota editorial:** O `acronimo-metodo-cadarn.md` e uma copia exata de uma secao do `excelente-escolha-fabiano.md` (duplicata literal). O `6-pilares` expande o metodo para alem do acronimo (inclui Inteligencia Agil, Terreno Proprio, Console S.I.C., etc.). O briefing para JP e contextual e unico.

**GRUPO 3 -- Missao/Visao/Proposito (3 documentos sobrepostos)**

| Documento | Conteudo |
|-----------|----------|
| `missao-visao-cadarn-martech.md` | Missao, Visao, Proposito + Visao Interna + Imagem Desejada 12 meses |
| `codigo-cadarn-memorando-fundacao-v2.md` (Parte I) | Missao, Visao, Proposito (versao refinada, com foco em marketing) |
| `memorando-estrategico-cadarn-martech.md` (Secao 1) | Sumario executivo com tese da empresa |

**Nota editorial:** O Memorando V2 tem a versao mais recente e ajustada da missao (foco em "Sindrome do Especialista Exausto" e "marketing" em vez de "processos e tecnologia de elite"). O `missao-visao` original foca mais em "Engenharia de Processos e Tecnologia de Elite". Sao visoes do mesmo conceito em momentos diferentes.

**GRUPO 4 -- Matriz de Diferenciacao (2 documentos sobrepostos)**

| Documento | Conteudo |
|-----------|----------|
| `matriz-diferenciacao-dna-cadarn.md` | 7 diferenciais com formato Cadarn-faz vs Concorrencia-faz |
| `codigo-cadarn-memorando-fundacao-v2.md` (Parte V) | 6 diferenciais no mesmo formato |

**Nota editorial:** A `matriz-diferenciacao-dna-cadarn.md` e mais completa (inclui Triade Operacional como 7o diferencial). O Memorando V2 e uma versao anterior com 6 itens.

---

### Incoerencias / Contradicoes

**1. Nomenclatura dos valores entre versoes**

- No `manifesto-ordem-valores.md`: os valores sao apresentados como principios narrativos (Verdade Radical, Arquitetura Evolutiva, Blindagem de Risco, Padrao Cirurgico, Lei da Autonomia, Pacto de Trincheira).
- No `bussola-valores-hexagono-moral.md`: os valores sao categorias abstratas (Excelencia, Prudencia, Justica, Inovacao, Poder, Lealdade).
- No `cadarn-valores.md`: usa ambas as nomenclaturas mapeadas (ex: "A Verdade Radical" = Valor Padrao JUSTICA).
- **O problema:** A ordem dos valores muda entre documentos. No manifesto a sequencia e Justica > Inovacao > Prudencia > Excelencia > Poder > Lealdade. Na Bussola e Excelencia > Prudencia > Justica > Inovacao > Poder > Lealdade. Nao ha consenso sobre qual e o "primeiro" valor.

**2. Mapeamento valores-para-letras C.A.D.A.R.N. tem conflitos**

- No `excelente-escolha-fabiano.md`: Prudencia = D (Dados), Justica = N (Norma), Poder = A (Acao), Inovacao = C (Clareza), Excelencia = "Cola" (Hanlon). Lealdade nao aparece.
- No `arquitetura-moral-cadarn-hexagonal.md`: Prudencia = D, Justica = N+R, Poder = A, Inovacao = C, Excelencia = A (Arquitetura), Lealdade = "Liga" (retencao). Ajustes de topicos (Curiosidade adicionada a Inovacao, Precisao adicionada a Excelencia).
- **O problema:** A Excelencia mapeia para "Cola/Hanlon" num documento e para "A (Arquitetura)" no outro. A Justica mapeia para "N" num e para "N+R" no outro.

**3. Quantos valores sao?**

- Todos os documentos atuais falam em 6 valores.
- A pasta `framework-antigo/` (nao analisada aqui) tem versao com 5 valores. O `arquitetura-moral-cadarn-hexagonal.md` marca Lealdade como "NOVO", confirmando que houve evolucao de 5 para 6.

**4. Missao -- foco divergente**

- `missao-visao-cadarn-martech.md`: "aplicar a Engenharia de Processos e a Tecnologia de Elite para MATERIALIZAR O LUCRO e BLINDAR O LEGADO"
- `codigo-cadarn-memorando-fundacao-v2.md`: "aplicar a Engenharia de Marketing e Vendas para MATERIALIZAR O LUCRO"
- **O problema:** A primeira versao fala de "Processos e Tecnologia de Elite" (visao mais ampla, gestao 360). A segunda foca em "Marketing e Vendas" (escopo reduzido, coerente com o momento atual). Qual e a missao oficial?

**5. SGC vs C.A.D.A.R.N. -- sobreposicao de nomenclatura**

- No `excelente-escolha-fabiano.md`, o "SGC" (Sistema de Gestao Cadarn) e o motor hexagonal com 6 fases proprias (Diagnostico, Validacao, Planejamento, Execucao, Conferencia, Padronizacao).
- Depois, o acronimo C.A.D.A.R.N. substitui esses nomes (Clareza, Arquitetura, Dados, Acao, Rastreio, Norma).
- **O problema:** O mapeamento nao e 1:1. "Diagnostico" virou "Clareza", "Validacao" virou "Dados", "Planejamento" virou "Arquitetura" (inverteu a ordem 2-3 para 1-2). A nomenclatura SGC e a C.A.D.A.R.N. coexistem no mesmo documento sem resolucao explicita de qual e a oficial.

**6. Letra "D" do C.A.D.A.R.N. -- nome conflitante**

- `acronimo-metodo-cadarn.md`: D = DADOS (A Validacao)
- `protocolo-hexagonal-engenharia-receita.md`: D = DADOS & DNA (A Identidade)
- `briefing-estrategico-ogilvy-para-jp.md`: D = DADOS & DNA (A Identidade)
- **O problema:** "D" significa "validacao com numeros" ou "identidade de marca (DNA)"? Sao funcoes completamente diferentes.

---

### Documentos Possivelmente Obsoletos

| Documento | Motivo |
|-----------|--------|
| `acronimo-metodo-cadarn.md` | Copia exata de uma secao do `excelente-escolha-fabiano.md`. Duplicata desnecessaria. |
| `excelente-escolha-fabiano.md` | E um log bruto de conversa com IA (Janus 2.0), contendo rascunhos, perguntas de aprovacao, carrosseis de Instagram e a genese do metodo. Muito do conteudo foi refinado em documentos posteriores (Memorando V2, 6 Pilares, cadarn-valores). A parte util (genese do SGC, nomenclatura, carrosseis) deveria ser extraida e o documento descartado como historico. |
| `arquitetura-moral-cadarn-hexagonal.md` | Versao anterior do mapeamento valores-metodo. O `cadarn-valores.md` e mais completo e maduro. |
| `contexto-do-problema.md` | Briefing tecnico para ferramenta de qualificacao de leads via Instagram. Nao e framework -- e um documento operacional pontual (briefing de prompt para IA). |
| `nova-estrutura-mensagem-elogio-sincero.md` | Scripts de abordagem comercial para clinicas e imobiliarias. E instrumental, nao doutrina. |

---

### Gaps Identificados

1. **Pipeline de produtos atualizado**: O Memorando V2 define 4 produtos (Auditoria, Diagnostico+Plano, Plano Tatico Hexagonal, Conselho Estrategico). O `insights-hanlon-cadarn.md` menciona venda do Plano Tatico a R$ 750. O `cadarn-futuro-backlog-estrategico.md` projeta novos produtos. Nao ha documento unico consolidando o catalogo de produtos com precos, escopos e status atualizados.

2. **ICP (Ideal Customer Profile) definitivo**: O Memorando Estrategico diz "Prestador de Servicos de Elite". O briefing para JP diz "PMEs com Sindrome de Atlas". O documento de contexto do problema fala de "clinicas de estetica". Nao ha documento unico definindo o ICP com criterios objetivos e priorizacao de segmentos.

3. **Console S.I.C. -- especificacao**: Mencionado em 5+ documentos como diferencial-chave, mas nenhum documento especifica o que ele e tecnicamente (dashboard? planilha? software?), quais metricas monitora e como funciona na pratica.

4. **Agentes de IA (Nexus, Flux, Ogilvy, Hanlon, Clio, Tay, Janus)**: Citados em multiplos documentos com funcoes diferentes. Nao ha catalogo unificado de agentes com: nome, funcao, status (ativo/descontinuado), tecnologia base.

5. **Processos operacionais internos**: O framework define o que vender e como vender, mas nao documenta como a Cadarn opera internamente (fluxo de trabalho entre Fabiano e Samira, SLAs de entrega, ferramentas usadas).

6. **Prova social e cases**: Multiplos documentos mencionam a necessidade de "Dossiês de Caso" e prova social, mas nao ha nenhum case documentado nos arquivos.

---

### Linha do Tempo (evolucao percebida)

| Fase | Periodo estimado | Evento | Documentos |
|------|-----------------|--------|------------|
| 1 | Pre-2025 | Valores originais com 5 pontas (sem Lealdade) | (framework-antigo/) |
| 2 | Inicio 2025 | Conversa com Janus 2.0: criacao do SGC (Motor Hexagonal), nomenclatura proprietaria, adocao do acronimo C.A.D.A.R.N., evolucao para 6 valores (adicao de Lealdade) | `excelente-escolha-fabiano.md` |
| 3 | Meados 2025 | Manifesto narrativo dos valores, Bussola Moral detalhada, Arquitetura Moral mapeando valores ao metodo | `codigo-cadarn-manifesto-ordem-valores.md`, `bussola-valores-hexagono-moral.md`, `arquitetura-moral-cadarn-hexagonal.md` |
| 4 | Final 2025 | Genesis narrativa (historia da Cadarn), definicao de missao/visao, analise SWOT, 5 Leis de Gestao | `genese-cadarn-do-caos-a-engenharia.md`, `missao-visao-cadarn-martech.md`, `5-leis-imutaveis-gestao-processos.md` |
| 5 | Inicio 2026 | Memorando de Fundacao V2 (consolidacao madura), Memorando Estrategico (tese de escala), Framework negocio digital, Briefing para JP, 6 Pilares como doutrina comercial | `codigo-cadarn-memorando-fundacao-v2.md`, `memorando-estrategico-cadarn-martech.md`, `framework-construir-negocio.md`, `briefing-estrategico-ogilvy-para-jp.md`, `6-pilares-engenharia-cadarn.md` |
| 6 | Fev-Mar 2026 | Refinamento de valores com dupla perspectiva, Roteiro de video, Matriz de Diferenciacao, Insights Ogilvy/Hanlon, Scripts comerciais, Backlog futuro, Diagnostico GPT | `cadarn-valores.md`, `roteiro-ciclo-engenharia-cadarn-valores.md`, `matriz-diferenciacao-dna-cadarn.md`, `insights-cadarn-ogilvy.md`, `insights-hanlon-cadarn.md`, `nova-estrutura-mensagem-elogio-sincero.md`, `cadarn-futuro-backlog-estrategico.md`, `briefing-diagnostico-instagram-automacao-dm.md` |

**Evolucao do pensamento:**
- Comecou como um sistema de gestao generico (SGC), pivotou para marketing como ponta de lanca.
- Valores evoluiram de 5 para 6 (adicao de Lealdade).
- Missao migrou de "Engenharia de Processos" para "Engenharia de Marketing e Vendas" (escopo reduzido por pragmatismo).
- Nomenclatura evoluiu de SGC para C.A.D.A.R.N., de "Digital" para "Martech".
- A letra "D" do acronimo mudou de "Dados/Validacao" para "Dados & DNA/Identidade" sem resolucao formal.

---

## CONTEUDO CONSOLIDADO

### 1. IDENTIDADE E FUNDACAO

#### Missao

**Versao mais recente (Memorando V2, 2026):**
"Erradicar a 'Gestao de Esperanca' que destroi os pequenos negocios e as familias. O nosso alvo e curar a 'Sindrome do Especialista Exausto' -- o profissional de excelencia tecnica cujo marketing caotico nao reflete a qualidade do seu trabalho. A nossa missao e aplicar a Engenharia de Marketing e Vendas para MATERIALIZAR O LUCRO. Existimos para transformar o esforco bruto do empreendedor numa maquina de vendas previsivel, para que o sonho de ter o proprio negocio jamais se torne o pesadelo da escravidao."

**Versao anterior (missao-visao, ~2025):**
"Erradicar a 'Gestao de Esperanca' que destroi negocios e familias. Nossa missao e aplicar a Engenharia de Processos e a Tecnologia de Elite para MATERIALIZAR O LUCRO e BLINDAR O LEGADO."

**Nota editorial:** A versao V2 e mais especifica (foca em marketing/vendas, define o alvo como "Especialista Exausto") e pragmatica. A anterior e mais ambiciosa (processos + tecnologia de elite). Fabiano precisa decidir qual e a oficial.

#### Visao

**Versao mais recente (Memorando V2):**
"Ser a bussola que liberta os negocios do caos, entregando o mapa e um metodo pratico, aplicavel e gerivel no dia a dia, para que as familias construam o seu proprio LEGADO DURADOURO. Visualizamos um mercado onde a escolha cruel entre 'Sucesso Empresarial' e 'Paz Familiar' foi abolida pela Ordem e pela execucao."

**Versao anterior (missao-visao):**
"Ser a 'Rocha' sobre a qual familias constroem um LEGADO DURADOURO. Visualizamos um mercado onde a escolha cruel entre 'Sucesso Empresarial' e 'Paz Familiar' foi abolida pela Ordem."

**Nota editorial:** A V2 e mais tangivel ("entregando o mapa e um metodo pratico"). Ambas compartilham o nucleo: abolir a escolha cruel entre sucesso e paz familiar.

#### Proposito Sintetizado

**Versao V2:** "Onde o mercado vende sorte, nos desenhamos o mapa. Processos praticos para que o seu talento nao morra no caos."

**Versao anterior:** "Nos nao vendemos sorte; nos construimos o chao firme para que o talento nao morra no caos."

#### Elevator Pitch

"Se voce quer brincar de internet com posts genericos, contrate fazedores de posts; se voce e um empreendedor que precisa escalar as suas vendas, estancar o sangramento e destravar o lucro, chame a Cadarn."

#### Antitese

"Somos o oposto da 'Gestao de Esperanca' (que vende sorte e hype); somos a Engenharia de Controle (que vende processos, dados e previsibilidade)."

#### Quem Somos (Auto-definicao)

- A Antitese dos Gurus: Enquanto eles vendem o palco, nos vendemos o bastidor blindado.
- Engenheiros de Liberdade: Organizacao e a unica liberdade possivel.
- Guardioes do Legado: O lucro e o meio; a familia blindada e o fim.
- A "Hermes" do B2B: Percebida como cara, exclusiva e indispensavel.
- Martech Nativa: Fusao de sabedoria humana com velocidade da IA.
- Anti-Guru: Referencia de sobriedade num mercado de promessas vazias.
- Velocidade de Elite: Instala infraestrutura de lucro em 10 dias.

#### A Triade Operacional

- **A Realizadora (Samira Alcantara - CRO):** Voz da Autoridade. Experiencia de trincheira no varejo de alta performance. Traduz engenharia fria em desejo de compra. Ancora valor, conduz negociacao, treina equipes. Premissa: "estetica sem venda e apenas decoracao". Background: Design de Moda (Faesa), Pos em Branding/Storytelling (PUC), IA Aplicada (Exame). 16+ anos de gestao de varejo (CS Club/Carmen Steffens, Itapua, M.Officer, Malwee).

- **O Arquiteto (Fabiano Cunha - CEO):** Mente da Engenharia. Background tecnico, juridico e financeiro. Desenha metodos, estabelece norte estrategico, audita riscos. Guardiao da paz familiar do cliente. Juiz do Console S.I.C. Se Samira e a ponta de lanca (Vendas), Fabiano e o general de guerra (Estrategia, Processo e Lucro).

- **O Legado (Gui - 11 anos):** Aprendiz e braco de tecnologia em formacao. Prova viva de que a Cadarn pratica o discurso sobre familia. Apoio no Laboratorio de IA. Arquiteto tecnologico responsavel por refinar os Agentes de IA (Nexus e Flux).

#### Visao Interna (Diagnostico Realista)

**O que somos hoje:**
- Uma "Unidade de Inteligencia Tatica" de altissima capacidade tecnica, operando como Triade Blindada (Familia como ativo de confianca maxima).
- Empresa em transicao: saindo da execucao bracal (agencia tradicional) para a engenharia de lucro (consultoria de elite).
- Laboratorio de inovacao validado (C.A.D.A.R.N.), mas que o mercado ainda confunde com "mais uma agencia de marketing".
- Operacao enxuta, capaz de resolver em 10 dias com tecnologia o que grandes estruturas nao resolvem em 6 meses.

**Lacunas percebidas:**
- Volume de Prova Social Publica: Transformar resultados internos em "Dossies de Caso" publicos.
- Descentralizacao Operacional: Reduzir dependencia extrema da energia vital dos fundadores.
- Reconhecimento Nacional: Romper a bolha regional.

---

### 2. METODOLOGIA C.A.D.A.R.N.

#### O Acronimo

O metodo C.A.D.A.R.N. e um ciclo hexagonal de 6 etapas de dependencia logica. Foi desenhado para funcionar em qualquer area (marketing, RH, financeiro).

| Letra | Nome | Conceito | Acao | Nomenclatura SGC |
|-------|------|----------|------|-----------------|
| C | CLAREZA | "Nao se gerencia o que nao se ve" -- Scan de Vulnerabilidade | Mapear onde esta as perdas (dinheiro ou tempo), definir ponto A. Inclui Matriz de Risco e Indice de Confianca. | Diagnostico / Scan de Vulnerabilidade |
| A | ARQUITETURA | Desenhar a solucao antes de gastar recursos | Criar o processo, o funil ou a regra. Planta baixa da solucao. Engenharia de Publico e Concorrencia. | Blueprint Tatico |
| D | DADOS | O fim do "Eu acho" | Testar a arquitetura em pequena escala. So avancamos se o numero permitir. | Teste de Estresse (Piloto) |
| A | ACAO | "Ofensiva Sincronizada" | Mao na massa com intensidade, seguindo a arquitetura. Cronograma preciso, territorios definidos. | Ofensiva Sincronizada |
| R | RASTREIO | "Tribunal do ROI" | Monitorar painel de controle. Deu lucro? O que quebrou? Foco em faturamento e leads, nao metricas de vaidade. | Tribunal do ROI |
| N | NORMA | "Lei de Ouro" | Se funcionou, vira protocolo. O dono sai da operacao e o processo fica. Termo de Homologacao. | A Lei (Blindagem) |

**Nota editorial sobre conflito da letra "D":** Em alguns documentos (briefing para JP, protocolo hexagonal), a letra D e descrita como "DADOS & DNA (A Identidade)" -- ou seja, codificacao da voz e imagem da marca. Nos documentos originais do acronimo, D e "DADOS (A Validacao)" -- teste com numeros antes de arriscar capital. Sao funcoes distintas. Fabiano precisa definir qual prevalece ou se a letra D absorve ambas.

#### Natureza Ciclica

O metodo nao e linear; e uma espiral ascendente. Quando o cliente atinge a Autonomia (via Norma), o cenario mudou. Novos desafios surgem, exigindo uma nova Verdade Radical para reiniciar o ciclo em nivel superior. Isso justifica a recorrencia (Conselho Estrategico quinzenal).

#### Transicao do Metodo 10P para o Hexagonal

A Cadarn utilizava anteriormente a "Estrategia 10P" (Metodo Like), nao proprietario, focado em Social Media (Objetivos, Persona, Canais, Linha Editorial). Limitacao: percebido como "mais do mesmo". A decisao foi "recarrocar" mantendo o motor operacional, mas com blindagem de gestao (C.A.D.A.R.N.).

#### Os 6 Pilares da Engenharia Cadarn (Doutrina Comercial)

Versao expandida do metodo para uso como argumento de venda:

1. **Sistema C.A.D.A.R.N.** -- Ativo Intelectual Proprietario. Protocolo de 6 etapas que elimina achismo e instala previsibilidade.

2. **Inteligencia Agil** -- Agentes de IA e Engenharia de Prompt proprietaria. Instala Departamento de Inteligencia em 10 dias uteis. Entrega em 2 semanas o que equipe de 10 levaria 6 meses.

3. **Lei da Autonomia** -- Forja Comandantes, nao refens. Sucesso medido pela soberania do cliente. Engenharia do tempo que permite sucesso sem sacrificio da paz familiar.

4. **Terreno Proprio** -- Foco em ativos imutaveis (Processos, Autoridade Intelectual, CRM) vs. terreno alugado (redes sociais). Aprendizado na dor (perda do perfil de 20k seguidores).

5. **Console S.I.C.** -- Monitoramento quinzenal focado em ROI, Leads e Faturamento. "Se o dado nao se transforma em decisao de lucro, e ignorado."

6. **Padrao Cirurgico (Hermes Tech)** -- Estetica de elite: sobria, funcional, de alto status. Cada elemento tem funcao estrategica. Elimina objecao de preco.

---

### 3. VALORES -- HEXAGONO MORAL

#### Versao Consolidada (fusao de `cadarn-valores.md` + `bussola-valores-hexagono-moral.md`)

**1. VERDADE RADICAL (Justica)**
- Topicos: Coragem, Integridade (Pensar=Falar=Fazer), Equidade, Respeito, Amabilidade
- Time: E proibido esconder o erro. Coragem de dizer "nao" a projetos sem crenca. Amabilidade para inspirar cooperacao, nao medo.
- Cliente: Antitese dos "Gurus de Palco". Se o produto e ruim, falamos com franqueza.
- Mantra: "Verdade sem empatia e crueldade. Nos entregamos a verdade dura que enriquece, sempre com a mao estendida para ajudar a levantar."

**2. ARQUITETURA EVOLUTIVA (Inovacao)**
- Topicos: Curiosidade, Clareza, Competitividade (1>0), Ousadia, Cooperacao
- Time: Inovar nao e inventar moda; e simplificar e expandir. Se o processo for complexo demais, nao escala.
- Cliente: Traduzimos "Marketingques" complexo para a lingua do lucro.
- Mantra: "O mercado complica para parecer inteligente; nos simplificamos para gerar lucro."

**3. BLINDAGEM DE RISCO (Prudencia)**
- Topicos: Memoria, Sagacidade, Previdencia, Circunspecao, Discernimento
- Time: Nao somos aventureiros. Usamos Memoria para nao repetir erros. Previdencia: antecipar o buraco antes que a empresa caia nele.
- Cliente: Freio de seguranca. Se a campanha e arriscada demais, alertamos. Opiniao pessoal perde para a matematica.
- Mantra: "O mercado vende sorte e aposta, disfarcado de metodo; nos vendemos dados e blindagem com clareza."

**4. PADRAO CIRURGICO (Excelencia)**
- Topicos: Paixao, Precisao, Foco/Perseveranca, Adaptabilidade, Inteligencia Emocional
- Time: O "bom" e inimigo do lucro. Precisao tecnica + Inteligencia Emocional para suportar pressao sem perder classe.
- Cliente: Estetica "Hermes Tech": impecavel, funcional, superior. Eleva status do cliente imediatamente.
- Mantra: "O mercado entrega o que foi pedido; nos entregamos o necessario para ser o numero 1, sem comprometer os valores."

**5. LEI DA AUTONOMIA (Poder)**
- Topicos: Autoconfianca, Liberdade, Autorresponsabilidade, Autoconhecimento, Influencia
- Time: Formamos lideres, nao seguidores. Autorresponsabilidade: bateu meta = merito. Errou = conserte.
- Cliente: Nao queremos cliente refem. Construimos estrutura para que nos veja como parceiro, nao carcere.
- Mantra: "O mercado cria dependentes; nos forjamos comandantes."

**6. PACTO DE TRINCHEIRA (Lealdade)**
- Topicos: Trincheira, Jogo Infinito, Confidencialidade, Defesa dos Nossos, Legado
- Time: Jogo Infinito. O que e debatido na mesa de estrategia, morre na mesa. Mexeu com um, mexeu com a colmeia.
- Cliente: Nao somos "agencia de post", somos socios de crescimento. Protegemos patrimonio e sono do cliente.
- Mantra: "O mercado quer a transacao rapida; nos queremos garantir o legado."

#### Mapeamento Valores <-> Metodo C.A.D.A.R.N.

| Valor | Letra(s) do Metodo | Funcao |
|-------|-------------------|--------|
| Justica (Verdade Radical) | N (Norma) + R (Rastreio) | Entregar numeros reais e auditaveis |
| Inovacao (Arq. Evolutiva) | C (Clareza) | Diagnostico curioso, simplificacao |
| Prudencia (Blindagem) | D (Dados) | Validar antes de gastar |
| Excelencia (Padrao Cirurgico) | A (Arquitetura) + Filtro geral | Precisao tecnica, estetica elite |
| Poder (Autonomia) | A (Acao) | Cliente executa, autonomia |
| Lealdade (Pacto) | Liga do sistema | Retencao, LTV, relacao longa |

---

### 4. POSICIONAMENTO E DIFERENCIACAO

#### Matriz de Diferenciacao (versao mais completa)

| Diferencial | Concorrencia faz | Cadarn faz | Prova |
|-------------|-----------------|------------|-------|
| Metodo C.A.D.A.R.N. | Pacotes de posts sem estrategia | Engenharia de Lucro sequencial, 6 etapas | Dossie de Engenharia entregue no 10o dia |
| Velocidade (10 dias) | Meses estudando marca sem entregar | Unidade de Inteligencia em 10 dias uteis | Kick-off com Plano Tatico pronto |
| Lei da Autonomia | Mensalidade eterna, dependencia | Forja Comandantes, entrega mapa e armas | Valor no Manifesto + foco em treinamento |
| Terreno Proprio | Foco em seguidores e curtidas | Ativos imutaveis: CRM, processos, autoridade | Plano focado em captacao de dados e funis |
| Console S.I.C. | Relatorios de alcance e impressoes | Auditoria de ROI e Leads reais | Rituais quinzenais de rastreio de lucro |
| Hermes Tech | Design "Carnaval" ou amador | Estetica sobria, funcional, alto status | Identidade visual de todos os materiais |
| Triade Operacional | Generalistas faz-tudo ou estruturas inchadas | 3 forcas especialistas sinergicas | Definicao clara de papeis + suporte IA |

#### SWOT/TOWS

**Forcas:**
- Metodologia proprietaria forte
- Socios complementares (Tecnico + Comercial, 360)
- Agilidade tecnologica (IA/Gui)
- Baixo custo operacional
- Integridade radical como diferencial comercial

**Fraquezas:**
- Sem prova social publica (apenas 1 cliente parente)
- Sem audiencia/autoridade online
- Equipe enxuta (limite de braco)
- Dependencia humana (conhecimento tacito dos fundadores)
- Braco tecnologico: falta CTO/Dev Team para tirar IA do papel

**Oportunidades:**
- Mercado de PMEs saturado de agencias ruins
- Necessidade de profissionalizacao rapida dos pequenos negocios
- IA barateando a entrega
- Ninguem fazendo "Gestao Aumentada" (IA nativa + alma humana)

**Ameacas:**
- Ceticismo do cliente queimado por agencias anteriores
- Concorrentes cobrando precos vil (R$ 300/mes)
- Invisibilidade da marca

**Vetores de Acao (TOWS):**
1. **Ataque (S+O):** "O Cirurgiao de Marketing" -- Auditorias de Pontos Cegos em 5 empresas/semana com dinheiro e marketing sangrento. Abordagem outbound direta.
2. **Alavancagem (W+O):** "Bastidores da Engenharia" -- Documentar evolucao do Cliente Zero e bastidores. Transparencia como trunfo.
3. **Defesa (S+T):** "A Muralha da Verdade" -- Metodologia C.A.D.A.R.N. e logica matematica contra ceticismo. Jamais competir por preco.
4. **Sobrevivencia (W+T):** "Caca de Precisao (Sniper)" -- Foco em 3-5 clientes de medio porte. Proibido aceitar clientes problematicos ou sem caixa.

---

### 5. PIPELINE E PRODUTOS

#### Pipeline Atual (Memorando V2)

| Produto | Descricao | Entrega | Preco |
|---------|-----------|---------|-------|
| **Isca:** Auditoria de Pontos Cegos | Sessao gratuita de 30 min | Imediato | Gratis |
| **Produto 1:** Diagnostico S.I.C. + Plano de Acao 30 dias + Repaginada de Oferta | Entrega em 7 dias | -- |
| **Produto 2:** Plano Tatico Hexagonal | Branding, Narrativa, Scripts. Entrega em 30 dias | R$ 750 (Lote Founders, ref. insights-hanlon) |
| **Produto 3:** Imersao Tatica S.I.C. (O Drill) | Treino pratico da equipe. 8h em 2 dias (online/presencial). Dia 1: Cultura e Ordem. Dia 2: Ataque e Vendas. | De R$ 2.400 por R$ 1.200 (Founders). Incluso fatiado se assinar Produto 4. |
| **Produto 4:** Conselho Estrategico | Recorrencia quinzenal de auditoria e manutencao guiada pelo Console S.I.C. | MRR |

#### Horizonte Estrategico (3 fases)

- **Fase 1 (Meses 1-3):** Validacao Lote Founders. Max 10 clientes. Overdelivery. Colher cases irrevogaveis.
- **Fase 2 (Meses 4-8):** Consolidacao do preco e MRR. Fechar Lote Founders. Foco absoluto em Produto 4 (Conselho Estrategico) para receita recorrente.
- **Fase 3 (Longo prazo):** Soberania Tecnologica. Agentes de IA autonomos. Console S.I.C. quase autonomo. Cadarn como Board of Advisors com margens altissimas e atrito zero.

#### Solucao Hibrida (honestidade estrategica)

| Horizonte | Produto | Status |
|-----------|---------|--------|
| H1 (pronto) | Marketing Estrategico & Engenharia de Vendas | Validado. Metodo, equipe e entrega prontos. "Cavalo de Troia" |
| H2 (gargalo) | Consultoria Operacional 360 (Financeiro, RH, Logistica) | Know-how existe, mas execucao manual inviavel (R$ 15-20k/mes). Atuacao apenas consultiva/leve. |
| H3 (futuro) | Cadarn Tech (SGC Automatizado / SaaS) | Em desenho. IA para trabalho bracal da gestao. Transformar consultoria cara em SaaS barato. |

#### Diagnostico Gratuito via GPT (MVP em andamento)

Projeto de diagnostico gratuito de Instagram via GPT customizado:
- Fluxo: Quebra-gelo > Preparacao > Link ou prints > Diagnostico automatico
- Saida: Resumo executivo, nota express (0-5) em 6 dimensoes, raio-x, 3 acoes de alto impacto, plano 7 dias, convite para diagnostico completo
- Regras: etiquetar tudo como [OBSERVADO], [INFERIDO] ou [HIPOTESE]
- Automacao por DM adiada (bloqueio tecnico: necessita coletor de dados)
- Knowledge base com benchmarks separados por Brand vs Creator em construcao

---

### 6. PROCESSOS E OPERACAO

#### 5 Leis Imutaveis da Gestao de Processos

1. **Lei do Valor (Outside-In):** Nenhum processo tem o direito de existir se nao gerar valor para o cliente. Desenhar de fora para dentro.
2. **Lei da Realidade dos Dados:** A verdade nao esta no que dizem, esta nos dados.
3. **Lei da Entropia:** Processos apodrecem sem manutencao.
4. **Lei da Cultura:** A cultura devora a estrategia.
5. **Lei da Visao Sistemica:** Otimizar uma parte pode quebrar o todo.

#### Protocolo de Engajamento Tatico (Manual de Doutrina)

**Filosofia:** Engenharia cognitiva, nao "posts criativos". Funil como mapa de topografia mental. Em alto ticket, cliente compra por confianca tecnica, nao por impulso.

**Regra de Ouro:** "Nunca tente vender a Solucao (Conversao) para quem ainda nao entendeu o Problema (Atracao)."

**5 Fases de Combate (rejeita Topo/Meio/Fundo):**

| Fase | Estado mental | Missao Cadarn | Tatica | Formato |
|------|-------------|---------------|--------|---------|
| 1. ATRACAO | Inconsciencia ("nao sabia do problema") | Quebrar indiferenca. Vender o Problema, nao a solucao. | Apontar o "Erro Invisivel" ou Custo da Ignorancia | Video curto (Reels), headline forte |
| 2. AUTORIDADE | Curiosidade cetica ("por que devo ouvir voce?") | Estabelecer hierarquia. Provar Metodo Proprio. | Ensinar o "Mecanismo Unico". Quem ensina, domina. | Carrossel ou video longo |
| 3. VALIDACAO | Medo do risco ("funciona pra mim?") | Mitigar medo. Provar que nao e aventura. | Prova Social, Estudos de Caso, Bastidores | Stories, post estatico |
| 4. CONVERSAO | Prontidao ("como contrato?" / "qual o proximo nivel?") | Clareza de proximo passo. Dois modos de copy: (a) primeira conversao = Hard de persuasao, (b) ascensao (prospect ja comprou) = Hard de ampliacao. | Oferta direta, escassez real, CTA inequivoco | Direct (X1), pagina de vendas |
| 5. RETENCAO | Duvida pos-compra ("fiz a escolha certa?") | Manobra ofensiva. Energia volta dobrada. | Overdelivery (7 dias), Nutricao continua, Extracao de ativos | WhatsApp pos-venda, email |

**Mapa Bandeiras x Fases de Combate (resumo):** B1 acorda, B2 traduz, B3 prova, B4 diferencia, B5 filtra e fideliza.

| Fase | Bandeira protagonista | Bandeira de apoio |
|------|----------------------|-------------------|
| 1. ATRACAO | B1 (A Ilusao do Faturamento) | B5 como filtro de mentalidade |
| 2. AUTORIDADE | B2 (Da Raca ao Metodo) | B1 reforco de diagnostico, B5 filtro |
| 3. VALIDACAO | B3 (A Marca de Quem Chegou) | B1 numeros, B2 bastidores, B5 tom |
| 4. CONVERSAO | Variavel por produto (B1 Score, B2 Protocolo, B3 Laboratorio, B4 Esquadrao IA, B5 Conselho Tatico) | Todas como apoio |
| 5. RETENCAO | B5 (O Comando e Seu) | Todas como overdelivery e upsell |

**3 Pilares da Retencao:**
- Overdelivery: Superar promessa nos primeiros 7 dias.
- Nutricao: Enviar inteligencia e valor continuamente (LTV).
- Extracao de Ativos: Nao esperar elogio; extrair caso de sucesso. Cliente satisfeito e municao para Fase 3 dos proximos.

**Lei de Kiso:** "Quem nao executa a Fase 5 com engenharia, e obrigado a gastar o dobro na Fase 1 para repor quem saiu falando mal."

**Checklist de Guerra (antes de publicar):**
- O ALVO: Resolve duvida real da Persona ou e apenas barulho?
- A HIERARQUIA: Estou ensinando (Autoridade) ou pedindo favor (Vendedor Chato)?
- A ESTETICA DE PODER: Identidade visual respeita sobriedade Cadarn?

#### Framework: Construir um Negocio Digital (5 camadas)

Modelo generico de construcao de negocio digital em 5 camadas sequenciais:

1. **NICHO (Base):** Micronicho > Expansao. Problema especifico, ICP, segmento claro.
2. **MODELO DE NEGOCIO (Viabilidade):** Simples > Define diferencial. Servicos simples, proposta de valor, canal de aquisicao, metodologia propria.
3. **VENDAS (Receita):** Servicos caros > Produtos escalavel. Consultorias, mentorias, done-for-you > cursos, comunidades, assinaturas.
4. **CONTEUDO (Distribuicao):** Equilibrio entre profundo (autoridade: educacional, newsletter, podcast) e raso (alcance: reels, stories, trends).
5. **SISTEMAS (Paz):** Processos (SOPs, checklists, fluxos) + Automacao (CRM, chatbots, integracoes, IA).

**Nota editorial:** Este framework e generico e nao referencia o C.A.D.A.R.N. Parece ser um material de referencia externa adaptado, nao doutrina proprietaria.

---

### 7. CONTEUDO E COMUNICACAO

#### Estrutura de Mensagem: "O Elogio Sincero" (Tecnica do Diamante Bruto)

Logica: Validar esforco atual (Elogio) > Apontar Discrepancia (Potencial) > Convite (Solucao).

Conceito: "Voce e bom demais para estar cobrando/vendendo so isso. O mercado nao esta vendo todo o ouro que voce tem." Acaricia ego e gera curiosidade.

**Script 1 (Clinicas):** Elogiar qualidade tecnica dos procedimentos > apontar que poderia posicionar como "Protocolo Exclusivo" (ticket maior) > convidar para Ciclo de Validacao Founders.

**Script 2 (Imobiliarias):** Elogiar curadoria dos imoveis > apontar oportunidade na "Narrativa de Desejo" vs. descricao fria (m2, quartos) > convidar para Grupo de Validacao Founders.

**Regra de seguranca:** Elogio DEVE ser especifico. Citar detalhe real do perfil. Errado: "Adorei seu perfil" (robo). Certo: "Dra., o contorno labial no ultimo post ficou muito natural."

#### Hipotese do ICP: "Vaidade do Especialista"

Com medicos/advogados, nao bater na tecla "voce e desorganizado" (ofende). Abordar pelo vies do PODER e LIBERDADE: "Voce e um excelente medico, mas esta operando como funcionario da propria clinica. Vamos te elevar a Empresario da Saude."

#### Hipotese da "Invisibilidade Ativa" do Fabiano

Fabiano nao aparece publicamente, mas sua autoridade tecnica e o diferencial. Tatica: Samira cita frequentemente "O meu socio, que cuida da Inteligencia, analisou os dados e disse..." Cria entidade "mitica" que valida sem precisar aparecer.

#### Tom de Voz

- Sobrio, tecnico, "Hermes Industrial"
- Sem gritaria
- "A Adulta na Sala": firme mas acolhedora
- Elite porem democratico: "levamos a regua das grandes ate o pequeno"
- Diplomatica assertiva: firmeza de General com elegancia de executiva

#### Bandeiras de Guerra (5 posicoes editoriais)

1. **Ditadura do Lucro Real (ROI):** Contra metricas de vaidade. "Fama nao paga fornecedor."
2. **Fim do Amadorismo Familiar:** Contra gestao de caderninho. "O amadorismo e o cancer do varejo."
3. **Branding como Escudo de Valor:** Contra guerra de precos. "A margem de lucro mora na percepcao de valor."
4. **Inteligencia Hibrida (Tecnologia + Alma):** Contra medo irracional da IA ou robotizacao fria. "Use a maquina para ganhar tempo e o coracao para ganhar o cliente."
5. **Protagonismo Radical (Anti-Vitimismo):** Contra terceirizacao de culpa. "Resultados ou Desculpas: voce pode ter um dos dois."

---

### 8. CONTEXTO E HISTORIA

#### Genesis da Cadarn (cronologia narrativa)

**Capitulo 1 -- O Batismo de Fogo (2020):** Pandemia. Samira empurrada para o centro do furacao. Convite do Sebrae para salvar pequenos negocios. O mercado nao precisava de "posts bonitos", precisava de socorro comercial.

**Capitulo 2 -- A Licao de Sangue:** Perda do perfil de Samira (20k seguidores). Validou a tese: construir imperio em terreno alugado e suicidio corporativo. Verdadeiro patrimonio = Processos, Autoridade Intelectual, CRM, Valores.

**Capitulo 3 -- O Choque de Realidade (PME):** Samira assume gerencia de operacao de varejo. Descobre a fragilidade da PME brasileira. Problema nao era comercial, era estrutural. Intervencao Tatica: Samira (vendas/equipe) + Fabiano (financeiro/processos). Primeira uniao de forcas na trincheira.

**Capitulo 4 -- O Paradoxo do Dono:** A tragedia do Dono Refem: escolha cruel entre empresa e familia. Causa: falta de processos e lideranca. "Teto de Vidro": sem ressignificacao na mentalidade do dono, ha limite tecnico para o que se pode fazer. Ciclo vicioso: sem cultura > sem talentos > sem delegacao > dono = gargalo > margem corroida > perde talentos.

**Capitulo 5 -- A Escolha Estrategica (2025):** Desejo: Sistema de Gestao Cadarn completo (360). Pragmatismo: inviavel para PME em crise. Decisao de engenharia: comecar pelo Marketing Estrategico como ponta de lanca para gerar caixa rapido. Desenvolvimento de Agentes de IA + validacao do Metodo C.A.D.A.R.N.

**Capitulo 6 -- A Pedra Fundamental (2026):** Transicao de consultoria tatica para Ecossistema de Performance Comercial. "Nao estamos prontos; estamos em obra." Norte: unir solidez de consultoria com tecnologia de startup. Acesso a ferramentas de eficiencia das gigantes do Vale do Silicio adaptadas a trincheira brasileira.

#### Perfil Detalhado de Samira Alcantara

**Trajetoria:**
- [2009-2011] M.Officer: base de disciplina operacional e lideranca
- [2012-2013] Cobra D'agua: gestao de estoque complexo e alto giro
- [2017-2019] CS Club (Carmen Steffens): CRM, fidelizacao classe A/B, transformou loja problema em franquia validada
- [2020-2022] Cadarn Consultoria V1.0: mentoria na pandemia, digitalizacao de PMEs
- [2022-2023] Itapua Calcados: KPIs financeiros, superou lojas favoritas da rede
- [2025] Malwee Kids: gestao de crise com equipe minima, meta batida com digital
- [2026] Cadarn Martech: refundacao com foco em tecnologia e engenharia de lucro

**Formacao:**
- Bacharelado em Design de Moda (Faesa)
- Gestao e Criacao de Negocios da Moda (UVV)
- Pos em Comunicacao Digital, Branding e Storytelling (PUC)
- IA Aplicada ao Marketing Digital (Faculdade Exame)
- Analista DISC + Coaching (Abracoaching)
- Gestao de Varejo (Grupo Friedman + Senac)

**Especialidades:**
- Arquitetura de Autoridade e Branding
- Engenharia de Vendas e Calendario Tatico
- Gestao Hibrida (Processos + IA)
- Visual Merchandising Estrategico
- Lideranca de Alta Performance

**Fator Unico:** Fusao "Caos + Ordem" (Protocolo Cadarn) -- materializa resultados unindo visao comercial visceral com engenharia de processos blindados.

**Atributos de Imagem:** Resolutividade Estrategica, Businesswoman de Elite, Engenheira de Receita, Sofisticada/High-End, "A Adulta na Sala", Mentora Humana.

---

### 9. DOCUMENTOS DE APOIO / INSTRUMENTAIS

#### Insights Cadarn-Ogilvy
- Hipotese do "Produto Ponte": vender "Kits de Ferramentas" (Productized Service) em vez de consultoria manual. Ex: "Kit Blindagem Financeira" (planilha + aulas + call).
- Matriz de Risco para usar na Fase C (Clareza): tabela Risco > Nivel de Impacto > Solucao Cadarn.
- TOC (Teoria das Restricoes): todo sistema tem UM gargalo. Melhorar qualquer coisa que nao seja o gargalo e perda de dinheiro.
- Benchmarking de Elite: "Nao somos uma Familia" (Netflix/Bridgewater). Time de Elite exige alta performance. Vetores do Punicao, Tabu e Linha Vermelha.

#### Briefing para Validacao Externa (JP)
Documento para especialista externo validar: coerencia do fluxo Clareza > Acao, robustez para ancorar autoridade de "Consultoria de Negocios", e future-proofing para expansao para RH/Financeiro.

#### Contexto do Problema (Qualificacao de Leads)
Briefing tecnico para ferramenta de analise de perfis Instagram via IA. Define dados disponiveis (bio, seguidores, posts) vs. nao disponiveis (visual, stories). Objetivo: criar checklist de qualificacao B2B com criterios objetivos e mensuraveis.

#### Backlog Estrategico 2025-2026

**Para Fase C (Clareza):** Scan 7S (McKinsey), Pre-Mortem, Shadow Processes
**Para Fase A (Arquitetura):** Analise VRIO, Brand Key (Ogilvy/Unilever)
**Para Fase R (Rastreio):** Unit Economics (LTV/CAC), Marketing Mix Modeling
**Para Fase N (Norma):** Seguranca Psicologica, Kaizen
**Novos Produtos:** Hypercare Package, SGC Audit (selo de qualidade), Cadarn Academy

---

## RECOMENDACOES EDITORIAIS

### Acoes Imediatas (Decisoes que Fabiano precisa tomar)

1. **Definir a missao oficial:** "Engenharia de Processos e Tecnologia de Elite" (ambiciosa/360) vs. "Engenharia de Marketing e Vendas" (pragmatica/focada). Recomendacao: adotar a V2 (marketing/vendas) como missao publica e manter a versao 360 como visao de futuro.

2. **Resolver o conflito da letra "D":** "Dados = Validacao com numeros" ou "Dados & DNA = Identidade de marca"? Sao funcoes distintas. Recomendacao: manter D = Dados (Validacao) conforme o acronimo original, e tratar DNA/identidade como subetapa da fase A (Arquitetura), que e onde naturalmente se encaixa (voce "arquiteta" a identidade).

3. **Fixar a ordem canonica dos valores:** Definir qual valor e o "primeiro" e qual e o "ultimo" no ciclo, para consistencia em todas as comunicacoes.

### Documentos para Fundir

| Fundir estes | Em um unico |
|-------------|-------------|
| `cadarn-valores.md` + `bussola-valores-hexagono-moral.md` + `arquitetura-moral-cadarn-hexagonal.md` | **"Codigo Moral Cadarn"** -- valores com taxonomia, perspectiva dupla (time/cliente), mantras e mapeamento ao metodo |
| `missao-visao-cadarn-martech.md` + Parte I do `codigo-cadarn-memorando-fundacao-v2.md` | **"Identidade Cadarn"** -- missao, visao, proposito, elevator pitch, auto-definicao, triade |
| `acronimo-metodo-cadarn.md` + `protocolo-hexagonal-engenharia-receita.md` + parte do `6-pilares-engenharia-cadarn.md` | **"Metodo C.A.D.A.R.N."** -- acronimo, 6 pilares expandidos, versao para cliente |

### Documentos para Descartar/Arquivar

| Documento | Acao | Motivo |
|-----------|------|--------|
| `acronimo-metodo-cadarn.md` | DESCARTAR | Duplicata exata de secao do `excelente-escolha-fabiano.md` |
| `excelente-escolha-fabiano.md` | ARQUIVAR como historico | Log bruto de conversa com IA. Conteudo util ja refinado em documentos posteriores. Manter apenas como registro da genese. |
| `arquitetura-moral-cadarn-hexagonal.md` | FUNDIR e descartar | Versao anterior do mapeamento. Substituida por `cadarn-valores.md` |

### Documentos para Manter como estao

| Documento | Motivo |
|-----------|--------|
| `genese-cadarn-do-caos-a-engenharia.md` | Narrativa unica e bem escrita. Nenhum outro documento cobre essa historia. |
| `codigo-cadarn-manifesto-ordem-valores.md` | Documento emocional/narrativo unico. Funciona como "constituicao poetica". Complementa (nao substitui) o codigo moral estruturado. |
| `memorando-estrategico-cadarn-martech.md` | Documento de estrategia de negocio unico. Contendo tese de escala, ICP, SWOT, horizontes. |
| `codigo-cadarn-memorando-fundacao-v2.md` | O documento mais completo e maduro. E a "biblia operacional" de fato. |
| `cadarn-futuro-backlog-estrategico.md` | Unico documento com visao de futuro de produtos e ferramentas. |
| `manual-doutrina-protocolo-engajamento-tatico.md` | Unico documento com o funil de 5 fases e doutrina de conteudo. |
| `insights-hanlon-cadarn.md` | Perfil da Samira + scripts de venda + bandeiras de guerra. Conteudo unico e denso. |
| `briefing-diagnostico-instagram-automacao-dm.md` | Especificacao tecnica do MVP de diagnostico. Documento operacional ativo. |

### Documentos Instrumentais (mover para pasta separada?)

| Documento | Tipo |
|-----------|------|
| `contexto-do-problema.md` | Briefing tecnico pontual |
| `nova-estrutura-mensagem-elogio-sincero.md` | Scripts de abordagem comercial |
| `briefing-estrategico-ogilvy-para-jp.md` | Briefing para validacao externa |
| `framework-construir-negocio.md` | Framework generico de referencia |
| `insights-cadarn-ogilvy.md` | Notas de analise e hipoteses |

Esses documentos nao sao doutrina; sao ferramentas de trabalho. Poderiam estar numa subpasta `instrumentais/` para nao se misturarem com os documentos fundacionais.

### Gap Critico a Enderecarprioritariamente

O maior gap do framework e a ausencia de **cases documentados e prova social**. Multiplos documentos identificam isso como fraqueza. Antes de produzir mais doutrina, o proximo passo deveria ser documentar os primeiros resultados reais com clientes do Lote Founders.
