---
name: "commit-standards"
displayName: "Commit Standards"
description: "Padrão de commits usando Conventional Commits, Semantic Release, Commitlint e Gitmoji. Garante consistência nas mensagens de commit com emojis, tipos padronizados e versionamento automático."
keywords: ["conventional-commits", "semantic-release", "commitlint", "gitmoji", "commit-emoji", "changelog"]
author: "Leonardo Cardoso"
---

# Commit Standards

## Overview

Este power define o padrão completo de mensagens de commit para projetos, combinando Conventional Commits, Semantic Release e Gitmoji. Ele garante que todas as mensagens de commit sigam um formato consistente com emojis, tipos padronizados e descrições claras em português brasileiro.

O padrão permite versionamento automático via Semantic Release, geração automática de CHANGELOG e validação de commits via Commitlint + Lefthook.

## Formato do Commit

```
<emoji> <type>: <subject>

[optional body]

[optional footer(s)]
```

### Estrutura

- **emoji**: Código do emoji no formato `:code:` (ex: `:bug:`, `:sparkles:`)
- **type**: Tipo da mudança (feat, fix, docs, etc.)
- **subject**: Descrição curta e imperativa da mudança
- **body**: Descrição detalhada (opcional)
- **footer**: Informações adicionais como breaking changes, issues relacionadas (opcional)

**IMPORTANTE**: Use sempre o código do emoji (`:bug:`) e não o emoji visual (🐛) na mensagem de commit.

## Tabela de Tipos, Emojis e Versionamento

### Releases e Versionamento (Semantic Release)

| Emoji | Code | Type | Descrição | Versão |
|-------|------|------|-----------|--------|
| 💥 | `:boom:` | `BREAKING CHANGE` | Mudança que quebra compatibilidade | MAJOR |
| ✨ | `:sparkles:` | `feat` | Nova funcionalidade | MINOR |
| 🐛 | `:bug:` | `fix` | Correção de bug | PATCH |
| 🚑 | `:ambulance:` | `fix` | Hotfix crítico | PATCH |
| 🔒 | `:lock:` | `fix` | Correção de segurança | PATCH |

### Documentação

| Emoji | Code | Type | Descrição |
|-------|------|------|-----------|
| 📝 | `:memo:` | `docs` | Adicionar ou atualizar documentação |
| 💡 | `:bulb:` | `docs` | Adicionar ou atualizar comentários no código |

### Estilo e Formatação

| Emoji | Code | Type | Descrição |
|-------|------|------|-----------|
| 🎨 | `:art:` | `style` | Melhorar estrutura/formato do código |
| 💄 | `:lipstick:` | `style` | Adicionar ou atualizar UI e arquivos de estilo |
| 🚨 | `:rotating_light:` | `style` | Corrigir avisos do compiler/linter |

### Refatoração

| Emoji | Code | Type | Descrição |
|-------|------|------|-----------|
| ♻️ | `:recycle:` | `refactor` | Refatorar código |
| 🔥 | `:fire:` | `refactor` | Remover código ou arquivos |
| ⚰️ | `:coffin:` | `refactor` | Remover código morto |

### Performance

| Emoji | Code | Type | Descrição |
|-------|------|------|-----------|
| ⚡ | `:zap:` | `perf` | Melhorar performance |

### Testes

| Emoji | Code | Type | Descrição |
|-------|------|------|-----------|
| ✅ | `:white_check_mark:` | `test` | Adicionar ou atualizar testes |
| 🧪 | `:test_tube:` | `test` | Adicionar teste que falha |
| 🤡 | `:clown_face:` | `test` | Mock de dados |

### Build e CI/CD

| Emoji | Code | Type | Descrição |
|-------|------|------|-----------|
| 🔧 | `:wrench:` | `build` | Adicionar ou atualizar arquivos de configuração |
| 👷 | `:construction_worker:` | `ci` | Adicionar ou atualizar sistema de CI/CD |
| 💚 | `:green_heart:` | `ci` | Corrigir build do CI |
| 📦 | `:package:` | `build` | Adicionar ou atualizar arquivos compilados |
| ⬆️ | `:arrow_up:` | `build` | Atualizar dependências |
| ⬇️ | `:arrow_down:` | `build` | Downgrade de dependências |
| 📌 | `:pushpin:` | `build` | Fixar dependências em versões específicas |
| ➕ | `:heavy_plus_sign:` | `build` | Adicionar dependência |
| ➖ | `:heavy_minus_sign:` | `build` | Remover dependência |

### Releases

| Emoji | Code | Type | Descrição |
|-------|------|------|-----------|
| 🔖 | `:bookmark:` | `release` | Release / Tags de versão |
| 🚀 | `:rocket:` | `release` | Deploy |

### Chores

| Emoji | Code | Type | Descrição |
|-------|------|------|-----------|
| 🔨 | `:hammer:` | `chore` | Adicionar ou atualizar scripts de desenvolvimento |
| 🙈 | `:see_no_evil:` | `chore` | Adicionar ou atualizar .gitignore |
| 🔀 | `:twisted_rightwards_arrows:` | `chore` | Merge de branches |
| ⏪ | `:rewind:` | `chore` | Reverter mudanças |
| 🚚 | `:truck:` | `chore` | Mover ou renomear recursos |

