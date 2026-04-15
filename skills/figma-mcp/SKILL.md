---
name: figma-mcp
description: >
  Integra o Figma MCP server remoto para workflows de design-to-code e code-to-design.
  Permite obter contexto de design, gerar estrutura visual e acelerar desenvolvimento
  de carrosseis com consistencia de design system.
type: mcp
version: "1.0.0"
mcp:
  server_name: figma
  transport: http
  url: "https://mcp.figma.com/mcp"
categories: [design, figma, mcp, carousel]
neural_parent_folder: "openSquadON/skills/figma-mcp/"
neural_references:
  - "Cerebros/90-Mapa-OpenSquadON/03-MOC-Skills"
  - "Cerebros/90-Mapa-OpenSquadON/22-SQUAD-ia-content"
neural_tags: [skill, figma, mcp, carousel]
---

# Figma MCP — Carousel Design Workflow

## Metadados Neurais
- Pasta pai: `skills/figma-mcp`
- Referencias: [[Cerebros/90-Mapa-OpenSquadON/03-MOC-Skills]], [[Cerebros/90-Mapa-OpenSquadON/22-SQUAD-ia-content]]
- Tags: #skills #figma #mcp #design

## Quando usar

- Quando o usuário quiser transformar tela/layout em estrutura Figma
- Quando precisar extrair contexto de design de um frame/link Figma
- Quando quiser padronizar carrossel com design system e tokens

## Fluxo recomendado para carrossel

1. Definir formato alvo (1080x1350 ou 1080x1440)
2. Obter contexto de frame no Figma (tokens, componentes, estilos)
3. Mapear layout em blocos (capa, miolo, CTA final)
4. Aplicar hierarquia tipográfica e spacing consistente
5. Validar consistência visual antes de exportação

## Observações

- O endpoint remoto é `https://mcp.figma.com/mcp`.
- Em Cursor, o plugin oficial Figma também pode ser instalado via `/add-plugin figma`.
- Dependendo do cliente MCP, pode ser necessário autenticar com Figma na primeira execução.
