---
name: copy-gary-halbert
description: Pipeline completo de ideia bruta de copy a peça de marketing revisada (gramática e estilo) e aprovada por gate humano, para sales letter, post de rede social ou Meta Ads. Use quando o usuário pedir para transformar uma ideia em peça de copy, retomar uma execução em andamento, ou continuar o trabalho de um slug existente em output/.
disable-model-invocation: true
argument-hint: --ideia <caminho-em-_insumos/ideias/> --formato <sales_letter|post_social|meta_ads> [--plataforma <linkedin|substack|instagram|youtube>]  |  --retomar <slug>
allowed-tools: Read Write Edit Glob Grep Bash(git checkout -b *) Bash(git checkout *) Bash(git add *) Bash(git commit *) Bash(git status *) Bash(git diff *) Bash(git log *) Bash(git branch *) Bash(git merge --no-ff *) Bash(git rev-parse *) Bash(mv *) Bash(mkdir -p *) AskUserQuestion Agent
---

Orquestrador do pipeline. Roda **na sessão principal** (não em subagente) — a etapa 8 é gate
humano interativo, e um subagente em background não consegue perguntar nada ao usuário.
Arquitetura completa (9 etapas, subagentes, skills, regras invioláveis): `../../../CLAUDE.md`
— leia antes de rodar este pipeline se ainda não leu nesta sessão.

## Invocação

- `/copy-gary-halbert --ideia <caminho> --formato <formato> [--plataforma <plataforma>]` —
  começa uma execução nova.
- `/copy-gary-halbert --retomar <slug>` — retoma uma execução existente a partir de
  `output/<formato>/<slug>/estado.json`, na última etapa concluída. `<formato>` é descoberto
  procurando `<slug>` em `output/*/`.

## Etapa 0 — Ingestão e validação

**Validação de flags primeiro, antes de qualquer efeito colateral** (nenhuma branch, nenhum
arquivo, nenhum commit até passar aqui):

1. `--formato` precisa ser exatamente um de `sales_letter`, `post_social`, `meta_ads`. Qualquer
   outro valor: pare e mostre o erro, não prossiga.
2. Se `--formato=post_social`: `--plataforma` é obrigatório e precisa ser um de `linkedin`,
   `substack`, `instagram`, `youtube`. Faltando ou fora da lista: pare com erro claro.
3. Se `--formato` for `sales_letter` ou `meta_ads`: `--plataforma` **não pode** ser passado —
   se vier, pare com erro claro (esses formatos não têm plataforma).
4. `--ideia` precisa apontar para um arquivo existente e não vazio em `_insumos/ideias/`. Se
   não existir: pare com erro claro (não crie o arquivo, não infira conteúdo).

Só depois de 1–4 passarem:

5. **Slug:** kebab-case do nome do arquivo de `--ideia` sem extensão (ex.:
   `_insumos/ideias/curso-gratuito-live-domingo.md` → slug
   `curso-gratuito-live-domingo`). Se `output/<formato>/<slug>/` já existir, pare e pergunte
   ao usuário se é para retomar essa execução (via `--retomar`) em vez de recomeçar — nunca
   sobrescreva silenciosamente.
6. `git rev-parse --short HEAD` em `main` → `commit_inicial`.
7. `git checkout -b copy/<slug>` a partir de `main`.
8. Crie `output/<formato>/<slug>/processo/` e `output/<formato>/<slug>/estado.json`:
   ```json
   {
     "etapa_atual": 0,
     "formato": "<formato>",
     "plataforma": "<plataforma ou null>",
     "loops_consumidos": 0,
     "aprovacoes": [],
     "pendencias": [],
     "commit_inicial": "<sha curto>"
   }
   ```
9. Commit: `feat(<slug>): inicia pipeline (ingestão)`.

## Retomada (`--retomar <slug>`)

`git checkout copy/<slug>`, leia `estado.json`. **Mostre ao usuário um resumo do que já foi
feito** (etapa atual, arquivos já produzidos em `processo/`, pendências registradas) antes de
prosseguir — nunca refaça uma etapa já concluída sem pedido explícito do gate humano ou do
`revisor-final`. Continue da etapa seguinte a `estado.json.etapa_atual`.

## Etapas 1–7: como rodar cada uma

Regra comum a todas: (a) grava sua saída em `processo/`; (b) atualiza
`estado.json.etapa_atual` para o número da etapa concluída (e `loops_consumidos`/`pendencias`
quando aplicável); (c) `git add` do que mudou em `output/<formato>/<slug>/` e commit
`feat(<slug>): <nome da etapa>` na branch `copy/<slug>`.

| # | Etapa | Como invocar | Lê | Produz |
|---|---|---|---|---|
| 1 | Coleta de contexto | Agent, subagente `coletor-contexto`, passando `--ideia`, `--formato`, `--plataforma` | arquivo de ideia + insumos compartilhados | `01-brief.md` |
| 2 | Pesquisa | Agent, subagente `pesquisador-copy` | `01-brief.md` | `02-pesquisa.md` |
| 3 | Redação | Agent, subagente `redator-copy` | `01-brief.md`, `02-pesquisa.md` (e, se reentrada, `07-veredito.md` anterior) | `03-vN.md` (N=1 na primeira passagem) |
| 4 | Revisão gramatical | Agent, subagente `revisor-gramatical` | `03-vN.md` mais recente | `04-revisao-gramatical.md` |
| 5 | Revisão de estilo | Agent, subagente `revisor-estilo` | `03-vN.md` mais recente | `05-revisao-estilo.md` |
| 6 | Consolidação | Você mesmo (sessão principal), aplicando os diffs marcados `norma`/`inegociável` de 4 e 5 ao `03-vN.md` mais recente | `03-vN.md`, `04-*.md`, `05-*.md` | nova versão `03-v(N+1).md` |
| 7 | Revisão final | Agent, subagente `revisor-final`, passando `estado.json` (para `loops_consumidos`) | `03-vN.md` consolidado + histórico de `07-veredito.md` anteriores | `07-veredito.md` |

