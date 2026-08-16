---
veredito: reprovado
loops_consumidos_recebido: 1
ponto_reentrada: "etapa_3"
---

# Veredito — post-cdb (etapa 7, segunda passagem)

Peça avaliada: `03-v3.md` (reentrada na etapa 3 a partir do loop 1/3, em resposta ao
apontamento bloqueante único de `07-veredito.md`, o `[VERIFICAR: ...]` bruto no parágrafo
"Terceiro"). `estado.json` recebido: `loops_consumidos: 1` — esta reprovação, ao reentrar na
etapa 3, consome o 2º dos 3 loops disponíveis (ainda não é a quarta tentativa; não escalona).

Reavaliação feita do zero contra todo o checklist (`formatos.md` §2.4/§4, `gary_halbert.md`
§3–4, direitos autorais/ética), não apenas verificação do apontamento anterior.

## 1. Checklist mecânico e de conteúdo (`formatos.md` §2.4 + §4)

- [x] **Limite mecânico do campo respeitado.** Linha de assunto "A confusão entre CDB e CDI
  (e por que ela existe)" — 49 caracteres, dentro do corte de ~50–60 em mobile
  (`formatos.md` §2.4). Sem limite mecânico relevante para o corpo (Substack).
- [x] **Abertura autossuficiente até o corte de preview.** A linha de assunto comunica o
  gancho sozinha; o primeiro parágrafo do corpo entra direto na confusão CDB/CDI (movimento
  Collier, `02-pesquisa.md` §1.2), sem abrir com definição institucional.
- [x] **Segmento/estágio de funil coerentes com `FUNIL.MD` §5.** `#GENZ-GREED` é segmento
  prioritário do estágio "curso gratuito (FVDT)". Resolução da ambiguidade rastreável a
  `02-pesquisa.md` §2.1, eixo mantido puro (nenhuma linguagem FEAR). CTA de fechamento
  (compartilhar/responder) é o correto para nutrição sem venda direta.
- [x] **Preço `[VERIFICAR]` não ancorado em número fechado.** Não se aplica — peça não
  menciona preço, corretamente (estágio de curso gratuito).
