# ÉPICO 7 — Orquestração completa e gate humano

**Depende de:** Épicos 1–6 (todos os subagentes e skills já funcionam isoladamente)
**Entrada:** `CLAUDE.md` (tabela das 9 etapas), todos os subagentes/skills anteriores

## Objetivo

Ter a skill orquestradora `copy-gary-halbert` rodando o pipeline completo, ponta a ponta,
etapa 0 a 8, incluindo retomada de execução interrompida e o gate humano real.

## Escopo

- `.claude/skills/copy-gary-halbert/SKILL.md`: `disable-model-invocation: true`,
  `argument-hint: --ideia <caminho> --formato <formato> [--plataforma <plataforma>]`. Roda
  **na sessão principal** (não em subagente) — mesmo motivo do hemingway: a etapa 8 é gate
  humano interativo.
- Implementa as 9 etapas da tabela em `CLAUDE.md`, cada uma:
  1. grava sua saída em `output/<formato>/<slug>/processo/`;
  2. atualiza `estado.json` (`etapa_atual`, e `loops_consumidos`/`pendencias` quando
     aplicável, conforme `epico-06`);
  3. commita na branch `copy/<slug>` com Conventional Commit.
- Retomada: se invocada com um slug existente, lê `estado.json.etapa_atual` e continua dali
  — nunca refaz etapa concluída sem pedido explícito do gate humano.
- Etapa 8 (gate humano) via `AskUserQuestion`, três saídas (ver `CLAUDE.md` §Etapa 8):
  aprovar e publicar / ajustar / abortar — com a lógica de merge, `changelog.md` e
  `_insumos/ideias/processadas/` já especificada em `CLAUDE.md`.
- Validação de `--formato`/`--plataforma` na etapa 0: erro claro e imediato se
  `--formato=post_social` sem `--plataforma`, ou se `--plataforma` for passado com outro
  `--formato`.

## Fora de escopo

Qualquer subagente/skill novo — este épico só conecta o que já existe. Melhoria de qualidade
de copy (isso é iteração de conteúdo das skills, não de orquestração).

## Critérios de aceite

- Dado `/copy-gary-halbert --ideia _insumos/ideias/teste.md --formato sales_letter`, quando
  executo pela primeira vez, então uma branch `copy/<slug>` é criada, `estado.json` é
  inicializado, e as etapas 0–7 rodam em sequência até parar na etapa 8 aguardando o gate
  humano.
- Dado que interrompo a execução após a etapa 4 (ex.: `/clear`) e invoco de novo com o mesmo
  slug, quando o pipeline retoma, então começa da etapa 5, sem refazer 0–4.
- Dado que o gate humano escolhe "ajustar" apontando um problema de redação, quando o
  pipeline reentra, então volta à etapa 3, incrementa `loops_consumidos`, e roda 3→7 de novo.
- Dado que o gate humano escolhe "aprovar e publicar", quando a etapa 8 conclui, então
  `final.md` e `changelog.md` existem, a branch foi mergeada em `main`, e o arquivo de ideia
  foi movido para `_insumos/ideias/processadas/`.
- Dado `--formato=post_social` sem `--plataforma`, quando a etapa 0 valida, então o pipeline
  para com erro claro antes de criar qualquer branch ou arquivo.

## Testes obrigatórios

- Execução ponta a ponta completa (etapa 0 a aprovação na etapa 8) para 1 ideia de teste por
  formato (3 execuções: sales_letter, post_social/instagram, meta_ads).
- Teste de retomada: interromper manualmente após uma etapa intermediária e confirmar que a
  reinvocação não refaz trabalho.
- Teste de "ajustar" no gate humano: confirmar reentrada correta e incremento de loop.
- Teste de "abortar": confirmar que a branch permanece intacta e a ideia não vai para
  `processadas/`.
- Teste de validação de flags: `--formato=post_social` sem `--plataforma` falha
  imediatamente, antes de tocar em git ou `output/`.

## Gate — não avance para o Épico 8 até que:

- [ ] As 3 execuções ponta a ponta (uma por formato) completam até o gate humano.
- [ ] Retomada após interrupção testada e funcionando.
- [ ] "Ajustar" e "abortar" testados no gate humano.
- [ ] Validação de flags falha corretamente antes de qualquer efeito colateral.

## Boas práticas aplicadas

Uma etapa = um commit (auditoria completa do processo, não só do resultado); merge para
`main` só após aprovação humana (nunca antes); orquestrador roda fora de subagente
especificamente porque precisa perguntar algo ao humano — subagente em background não
consegue.