### Internacionalização e Acessibilidade

| Emoji | Code | Type | Descrição |
|-------|------|------|-----------|
| 🌐 | `:globe_with_meridians:` | `i18n` | Internacionalização e localização |
| ♿ | `:wheelchair:` | `a11y` | Melhorar acessibilidade |
| 🚧 | `:construction:` | `wip` | Trabalho em progresso |

## Regras Obrigatórias

1. Todo commit DEVE começar com emoji + type
2. Subject em português brasileiro, modo imperativo ("adicionar" não "adicionado")
3. Subject com letra minúscula (exceto nomes próprios)
4. Sem ponto final no subject
5. Máximo 72 caracteres no subject
6. Breaking changes explícitos: use `!` após type E/OU footer `BREAKING CHANGE:`

### Recomendado

- Body descritivo para mudanças complexas
- Referencie issues: `Closes #123`, `Fixes #456`, `Refs #789`
- Um commit = uma mudança lógica
- Commits atômicos e focados

### Proibido

- ❌ Commits sem emoji ou type
- ❌ Mensagens genéricas ("fix", "update", "changes")
- ❌ Múltiplas mudanças não relacionadas no mesmo commit
- ❌ Commits de merge manual (use squash ou rebase)
- ❌ Breaking changes sem documentação adequada

## Semantic Release — Versionamento Automático

- **MAJOR (x.0.0)**: Commits com `BREAKING CHANGE` ou `!`
- **MINOR (0.x.0)**: Commits do tipo `feat`, `perf`
- **PATCH (0.0.x)**: Commits do tipo `fix`, `refactor`, `style`, `test`, `build`, `ci`, `chore`

O CHANGELOG é gerado automaticamente:
- Breaking changes destacados no topo
- Features listadas
- Bug fixes agrupados
- Outros tipos categorizados

## Exemplos de Commits

### Feature (MINOR)
```
:sparkles: feat: adicionar suporte para validação customizada

Implementa sistema de validação customizada que permite
aos desenvolvedores criar suas próprias regras de validação.

Closes #123
```

### Bug Fix (PATCH)
```
:bug: fix: corrigir erro ao exportar dados vazios

Adiciona verificação para prevenir erro quando não há dados
para exportar.

Fixes #456
```

### Breaking Change (MAJOR)
```
:boom: feat!: alterar estrutura de resposta da API

BREAKING CHANGE: A estrutura de resposta da API foi alterada.
O campo `data` agora retorna um objeto em vez de array.

Migração:
- Antes: response.data[0].name
- Depois: response.data.name

Refs #789
```

### Hotfix Crítico
```
:ambulance: fix: corrigir vulnerabilidade de segurança no login
```

### Documentação
```
:memo: docs: atualizar instruções de instalação
```

### Refatoração
```
:recycle: refactor: simplificar lógica de cache
```

### Performance
```
:zap: perf: otimizar renderização de tabelas grandes
```

### Testes
```
:white_check_mark: test: adicionar testes para validação de email
```

### Build/CI
```
:construction_worker: ci: adicionar stage de análise de segurança
```

### Chore
```
:hammer: chore: adicionar script de setup do ambiente
```

### Style
```
:lipstick: style: atualizar cores do tema primário
```

## Exemplos Ruins vs Bons

### ❌ Ruim
```
update code
fix bug
changes
WIP
```

### ✅ Bom
```
:sparkles: feat: adicionar autenticação OAuth2
:bug: fix: corrigir ordenação de colunas
:memo: docs: atualizar documentação de endpoints
:recycle: refactor: simplificar função de formatação
```

## Workflow de Commit

1. Faça suas mudanças no código
2. Stage suas mudanças: `git add .`
3. Escolha o emoji e type apropriado usando as tabelas acima
4. Escreva o commit seguindo o formato: `:emoji: type: subject`
5. Valide localmente com commitlint
6. Push para o repositório

## Ferramentas Recomendadas

### CLI
- **commitizen**: `npm install -g commitizen` → `git cz`
- **gitmoji-cli**: `npm install -g gitmoji-cli` → `gitmoji -c`

### Extensões VSCode/Kiro
- Conventional Commits — autocomplete para commits
- Gitmoji — picker de emojis
- GitLens — visualização de histórico

## Troubleshooting

### Commitlint rejeita meu commit
- Verifique se o type está na lista permitida (feat, fix, docs, style, refactor, perf, test, build, ci, chore, revert, wip, release, i18n, a11y)
- Verifique se o subject começa com letra minúscula
- Verifique se o subject tem no máximo 72 caracteres
- Verifique se o header total tem no máximo 100 caracteres

### Semantic Release não gera versão
- Verifique se o commit type está correto (feat → MINOR, fix → PATCH)
- Verifique se o formato do commit segue o padrão Conventional Commits
- Breaking changes precisam de `BREAKING CHANGE:` no footer ou `!` após o type

## Referências

- [Conventional Commits](https://www.conventionalcommits.org/)
- [Semantic Versioning](https://semver.org/)
- [Gitmoji](https://gitmoji.dev/)
- [Commitlint](https://commitlint.js.org/)
- [Lefthook](https://github.com/evilmartians/lefthook)
