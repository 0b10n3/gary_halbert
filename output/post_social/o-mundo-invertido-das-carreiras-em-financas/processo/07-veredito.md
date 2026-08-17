---
veredito: aprovado
loops_consumidos_recebido: 0
ponto_reentrada: null
---

# 07 — Veredito (revisão final)

Peça avaliada: `03-v2.md` (post_social / LinkedIn, segmento `#GENZ-FEAR`, estágio "curso
gratuito ao vivo FVDT" — `FUNIL.MD` §3.2). Primeira passagem pela etapa 7, `loops_consumidos`
recebido em `estado.json` = 0.

## 1. Checklist mecânico e de conteúdo (`formatos.md` §2.1 + §4)

- [x] **Limite mecânico do campo respeitado.** Corpo da peça (excluindo frontmatter e nota de
  processo em HTML comment, que são removidos antes de publicar) tem ~2.050 caracteres —
  dentro do limite de 3.000 do LinkedIn, e dentro da faixa geral de melhor engajamento
  (1.300–2.500; a subfaixa "narrativa pessoal" de 1.200–1.800 é levemente ultrapassada, mas é
  recomendação de melhor prática, não limite mecânico — não é critério de reprovação).
- [x] **Abertura autossuficiente até o corte de preview.** Até ~140 caracteres (corte mobile)
  a peça já entrega o gancho completo: "Eu sabia derivar o modelo inteiro. [...] pediam pra
  provar, eu provava. O que eu não sabia faz[er]..." — contraste que funciona sozinho, sem
  depender do texto atrás do "ver mais". Até ~210 caracteres (corte desktop), o gancho já
  nomeia o registro técnico (dissertação de mestrado, precificação de opções), reforçando a
  autoridade sem precisar do resto do texto. Critério de "Atenção" do AIDA satisfeito na
  abertura isolada.
- [x] **Segmento/estágio de funil coerentes com `FUNIL.MD` §5.** `#GENZ-FEAR` é segmento
  prioritário do estágio "curso gratuito FVDT" (`FUNIL.MD` §5, linha 2), sem divergência —
  confirmado também em `01-brief.md`. O uso de LinkedIn como canal está calibrado ao papel
  correto (`FUNIL.MD` §4: canal secundário de credibilidade para Gen Z, não de conversão
  direta) — a nota de processo do redator já registra essa calibração explicitamente, e a
  peça não se comporta como se fosse peça de conversão primária (sem promessa de volume de
  inscrição, sem otimização agressiva de CTA único).
- [x] **Preço `[VERIFICAR]` não ancorado em número fechado.** Não se aplica — o curso é
  gratuito e confirmado em `PRICE_TAG.md` (status "Confirmado"), nenhuma menção de preço na
  peça.
- [x] **Nenhum dado sem fonte rastreável.** A única alegação factual externa (estrutura de
  capítulos de *Options, Futures, and Other Derivatives*, de John Hull — juros/preço a termo
  nos capítulos 4–6, opções no capítulo 10) é uma referência de estrutura de livro-texto real
  e verificável, tratada como "reason why" (`gary_halbert.md` §6), não como estatística de
  mercado. Nenhum percentual ou número de segmento foi inventado — `02-pesquisa.md` registra
  explicitamente que nenhuma estatística nova foi usada além do que já está em
  `AUDIENCES.md` §3.3, e que a lacuna de evidência (quantos estagiários vivem essa situação)
  foi deliberadamente **não** preenchida com número inventado.

## 2. Completude estrutural (`gary_halbert.md` §3–4)

Post curto → critério aplicável é PAS, não as seis partes de sales letter (§10, não se
aplica a este formato).

- [x] **Problema:** aprender fora de ordem (ponta complexa antes do alicerce) — nomeado nos
  parágrafos 3–4.
- [x] **Agitação, sem catástrofe:** parágrafos 5–7 mostram que o problema é comum (Hull, mesa
  de risco) e reafirmam "não é vergonha" antes de qualquer convite — segue à risca o
  anti-padrão a evitar de `AUDIENCES.md` §5 para `#GENZ-FEAR` (medo sem saída imediata não
  ocorre aqui: a saída é explicitada antes do CTA, não só embutida nele).
- [x] **Solução:** parágrafo 8, curso gratuito FVDT, com CTA de cadastro.

AIDA como checklist complementar: Atenção (abertura, ver §1 acima) → Interesse (a
generalização "isso tem nome, não é falha pessoal" dá razão para continuar) → Desejo
(construído com prova — citação nomeada e verificável, não afirmação vazia) → Ação (CTA único
e sem ambiguidade: "Cadastro aqui"). Ordem respeitada, todas as partes presentes.

## 3. Direitos autorais e ética de promessa

- [x] **Nenhuma frase citável de fonte protegida.** A referência a Hull extrai estrutura/dado
  (ordem de capítulos), não frase do livro — conforme a regra de `pesquisa-direct-response`.
- [x] **Nenhuma promessa de resultado fora do controle da Syntaxis.** A peça não promete
  salário, promoção ou vaga — oferece apenas o curso e a oportunidade de preencher a lacuna
  (`CONTEXT.md` §9 respeitado; já confirmado independentemente em `05-revisao-estilo.md`).
- [x] **Urgência real.** A data de início (setembro) é fato confirmado (`PRICE_TAG.md`,
  status "Confirmado"), sem contagem regressiva nem escassez artificial — `02-pesquisa.md` já
  registrou explicitamente que não há justificativa para inserir urgência fabricada aqui.

## Pendência externa — destacada para o gate humano (etapa 8)

**Link de cadastro do curso FVDT ainda não existe.** O corpo da peça traz
`[VERIFICAR: URL de cadastro do curso FVDT]` no lugar do link real (parágrafo 8). Isso não é
defeito de redação — reescrever o texto não cria a URL, que depende de o founder disponibilizar
o formulário de inscrição do FVDT. A peça já trata essa pendência corretamente (marca
explicitamente `[VERIFICAR]`, não inventa nem finge um link). **Recomendação para a etapa 8:**
decidir entre (a) aprovar e arquivar `final.md` aguardando a URL antes de publicar, ou (b)
publicar só depois que o link existir — mas o texto em si não precisa de nova iteração por
causa disso.

## Observações não bloqueantes (não exigem nova iteração)

Duas sugestões de registro ficaram documentadas em `04-revisao-gramatical.md` e
`05-revisao-estilo.md` como classificação `linha`/sugestão (não `norma`, não inegociável) e
não foram aplicadas na consolidação (`03-v2.md`), por decisão explícita registrada na nota de
processo do próprio arquivo:
- Gloss ausente em "derivativos"/"preço a termo" (itens de lista ilustrativa) — `04`.
- Fecho "Conta aí embaixo" poderia ser mais específico ("Me conta onde: [...]") — `05`.

Nenhuma das duas viola critério de aprovação (mecânico, estrutural ou ético) — não geram
reprovação. Ficam registradas aqui apenas para visibilidade do gate humano, caso prefira
pedir o ajuste antes de publicar; não é exigência deste veredito.

## Conclusão

Todos os itens do checklist de `formatos.md` §4, da completude estrutural PAS/AIDA de
`gary_halbert.md` §3–4 e dos critérios de direitos autorais/ética de promessa foram
verificados e aprovados. **Veredito: aprovado**, com a pendência do link de cadastro
destacada acima para decisão da etapa 8.
