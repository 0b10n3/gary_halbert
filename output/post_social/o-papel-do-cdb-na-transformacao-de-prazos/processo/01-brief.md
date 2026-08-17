# 01 — Brief (coleta de contexto)

## Ideia central em uma frase

O CDB não é "produto de investimento com nome estranho": é o instrumento pelo qual o banco
faz "transformação de maturidade" (termo do próprio Bacen) — capta a prazo curto e transforma
em crédito de prazo longo — e a remuneração que o investidor recebe é o preço que o banco paga
por essa transformação, não um número arbitrário.

Fonte de conteúdo: `../../../../SyntaxisSubstack/hemingway/posts/2026-08-14-o-papel-do-cdb-na-transformacao-de-prazos/post.md`
(status **rascunho**, ainda não revisado/aprovado pelo pipeline `hemingway` — usar como base
de argumento, não copiar trecho a trecho; números e citações regulatórias (Bacen, CVM, Lei
4.728/1965, Resoluções CMN, Circular BC nº 3.869/2017) são atribuídos às fontes primárias já
citadas no post-fonte, não tratados como fato fechado do rascunho em si).

## Segmento declarado

Não há um único segmento inequívoco em `AUDIENCES.md` para este conteúdo — é uma peça
educacional pura (autoridade técnica), não uma peça de conversão direcionada a um perfil de
carreira específico. Registro como ambiguidade a resolver, não decisão fechada:

