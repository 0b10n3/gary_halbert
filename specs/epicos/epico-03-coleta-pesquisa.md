# ÉPICO 3 — Subagentes de coleta de contexto e pesquisa

**Depende de:** Épico 2
**Entrada:** `../../../_insumos/CONTEXT.md`, skill `pesquisa-direct-response`

## Objetivo

Ter os dois subagentes de abertura do pipeline (`coletor-contexto`, `pesquisador-copy`)
funcionando isoladamente, cada um produzindo seu laudo a partir de uma ideia de teste — antes
de existir qualquer redação.

## Escopo

- `.claude/agents/coletor-contexto.md`: lê o arquivo de ideia (`--ideia`), `--formato`,
  `--plataforma`, e os arquivos de `CONTEXT.md` §1–7 (identidade, promessa, público, funil,
  preço, voz). Produz `01-brief.md` com: ideia central em 1 frase, segmento declarado
  (`#Millennials-FEAR` etc.), estágio do funil, mecanismo (qual dos 3 diferenciais de
  `MARKETING.md` §4 a peça vai provar), restrições de formato/plataforma relevantes (aponta
  para a seção certa de `formatos.md`, não duplica o conteúdo).
- `.claude/agents/pesquisador-copy.md`: a partir do brief, pesquisa (web) ganchos/estruturas
  de copy semelhantes, no nicho de educação financeira e no cânone de direct-response
  (`fontes_pesquisa.md`). Produz `02-pesquisa.md` com fontes citadas e, se `exemplos_aprovados/`
  já tiver conteúdo, prioriza dado interno sobre inferência externa.
- Ambos os agent files seguem o formato do hemingway: frontmatter `name`, `description`
  (com gatilho de uso claro — "use na etapa 1/2 do pipeline copy-gary-halbert"), `tools`,
  `skills`, `model: inherit`.
- `coletor-contexto` não usa ferramentas de escrita além de `Write` no próprio `01-brief.md`
  — não deve ter permissão para editar `_insumos/` (são fonte, não destino).

## Fora de escopo

Redação da copy em si (Épico 4). Orquestração/chamada real dentro do pipeline completo
(Épico 7) — aqui os subagentes são testados isoladamente, com uma ideia de teste fixa.

## Critérios de aceite

- Dado um arquivo de ideia de teste em `_insumos/ideias/`, quando invoco `coletor-contexto`
  isoladamente, então recebo `01-brief.md` com segmento, estágio de funil e mecanismo
  declarados explicitamente (não implícitos).
- Dado o `01-brief.md` de teste, quando invoco `pesquisador-copy`, então recebo
  `02-pesquisa.md` com pelo menos 2 fontes citadas (URL ou referência ao cânone).
- Dado um dado sem fonte rastreável, quando `pesquisador-copy` for tentado a citá-lo, então o
  laudo marca `[VERIFICAR: ...]` em vez de apresentar como fato.

## Testes obrigatórios

- Rodar `coletor-contexto` com 3 ideias de teste diferentes (uma por formato: sales_letter,
  post_social, meta_ads) e confirmar que o brief resultante declara segmento/funil/mecanismo
  coerentes com o conteúdo da ideia em cada caso.
- Rodar `pesquisador-copy` a partir de um brief de teste e confirmar que nenhuma citação sem
  fonte aparece no laudo.
- Confirmar que `coletor-contexto` não escreve nem edita nenhum arquivo fora de
  `output/<formato>/<slug>/processo/`.

## Gate — não avance para o Épico 4 até que:

- [ ] `coletor-contexto` produz brief completo (segmento + funil + mecanismo) para os 3
      formatos de teste.
- [ ] `pesquisador-copy` produz pesquisa com fontes citadas, sem dado inventado.
- [ ] Nenhum dos dois subagentes escreve fora de `processo/`.

## Boas práticas aplicadas

Subagente devolve só um laudo (o transcript de pesquisa não entra no contexto principal —
mesmo padrão do `pesquisador-editorial` do hemingway); Conventional Commits
(`feat(agentes): adiciona coletor-contexto e pesquisador-copy`).