- [x] **Notação de processo não vaza para o texto publicável.** O apontamento bloqueante da
  rodada anterior — `[VERIFICAR: ...]` bruto no parágrafo "Terceiro" — foi corretamente
  resolvido. A v3 reescreve a ressalva em prosa autoral (linhas 140–144: "A leitura mais
  aceita para essa diferença é que dinheiro pulverizado... — mas essa razão específica não
  aparece declarada como tal no texto da norma; é a explicação que o mercado usa para
  entender o peso, não uma citação regulatória"), preservando integralmente a distinção entre
  dado confirmado (pesos 95%/90%, Circular BCB 3.869/2017) e leitura de mercado não
  confirmada. Nenhum colchete de metadado chega ao leitor. Este item passa.
- [ ] **Nenhum dado sem fonte rastreável apresentado como fato — e nenhum dado sourceado
  representado de forma incorreta.** Ver apontamento bloqueante abaixo — problema novo, não
  detectado na rodada anterior porque o escopo daquela reprovação era só o parágrafo
  "Terceiro". O restante da peça, incluindo o parágrafo "Primeiro" (compulsório), não havia
  sido reavaliado linha a linha contra `02-pesquisa.md`/a ideia-fonte até esta passagem.

## 2. Completude estrutural (`gary_halbert.md` §3–4)

- [x] Sales letter não se aplica (formato é `post_social`).
- [x] **PAS coerente**, com adaptação documentada (`02-pesquisa.md` §1.1, leitor
  product-aware/mechanism-naive): Problema (confusão CDB/CDI nomeada na abertura), Agitação
  sem catástrofe ("repetir a frase não é entender o produto"; explicadores/vídeos que pulam o
  mecanismo), Solução (cadeia regulatória completa). Ordem preservada, estrutura em H2 por
  movimento do argumento.
- [x] Objeção-mestra do segmento ("consigo aprender isso de graça no YouTube") endereçada
  implicitamente pelo contraste recorrente com "explicadores"/"vídeos e artigos" superficiais
  — consistente com `02-pesquisa.md` §1.5/§3.
- [~] **"Reason why" (Halbert §6).** A promessa central do parágrafo "Terceiro" — CDB como
  peça que ajuda o banco a cumprir métrica regulatória — depende de uma cadeia de três razões
  (compulsório, Basileia/LCR/NSFR, ALM). A primeira razão dessa cadeia (compulsório) está
  factualmente invertida no texto atual (ver apontamento abaixo), o que enfraquece a cadeia de
  "reason why" que sustenta todo o parágrafo "O que fica" — justamente o parágrafo que declara
  o compromisso de rigor da série. Não é falha de estrutura (a peça tem P-A-S e reason why
  como movimento), é falha de fidelidade do dado dentro da estrutura correta.

## 3. Direitos autorais e ética de promessa

- [x] Nenhuma frase citável de fonte protegida — pesquisa registra apenas movimentos
  estruturais (Collier, Schwartz), peça é redação original.
- [x] Nenhuma promessa de resultado que a Syntaxis não controla (`CONTEXT.md` §9) — peça é
  puramente educacional.
- [x] Urgência: não há, correto para este estágio/formato.

---

## Apontamento bloqueante (reprova a peça)

**Critério violado:** checklist §1 — dado tratado como fato ao leitor de forma que contradiz
a própria fonte que o pipeline levantou para sustentá-lo (`02-pesquisa.md` §2.2 e a
ideia-fonte, `_insumos/ideias/POST_CDB.md` linha 34). Não é dado inventado nem sem fonte — é
dado **sourceado, mas invertido** na hora de descrever onde o compulsório fica retido.

**Trecho (`03-v3.md`, linhas 125–128, seção "Por que o banco precisa do seu dinheiro" —
"Primeiro"):**

> "Primeiro, o compulsório: o Banco Central exige que os bancos deixem retida, **na própria
> instituição**, uma parcela do que captam — de conta corrente a poupança. O dinheiro
> 'parado' na sua conta, portanto, não está inteiramente disponível para o banco emprestar:
> parte dele está fora de alcance por regra, não por escolha do banco."

**O que a fonte de fato diz:**

- `02-pesquisa.md` §2.2, "Compulsório": "O Bacen exige que bancos retenham, **em conta no
  próprio Banco Central**, uma parcela dos recursos que captam..."
- `_insumos/ideias/POST_CDB.md`, linha 34 (o próprio material-fonte da ideia, que a pesquisa
  confirma): "Encaixe Compulsório: O Bacen exige que os bancos recolham compulsoriamente
  (**deixem retida em uma conta no Banco Central**) uma parcela de tudo o que captam."

**Por que isso reprova:** o mecanismo do recolhimento compulsório é justamente que o dinheiro
sai da instituição financeira e fica retido em conta no Banco Central — é isso que o torna
indisponível para o banco emprestar, sem depender de "escolha" ou política interna do banco.
O texto atual diz o oposto ("retida, na própria instituição"), o que descreve um mecanismo
diferente (retenção interna) e desalinha a peça da única fonte que a pesquisa levantou para
esse dado. Isso importa mais do que um deslize pontual porque:

1. É exatamente o tipo de erro que o parágrafo "O que fica" promete não cometer — a peça se
   posiciona contra "musiquinha, decoreba" e a favor de "entender o mecanismo por trás do
   número" (mecanismo "professor híbrido", `01-brief.md` §4); um erro de mecanismo regulatório
   no primeiro dos três pilares da "prova" central da peça mina esse posicionamento.
2. É a primeira das três razões da cadeia de "reason why" (compulsório → Basileia/LCR/NSFR →
   ALM) que sustenta a afirmação central do parágrafo "Terceiro" e do fechamento "O que fica"
   — um elo errado enfraquece a cadeia inteira, mesmo que os outros dois elos (Basileia,
   NSFR/Circular BCB 3.869/2017) estejam corretos e bem sourceados.
3. Ao contrário da ressalva do `[VERIFICAR]` anterior (que era sobre uma leitura causal não
   confirmada, corretamente sinalizada como tal), aqui não há sinalização nenhuma — o dado é
   apresentado como fato direto, sem ressalva, e a versão apresentada é a factualmente
   incorreta.

**O que a redação precisa decidir (etapa 3):** corrigir a direção do dado — o compulsório
fica retido em conta no Banco Central, não na própria instituição financeira — preservando o
raciocínio que o parágrafo já constrói (o dinheiro "parado" na conta do cliente não está
livre para o banco emprestar, por regra e não por escolha). Não é uma decisão de peso
persuasivo como a da rodada anterior — é correção factual direta, sem trade-off de força
argumentativa; não deveria alterar o restante do parágrafo nem os parágrafos seguintes
("Segundo", "Terceiro"), que não dependem dessa localização para fazer sentido.

**Ponto de reentrada: etapa 3.** (Defeito de redação — dado mal representado apresentado como
fato; não é resíduo de acabamento de linha, é conteúdo.)

---

## Pendência externa (não é o motivo desta reprovação — segue registrada para o gate humano)

`estado.json.pendencias` mantém: relação entre isca paga (R$ 9,90) e curso gratuito ainda
`[VERIFICAR — MARKETING.md §13.2]` (`FUNIL.MD` §3.1). `FUNIL.MD` §3.1 cogita um recorte do
case CDB como possível formato da própria isca paga — se essa decisão for tomada pelo founder
antes da publicação, vale checar sobreposição de conteúdo entre a isca e este post. Esta
pendência não depende de reescrita e não bloqueia nenhuma rodada desta peça; segue para o gate
humano (etapa 8) independentemente de quando a peça for reaprovada.
