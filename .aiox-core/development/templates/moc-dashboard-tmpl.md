---
id: "{{uuid}}"
aliases: []
checksum: "{{sha256}}"
version: "1.0"
origin_path: "{{relative_path}}"
tipo: "map-of-content"
area: ""
status: "🗺️ active"
---

# 🗺️ MOC: {{title}}

> [!INFO] Visão Macro
> Mapa estratégico para a área de **{{title}}**. Este dashboard consolida a inteligência coletada e identifica lacunas de conhecimento.

## 🔥 Tópicos Quentes (Atenção Imediata)
- [ ] <!-- Tópico que exige refinamento ou pesquisa -->

## 🗂️ Índice de Conteúdo (Links Dinâmicos)

### 🏗️ Estruturas Fundamentais
```dataview
LIST FROM #Atômico 
WHERE (contains(tags, "#MOC/{{title}}") OR contains(file.outlinks, this.file.link)) 
AND tipo = "atomic-concept"
```

### 🧪 Em Desenvolvimento
```dataview
TABLE status AS "Maturidade", criado_em AS "Data"
FROM #Atômico
WHERE (contains(tags, "#MOC/{{title}}") OR contains(file.outlinks, this.file.link))
AND (status = "🌱 seedling" OR status = "budding")
SORT criado_em DESC
```

## 📉 Insights & Grafos
<!-- Área para o Argos ou Usuário descrever padrões detectados nesta MOC -->

---
#Dashboard #MOC #Argos #DesignAtômico
