---
type: cadarn-method
domain: validacao
shared: true
---

# Árvore de Decisão — Validação de Conteúdo

Algoritmo de 6 nós que toda peça de conteúdo deve passar antes de ser publicada.

## Flowchart

```
INPUT: [RASCUNHO DO CONTEÚDO]
  │
  ▼
NÓ 01: O ALVO ESTÁ TRAVADO?
  "Sei exatamente quem é a Persona e a Fase (Atração a Conversão)?"
  ├── NÃO → Ajuste
  └── SIM → Avança
  │
  ▼
NÓ 02: A ARMA É VÁLIDA?
  "O tema pertence a uma das Linhas Editoriais definidas?"
  ├── NÃO → Descarte
  └── SIM → Avança
  │
  ▼
NÓ 03: FOCO ÚNICO?
  "Estou tentando resolver apenas UMA dúvida?"
  ├── NÃO → Fatie o post
  └── SIM → Avança
  │
  ▼
NÓ 04: TEM LASTRO DE PROVA?
  "Existe evidência técnica/visual ou é só opinião?"
  ├── NÃO → Insira prova
  └── SIM → Avança
  │
  ▼
NÓ 05: O COMANDO É LÓGICO?
  "O CTA faz sentido para a fase do funil?"
  ├── NÃO → Ajuste o CTA
  └── SIM → Avança
  │
  ▼
NÓ 06: COMPLIANCE INTEGRAL
  "Respeita a identidade visual e o tom de voz do cliente?"
  └── SIM → LIBERADO
```

## Aplicação

- Logos (Copywriter) e Magnética (Roteirista) usam antes de entregar rascunho
- Coel (Brand Guardian) usa como checklist de auditoria
- Pulso (Social Media) usa antes de agendar publicação
