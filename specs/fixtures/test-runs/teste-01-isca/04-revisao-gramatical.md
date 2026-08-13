# Revisão gramatical — teste-01-isca / 03-v1.md

Revisão de linha (`linha`) e de norma culta pt-BR (`norma`), na ordem em que os trechos
aparecem na peça. Fixture de teste — nenhuma execução real do pipeline, apenas o subagente
`revisor-gramatical` aplicado a `03-v1.md`.

Não mexi em headline, oferta, CTA, garantia ou urgência como elementos estruturais — só em
gramática e clareza de frase dentro desses blocos, quando havia erro objetivo ou ambiguidade
sintática. Nenhuma correção abaixo altera a promessa, o preço, o mecanismo, o prazo ou a
reversão de risco já decididos na etapa 3.

---

## Bloco 1 — Lead ("Você já sabe qual vai ser a pergunta")

**Original:**
> ...que todo currículo de finanças promete que você conhece. CDB (Certificado de Depósito
> Bancário) e LCI (Letra de Crédito Imobiliário). E a pergunta não é "você sabe a diferença".

**Sugerido:**
> ...que todo currículo de finanças promete que você conhece: CDB (Certificado de Depósito
> Bancário) e LCI (Letra de Crédito Imobiliário). E a pergunta não é "você sabe a diferença".

**Motivo (`linha`):** o fragmento "CDB (...) e LCI (...)." depois de ponto final lê como um
corte solto — não é o fragmento de efeito/uma palavra que a voz do autor usa deliberadamente
(`estilo-autoral.md` regra 4 nota; `estilo-syntaxis` §"voz vs. registro"), é uma aposição
definicional que o próprio guia recomenda articular com dois-pontos (regra 3). Trocar o ponto
por dois-pontos une as duas frases sem alterar nenhuma palavra de conteúdo. Sugestão, não
obrigatória.

---

**Original:**
> ...você consegue *dizer* essa diferença, em voz alta, sem gaguejar...

**Sugerido:**
> ...você consegue dizer essa diferença, em voz alta, sem gaguejar...
> (ou, se a ênfase for necessária: 'dizer')

**Motivo (`linha`):** itálico de ênfase de frase é antipadrão confirmado do autor —
`estilo-autoral.md` regra 4: "Nunca usa negrito ou itálico de ênfase — aspas simples fazem
esse trabalho." Isso não é a exceção de "ausência sistemática de itálico é voz, não lacuna"
(`revisor-gramatical.md` §"A distinção mais importante") — aqui o itálico foi *adicionado*,
o que é o antipadrão inverso. Mesma correção se aplica a "*por que*" duas seções abaixo.

---

## Bloco 2 — "O que separa quem sabe de quem parece saber"

**Original:**
> O que separa é conseguir explicar *por que* essa diferença existe, com um caso real na mão...

**Sugerido:**
> O que separa é conseguir explicar por que essa diferença existe, com um caso real na mão...

**Motivo (`linha`):** mesmo antipadrão do Bloco 1 (itálico de ênfase, regra 4 de
`estilo-autoral.md`).

---

**Original:**
> É um caso brasileiro: a tensão entre CVM (Comissão de Valores Mobiliários) e CMN (Conselho
> Monetário Nacional) — os dois órgãos que decidem, cada um do seu jeito, como esses produtos
> são regulados no Brasil — e por que essa tensão institucional é a razão real da diferença
> entre os dois produtos, não só um detalhe de prova.

**Sugerido:**
> É um caso brasileiro: a tensão entre CVM (Comissão de Valores Mobiliários) e CMN (Conselho
> Monetário Nacional) — os dois órgãos que decidem, cada um do seu jeito, como esses produtos
> são regulados no Brasil. É essa tensão institucional que explica a razão real da diferença
> entre os dois produtos — não só um detalhe de prova.

**Motivo (`linha`):** depois do travessão de fechamento, o "e" coordena um sintagma nominal
("a tensão entre CVM e CMN") com uma oração ("por que essa tensão... é a razão real"), que não
são paralelos — a frase original não tem verbo principal claro para o segundo membro. Copy é
lida em segundos, não relida (foco explícito do revisor-gramatical): separar em duas frases
resolve a ambiguidade sintática sem tocar no conteúdo (mesmo caso, mesma razão institucional
citada).

---

