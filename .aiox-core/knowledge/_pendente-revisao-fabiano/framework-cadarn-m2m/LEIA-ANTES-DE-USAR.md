---
status: pendente-decisao-fabiano
criado_em: 2026-07-19
criado_por: Emrys (vistoria noturna, autonomia autorizada por Fabiano)
---

# Por que este conteúdo está aqui e não em `.aiox-core/knowledge/framework-cadarn-m2m/`

`estrategista.md` (Squad MKT Healthtech) e outros agentes referenciam
`.aiox-core/knowledge/framework-cadarn-m2m/` como `knowledge_path`, mas essa
pasta não existe no Tarian Healthtech. Copiei da Martech pra resolver o path
quebrado e, ao revisar, achei que a subpasta `estrategia-10p/` contém
identidade **já aplicada** da Cadarn Martech (DNA da Samira, DNA da empresa,
tom de voz, análise de concorrentes da própria Martech, personas dos clientes
da Martech) — não é método genérico reutilizável. Copiar isso pra dentro do
conhecimento ativo da Healthtech faria os agentes MKT de lá confundirem a
identidade da Martech com a própria. Por isso: revertido pra cá, não
mergeado. Ver `.claude/rules/` sobre isolamento total entre Tarians.

## Triagem preliminar (não é decisão — é economia de tempo pra sua leitura)

**Alta confiança — identidade aplicada da Martech, provavelmente NÃO deve virar conhecimento ativo da Healthtech:**
- `estrategia-10p/02-dna-conteudo/` — inteira (DNA Samira, DNA empresa, tom de voz)
- `estrategia-10p/03-concorrentes/` — inteira (concorrentes DA MARTECH: Ariany SA, Camille Marketing, Clarissa, Dominique Saraiva, Victoria Tetzlaff — não fazem sentido como concorrentes da Healthtech)
- `estrategia-10p/04-personas/` — inteira (personas de clientes da MARTECH: dono de imobiliária, arquiteto/engenheiro, serviços intelectuais, beleza — não são o ICP da Healthtech)
- `estrategia-10p/01-objetivos/` — objetivos de projeto da própria Martech
- `estrategia-10p/05-jornada-compra/` e `07-linhas-editoriais/` — pesquisa aplicada ao conteúdo da Martech

**Precisa leitura antes de decidir — podem ser método genuinamente genérico:**
- `pipeline-cadarn/` (4 arquivos) — pode ser o pipeline operacional do MÉTODO (como conduzir um cliente), não identidade da Martech. Não lido a fundo por mim ainda.
- `DOSSIE-FRAMEWORK-CADARN*.md` (2 arquivos, um já marcado "SUPERADO" no próprio cabeçalho) — mistura estrutura de método com exemplos da Martech
- `codigo-cadarn-memorando-fundacao-v2.md` — "memorando de fundação", título sugere identidade, não confirmado
- `diretrizes-operacionais-squad-engenharia-estrategia.md` — pode ser processo genérico de como a squad de estratégia trabalha

## O que o estrategista.md realmente precisa (achado nesta vistoria)

O texto do agente cita especificamente precisar da lista completa dos **30
sub-atributos do Hexágono Moral** (6 valores × 5 sub-atributos cada). Não
encontrei esse detalhe em nenhum arquivo desta pasta nem no
`.aiox-core/knowledge/cadarn-method/` que a Healthtech já tem (mais enxuto:
metodo-cadarn.md, funil-5-fases, plano-tatico, arvore-decisao, glossario).
Pode estar em `docs/negocio-cadarn/01-vigente/` na Martech (fonte "vigente"
citada no DOSSIE como sucessora desta versão) — não verificado.

## Recomendação (não é martelo — é ponto de partida pra sua leitura)

Se o objetivo é só destravar o `knowledge_path` do estrategista.md: mais
seguro e rápido é extrair SÓ o trecho do Hexágono Moral (30 sub-atributos) de
onde quer que ele esteja na fonte vigente da Martech, e colar como um arquivo
pequeno e citado em `.aiox-core/knowledge/cadarn-method/hexagono-moral.md` —
em vez de importar a pasta inteira com risco de contaminação de identidade.
