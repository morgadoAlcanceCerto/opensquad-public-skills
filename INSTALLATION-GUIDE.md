# Arquivo de instalação — Claude Code (Skills + MCP)

## Para quem é este arquivo

Para quem comentou **Claude** e quer montar uma stack profissional no Claude Code/Cursor.

## Resultado final esperado

Você terá 7 integrações base para:
- Design-to-code
- Testes automatizados
- Pesquisa e leitura de documentação
- Scraping estruturado
- Entrega por email

---

## Stack recomendada (7 obrigatórias)

1. **Figma MCP** — design context + UI workflow  
2. **Playwright MCP** — browser automation e E2E  
3. **GitHub CLI (`gh`)** — PR, review e gestão de branch  
4. **Web Search** — pesquisa atualizada  
5. **Web Fetch** — leitura estruturada de páginas/docs  
6. **Apify** — scraping e coleta de dados  
7. **Resend** — envio de email transacional

---

## Links oficiais

- Figma MCP Guide: [https://help.figma.com/hc/en-us/articles/32132100833559-Guide-to-the-Figma-MCP-server](https://help.figma.com/hc/en-us/articles/32132100833559-Guide-to-the-Figma-MCP-server)
- Figma plugin (Cursor): [https://cursor.com/en-US/marketplace/figma](https://cursor.com/en-US/marketplace/figma)
- Figma MCP server guide (repo): [https://github.com/figma/mcp-server-guide](https://github.com/figma/mcp-server-guide)
- Playwright MCP: [https://www.npmjs.com/package/@playwright/mcp](https://www.npmjs.com/package/@playwright/mcp)
- GitHub CLI (`gh`): [https://cli.github.com/](https://cli.github.com/)
- Apify: [https://apify.com/](https://apify.com/)
- Resend: [https://resend.com/](https://resend.com/)

---

## Instalação rápida (ordem sugerida)

### 1) Figma MCP (Cursor)

No chat do Cursor:

```text
/add-plugin figma
```

Se preferir manual, adicione no `mcp.json`:

```json
{
  "mcpServers": {
    "figma": {
      "url": "https://mcp.figma.com/mcp"
    }
  }
}
```

### 2) Playwright MCP

No `mcp.json`:

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest", "--config", "_opensquad/config/playwright.config.json"]
    }
  }
}
```

### 3) GitHub CLI

Instalar `gh`, autenticar e validar:

```bash
gh auth login
gh repo view
```

### 4) Web Search + Web Fetch

Já são nativos no fluxo do agente (não exigem instalação extra no projeto).

### 5) Apify

Criar token e configurar no `.env`:

```env
APIFY_TOKEN=seu_token_aqui
```

### 6) Resend

Criar API key e configurar no `.env`:

```env
RESEND_API_KEY=sua_api_key_aqui
```

---

## Checklist de validação

- `figma` aparece ativo na lista de MCPs do editor
- `playwright` aparece ativo na lista de MCPs do editor
- `gh auth status` retorna autenticado
- `.env` contém `APIFY_TOKEN` e `RESEND_API_KEY`
- Projeto consegue executar um run com output em `output/{run_id}/`

---

## Teste mínimo de funcionamento

1. Pedir ao agente: "busque referência atualizada sobre MCP e resuma".  
2. Pedir ao agente: "ler um link específico e extrair passos".  
3. Pedir ao agente: "validar um fluxo web com Playwright".  
4. Pedir ao agente: "usar um frame Figma para contexto de design".  
5. Pedir ao agente: "gerar resposta pronta para PR com `gh`".

---

## Mensagem pronta para enviar para quem comentar

Comenta **Claude** e eu te envio:
- arquivo de instalação (skills + MCP),
- links oficiais,
- checklist de validação,
- ordem ideal para setup.

Se quiser, eu te mando também um template pronto de `mcp.json` para copiar e colar.
