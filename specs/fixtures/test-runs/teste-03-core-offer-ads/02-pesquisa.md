# 02-pesquisa.md

> Material de pesquisa para `redator-copy` (etapa 3). Não é copy pronta — nenhuma frase
> abaixo deve ser usada literalmente na peça; o que se entrega aqui é movimento estrutural,
> dado com fonte, e alerta de saturação de mercado.

## Decisão de segmento (pendência herdada de `01-brief.md`)

O brief registra uma divergência real e não a resolve — corretamente, porque não há dado de
audiência real (composição etária da lista de retargeting) disponível a nenhum subagente
deste pipeline. Como pesquisador, preciso de um segmento de trabalho para orientar ganchos e
estruturas; decido o seguinte, e registro a decisão em vez de tratar a ambiguidade como
resolvida:

**Segmento de trabalho adotado: `#Millennials-GREED`.**

Razões:

1. **`FUNIL.MD` §3.3 reserva `#Millennials-*` para o core offer como escolha estratégica de
   encaixe oferta↔mensagem** ("é onde a promessa 'recuperar terreno'/'top da distribuição'
   faz mais sentido de oferta"), não como estimativa de quem está fisicamente na lista de
   retargeting. Essa é uma decisão de arquitetura de funil já tomada; a origem do público
   (`FUNIL.MD` §3.2, "GenZ é o público mais alcançável organicamente" **no estágio do curso
   gratuito**) descreve alcance de aquisição, não a composição definitiva de quem permanece
   engajado até o retargeting de conversão.
2. **A linguagem da própria ideia** ("já provou pra si mesmo", "quer o pacote completo")
   casa lexicalmente com o gatilho de `#Millennials-GREED` — "colheita: já plantou, quer o
   retorno agora" (`AUDIENCES.md` §3.2) — e não com `#GENZ-FEAR` ("estabilidade") nem
   `#GENZ-GREED` ("prova rápida e mensurável", `AUDIENCES.md` §3.4). Um retargeting de
   most-aware (ver seção 1 abaixo) tende a refletir a intenção que o próprio criador da ideia
   já leu no comportamento do público (assistiu, não converteu, quer mais) — dado subjetivo,
   mas é o único sinal de intenção disponível além da inferência demográfica.
3. **Risco de misturar eixos é maior que o risco de errar geração.** `AUDIENCES.md` §6 exige
   eixo puro (não misturar FEAR/GREED no mesmo bloco); não há regra equivalente proibindo que
   uma peça `#Millennials-GREED` seja lida por um espectador GenZ sem dano severo, desde que a
   peça evite gírias/referências geracionalmente marcadas e ancore o tom em **estágio de
   carreira** (analista pleno/sênior, já tem repertório — `AUDIENCES.md` §3.1/§3.2, "não
   infantilizar") em vez de idade explícita.

**O que isto não faz:** não resolve a pendência. `estado.json.pendencias` deve manter o item
1 do brief aberto — esta é uma hipótese de trabalho para permitir que a pesquisa e a redação
avancem, sujeita a correção se o founder confirmar composição etária real da lista antes da
etapa 8. `redator-copy` deve tratar `#Millennials-GREED` como *default editável*, não como
segmento fechado, e evitar qualquer referência que dependa de a audiência ser
inequivocamente Millennial (ex.: menção a "anos de carreira" específicos).

**Fonte interna consultada e confirmada vazia:** `_insumos/exemplos_aprovados/` contém
apenas `README.md` (nenhuma peça aprovada ainda) — não há precedente interno de
`#Millennials-GREED` em Meta Ads para conferir. Ver seção 1 para o que isso implica.

---

## 1. Ganchos/estruturas correlatas

Nenhuma peça aprovada existe em `_insumos/exemplos_aprovados/meta_ads/` (pasta contém só o
`README.md` de convenção — confirmado por listagem direta). Sem precedente interno, a
calibração de estrutura vem inteiramente do cânone (`_insumos/gary_halbert.md`, via skill
`pesquisa-direct-response`) e de leitura de posicionamento de mercado
(`_insumos/fontes_pesquisa.md` §2 / `MARKETING.md` §4). Nenhuma frase abaixo é citação —
apenas o movimento estrutural.

- **Estágio de consciência = most-aware, não problem-aware.** Eugene Schwartz, via
  `gary_halbert.md` §9: quem já assistiu lives da FVDT sem se inscrever já conhece o
  problema, a solução genérica e o produto — não precisa de introdução ao tema "renda fixa"
  nem de explicar o que é a Syntaxis. O movimento correto é pular direto para "por que a
  trilha paga, por que agora", não reabrir a promessa do curso gratuito. Isso também resolve
  uma tensão de formato: `_insumos/formatos.md` §3 recomenda que os 125 primeiros caracteres
  do texto principal carreguem "o gancho do segmento" — para most-aware, esse gancho pode
  assumir conhecimento prévio (ex.: referência direta a "o que você viu nas lives"), o que
  economiza caracteres para o "reason why" da oferta.
- **PAS invertido para GREED** (`gary_halbert.md` §4): em vez de nomear um problema a
  agitar, o movimento é nomear a prova que o leitor já deu a si mesmo (assistiu, entendeu,
  ficou) e tornar tangível a lacuna entre "ainda assistindo de fora" e "ter o pacote
  completo" — sem catastrofizar a não-compra (regra `AUDIENCES.md` §5 contra medo sem saída,
  que também vale por analogia a não fabricar urgência artificial num eixo GREED).
- **Reason why concreto** (`gary_halbert.md` §6): a oferta já tem três "reason why" nomeados
  no brief — notas de aula, AI Skills, guias de case — que são o material correto para
  ancorar a promessa "pacote completo" em algo verificável, em vez de adjetivo. Isso também
  atende `MARKETING.md` §4 (mecanismo único #3: "AI-First como competência entregável, não
  marketing de IA").
- **Bônus/estrutura de oferta empilhada** (Dan Kennedy, via `gary_halbert.md` §9): útil para
  apresentar os componentes do pacote (notas + AI Skills + guias de case) como unidades
  discretas de valor, não como descrição solta — sem inventar bônus que não estão no brief.
- **"Duas portas"** (`gary_halbert.md` §7): como o segmento de trabalho é uma hipótese (ver
  seção acima), a persona a escrever é ainda mais específica do que o padrão — a pessoa que
  já assistiu, tomou nota, e está adiando a decisão por hesitação de investimento (não por
  desconhecimento). Isso é distinto da persona "de carrinho abandonado por preço" — mecanismo
  de hesitação é diferente e deve orientar o "reason why" acima, não um desconto.

## 2. Dados de mercado

`FEAR.md`/`GREED.md` já cobrem os dados-âncora de `#Millennials-GREED` (topo da distribuição,
prêmio salarial de IA, ambições declaradas — `GREED.md` §3) e os ângulos de copy já derivados
deles (`GREED.md` §6) — não repetidos aqui por instrução do `pesquisador-copy`. O que segue é
material adicional, fora do que o brief já cobre:

- **Compliance Meta Ads — conteúdo financeiro (obrigatório checar antes da redação final,
  por `_insumos/formatos.md` §3):** consultei a Central de Transparência oficial da Meta
  (fonte primária, conforme recomendado por `_insumos/fontes_pesquisa.md` §3) —
  https://transparency.meta.com/policies/ad-standards/restricted-goods-services/financial-services/
  (acesso 12/08/2026). Achados:
  - Cursos e treinamento financeiro **são explicitamente permitidos** e não se enquadram nas
    restrições aplicadas a produtos financeiros reais (empréstimos, corretagem, opções
    binárias, ICOs, etc.) — a peça deste teste (curso pago sobre renda fixa, sem venda de
    produto de investimento) está na categoria permitida.
  - A política proíbe conteúdo enganoso sobre resultado financeiro — nenhuma promessa de
    retorno/rendimento pode ser implícita na copy. Isso reforça (não substitui) a regra já
    existente em `AUDIENCES.md` §5 contra dado sem fonte e contra promessa que a Syntaxis não
    controla.
  - `[VERIFICAR: exigência de licença/verificação de identidade para anunciante de educação
    financeira]` — a busca (WebFetch em transparency.meta.com, complementada por
    stackmatix.com, auditsocials.com e roaspig.com, acesso 12/08/2026) não trouxe menção
    explícita de que cursos (diferente de corretoras/gestoras) precisem de licença
    regulatória para anunciar no Meta Ads. Os agregadores descrevem a exigência de licença
    como aplicável a quem vende o produto financeiro em si, não a quem ensina sobre ele — mas
    nenhuma fonte tratou esse caso especificamente. Recomendo checagem manual da conta de Ads
    Manager Syntaxis antes de publicar (a política pode variar por sinalização automática de
    palavras-chave como "renda fixa", "investimento").
- **Leitura de posicionamento de concorrentes/parceiros mapeados** (`fontes_pesquisa.md` §2 +
  `MARKETING.md` §4, mercado direto já mapeado): busca rápida sobre Toro Academy/Rafael Toro
  (WebSearch, acesso 12/08/2026) confirma que a oferta paga do maior concorrente de
  posicionamento próximo (renda fixa/mercado de capitais BR) é majoritariamente enquadrada
  como **preparatório de certificação** (CFA, CFG/ANBIMA) — ver seção 3 abaixo para a
  implicação de ângulo.

## 3. O que evitar

- **Ângulo de "preparatório de certificação"** já está ocupado pelo concorrente de
  posicionamento mais próximo (Toro Academy/Rafael Toro — preparatórios CFA e CFG/ANBIMA,
  confirmado por busca direta, seção 2). A Syntaxis já tem mecanismo diferenciado documentado
  (`MARKETING.md` §4: professor híbrido, case brasileiro real, IA como competência
  entregável) — a peça deve ancorar nesse mecanismo, não competir em "prepare para a prova X",
  que não é a promessa do pacote "Profissional de Renda Fixa".
- **Não reabrir a promessa do curso gratuito.** Como o público é most-aware (seção 1), repetir
  "aprenda os fundamentos" ou reexplicar por que renda fixa importa desperdiça os 125
  caracteres críticos do texto principal (`formatos.md` §3) — esse erro é comum em retargeting
  malfeito (trata o lead requentado como tráfego frio).
- **Não ancorar preço fechado.** Pendência 2 do brief (`PRICE_TAG.md`, faixa R$700–1.200 não
  validada) — usar enquadramento de valor/ROI, não número, conforme já determinado no brief.
- **Não assumir geração de forma explícita na copy.** Dada a decisão de segmento de trabalho
  (`#Millennials-GREED`, não confirmada — ver seção acima), evitar qualquer marcador etário
  explícito ("para quem já tem 10 anos de carreira", gíria geracionalmente codificada) que
  quebre a peça caso a lista de retargeting seja, na prática, mais GenZ do que a hipótese
  assume. Ancorar em estágio de carreira e comportamento (já assistiu, já entendeu, hesita em
  investir), não em idade.
- **Não prometer retorno/rendimento financeiro**, mesmo implicitamente — bloqueio de política
  Meta (seção 2), não só de estilo Syntaxis.