Cada subagente devolve só o laudo (arquivo em `processo/`) — o transcript de trabalho dele não
precisa entrar no seu contexto principal.

## Loop da etapa 7

Leia `07-veredito.md`:

- **`aprovado`:** siga para a etapa 8. Se houver pendência externa destacada, leve-a para o
  gate humano junto com a peça.
- **`reprovado`:** reentre no `ponto_reentrada` indicado.
  - Reentrada em **etapa 3**: incremente `estado.json.loops_consumidos` em 1, commit
    `fix(<slug>): endereça apontamentos da revisão final (loop N)`, rode 3→7 de novo.
  - Reentrada em **etapas 4–6**: não incrementa loop; rode 4→7 de novo (ou só a etapa
    específica se o apontamento for estreito o bastante).
- **`escalonado`:** não decida nada sozinho — siga para a etapa 8 mesmo assim, levando o
  resumo de não-convergência de `07-veredito.md` para o usuário ler no gate.

Nunca deixe o `revisor-final` rodar uma quarta vez consumindo loop — se
`estado.json.loops_consumidos` já é 3 ao entrar na etapa 7, o próprio subagente escalona (ver
`revisor-final.md`); você só precisa não forçar mais uma rodada por conta própria.

## Etapa 8 — Gate humano

Apresente ao usuário, de forma resumida (não despeje o arquivo inteiro sem contexto): a peça
final (`03-vN.md` mais recente), o que mudou desde a versão anterior (se houve loop), e
qualquer pendência de `estado.json.pendencias` ou destacada em `07-veredito.md`. Depois use
`AskUserQuestion` com exatamente três saídas:

**Aprovar e publicar**
1. Copie a última versão de `03-vN.md` para `output/<formato>/<slug>/final.md`, com
   frontmatter (`formato`, `plataforma`, `segmento`, `estagio_funil`, `data_aprovacao` —
   schema de `../../../../_insumos/exemplos_aprovados/README.md`).
2. Escreva `output/<formato>/<slug>/changelog.md`: o que mudou em cada versão intermediária
   (`03-v1` → `03-v2` → ...) e por quê (motivo de cada reentrada).
3. `estado.json.aprovacoes` recebe `"etapa8:aprovar:<data-de-hoje>"`; `etapa_atual` = 8.
   Commit `feat(<slug>): aprova e consolida entregáveis finais`.
4. `git checkout main && git merge --no-ff copy/<slug>` — mensagem de merge resume a peça em
   três linhas (formato, segmento, gancho principal).
5. `mv _insumos/ideias/<slug>.md _insumos/ideias/processadas/` (caminho relativo à raiz de
   `Syntaxis/`) e commit desse `mv` em `main` (`chore(<slug>): move ideia para processadas`).
6. Informe ao usuário onde ficaram `final.md` e `changelog.md`.

**Ajustar**
1. Pergunte especificamente o que mudar (nunca assuma).
2. Determine o ponto mais raso que resolve o pedido — mesma lógica da etapa 7: se o pedido é
   de redação, reentra na etapa 3 (consome loop); se é acabamento (gramática/estilo/formatação
   que passou), reentra em 4–6 (não consome).
3. Registre em `estado.json.aprovacoes`: `"etapa8:ajustar:<data-de-hoje>:<resumo do pedido>"`.
4. Reentre no pipeline a partir do ponto determinado.

**Abortar**
1. Não delete a branch `copy/<slug>` — o histórico (drafts descartados, laudos) é material de
   aprendizado futuro.
2. Não mova o arquivo de ideia para `processadas/` — ele permanece em `_insumos/ideias/` para
   retomar depois.
3. Registre `estado.json.aprovacoes`: `"etapa8:abortar:<data-de-hoje>"`. Commit
   `chore(<slug>): aborta execução no gate humano` na branch `copy/<slug>` (sem merge).
4. Avise o usuário onde a branch ficou e que pode retomar com `--retomar <slug>` depois.

## Regras que valem para toda etapa

- Nada de sobrescrita silenciosa: retomar um slug existente sempre mostra o que já foi feito
  antes de prosseguir.
- Nunca invente número, fonte, fórmula ou preço — herdado de `CLAUDE.md` §Regras invioláveis;
  qualquer subagente que sinalizar `[VERIFICAR]` mantém o marcador até o gate humano resolver.
- Máximo de 3 loops de revisão (etapa 3 ↔ etapa 7) antes de escalar — ver §Loop da etapa 7.
- Uma etapa do pipeline = um commit, sempre na branch `copy/<slug>` (nunca direto em `main`,
  exceto o merge e o `mv` de ideia processada, que só acontecem depois da aprovação humana).

## Segurança

Nunca `push --force`, `reset --hard`, `rebase` de histórico já commitado, `clean -fd`, ou
deleção de branch — em nenhuma etapa, mesmo em "abortar". Se o merge da etapa 8 tiver
conflito, pare e mostre o conflito ao usuário — não resolva automaticamente escolhendo um
lado.
