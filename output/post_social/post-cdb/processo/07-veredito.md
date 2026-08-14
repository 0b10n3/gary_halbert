---
veredito: reprovado
loops_consumidos_recebido: 0
ponto_reentrada: "etapa_3"
---

# Veredito — post-cdb (etapa 7, primeira passagem)

Peça avaliada: `03-v2.md` (consolidação da etapa 6, base `03-v1.md` + diffs de
`04-revisao-gramatical.md` e `05-revisao-estilo.md`). `estado.json` recebido:
`loops_consumidos: 0` — esta reprovação, ao reentrar na etapa 3, consome o 1º dos 3 loops
disponíveis.

## 1. Checklist mecânico e de conteúdo (`formatos.md` §2.4 + §4)

- [x] **Limite mecânico do campo respeitado.** Único limite mecânico real do Substack é a
  linha de assunto (~50–60 caracteres antes de truncar em mobile — `formatos.md` §2.4).
  "A confusão entre CDB e CDI (e por que ela existe)" tem 49 caracteres — dentro do limite,
  tratada com o rigor de headline pedido pela spec.
- [x] **Abertura autossuficiente até o corte de preview.** A linha de assunto comunica o
  gancho sozinha (confusão nomeada, sem depender do corpo). O primeiro parágrafo do corpo
  também entra direto na confusão CDB/CDI (movimento Collier, conforme `02-pesquisa.md`
  §1.2), sem abrir com definição institucional — coerente com o anti-padrão mapeado em
  `02-pesquisa.md` §3.
- [x] **Segmento/estágio de funil coerentes com `FUNIL.MD` §5.** `#GENZ-GREED` é segmento
  prioritário do estágio "curso gratuito (FVDT)" (`FUNIL.MD` §5). A ambiguidade registrada em
  `01-brief.md` §2 e `estado.json.pendencias` foi resolvida com justificativa rastreável
  (`02-pesquisa.md` §2.1) e o eixo GREED foi mantido puro — nenhuma linguagem FEAR
  ("ficar para trás") entrou no texto. CTA de fechamento (compartilhar/responder) é o CTA
  correto para nutrição sem venda direta (`FUNIL.MD` §4/§6).
- [x] **Preço `[VERIFICAR]` não ancorado em número fechado.** Não se aplica — peça não
  menciona preço, corretamente (estágio de curso gratuito, `01-brief.md` §6).
- [ ] **Nenhum dado sem fonte rastreável apresentado como fato final ao leitor.** Ver
  apontamento bloqueante abaixo — o problema não é dado inventado (todo número tem fonte
  rastreada em `02-pesquisa.md` §2.2), é a forma como uma ressalva de fonte foi deixada no
  corpo publicável.

## 2. Completude estrutural (`gary_halbert.md` §3–4, via `pesquisa-direct-response`)

- [x] Sales letter não se aplica (formato é `post_social`).
- [x] **PAS coerente**, com adaptação documentada e legítima: `02-pesquisa.md` §1.1 justifica
  pular a etapa de "provar que o problema existe" porque o leitor é *product-aware,
  mechanism-naive* (Schwartz) — o texto ainda assim tem Problema (confusão CDB/CDI nomeada),
  Agitação sem catástrofe (repetir a frase não é entender o produto; a maioria dos
  explicadores/vídeos pula o mecanismo) e Solução (a cadeia regulatória completa, do
  compulsório ao NSFR). Estrutura em H2 por movimento do argumento, sem quebra de ordem.
