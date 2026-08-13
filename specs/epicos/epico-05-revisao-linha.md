# ÉPICO 5 — Subagentes de revisão de linha: gramática e estilo

**Depende de:** Épico 4
**Entrada:** `03-vN.md`, skill `estilo-syntaxis`,
`../../SyntaxisSubstack/hemingway/.claude/agents/revisor-gramatical.md` (referência direta)

## Objetivo

Ter `revisor-gramatical` e `revisor-estilo` produzindo diffs comentados sobre uma versão de
copy, sem tocar em estrutura — a mesma fronteira que o hemingway já validou em produção.

## Escopo

- `.claude/agents/revisor-gramatical.md`: adaptação do agente homônimo do hemingway. Mesma
  fronteira (norma culta pt-BR: crase, regência, vírgula em oração reduzida, sigla,
  itálico/aspas em estrangeirismo financeiro — duration, hedge, spread) e mesmo formato de
  saída (diff comentado, classificado `norma` ou `linha`). Diferença real em relação ao
  original: **não reabre nem questiona estrutura de venda** (headline/CTA/oferta) — se
  encontrar algo estrutural, sinaliza separadamente para `revisor-final`, não corrige.
- `.claude/agents/revisor-estilo.md`: carrega `estilo-syntaxis`, confirma que a peça soa como
  a voz Syntaxis (não confundir escolha deliberada de voz com erro — mesma distinção que
  `revisor-gramatical` do hemingway já documenta) **adaptada ao registro de copy** — uma
  sales letter pode ser mais direta/persuasiva que um post de Substack sem deixar de ser a
  mesma voz; a skill `estilo-syntaxis` deve orientar essa adaptação de registro, não just
  bloquear qualquer desvio do tom editorial.
- Saída de cada um: `04-revisao-gramatical.md` e `05-revisao-estilo.md`, diff comentado,
  agrupado por parágrafo/bloco na ordem em que aparecem na peça.

## Fora de escopo

Aplicação das correções (isso é a etapa 6, "Consolidação", feita pelo principal — Épico 7).
Veredito de aprovação/reprovação (Épico 6).

## Critérios de aceite

- Dado `03-v1.md` de uma sales letter, quando `revisor-gramatical` roda, então o diff não
  contém nenhuma alteração de estrutura (headline, ordem de seção, oferta) — só norma/linha.
- Dado uma peça com escolha deliberada de voz (frase fragmentada como ênfase, por exemplo),
  quando `revisor-gramatical` roda, então essa escolha não é "corrigida" — mesmo teste que o
  hemingway já valida.
- Dado `03-v1.md` de um post para LinkedIn (registro mais direto que um ensaio de Substack),
  quando `revisor-estilo` roda, então a peça não é sinalizada como "fora da voz" só por ser
  mais direta — a skill distingue registro de desvio real.

## Testes obrigatórios

- Rodar os dois subagentes sobre as 3 peças de teste do Épico 4 e conferir que nenhum diff
  altera estrutura.
- Teste de falso positivo: inserir deliberadamente uma escolha de voz (ex.: frase curta de
  ênfase) em uma peça de teste e confirmar que nem `revisor-gramatical` nem `revisor-estilo`
  a sinalizam como erro.
- Teste de verdadeiro positivo: inserir um erro real de crase/regência e confirmar que
  `revisor-gramatical` o pega e classifica corretamente.

## Gate — não avance para o Épico 6 até que:

- [ ] Ambos os subagentes produzem diff comentado, sem tocar estrutura, para as 3 peças de
      teste.
- [ ] Teste de falso positivo (voz deliberada) passa para ambos.
- [ ] Teste de verdadeiro positivo (erro real) passa para `revisor-gramatical`.

## Boas práticas aplicadas

Reaproveitamento de agente já validado em produção (hemingway) em vez de reescrever do zero;
fronteira clara entre camadas de revisão (estrutura vs. linha vs. norma) evita que uma etapa
desfaça o trabalho da anterior; Conventional Commits
(`feat(agentes): adiciona revisor-gramatical e revisor-estilo`).
