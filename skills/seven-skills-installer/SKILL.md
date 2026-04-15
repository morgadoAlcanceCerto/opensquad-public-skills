---
name: seven-skills-installer
description: >
  Instalador guiado das 7 skills/MCPs essenciais para Claude Code.
  Executa checklist de setup, pre-configuracao, validacao e entrega os
  proximos passos para deixar o ambiente pronto rapidamente.
type: prompt
version: "1.0.0"
categories: [installation, setup, mcp, claude-code]
---

# Seven Skills Installer

Skill para instalar e pre-configurar o pacote de 7 integracoes essenciais.

## Quando usar

Use quando o usuario pedir:
- "instala as 7 skills"
- "faz setup completo do claude code"
- "deixa meu ambiente pronto com mcp"

## Stack alvo (7)

1. Figma MCP
2. Playwright MCP
3. GitHub CLI (`gh`)
4. Web Search
5. Web Fetch
6. Apify
7. Resend

## Entrada minima

O usuario precisa fornecer:
- sistema operacional (se necessario para comandos)
- preferencia de editor (Cursor, VS Code ou Claude Code)

Se nao informar, assuma Cursor por padrao.

## Fluxo obrigatorio

1. **Diagnostico**
   - Verificar o que ja esta instalado/configurado.
   - Evitar reinstalar componentes ja funcionando.

2. **Instalacao base**
   - Figma MCP (plugin ou configuracao manual no `mcp.json`).
   - Playwright MCP no `mcp.json`.
   - GitHub CLI (`gh`) e autenticacao.

3. **Pre-configuracao**
   - Criar ou atualizar `.env` com:
     - `APIFY_TOKEN=`
     - `RESEND_API_KEY=`
   - Se o projeto usar `.env.example`, partir dele.

4. **Validacao**
   - Confirmar MCPs ativos (`figma`, `playwright`).
   - Confirmar `gh auth status`.
   - Confirmar variaveis obrigatorias detectadas.

5. **Entrega final**
   - Status por item (OK / pendente / erro).
   - Lista de pendencias objetivas.
   - Proximo passo recomendado para uso pratico.

## Output esperado (sempre)

Responder com os blocos:

1. **Resumo**
2. **Status das 7 skills**
3. **Pendencias**
4. **Proximos passos**

## Regras de seguranca

- Nao expor segredos em texto aberto.
- Nao commitar `.env` ou tokens.
- Nao executar comandos destrutivos.
- Em caso de erro externo (rede/permissao), propor fallback seguro.

## Prompt pronto para acionamento

```text
Instale as 7 skills obrigatorias para Claude Code neste projeto, com pre-configuracao e checklist final.
```
