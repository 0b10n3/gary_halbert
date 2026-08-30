# gary_halbert — pipeline de copy Syntaxis

Este repositório transforma uma ideia bruta de copy em uma peça de marketing revisada
(gramática e estilo), aprovada por um humano, para um de três formatos: **sales letter**,
**post de rede social** (LinkedIn, Substack, Instagram ou YouTube) ou **Meta Ads**. Não é um
repositório de código de produto — é um sistema de skills, subagentes e arquivos versionados
que juntos formam um pipeline editorial de copy, irmão do pipeline `hemingway` (Substack).

## Regras invioláveis

- **Gate humano é obrigatório ao final de todo fluxo**, para qualquer formato — o pipeline
  nunca publica ou finaliza sozinho, mesmo que `revisor-final` dê "aprovado". Mesmo padrão
  do `hemingway`.
- **Não invente número, fonte, fórmula ou preço.** Dado sem fonte verificável em
  `FEAR.md`/`GREED.md`/`MARKETING.md`/`PRICE_TAG.md` vira `[VERIFICAR: ...]` no rascunho.
- **Uma fonte por fato.** Voz autoral, público, funil e preço vivem cada um em exatamente um
  arquivo (ver §Fonte única abaixo); este repositório referencia por caminho relativo, nunca
  copia.
- **Toda skill que escreve arquivo ou dispara pipeline leva `disable-model-invocation: true`.**
- **Máximo de 3 loops de revisão** (`revisor-final` ↔ `redator-copy`) antes de escalar para
  decisão humana. Ao esgotar, `revisor-final` **nunca aprova nem rejeita por conta própria**
  — entrega o estado atual com um resumo honesto do que não convergiu.
- **Nada de sobrescrita silenciosa.** Retomar um slug existente sempre mostra o que já foi
  feito antes de prosseguir.
- **Git nunca destrói histórico.** Ver §Git abaixo.

## Estrutura

```
_insumos/                     (na raiz Syntaxis/, compartilhado com outros projetos)
  CONTEXT.md                  brief de orientação — aponta para as fontes, não duplica
  gary_halbert.md             princípios de direct-response copywriting
  formatos.md                 specs mecânicos + melhor prática por formato/plataforma
  fontes_pesquisa.md          cânone de copy + concorrência/mercado já mapeados
  exemplos_aprovados/         peças reais já aprovadas (cresce com o uso, vazia no início)
  ideias/                     ideias brutas apontadas via --ideia
    processadas/              ideias já aprovadas e publicadas (movidas para cá)
pipelines/gary_halbert/
  specs/epicos/                especificação de implementação, por épico, com testes
  output/<formato>/<slug>/     entregáveis + processo de uma execução do pipeline
  .claude/skills/               skill orquestradora + skills de referência
  .claude/agents/                subagentes de trabalho isolado
```

## Fonte única de cada coisa

- **Identidade e missão:** `../../strategy/SYNTAXIS.md`.
- **Público e gatilhos emocionais:** `../../strategy/AUDIENCES.md` + `../../strategy/FEAR.md` + `../../strategy/GREED.md`.
- **Funil e oferta:** `../../strategy/FUNIL.md` (destilação de `../../strategy/MARKETING.md` §5–8).
- **Preço:** `../../strategy/PRICE_TAG.md`.
- **Voz autoral:** `../../pipelines/hemingway/estilo/estilo-autoral.md` + skill
  `voz-syntaxis` do repositório `hemingway` — referenciados, nunca copiados.
- **Técnica de copywriting:** `../_insumos/gary_halbert.md`.
- **Especificação de formato/plataforma:** `../_insumos/formatos.md`.

## O pipeline: `/copy-gary-halbert --ideia <caminho> --formato <formato> [--plataforma <plataforma>]`

```
--formato = sales_letter | post_social | meta_ads
--plataforma = linkedin | substack | instagram | youtube   (obrigatório só se post_social)
--ideia = caminho para o arquivo em _insumos/ideias/
```

Nove etapas (0–8), cada uma grava em `output/<formato>/<slug>/processo/`, atualiza
`estado.json` e **commita**. A skill retoma da última etapa concluída se invocada de novo
com o mesmo slug — nunca refaz etapa já concluída sem que o gate humano peça isso
explicitamente.

