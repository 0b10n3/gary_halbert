# ÉPICO 2 — Skills de referência: estilo, formatos e pesquisa

**Depende de:** Épico 1
**Entrada:** `../../../_insumos/formatos.md`, `../../../_insumos/gary_halbert.md`,
`../../../_insumos/fontes_pesquisa.md`, `../../../hemingway/.claude/skills/voz-syntaxis/SKILL.md`

## Objetivo

Ter as três skills de conhecimento procedural do pipeline prontas e carregáveis, antes de
qualquer subagente que dependa delas (redator, revisor-estilo, revisor-final, pesquisador).

## Escopo

- `.claude/skills/estilo-syntaxis/SKILL.md` — **não duplica** conteúdo de voz. Aponta por
  caminho relativo para `../../../hemingway/estilo/estilo-autoral.md` e
  reexplica quando usar (redação e revisão de estilo, qualquer formato de copy). Frontmatter
  com `disable-model-invocation: true` seria incorreto aqui — esta é skill de referência, não
  de escrita de arquivo/disparo de pipeline; usar invocação automática por descrição.
- `.claude/skills/formatos-copy/SKILL.md` — aponta para `../../../_insumos/formatos.md`,
  explica quando cada seção se aplica (por `--formato`/`--plataforma`).
- `.claude/skills/pesquisa-direct-response/SKILL.md` — aponta para
  `../../../_insumos/gary_halbert.md` e `../../../_insumos/fontes_pesquisa.md`; documenta a
  regra de direitos autorais (extrair estrutura, nunca frase pronta — já enunciada em
  `gary_halbert.md` §11).
- Cada `SKILL.md` segue o formato de frontmatter do hemingway: `name`, `description`
  (específica o bastante para invocação automática correta), `allowed-tools` quando aplicável.

## Fora de escopo

Subagentes que consomem estas skills (Épicos 3–6). Conteúdo novo de estilo/formato/técnica —
este épico só empacota os insumos já escritos em `_insumos/` como skills invocáveis, não
escreve conteúdo original.

## Critérios de aceite

- Dado que `redator-copy` precisa da voz autoral, quando ele carrega a skill
  `estilo-syntaxis`, então recebe o caminho para `estilo-autoral.md` sem que o conteúdo
  tenha sido copiado para dentro do repositório `gary_halbert`.
- Dado um `--formato=meta_ads`, quando `formatos-copy` é carregada, então a seção 3 de
  `formatos.md` (specs de Meta Ads) é a parte relevante indicada.
- Dado que `pesquisador-copy` está prestes a citar um autor do cânone de copywriting, quando
  ele consulta `pesquisa-direct-response`, então encontra a regra explícita de não citar
  frase protegida.

## Testes obrigatórios

- Invocação manual de cada skill (`/estilo-syntaxis`, etc., ou describe-trigger) confirma que
  o conteúdo carregado é o esperado e que os caminhos relativos resolvem a partir da raiz do
  repositório onde a skill é invocada.
- Teste de não-duplicação: `grep` por um trecho característico de `estilo-autoral.md` dentro
  de `.claude/skills/estilo-syntaxis/` deve retornar vazio (prova de que é referência, não
  cópia).

## Gate — não avance para o Épico 3 até que:

- [ ] As três skills existem e carregam sem erro de caminho.
- [ ] `estilo-syntaxis` referencia (não copia) `estilo-autoral.md`.
- [ ] Cada skill tem `description` específica o bastante para invocação automática correta
      (testado pedindo, em sessão nova, para "revisar o estilo desta copy" e confirmando que
      a skill certa é sugerida).

## Boas práticas aplicadas

Uma fonte por fato (regra do ecossistema, ver `CLAUDE.md` §Fonte única); Conventional
Commits (`feat(skills): adiciona estilo-syntaxis/formatos-copy/pesquisa-direct-response`).
