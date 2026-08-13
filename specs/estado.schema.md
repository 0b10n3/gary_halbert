# Schema de `estado.json`

Um `estado.json` por execução do pipeline, em `output/<formato>/<slug>/estado.json`. Criado
na etapa 0, atualizado a cada etapa subsequente, commitado junto com a saída de cada etapa
(ver `CLAUDE.md` §Git). É o que permite retomar uma execução interrompida sem refazer
trabalho já feito.

## Campos

| Campo | Tipo | Valores possíveis | Escrito em |
|---|---|---|---|
| `etapa_atual` | integer | `0`–`8` (ver tabela de etapas em `CLAUDE.md`) | toda etapa, ao concluir |
| `formato` | string | `"sales_letter"` \| `"post_social"` \| `"meta_ads"` | etapa 0, imutável depois |
| `plataforma` | string \| null | `"linkedin"` \| `"substack"` \| `"instagram"` \| `"youtube"` \| `null` | etapa 0, imutável depois. `null` sempre que `formato != "post_social"` |
| `loops_consumidos` | integer | `0`–`3` | etapa 7, só quando a reentrada de reprovação for na etapa 3 (ver `epico-06`) |
| `aprovacoes` | array de string | histórico de decisões do gate humano (ex.: `"etapa8:ajustar:2026-08-12"`) | etapa 8, a cada passagem pelo gate |
| `pendencias` | array de string | apontamentos abertos ainda não resolvidos (ex.: itens `[VERIFICAR]` da peça) | qualquer etapa que identifique uma pendência não resolvida |
| `commit_inicial` | string | sha curto de `main` no momento da criação da branch `copy/<slug>` | etapa 0, imutável depois |

## Exemplo

```json
{
  "etapa_atual": 3,
  "formato": "post_social",
  "plataforma": "instagram",
  "loops_consumidos": 1,
  "aprovacoes": [],
  "pendencias": ["preço da isca marcado [VERIFICAR] — PRICE_TAG.md ainda não validado"],
  "commit_inicial": "a1b2c3d"
}
```

## Regras de escrita

- Nunca decrementar `etapa_atual` fora do fluxo de reentrada do gate humano (etapa 8) ou do
  `revisor-final` (etapa 7) — retomada normal só avança.
- `loops_consumidos` é a única contagem que trava o pipeline (máx. 3, ver `CLAUDE.md`
  §Regras invioláveis) — nenhum outro campo deste schema implementa lógica de limite.
- Ao aprovar na etapa 8, o arquivo permanece no histórico da branch mergeada — não é apagado
  nem resetado; é o registro de como a peça chegou à versão final.
