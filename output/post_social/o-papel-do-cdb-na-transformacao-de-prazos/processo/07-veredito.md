---
veredito: aprovado
loops_consumidos_recebido: 0
ponto_reentrada: null
---

# 07 — Veredito (revisão final, etapa 7)

Peça avaliada: `03-v2.md` (post_social / LinkedIn, v2 — consolidação dos apontamentos `norma`
de `04-revisao-gramatical.md`). Primeira passagem pela etapa 7 (`loops_consumidos` recebido =
0; não há `07-veredito.md` anterior a reconciliar).

## 1. Checklist mecânico e de conteúdo (`formatos.md` §4, via `formatos-copy`)

- [x] **Limite mecânico do campo respeitado.** LinkedIn permite até 3.000 caracteres
  (`formatos.md` §2.1). O corpo da peça (sem frontmatter/notas do redator) tem ~280 palavras,
  estimativa de ~1.650–1.750 caracteres — dentro do limite mecânico e dentro da faixa de
  melhor engajamento (1.300–2.500 caracteres).
- [x] **Abertura autossuficiente até o corte de preview.** Corte desktop ~210 caracteres,
  mobile ~140. O parágrafo 1 sozinho ("O dinheiro na sua conta corrente está disponível a
  qualquer momento. Você pode sacar agora, sem aviso prévio, sem prazo.", 120 caracteres) já
  fecha uma ideia completa e cria tensão (implícito: "e o banco?"); o corte desktop (~210
  caracteres) inclui ainda a primeira frase do parágrafo 2, que nomeia o contraste ("O banco
  não tem essa liberdade sobre o mesmo saldo."). A peça funciona sozinha antes do "ver mais"
  em ambos os cortes, sem depender do restante do texto.
- [~] **Segmento/estágio de funil coerentes com `FUNIL.MD` §5** — ver pendência externa #1 e
  #2 abaixo. Não é defeito de redação: o brief (`01-brief.md`) já documentou a ambiguidade
  antes da redação, e a peça trata o segmento e o estágio exatamente como hipóteses de
  trabalho não fechadas (frontmatter explícito: "hipótese de trabalho, não fechada"), sem
  fingir uma resolução que não existe. `redator-copy` seguiu o padrão que o brief instruiu
  como default. Confirmado contra `FUNIL.MD` §4–5: LinkedIn é canal secundário
  (credibilidade/B2B), nenhum dos quatro estágios do funil mapeia CTA comercial para
  conteúdo puramente educacional — a tensão é real e pré-existente, não fabricada pela
  redação.
- [x] **Preço `[VERIFICAR]` não ancorado em número fechado.** Não se aplica — a peça não
  menciona preço, oferta ou produto comercial algum (instrução explícita da ideia-fonte e do
  brief, `01-brief.md` §Pendências item 5). Nenhuma violação possível porque não há preço na
  peça.
- [~] **Nenhum dado sem fonte rastreável** — ver pendência externa #3 abaixo. Os números
  citados (compulsório 21%/20%, "transformação de maturidade" como termo do Bacen, Relatório
  de Estabilidade Financeira) são atribuídos por nome à fonte primária (Bacen) dentro do
  próprio texto — cumprem a regra de "reason why"/citação de fonte nomeada
  (`gary_halbert.md` §6). A rastreabilidade final desses números depende do post-fonte do
  pipeline `hemingway`, que ainda está em status "rascunho" — isso é documentado como
  pendência no brief (`01-brief.md` §Pendências item 3) e não é algo que a redação desta
  peça resolve reescrevendo.

## 2. Completude estrutural (`gary_halbert.md` §3–4, via `pesquisa-direct-response`)

Peça curta, formato PAS (não AIDA/sales letter — `formatos.md` §1 e §10 de `gary_halbert.md`
não se aplicam a `post_social`):

- [x] **Problema:** o leitor acha que está comprando "uma taxa" quando na verdade não entende
  o que o CDB é — estabelecido nos parágrafos 1–4 (contraste liquidez do correntista vs.
  compulsório do banco).
- [x] **Agitação (sem catástrofe):** "A diferença parece pequena. Não é." — reformula o CDB
  como "o preço que o banco paga" por uma função regulatória, não uma vantagem casual.
  Nenhuma linguagem de urgência ou perda catastrófica; consistente com o anti-padrão de
  `AUDIENCES.md` §5 contra medo sem saída.
- [x] **Solução (reveal do mecanismo):** parágrafos 5–6 nomeiam o mecanismo
  ("transformação de maturidade", termo do Bacen) e reenquadram a remuneração do CDB como
  preço de uma função, não número arbitrário — entrega a promessa do brief
  (`01-brief.md` §Ideia central).
- [x] **Ação:** CTA único, sem ambiguidade — "Acompanhe" a próxima nota da série. Coerente
  com a decisão documentada no brief de não forçar CTA comercial numa peça sem oferta.

## 3. Direitos autorais e ética de promessa

- [x] **Nenhuma frase citável de fonte protegida.** Não há uso do cânone de copywriting
  (Halbert, Schwartz, Hopkins, Collier, Carlton, Kennedy) nem de concorrente mapeado nesta
  peça — os dados citados são fatos regulatórios de fonte pública (Bacen), não conteúdo
  autoral de terceiros.
- [x] **Nenhuma promessa de resultado que a Syntaxis não controla** (`CONTEXT.md` §9). A peça
  é puramente explicativa; não há projeção de ganho, salário, promoção ou retorno. Confirmado
  também em `05-revisao-estilo.md` §6.
- [x] **Urgência, se houver, é real.** Não há elemento de urgência/escassez na peça — N/A.

## Consolidação dos laudos 04/05

Os 3 apontamentos `norma` de `04-revisao-gramatical.md` (gloss de "Bacen", "no Relatório de
Estabilidade Financeira" com artigo definido, gloss de "CDI" no CTA) foram aplicados em v2 —
confirmado por leitura direta de `03-v2.md`. Os 4 apontamentos `linha` de 04 e o único
apontamento de registro (você/te, §6) de `05-revisao-estilo.md` não foram aplicados — ambos
são sugestões explicitamente marcadas como opcionais pelos próprios laudos, não erros de
norma nem de voz. Não geram reprovação.

## Pendências externas — destacadas para o gate humano (etapa 8)

Nenhuma das três pendências abaixo é resolvível reescrevendo a peça: dependem de decisão do
founder ou do avanço de outro pipeline. A peça já as trata corretamente (documenta a
ambiguidade em vez de fingir resolução).

1. **Segmento não fechado.** `#Millennials-FEAR` (melhor encaixe pelo conteúdo técnico, e
   segmento prioritário do core offer — `FUNIL.MD` §5) vs. `#GENZ-FEAR`/`#GENZ-GREED`
   (segmento prioritário do canal LinkedIn nos estágios de isca/curso gratuito, também
   `FUNIL.MD` §5). `FUNIL.MD` §4 já marca LinkedIn como canal secundário — nenhum dos dois
   segmentos se encaixa sem alguma tensão. O gate humano precisa decidir se aceita
   `#Millennials-FEAR` como está ou pede reescrita para `#GENZ-*`.
2. **Estágio do funil indefinido.** Post-fonte é conteúdo educacional puro, sem CTA
   comercial; nenhum dos quatro estágios de `FUNIL.MD` §2 se aplica sem forçar leitura. A
   peça usa CTA leve de "acompanhe a próxima nota da série" em vez de CTA de conversão — essa
   é a opção padrão que o brief autorizou até decisão humana em contrário.
3. **Post-fonte em status "rascunho".** O post que serviu de base
   (`SyntaxisSubstack/hemingway/posts/2026-08-14-o-papel-do-cdb-na-transformacao-de-prazos/post.md`)
   ainda não foi aprovado pelo pipeline `hemingway`. Os dados regulatórios citados nesta peça
   (compulsório 21%/20%, termo "transformação de maturidade", Relatório de Estabilidade
   Financeira) são atribuídos às fontes primárias já citadas no post-fonte, mas a
   confiabilidade final desses números só se confirma quando o post-fonte passar pela própria
   revisão do `hemingway`. Recomendação: não publicar esta peça antes de o post-fonte sair de
   "rascunho", ou publicar com a ressalva explícita de que os números aguardam confirmação —
   decisão do gate humano.
4. (Herdada, hoje sem impacto direto): formato de entrega da isca paga e relação
   isca↔curso gratuito (`FUNIL.MD` §3.1) seguem `[VERIFICAR]`. Só voltam a ser relevantes se
   o gate humano decidir reposicionar esta peça como isca — não é o caso na leitura atual da
   peça (sem CTA comercial).

## Veredito

**Aprovado.** Nenhum defeito corrigível pela redação foi identificado: limite mecânico
respeitado, abertura autossuficiente até o corte de preview, estrutura PAS completa e na
ordem certa, nenhuma promessa fora de controle da Syntaxis, nenhuma urgência fabricada,
nenhuma frase de fonte protegida. As três pendências acima são externas ao trabalho de
redação (decisão do founder sobre segmento/estágio; avanço do post-fonte no pipeline
`hemingway`) e já estão corretamente sinalizadas na peça e no processo — seguem destacadas
para a etapa 8 decidir se publica, adia ou arquiva a versão aprovada.
