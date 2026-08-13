# 01-brief.md

## Ideia central

Anúncio de retargeting (Meta Ads) para quem assistiu ao menos uma live do curso gratuito
FVDT mas ainda não se inscreveu em nenhuma oferta paga — oferecendo a trilha "Renda Fixa —
Títulos Públicos e Privados" como o próximo passo natural, para quem já provou a si mesmo
(nas lives) que acompanha o nível técnico e agora quer o pacote completo (notas de aula, AI
Skills, guias de case).

## Segmento declarado

**Pendência — não decidido sozinho, ver seção "Pendências".** A ideia não especifica geração
nem eixo emocional do público de retargeting. Há uma divergência real entre duas leituras
possíveis de `AUDIENCES.md`:

- Pelo **estágio do funil** (core offer), o segmento prioritário é `#Millennials-FEAR` ou
  `#Millennials-GREED` (`FUNIL.MD` §5). A linguagem da ideia — "já provou pra si mesmo",
  "quer o pacote completo" — casa com o gatilho de `#Millennials-GREED` ("colheita: já
  plantou, quer o retorno agora", `AUDIENCES.md` §3.2).
- Mas a **origem real do público de retargeting** é quem assistiu ao FVDT, cujo segmento
  prioritário no estágio "curso gratuito" é `#GENZ-*` (`FUNIL.MD` §3.2 e §5) — ou seja, a
  audiência que efetivamente existe nas listas de retargeting pode ser majoritariamente
  GenZ, não Millennial.

Candidato de trabalho, se for preciso seguir adiante sem resolver a pendência:
`#Millennials-GREED` (mecanismo de "colheita" mais próximo do texto da ideia) — mas isso é
uma hipótese, não uma declaração definitiva. `pesquisador-copy` e `redator-copy` não devem
tratar este segmento como fechado.

## Estágio do funil

**Core offer — Pacote "Profissional de Renda Fixa"**, trilha "Renda Fixa — Títulos Públicos
e Privados" (`FUNIL.MD` §2 e §3.3). Segmento prioritário deste estágio, para conferência:
`#Millennials-FEAR` / `#Millennials-GREED` (`FUNIL.MD` §5) — ver divergência acima.

O canal (Ads pagos de retargeting para quem assistiu lives sem se inscrever) está
explicitamente autorizado por `FUNIL.MD` §4, item 4(a): "retargeting de quem assistiu
lives/visitou a lista sem se inscrever" é um dos dois únicos usos aprovados de mídia paga.

## Mecanismo

**Mecanismo 3 — IA como competência entregável** (`CONTEXT.md` §3, item 3): a ideia cita
explicitamente "AI Skills" como parte do pacote que diferencia a trilha paga do curso
gratuito. É o mecanismo mais direto para esta peça provar, junto com "notas de aula" e
"guias de case" como prova de completude da oferta.

## Restrições de formato/plataforma

Formato: **Meta Ads** — ver `_insumos/formatos.md` §3 ("Meta Ads (Facebook + Instagram)"),
resolvido em detalhe pela skill `formatos-copy` na etapa 3. Plataforma não se aplica (Meta
Ads não usa `--plataforma`, que é exclusivo de `post_social`).

## Pendências

1. **Segmento não declarável com segurança** (ver seção acima) — a ideia não informa se o
   público de retargeting é predominantemente Millennial ou GenZ, nem qual eixo (FEAR/GREED)
   predomina. Precisa de decisão humana ou de dado de audiência real (ex.: faixa etária dos
   inscritos na lista de retargeting) antes da redação final. Registrar em
   `estado.json.pendencias`.
2. **Preço da trilha "Renda Fixa" está `[VERIFICAR]`** — `PRICE_TAG.md` marca a trilha
   individual em R$700–1.200, faixa "a validar", não confirmada pelo founder. Por
   `PRICE_TAG.md` ("Notas de uso em copy"), copy de venda direta (Meta Ads de conversão) não
   deve ancorar em número fechado enquanto isso não for resolvido — usar enquadramento de
   valor/ROI. Registrar em `estado.json.pendencias`.