- [x] Objeção-mestra do segmento (`AUDIENCES.md` §3.4: "consigo aprender isso de graça no
  YouTube") endereçada implicitamente pelo contraste recorrente com "explicadores"/"vídeos e
  artigos" que não vão a fundo no mecanismo — consistente com o anti-padrão mapeado em
  `02-pesquisa.md` §1.5/§3 (saturação de conteúdo definicional raso).

## 3. Direitos autorais e ética de promessa

- [x] Nenhuma frase citável de fonte protegida — pesquisa registra apenas *movimentos*
  estruturais (Collier, Schwartz), nunca frase pronta; peça é redação original.
- [x] Nenhuma promessa de resultado que a Syntaxis não controla (`CONTEXT.md` §9) — peça é
  puramente educacional, sem promessa de efetivação/salário/promoção.
- [x] Urgência: não há urgência na peça (correto para este estágio/formato — não se aplica).

---

## Apontamento bloqueante (reprova a peça)

**Critério violado:** checklist §1, item "nenhum dado sem fonte rastreável" — mais
precisamente, a forma como uma ressalva de fonte não confirmada foi tratada no corpo que irá
para `final.md`.

**Trecho (`03-v2.md`, linhas 119–129, seção "Por que o banco precisa do seu dinheiro" —
"Terceiro"):**

> "Depósitos de varejo com prazo acima de um ano chegam a peso de 95%; mesmo os de prazo mais
> curto ficam em 90% (Circular BCB 3.869/2017). **[VERIFICAR: a leitura mais comum para essa
> ponderação diferenciada — a de que o varejo pulverizado corre menos risco de gerar uma
> corrida bancária, um saque em massa simultâneo — é uma inferência de mercado plausível, mas
> não foi localizado texto regulatório que declare essa razão explicitamente; tratar como
> hipótese razoável, não como citação regulatória confirmada.]** Na prática, isso significa
> que o seu CDB não é só uma forma de o banco te pagar juros..."

**Por que isso reprova:** o dado em si (peso 95%/90%, Circular BCB 3.869/2017) está
corretamente sourceado em `02-pesquisa.md` §2.2 — isso não é o problema. O problema é que a
peça deixou a anotação de processo `[VERIFICAR: ...]` **dentro do texto que vai para
`final.md` e será lido por assinantes do Substack**. `[VERIFICAR: ...]` é convenção de
rascunho/laudo interno (`CONTEXT.md` §9, `CLAUDE.md`: "vira `[VERIFICAR: ...]` **no
rascunho**") — em nenhum lugar do pipeline essa notação é definida como algo publicável. Um
leitor final não deve ver colchetes de anotação editorial no meio de um parágrafo. A cautela
epistêmica em si está certa e deve ser preservada (a explicação causal da corrida bancária
não tem fonte regulatória confirmada e não pode virar afirmação de fato) — é a **forma**, não
o **conteúdo**, que precisa ser reescrita.

Nota: `04-revisao-gramatical.md` e `05-revisao-estilo.md` já passaram por este trecho e
ambos, corretamente dentro do escopo de cada um (norma culta / registro de estilo), não o
tratam como erro deles — `05-revisao-estilo.md` inclusive registra "o redator já sinalizou
corretamente com `[VERIFICAR]` a parte não confirmada" como observação não-bloqueante. Do
ponto de vista de cada revisor isolado, o julgamento é correto (não é erro de gramática nem
de registro de voz). É a etapa 7, com visão de publicação, que precisa capturar que a notação
de processo não pode chegar ao leitor — por isso o apontamento aparece aqui, não antes.

**O que a redação precisa decidir (etapa 3, não é ajuste de linha):** como o `[VERIFICAR]`
altera se a explicação causal é ou não apresentada ao leitor — e isso é uma decisão de peso
argumentativo (este é o parágrafo mais denso em prova numérica da peça, central ao
posicionamento GREED de "rigor/evidência" — `02-pesquisa.md` §2.1), não uma troca mecânica de
palavra — a opção final cabe ao `redator-copy`, entre (pelo menos) duas saídas equivalentes:

1. Reescrever a ressalva em voz autoral natural, sem colchetes, preservando a distinção entre
   o dado confirmado (pesos e Circular BCB) e a leitura causal não confirmada (ex.: algo como
   "uma leitura comum é que o varejo pulverizado corre menos risco de gerar corrida bancária —
   embora essa razão específica não apareça declarada em texto regulatório, é a explicação
   mais aceita para o porquê do peso diferenciado"); ou
2. Remover a explicação causal não confirmada do corpo e manter só o dado sourceado (pesos
   95%/90%, Circular BCB 3.869/2017), deixando a "prova" mais enxuta mas 100% verificável sem
   qualquer ressalva necessária.

Qualquer uma resolve o defeito — a escolha entre elas afeta a força persuasiva do parágrafo
central de "prova" da peça, por isso a reentrada é etapa 3 (redação), não etapas 4–6
(acabamento).

**Ponto de reentrada: etapa 3.**

---

## Pendência externa (não bloqueia esta reprovação, mas deve seguir junto da peça)

`estado.json.pendencias` registra: relação entre isca paga (R$ 9,90) e curso gratuito ainda
`[VERIFICAR — MARKETING.md §13.2]` (`FUNIL.MD` §3.1). `01-brief.md` §6 já registrou que isso
não bloqueia esta peça especificamente (nutrição do curso gratuito, não a isca) — mas
`FUNIL.MD` §3.1 cogita um recorte do case CDB como possível formato da própria isca paga. Se
essa decisão for tomada pelo founder no meio-tempo, pode haver sobreposição de conteúdo entre
a isca e este post que vale checar antes de publicar. Esta pendência não depende de
reescrita — segue registrada para o gate humano (etapa 8), independentemente de quando esta
peça for reaprovada.