## Bloco 3 — "Vinte minutos, uma primeira vitória"

**Original:**
> No fim, você tem uma resposta articulada para uma das perguntas mais comuns de entrevista
> técnica júnior em finanças, com o "porquê" institucional que a maioria de quem decorou
> tabela não tem.

**Sugerido:**
> No fim, você tem uma resposta articulada para uma das perguntas mais comuns de entrevista
> técnica de nível júnior em finanças, com o 'porquê' institucional que a maioria de quem
> decorou a tabela não tem.

**Motivos:**
- `linha` — "entrevista técnica júnior em finanças" empilha três modificadores em sequência e
  pode ser lido como se "júnior" qualificasse "técnica"; "de nível júnior" desfaz a
  ambiguidade sem mudar o que a oferta promete.
- `norma` — aspas duplas em `"porquê"` deveriam ser aspas simples: o corpus do autor usa aspas
  simples, nunca duplas, para marcar um termo isolado (`estilo-autoral.md` regra 4, exemplo
  `'internamente homogêneo'`). A grafia "porquê" (junto) em si está correta — é substantivo
  aqui, não interrogativa — só a marcação de aspas precisa mudar.
- `linha` (opcional) — "decorou tabela" sem artigo é elipse aceitável em registro coloquial,
  mas "decorou a tabela" lê mais limpo em voz alta; sugestão de menor prioridade.

---

## Bloco 4 — "Isso não espera o calendário te avisar"

**Original:**
> Processo seletivo de estágio e trainee não avisa com antecedência longa.

**Sugerido:**
> Processo seletivo de estágio e 'trainee' não avisa com antecedência longa.

**Motivo (`norma`):** estrangeirismo isolado sem marcação. O foco de norma deste revisor
inclui explicitamente "itálico/aspas em estrangeirismo... o corpus do autor usa aspas simples
em vez de itálico" (`revisor-gramatical.md` §"Focos específicos"). "Trainee" é o único
estrangeirismo solto na peça e está sem aspas simples nem itálico.

---

**Original:**
> Se você já está se candidatando, ou vai começar essa semana, o momento de montar essa
> resposta é antes da entrevista chegar — não depois.

**Sugerido:**
> Se você já está se candidatando ou vai começar essa semana, o momento de montar essa
> resposta é antes da entrevista chegar — não depois.

**Motivo (`norma`):** vírgula indevida separando as duas alternativas verbais coordenadas por
"ou" dentro da mesma oração condicional ("se está se candidatando ou vai começar"); a vírgula
que resta antes de "o momento..." já marca o fim da subordinada — não precisa de uma segunda
vírgula no meio dela.

---

## Fora de escopo — para `revisor-final`

Nenhuma observação estrutural fora de escopo identificada nesta revisão. Headline, lead,
oferta, garantia (reversão de risco em vez de garantia formal — já justificada e documentada
na nota de processo do próprio `03-v1.md`), urgência e CTA foram lidos apenas para checar
gramática interna a eles, e nenhum problema de completude ou de persuasão estrutural chamou
atenção que já não estivesse sinalizado pelo `redator-copy` na nota de processo (bloqueio
`[VERIFICAR]` da relação isca↔curso gratuito, formato de entrega `[VERIFICAR]`).

---

## Resumo

| # | Bloco | Classificação | Item |
|---|---|---|---|
| 1 | Lead | linha | fragmento "CDB e LCI." → unir com dois-pontos |
| 2 | Lead | linha | itálico de ênfase em *dizer* |
| 3 | Subtítulo 1 | linha | itálico de ênfase em *por que* |
| 4 | Subtítulo 1 | linha | coordenação NP+oração desbalanceada (CVM/CMN) |
| 5 | Subtítulo 2 | linha | "entrevista técnica júnior em finanças" ambíguo |
| 6 | Subtítulo 2 | norma | aspas duplas → simples em 'porquê' |
| 7 | Subtítulo 2 | linha (opcional) | "decorou tabela" → "decorou a tabela" |
| 8 | Subtítulo 3 | norma | "trainee" sem marcação de estrangeirismo |
| 9 | Subtítulo 3 | norma | vírgula indevida antes de "ou" na condicional |

Total: 9 apontamentos (4 `norma`, 5 `linha`, sendo 1 destas de prioridade opcional). Zero
observações estruturais fora de escopo.
