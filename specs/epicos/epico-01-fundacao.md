# ÉPICO 1 — Fundação: estrutura de repositório, estado e convenção de Git

**Depende de:** nada (ponto de partida)
**Entrada:** `CLAUDE.md` (raiz deste repositório), `../../_insumos/CONTEXT.md`

## Objetivo

Ter a estrutura de pastas, o schema de `estado.json` e a convenção de Git prontos e
documentados — antes de qualquer subagente ou skill ser implementado. Nenhuma linha de
pipeline roda neste épico; é infraestrutura documental e de repositório.

## Escopo

- Confirmar/criar estrutura de pastas em `SyntaxisCopywriter/gary_halbert/`:
  `output/`, `specs/epicos/` (já existe), `.claude/skills/`, `.claude/agents/`.
- Documentar o schema de `estado.json` em `specs/estado.schema.md` (campos, tipos, valores
  possíveis de `etapa_atual` 0–8, exemplo comentado) — usado por toda etapa do pipeline daqui
  em diante.
- Script ou instrução manual (documentada, não necessariamente automatizada) para criar
  branch `copy/<slug>` a partir de `main` e inicializar `output/<formato>/<slug>/estado.json`.
- `.gitignore` do repositório (nada de segredo aplicável aqui, mas padronizar arquivos de
  sistema/editor).
- `README.md` do repositório: o que é, como invocar o pipeline (mesmo que a skill ainda não
  exista), link para `CLAUDE.md`.
- Confirmar que os insumos compartilhados existem e são legíveis por caminho relativo a
  partir daqui: `../../_insumos/CONTEXT.md`, `gary_halbert.md`, `formatos.md`,
  `fontes_pesquisa.md`, `../../AUDIENCES.md`, `../../FUNIL.MD`,
  `../../SyntaxisEducation/PRICE_TAG.md`, `../../SyntaxisSubstack/hemingway/estilo/estilo-autoral.md`.

## Fora de escopo

Qualquer skill ou subagente funcional — isso começa no Épico 2. Automação de CI — este
pipeline é disparado manualmente, não há workflow a configurar.

## Critérios de aceite

- Dado o repositório `gary_halbert` clonado, quando eu abro `CLAUDE.md`, então encontro a
  arquitetura completa do pipeline (9 etapas, subagentes, skills, git).
- Dado que preciso saber o schema de `estado.json`, quando eu abro `specs/estado.schema.md`,
  então encontro todos os campos com tipo e propósito documentados.
- Dado qualquer um dos 8 caminhos relativos listados no Escopo, quando eu tento ler o
  arquivo a partir da raiz de `gary_halbert/`, então o arquivo existe e não está vazio.

## Testes obrigatórios

- Checklist manual: todos os 8 caminhos relativos resolvem para um arquivo existente e não
  vazio (`test -s <caminho>`).
- Revisão manual: `estado.schema.md` cobre exatamente os campos usados no exemplo de
  `CLAUDE.md` §`estado.json` (nenhum campo a mais, nenhum a menos).

## Gate — não avance para o Épico 2 até que:

- [ ] `output/`, `.claude/skills/`, `.claude/agents/` existem (podem estar vazios).
- [ ] `specs/estado.schema.md` existe e documenta todos os campos de `estado.json`.
- [ ] `README.md` existe e explica a invocação do pipeline.
- [ ] Todos os 8 caminhos relativos aos insumos compartilhados resolvem e têm conteúdo.

## Boas práticas aplicadas

Conventional Commits (`docs(fundacao): ...`); nenhum segredo neste épico (não aplicável, mas
`.gitignore` já preparado para quando houver); documentação antes de código — ninguém escreve
uma skill sem saber o schema de estado que ela vai ler/escrever.
