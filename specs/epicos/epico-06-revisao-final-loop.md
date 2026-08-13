# ÉPICO 6 — Revisão final e loop de decisão

**Depende de:** Épico 5
**Entrada:** `03-vN.md` consolidado, `04-revisao-gramatical.md`, `05-revisao-estilo.md`,
skill `formatos-copy`, `specs/estado.schema.md`

## Objetivo

Ter `revisor-final` decidindo, com critério objetivo, entre aprovar (→ gate humano) ou
devolver ao `redator-copy` com apontamentos específicos — e a lógica de loop (máx. 3,
`estado.json.loops_consumidos`) implementada corretamente, incluindo o caso de esgotamento.

## Escopo

- `.claude/agents/revisor-final.md`: avalia a peça consolidada contra o checklist de
  `formatos.md` §4 (limite mecânico, abertura autossuficiente, segmento/funil coerentes,
  preço respeitando `[VERIFICAR]`, nenhum dado inventado) **e** contra AIDA/PAS
  (`gary_halbert.md` §3–4) como critério de completude estrutural. Produz `07-veredito.md`
  com veredito binário (aprovado/reprovado) + lista de apontamentos específicos e acionáveis
  se reprovado (nunca "melhore a peça" genérico).
- Lógica de loop (documentada aqui, implementada na skill orquestradora do Épico 7, mas
  especificada neste épico porque é regra de negócio do `revisor-final`):
  - Reprovação → incrementa `loops_consumidos` **somente se** a reentrada for na etapa 3
    (redação) — reentrada nas etapas 4–6 (acabamento) não consome loop. Mesma regra do
    hemingway.
  - `loops_consumidos` chega a 3 → `revisor-final` **não aprova nem reprova por conta
    própria**. Produz `07-veredito.md` com resumo honesto do que não convergiu entre as
    tentativas e o que precisa de decisão humana — o pipeline segue para a etapa 8 (gate
    humano) de qualquer forma, mas com esse resumo em vez de um veredito automático.
- `revisor-final` nunca corrige a peça diretamente — só avalia e aponta.

## Fora de escopo

O gate humano em si (`AskUserQuestion`, Épico 7) — este épico só garante que o insumo que
chega ao gate humano (aprovação normal ou escalonamento por esgotamento) está correto.

## Critérios de aceite

- Dado uma peça que viola o limite mecânico do formato (ex.: headline de Meta Ads > 40
  caracteres), quando `revisor-final` avalia, então reprova com apontamento específico
  citando o campo e o limite violado.
- Dado uma peça que passa em todos os critérios de `formatos.md` §4, quando `revisor-final`
  avalia, então aprova e o veredito aponta explicitamente para a etapa 8.
- Dado `loops_consumidos == 2` e uma nova reprovação que reentraria na etapa 3, quando
  `revisor-final` roda, então `loops_consumidos` chegaria a 3 e o veredito **não** é
  aprovação nem reprovação simples — é o resumo de escalonamento.
- Dado uma reentrada apenas na etapa 5 (revisão de estilo, acabamento), quando o loop é
  contado, então `loops_consumidos` **não** incrementa.

## Testes obrigatórios

- Simular uma peça com violação mecânica clara (headline longa demais) e confirmar
  reprovação com apontamento específico e acionável.
- Simular 3 rodadas consecutivas de reprovação com reentrada na etapa 3 e confirmar que a
  terceira produz o resumo de escalonamento, não uma quarta tentativa automática.
- Simular uma reentrada de acabamento (etapa 5) e confirmar que `loops_consumidos` não muda.

## Gate — não avance para o Épico 7 até que:

- [ ] `revisor-final` aprova/reprova com critério rastreável a `formatos.md` §4.
- [ ] Loop de 3 tentativas testado, incluindo o caso de esgotamento sem aprovação automática.
- [ ] Distinção entre reentrada que consome loop (etapa 3) e a que não consome (etapas 4–6)
      testada.

## Boas práticas aplicadas

Decisão binária + apontamento acionável (evita ida-e-volta vaga entre revisor e redator);
nunca aprovar por conta própria ao esgotar tentativas (mesma regra do hemingway,
`MAX_LOOPS_REVISAO`); Conventional Commits (`feat(agentes): adiciona revisor-final e loop`).