| # | Etapa | Executor | Saída em `processo/` |
|---|---|---|---|
| 0 | Ingestão | principal | valida `--formato`/`--plataforma`, cria `estado.json` e branch `copy/<slug>` a partir de `main` |
| 1 | Coleta de contexto | subagente `coletor-contexto` | `01-brief.md` — segmento (`AUDIENCES.md`), estágio do funil (`FUNIL.md`), mecanismo (`CONTEXT.md` §3) |
| 2 | Pesquisa | subagente `pesquisador-copy` + skill `pesquisa-direct-response` | `02-pesquisa.md` — ganchos/estruturas correlatas, com fontes |
| 3 | Redação | subagente `redator-copy` + skills `estilo-syntaxis` + `formatos-copy` | `03-vN.md` |
| 4 | Revisão gramatical | subagente `revisor-gramatical` | `04-revisao-gramatical.md` — diff comentado, não mexe em estrutura |
| 5 | Revisão de estilo | subagente `revisor-estilo` + skill `estilo-syntaxis` | `05-revisao-estilo.md` |
| 6 | Consolidação | principal | aplica 4+5 em `03-vN.md`, gera nova versão |
| 7 | Revisão final | subagente `revisor-final` + skill `formatos-copy` | `07-veredito.md` — aprova (→ 8) ou devolve à etapa 3 com apontamentos (máx. 3 loops; ao esgotar, escala ao humano) |
| 8 | **Gate humano** | principal | `AskUserQuestion`: aprovar e publicar / ajustar / abortar |

**Se a etapa 7 devolver reprovação:** reentrada na etapa 3 **consome um loop**
(`estado.json.loops_consumidos`); reentrada nas etapas 4–6 (acabamento) não consome.

## Etapa 8 — gate humano

Três saídas via `AskUserQuestion`:

- **Aprovar e publicar** → copia a última versão para `final.md`, escreve `changelog.md`
  (o que mudou em cada iteração e por quê), **merge da branch `copy/<slug>` para `main`**,
  move o arquivo de `_insumos/ideias/<slug>.md` para `_insumos/ideias/processadas/`.
- **Ajustar** → pergunta o que mudar, reentra no ponto mais raso que resolve o pedido
  (mesma lógica de loop da etapa 7).
- **Abortar** → deixa a branch `copy/<slug>` como está (não deleta — histórico alimenta
  aprendizado futuro), avisa onde ela ficou. A ideia permanece em `_insumos/ideias/` (não
  vai para `processadas/`).

## `estado.json`

```json
{
  "etapa_atual": 0,
  "formato": "sales_letter",
  "plataforma": null,
  "loops_consumidos": 0,
  "aprovacoes": [],
  "pendencias": [],
  "commit_inicial": "<sha curto de main no momento da criação>"
}
```

## Os entregáveis (etapa 8, na raiz de `output/<formato>/<slug>/`)

**`final.md`** — peça aprovada, com frontmatter (formato, plataforma, segmento, estágio do
funil, data de aprovação — mesmo schema de `_insumos/exemplos_aprovados/README.md`).
**`changelog.md`** — o que mudou em cada versão intermediária e por quê.

## Git

Convenção de commit: `<tipo>(<escopo>): <o que mudou, no imperativo>`. Tipos: `feat`, `fix`,
`docs`, `chore`, `refactor`. Escopo: o slug da execução. Uma etapa do pipeline = um commit.

Branches: `main` (só conteúdo aprovado), `copy/<slug>` (ciclo de uma ideia).

Disparo **sempre manual pelo usuário via Claude Code** — sem automação por CI. Commit a cada
etapa acontece na branch `copy/<slug>`; **merge para `main` só depois da aprovação humana**
(etapa 8). **Nunca** pré-aprove nem execute sem perguntar: `push --force`, `reset --hard`,
`rebase` de histórico já publicado, `clean -fd`, `filter-branch`, deleção de branch remota.

## Ao rodar este repositório de novo

Verifique `specs/epicos/` e este `CLAUDE.md` antes de propor recriar qualquer coisa — se já
existem `.claude/skills/` e `.claude/agents/` populados, o modo é auditoria/atualização, não
bootstrap.
