---
name: github-auto-installer
description: >
  Instala projetos a partir de um link de GitHub com pre-configuracao automatica.
  O usuario so cola a URL e o agente analisa o repositorio, instala dependencias,
  aplica configuracoes iniciais e entrega proximos passos.
type: prompt
version: "1.0.0"
categories: [installation, github, setup, automation]
neural_parent_folder: "openSquadON/skills/github-auto-installer/"
neural_references:
  - "Cerebros/90-Mapa-OpenSquadON/43-SKILL-github-auto-installer"
  - "Cerebros/90-Mapa-OpenSquadON/03-MOC-Skills"
neural_tags: [skill, github, install, setup]
---

## Metadados Neurais
- Pasta pai: `skills/github-auto-installer`
- Referencias: [[Cerebros/90-Mapa-OpenSquadON/43-SKILL-github-auto-installer]], [[Cerebros/90-Mapa-OpenSquadON/03-MOC-Skills]]
- Tags: #skills #github #install #setup

# GitHub Auto Installer

Skill para instalacao guiada e pre-configuracao de projetos a partir de um link de GitHub.

## When to use

Use quando o usuario pedir:
- "cola esse link e instala tudo"
- "configura esse repositorio pra mim"
- "faz setup completo desse github"
- "deixa pronto para comecar"

## Required input

O usuario precisa fornecer apenas:
- URL publica do repositorio GitHub (ex.: `https://github.com/org/repo`)

## Workflow (mandatory)

1. **Validar URL**
   - Confirmar que a URL e um repositorio GitHub valido.
   - Se for URL de subpasta/arquivo, identificar o repo base.

2. **Diagnostico inicial**
   - Ler `README`, arquivos de manifesto e configuracao (`package.json`, `pyproject.toml`, `requirements.txt`, `Dockerfile`, `Makefile`, etc.).
   - Detectar stack principal (Node, Python, Go, Rust, Java, etc.).
   - Detectar gerenciador de pacotes correto (npm/pnpm/yarn/pip/poetry/bun).

3. **Instalacao de dependencias**
   - Rodar instalacao conforme stack detectada.
   - Nunca inventar versoes de dependencia.
   - Em caso de erro, registrar causa e tentar alternativa segura (ex.: npm -> pnpm somente se houver lockfile compatível).

4. **Pre-configuracao**
   - Criar `.env` a partir de `.env.example` quando existir.
   - Sinalizar variaveis obrigatorias sem valor.
   - Configurar scripts basicos de run/test/build quando o projeto fornecer.
   - Se houver MCP/config de editor no repo, orientar e aplicar setup local seguro.

5. **Validacao**
   - Executar checks minimos do projeto:
     - install OK
     - run/test/lint (quando disponivel)
   - Registrar o que passou e o que falhou.

6. **Entregar proximo passo**
   - Responder ao usuario com:
     - status final (pronto / parcial / bloqueado)
     - comandos para iniciar
     - pendencias (chaves/API/env)
     - proximo passo recomendado em 1-3 itens objetivos

## Output format (mandatory)

Sempre responder com:

1. **Resumo de instalacao**
2. **Checklist de status**
3. **Comandos para iniciar**
4. **Pendencias**
5. **Proximo passo**

## Safety rules

- Nao rodar comandos destrutivos.
- Nao sobrescrever arquivos sensiveis sem necessidade.
- Nao commitar/push automatico sem pedido explicito.
- Nao expor segredos em logs ou respostas.

## Example trigger

Usuario:
- "Instala esse repo para mim: https://github.com/exemplo/projeto"

Comportamento esperado:
- Executa fluxo completo de diagnostico + instalacao + pre-configuracao + validacao + proximos passos.
