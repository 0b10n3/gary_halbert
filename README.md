# gary_halbert

Pipeline de agentes e skills do Claude Code que transforma uma ideia bruta de copy em uma
peça de marketing revisada (gramática e estilo) e aprovada por um humano, para um dos
formatos: **sales letter**, **post de rede social** (LinkedIn, Substack, Instagram ou
YouTube) ou **Meta Ads**.

Irmão do pipeline editorial [`hemingway`](../../SyntaxisSubstack/hemingway) (Substack) —
reaproveita a mesma skill de voz autoral e o mesmo padrão de orquestração (skill principal +
subagentes de trabalho isolado + gate humano obrigatório).

## Como rodar

```
/copy-gary-halbert --ideia <caminho-em-_insumos/ideias/> --formato <formato> [--plataforma <plataforma>]
```

```
--formato = sales_letter | post_social | meta_ads
--plataforma = linkedin | substack | instagram | youtube   (obrigatório só se --formato=post_social)
```

Retoma automaticamente uma execução interrompida se invocado de novo com o mesmo slug de
ideia. Detalhes completos da arquitetura, das 9 etapas do pipeline e das regras invioláveis:
ver [`CLAUDE.md`](./CLAUDE.md).

## Status

Em implementação — ver [`specs/epicos/`](./specs/epicos/) para o roteiro de épicos e
[`PROMPT_IMPLEMENTACAO.md`](./PROMPT_IMPLEMENTACAO.md) para o prompt de continuação.

- [x] Épico 1 — Fundação (estrutura, `estado.json`, convenção de Git)
- [x] Épico 2 — Skills de referência (estilo, formatos, pesquisa)
- [x] Épico 3 — Subagentes de coleta e pesquisa
- [x] Épico 4 — Subagente de redação
- [x] Épico 5 — Subagentes de revisão de linha
- [ ] Épico 6 — Revisão final e loop
- [ ] Épico 7 — Orquestração e gate humano
- [ ] Épico 8 — QA e piloto real

## Estrutura

```
CLAUDE.md                      arquitetura completa do pipeline
README.md                      este arquivo
PROMPT_IMPLEMENTACAO.md        prompt de partida para implementar os épicos
specs/
  estado.schema.md             schema de estado.json
  epicos/                      especificação + testes, um arquivo por épico
output/<formato>/<slug>/       entregáveis e processo de cada execução (gerado em runtime)
.claude/skills/                skill orquestradora + skills de referência (em implementação)
.claude/agents/                subagentes de trabalho isolado (em implementação)
```

Insumos compartilhados com o resto do ecossistema Syntaxis (não duplicados aqui, sempre
referenciados por caminho relativo): `../../_insumos/`, `../../AUDIENCES.md`,
`../../FEAR.md`, `../../GREED.md`, `../../FUNIL.MD`, `../../MARKETING.md`,
`../../SYNTAXIS.md`, `../../SyntaxisEducation/PRICE_TAG.md`,
`../../SyntaxisSubstack/hemingway/estilo/`.
