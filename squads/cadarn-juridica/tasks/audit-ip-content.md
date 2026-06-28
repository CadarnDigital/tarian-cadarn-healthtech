---

## Task Definition

```yaml
task: auditIpContent()
responsavel: Signum (Especialista Propriedade Intelectual)
responsavel_type: Agente
squad: cadarn-juridica
templates:
  - cessao-direitos-tmpl.yaml
  - termo-uso-imagem-tmpl.yaml
tarian_portable: true

description: >
  Auditoria de propriedade intelectual para conteúdo de marketing:
  direitos autorais, uso de imagem, marcas, IA generativa, música
  e licenciamento. Gera cessões, termos e checklists.

Entrada:
  - campo: conteudo_ou_questao
    tipo: string
    origem: Elicitação
    obrigatório: true

Saída:
  - campo: parecer_pi
    tipo: markdown
    destino: File system
    persistido: true
```

---

## Execution Modes

### 1. Auditoria de Conteúdo (2-3 prompts) **[DEFAULT]**
- Pipeline 6 etapas para peça/campanha
- **Trigger:** `*auditar-conteudo {peça ou campanha}`

### 2. Gerar Cessão de Direitos (2-3 prompts)
- Cláusula por tipo: autoral, imagem, marca, software
- **Trigger:** `*gerar-cessao {tipo}`

### 3. Termo de Uso de Imagem (2-3 prompts)
- Termo completo com 11 campos
- **Trigger:** `*termo-imagem {contexto}`

### 4. Checklist IA Generativa (1-2 prompts)
- Compliance para uso de IA em conteúdo
- **Trigger:** `*checklist-ia`

### 5. Checklist de Marca (1-2 prompts)
- 10 etapas para registro INPI
- **Trigger:** `*checklist-marca {nome da marca}`

---

## Workflow — Auditoria de Conteúdo

### Fase 1 — Recepção

**Passo 1: Material**
```
elicit: true
prompt: |
  ✍️ Auditoria de Propriedade Intelectual — Signum

  1. Descreva a peça/campanha (ou cole texto/link)
  2. Contém: fotos, vídeo, música, textos, design, logo?
  3. Quem criou o conteúdo? (equipe interna, freelancer, IA, banco de imagens)
  4. Usa imagem de pessoas? (modelo, cliente, influencer)
  5. Usa IA generativa? (qual ferramenta)
```

### Fase 2 — Pipeline de 6 Etapas

```
task: |
  ETAPA 1 — DIREITOS AUTORAIS (Lei 9.610/98)
  - Quem é o autor? Cessão expressa existe?
  - Obra sob encomenda: cessão escrita obrigatória (Art. 49, I)
  - Direitos morais: inalienáveis (Art. 24)
  - Banco de imagens: licença verificada?

  ETAPA 2 — USO DE IMAGEM (CF Art. 5, X + CC Art. 20)
  - Pessoa identificável? Termo de imagem assinado?
  - Menor de idade: autorização de AMBOS responsáveis
  - Funcionário: consentimento específico (não genérico)
  - Modelo: contrato com escopo, prazo, territorialidade

  ETAPA 3 — MARCAS
  - Usa marca própria? Registro INPI em dia?
  - Usa marca de terceiro? Autorização escrita?
  - Uso comparativo? (Art. 32 CONAR, precisa ser objetivo)
  - Keyword com marca concorrente? (PROIBIDO, STJ jul/2024)

  ETAPA 4 — MÚSICA E ÁUDIO
  - Música original ou licenciada?
  - ECAD: necessário para execução pública
  - Biblioteca royalty-free: licença verificada?
  - Cover/remix: autorização do titular obrigatória

  ETAPA 5 — IA GENERATIVA
  - Conteúdo gerado por IA? Disclosure feito?
  - Garantia limitada de não-infração (nunca absoluta)
  - Dados pessoais na geração? (LGPD + PROIBIDO em web IA)
  - Cessão de uso comercial sobre output?

  ETAPA 6 — LICENCIAMENTO
  - Todos os assets têm licença comercial?
  - Licenças são compatíveis entre si?
  - Prazo das licenças cobre o uso pretendido?
  - Territorialidade atende a campanha?

  Para cada etapa: ✅ CONFORME / ⚠️ RISCO / ❌ NÃO CONFORME

output: auditoria-pi-{tipo}-{data}.md
```

---

## Output

```
{output_dir}/
├── auditoria-pi-{tipo}-{data}.md           # Parecer completo
├── cessao-direitos-{tipo}-{data}.md         # Cláusula de cessão
├── termo-imagem-{contexto}-{data}.md        # Termo de uso de imagem
├── checklist-ia-{data}.md                   # Checklist IA generativa
└── checklist-marca-{nome}-{data}.md         # Checklist registro INPI
```

**Output dir padrão:** `docs/juridico/propriedade-intelectual/`

---

## Integração Cross-Squad

| Agente Marketing | Quando aciona Signum |
|-----------------|---------------------|
| Magnética (Roteirista) | Música, imagens de terceiros no roteiro |
| Iris (Diretora Criativa) | Uso de assets de banco, referências visuais |
| Pixel (Designer) | Logo, marca, assets licenciados |
| Logos (Copywriter) | Referência a marcas concorrentes |

---

*Squad Cadarn Jurídica — Task v1.0*
*Framework: Lei 9.610/98 + INPI + CF Art. 5 + IA Generativa*
