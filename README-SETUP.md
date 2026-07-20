# Tarian Cadarn — Guia de Setup para Produto Próprio

## Como criar um Tarian para um produto Cadarn

### 1. Clonar o template

```bash
git clone https://github.com/CadarnDigital/tarian-cadarn-template.git tarian-cadarn-{slug-produto}
cd tarian-cadarn-{slug-produto}
rm -rf .git
git init
git add .
git commit -m "chore: initialize tarian-cadarn-{slug-produto} from template"
```

### 2. Customizar CLAUDE.md

Editar `CLAUDE.md` e substituir:
- `{NOME_PRODUTO}` → Nome do produto (ex: "Cadarn Healtech", "Cadarn Locus")
- `{DOMINIO}` → Domínio técnico (ex: "Saúde Suplementar", "Mercado Imobiliário")
- `{VERTICAL}` → Vertical Cadarn (ex: "Healtech", "Proptech", "Fintech")
- `{OPERADOR}` → Quem opera (ex: "Fabiano + Gui")

Preencher também a seção **Squads Ativas** com os agentes que serão usados.

### 3. Criar a squad do produto

Renomear o diretório placeholder e configurar o manifesto:

```bash
mv squads/cadarn-\{produto\} squads/cadarn-{slug-produto}
```

Editar `squads/cadarn-{slug-produto}/squad.yaml` e substituir:
- `{PRODUTO}` → slug do produto (ex: `healthtech`)
- `{NOME_PRODUTO}` → nome legível (ex: `Cadarn Healtech`)
- Adicionar agentes na seção `agents:`

### 4. Popular a knowledge base

#### 4a. Domain Knowledge (corpus técnico do domínio)

Popular `.aiox-core/knowledge/domain/` com o corpus do domínio:

```
.aiox-core/knowledge/domain/
├── INDEX.md              ← atualizar com guia de carregamento por tarefa
├── regulamentacao/       ← normas, leis, resoluções do setor
├── protocolos/           ← protocolos técnicos do domínio
├── pesquisas/            ← benchmarks, estudos, dados de mercado
└── (subtemas conforme domínio)
```

#### 4b. Produto Knowledge (DNA do produto)

Preencher os arquivos em `.aiox-core/knowledge/produto/`:
- `visao.md` — visão, missão, posicionamento do produto
- `icp.md` — perfil do usuário/parceiro ideal
- `roadmap.md` — roadmap de capacidades
- `tom-de-voz.md` — voz e tom de comunicação do produto

#### 4c. Operacional

Preencher `.aiox-core/knowledge/operacional/runbook.md` com:
- Procedimento de onboarding de novos operadores
- Rotinas de operação (backups, revisões, atualizações)
- Runbook de incidentes

### 5. Configurar git remoto

```bash
git remote add origin https://github.com/CadarnDigital/tarian-cadarn-{slug-produto}.git
git push -u origin master
```

### 6. Setup do Cowork (manual)

1. Abrir Cowork (claude.ai desktop)
2. Criar Project "Tarian {NOME_PRODUTO} — Operação"
3. Adicionar instruções (copiar de CLAUDE.md)
4. Upload do corpus de domínio e DNA do produto
5. Conectar: conforme stack do produto
6. Ativar memória

### 7. Checklist de verificação

- [ ] CLAUDE.md sem nenhum `{placeholder}` — tudo substituído
- [ ] Squad do produto renomeada e configurada em `squads/cadarn-{slug-produto}/`
- [ ] `domain/INDEX.md` atualizado com guia de carregamento
- [ ] `produto/visao.md` preenchido
- [ ] `produto/icp.md` preenchido
- [ ] `operacional/runbook.md` preenchido
- [ ] Git remoto configurado e push realizado
- [ ] Cowork Project criado com knowledge + connectors
- [ ] Seção "Squads Ativas" do CLAUDE.md preenchida

---

## Diferença entre tarian-template e tarian-cadarn-template

| | tarian-template | tarian-cadarn-template |
|---|---|---|
| **Para quem** | Clientes da Cadarn (agência) | Produtos próprios da Cadarn |
| **Knowledge** | DNA do cliente (voz, personas, editorial) | Corpus técnico do domínio + DNA do produto |
| **Squad central** | Squad Marketing + squads de serviço | Squad do produto (específica por produto) |
| **Framing** | "Serve o cliente" | "Opera o produto" |
| **Especialistas por nicho** | `specialists/` com pré-built por setor | Criar conforme produto exigir |
