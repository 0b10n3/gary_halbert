# ÉPICO 4 — Subagente de redação

**Depende de:** Épico 3
**Entrada:** `01-brief.md`, `02-pesquisa.md` (saídas do Épico 3), skills `estilo-syntaxis` e
`formatos-copy`

## Objetivo

Ter `redator-copy` produzindo uma primeira versão de peça de copy, coerente com o brief, a
pesquisa, a voz Syntaxis e a especificação do formato/plataforma.

## Escopo

- `.claude/agents/redator-copy.md`: recebe `01-brief.md` + `02-pesquisa.md`, carrega
  `estilo-syntaxis` e `formatos-copy`, escreve `03-v1.md`. Aplica a estrutura correta do
  formato (`formatos.md` §1–3: sales letter usa a estrutura de `gary_halbert.md` §10; post
  social usa a estrutura de abertura-forte por plataforma; Meta Ads respeita limite mecânico
  de cada campo desde o rascunho, não só na revisão).
- Declara no topo do rascunho (não na peça final): segmento, estágio do funil, formato,
  plataforma — herdado do brief, não reinventado.
- Se o brief sinalizar `[VERIFICAR]` em algum dado necessário à peça (ex.: preço da isca),
  o redator escreve a peça sem ancorar nesse dado, preservando o `[VERIFICAR]` visível no
  rascunho para as etapas seguintes — nunca resolve a lacuna com um valor inventado.
- Recebimento de reentrada (etapa 7/8 do pipeline devolvendo com apontamentos): `redator-copy`
  deve saber ler `07-veredito.md` ou o pedido de ajuste do gate humano e produzir `03-vN.md`
  (incrementando N), preservando as versões anteriores (nunca sobrescreve `03-v1.md`).

## Fora de escopo

Revisão gramatical/estilo/final (Épicos 5–6) — `redator-copy` não se autorrevisa além do que
a skill de estilo já orienta na escrita.

## Critérios de aceite

- Dado um brief de sales letter para `#GENZ-FEAR` no estágio "isca paga", quando
  `redator-copy` escreve `03-v1.md`, então a peça contém headline, lead, prova do mecanismo,
  oferta, urgência (se real) e CTA — as partes de `gary_halbert.md` §10.
- Dado um brief de post para Instagram, quando `redator-copy` escreve a peça, então os
  primeiros ~125 caracteres carregam o gancho do segmento, sem depender do texto após o corte.
- Dado um brief com preço marcado `[VERIFICAR]`, quando a peça é escrita, então nenhum valor
  numérico de preço aparece como fato definitivo.
- Dado um `07-veredito.md` de reprovação apontando problema específico, quando
  `redator-copy` é invocado de novo, então `03-v2.md` é criado (não sobrescreve `03-v1.md`)
  e o apontamento específico é endereçado.

## Testes obrigatórios

- Gerar `03-v1.md` para os 3 formatos de teste do Épico 3 e conferir contra o checklist de
  `formatos.md` §4 (limite mecânico, abertura autossuficiente, segmento/funil coerentes,
  nenhum dado inventado).
- Simular uma reentrada (fornecer um `07-veredito.md` de teste com reprovação) e confirmar
  que `03-v2.md` é gerado preservando `03-v1.md`.

## Gate — não avance para o Épico 5 até que:

- [ ] `03-v1.md` gerado para os 3 formatos de teste, todos passando no checklist de
      `formatos.md` §4.
- [ ] Nenhuma peça de teste ancora em dado `[VERIFICAR]`.
- [ ] Reentrada com incremento de versão testada e funcionando.

## Boas práticas aplicadas

Voz herdada da skill (`voz-syntaxis`), não reinventada por peça; versionamento explícito
(`03-vN.md`) em vez de sobrescrita, para que `changelog.md` (Épico 7) tenha o que comparar;
Conventional Commits (`feat(agentes): adiciona redator-copy`).
