---
name: obsidian-neural-organizer
description: >
  Instala e configura Obsidian para criar uma base neural interligada com IA.
  Organiza pastas, metadados, links internos, hubs e mapa de conhecimento no padrao Opensquad.
type: prompt
version: "1.0.0"
categories: [obsidian, organization, knowledge-base, neural-network]
---

# Obsidian Neural Organizer

Skill para instalar Obsidian e estruturar uma base de conhecimento interligada para squads e agentes.

## Quando usar

Use quando o usuario pedir:
- organizar o projeto em formato second brain no Obsidian
- criar links entre arquivos/pastas
- aplicar metadados parent/references/tags nos arquivos
- montar hubs e MOCs (maps of content)

## Entrada minima

1. Caminho da pasta do projeto (vault alvo)
2. Sistema operacional (Windows/macOS/Linux), se nao detectavel
3. Preferencia de idioma (opcional)

## Fluxo obrigatorio

### 1) Instalar Obsidian

No Windows (preferencial):
```powershell
winget install --id Obsidian.Obsidian -e --accept-source-agreements --accept-package-agreements
```

Alternativa manual:
- baixar em: [https://obsidian.md/download](https://obsidian.md/download)

### 2) Abrir o vault do projeto

1. Abrir Obsidian
2. Selecionar **Open folder as vault**
3. Escolher a pasta raiz do projeto

### 3) Criar estrutura neural base

Garantir (ou criar) diretórios:
- `Cerebros/`
- `Cerebros/estudos/`
- `Cerebros/transcricoes/`
- `Cerebros/conceitos/`
- `Cerebros/fontes/`
- `Cerebros/duvidas/`
- `Cerebros/90-Mapa-Workspace/`

### 4) Aplicar metadados nos arquivos

Em cada arquivo de texto/codigo relevante, incluir metadados no inicio ou fim, respeitando formato:
- pasta pai
- referencias internas
- tags

Exemplo markdown:
```markdown
## Metadados Neurais
- Pasta pai: `projeto/pasta`
- Referencias: [[Cerebros/90-Mapa-Workspace/00-HUB]], [[Cerebros/90-Mapa-Workspace/99-POLITICA]]
- Tags: #organizacao #neural #obsidian
```

Exemplo JSON:
```json
"neuralMetadata": {
  "parentFolder": "projeto/pasta",
  "references": ["Cerebros/90-Mapa-Workspace/00-HUB"],
  "tags": ["organizacao", "neural", "obsidian"]
}
```

### 5) Construir hubs e mapa

Criar no minimo:
- `00-HUB-Workspace.md` (hub principal)
- `01-MOC-Core.md`
- `02-MOC-Squads.md`
- `03-MOC-Skills.md`
- `99-POLITICA-MENCOES-TAGS.md`

### 6) Configurar grafo no Obsidian

No `graph.json` (ou config equivalente):
- focar `path:Cerebros`
- ocultar orfaos se necessario
- criar grupos de cor por area (estudos, transcricoes, skills, squads, mapas)

### 7) Regra de consulta para agentes

Definir e documentar:
1. consultar `Cerebros` primeiro
2. se nao achar, buscar web
3. registrar novos aprendizados de volta no Cerebros

## Entrega final obrigatoria

Responder com:

1. **Resumo do setup**
2. **Checklist concluido**
3. **Arquivos criados/ajustados**
4. **Proximo passo recomendado**

## Checklist de validacao

- Obsidian instalado
- Vault aberto na pasta certa
- Estrutura `Cerebros/` criada
- Metadados aplicados em arquivos-chave
- HUB e MOCs criados
- Grafo exibindo conexoes
- Regra de consulta local-first documentada

## Prompt rapido para usar esta skill

```text
Organize este projeto no Obsidian como uma rede neural interligada, com metadados, links internos, hubs e mapa de workspace. Instale e configure tudo, depois me passe o checklist final e o próximo passo.
```