- **Melhor encaixe:** `#Millennials-FEAR` — o gancho (banco não é livre para usar o dinheiro
  do CDB; a remuneração é o preço de uma função regulatória, não sorte de produto) fala a um
  público que já investe e teme estar tomando decisão "genérica"/rasa sem entender o mecanismo
  por trás — condiz com a objeção-mestra de `AUDIENCES.md` §3.1 ("já é tarde para me
  especializar" → aqui, "estou investindo sem entender o que estou comprando"). Este é
  também o segmento prioritário do **core offer** (`FUNIL.MD` §5), que é o estágio mais
  compatível com conteúdo técnico denso de renda fixa (ver seção seguinte).
- **Alternativa descartada:** `#GENZ-*` — tecnicamente é o segmento prioritário do canal
  LinkedIn no estágio de isca/curso gratuito (`FUNIL.MD` §5), mas `FUNIL.MD` §4 já marca
  LinkedIn como **canal secundário** de aquisição para Gen Z (26% de uso vs. YouTube 80%/
  Instagram 73%) — usar Gen Z como segmento nesta peça específica (LinkedIn, conteúdo técnico
  regulatório denso) seria forçar um encaixe que o próprio `FUNIL.MD` desaconselha.
- **Eixo:** FEAR (custo de não entender o mecanismo por trás do produto que já se possui),
  não GREED — não há gatilho de "retorno"/"colheita" no conteúdo-fonte, é puramente
  explicativo/técnico.

**Pendência para o gate humano (etapa 8) ou correção antes disso:** confirmar se
`#Millennials-FEAR` é aceitável para uma peça de LinkedIn cujo canal prioritário (`FUNIL.MD`
§4) hoje é B2B/credibilidade, não aquisição de Millennials-FEAR especificamente (esse
segmento está mapeado ao core offer, não a um canal). Ver seção "Estágio do funil" abaixo
para o motivo dessa tensão.

## Estágio do funil

**Não há estágio de funil limpo para esta peça.** O post-fonte é conteúdo educacional puro
("Notas de um Professor", primeira nota de série) e **não tem CTA comercial** — não menciona
isca, curso gratuito, core offer nem mentoria. Isso não se encaixa diretamente em nenhum dos
quatro estágios de `FUNIL.MD` §2 como oferta ativa. Registrando como pendência explícita, não
forçando estágio:

- **Leitura mais defensável:** peça de **construção de autoridade/topo de funil**, adjacente
  ao papel do LinkedIn descrito em `FUNIL.MD` §4 ("canal secundário de credibilidade/parcerias
  B2B, não tráfego de topo") — ou seja, o próprio canal já é atípico para este pipeline
  (nenhum estágio do funil lista LinkedIn como canal primário).
  - Se a leitura for "autoridade pura sem CTA de conversão": não há segmento prioritário
    correspondente em `FUNIL.MD` §5, porque §5 mapeia estágios de oferta, e esta peça não é
    de nenhuma oferta.
  - Se a leitura for "isca de conteúdo para o curso gratuito FVDT" (Fundamentos do Valor do
    Dinheiro no Tempo, §3.2): o segmento prioritário citado em `FUNIL.MD` §5 seria
    `#GENZ-FEAR`/`#GENZ-GREED`, o que **diverge** do segmento sugerido acima
    (`#Millennials-FEAR`) — sinalizando, não decidindo.
- **CTA:** conforme a própria ideia-fonte instrui, não inventar oferta/produto/preço. CTA
  sugerido de baixo risco: convite para acompanhar a próxima nota da série ("Notas de um
  Professor") — não é CTA de conversão comercial, é CTA de retenção de audiência/série.
  `redator-copy` deve tratar isso como a opção padrão até o gate humano decidir diferente.

**Resumo da divergência a levar ao gate humano (etapa 8):** ideia-fonte sugere segmento
Millennials/conteúdo técnico avançado; `FUNIL.MD` mapeia LinkedIn e conteúdo de topo/série
educacional mais perto do público Gen Z do curso gratuito. Este brief não resolve — apenas
documenta os dois caminhos possíveis para `pesquisador-copy` e `redator-copy` decidirem com
critério, e para o humano confirmar na aprovação final.

## Mecanismo

Dos três diferenciais de `CONTEXT.md` §3, a peça prova o **#2 — case brasileiro real (tensão
institucional CVM/CMN)**: o argumento inteiro depende de regulação brasileira concreta
(compulsório Bacen, LCR/NSFR via CMN, Circular BC 3.869/2017, definição CVM sob a Lei
4.728/1965), não de teoria genérica de renda fixa traduzida de fora. Secundariamente, toca o
diferencial **#1 — professor híbrido**: o enquadramento "Notas de um Professor" e o uso de
fonte primária regulatória (Relatório de Estabilidade Financeira do Bacen) é a assinatura de
quem ensina com rigor acadêmico aplicado ao mercado real, não "guru de resultado". O
diferencial #3 (IA como competência entregável) não aparece no conteúdo-fonte e não deve ser
forçado nesta peça.

## Restrições de formato/plataforma

Peça é `post_social` / `linkedin` — especificação mecânica e melhores práticas de plataforma
estão em `../../../../_insumos/formatos.md` §2.1 (LinkedIn), dentro de §2 (Post de rede
social). `formatos-copy` resolve os detalhes na etapa 3; este brief só aponta a seção.
Observação herdada da ideia-fonte, relevante para escopo (não é restrição mecânica, é de
conteúdo): o post-fonte é denso e técnico (renda fixa, regulação bancária) — para o formato
curto de LinkedIn, o gancho do compulsório (21% vs. 20%) e a ideia de "transformação de
maturidade" devem ser o fio condutor; não tentar caber CDB vs. CDI, LCR/NSFR e os três casos
de uso por prazo/indexador no mesmo post curto.

## Pendências

1. **Segmento ambíguo** — `#Millennials-FEAR` (melhor encaixe pelo conteúdo) vs.
   `#GENZ-FEAR`/`#GENZ-GREED` (segmento prioritário do canal/estágio mais próximos em
   `FUNIL.MD` §5) não resolvidos por este brief; decisão para `pesquisador-copy`/
   `redator-copy` com critério documentado, ou gate humano (etapa 8).
2. **Estágio do funil indefinido** — post-fonte não tem CTA comercial; nenhum dos quatro
   estágios de `FUNIL.MD` §2 se aplica sem forçar leitura. Tratar como peça de
   autoridade/topo de funil sem CTA de conversão, com CTA leve de "próxima nota da série"
   como padrão, sujeito a confirmação humana.
3. **Post-fonte em status "rascunho"** — ainda não passou pelo pipeline `hemingway`; números e
   citações regulatórias devem ser tratados como atribuídos às fontes primárias citadas no
   próprio post-fonte (Bacen, CVM, CMN), não como fato fechado do rascunho.
4. **Formato de entrega da isca paga** (`FUNIL.MD` §3.1) e **relação isca↔curso gratuito**
   (`FUNIL.MD` §3.1) seguem `[VERIFICAR]` — irrelevantes para esta peça específica (sem CTA
   comercial), mas registrados aqui porque a pendência de estágio do funil (item 2) poderia,
   em tese, reabrir essa dependência se o gate humano decidir transformar esta peça em isca
   para o curso gratuito.
5. **Preço:** não se aplica — post-fonte não menciona preço/oferta, e a ideia-fonte instrui
   explicitamente não inventar oferta/produto/preço nesta peça. Nenhuma consulta a
   `PRICE_TAG.md` necessária além desta constatação.
