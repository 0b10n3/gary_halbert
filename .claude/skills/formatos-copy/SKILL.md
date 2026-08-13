---
name: formatos-copy
description: Especificação técnica por formato/plataforma de copy — limites mecânicos, estrutura esperada, ponto de corte de preview. Use ao escrever (redator-copy) ou avaliar (revisor-final) qualquer peça, para saber a estrutura e os limites exatos do formato/plataforma declarados em --formato/--plataforma.
---

A especificação completa vive em `../../../../../_insumos/formatos.md` — este `SKILL.md` não
repete os números, só indexa qual seção usar para cada combinação de `--formato`/
`--plataforma`. **Leia a seção inteira do formato em uso antes de escrever ou avaliar uma
peça** — limite mecânico errado gera peça cortada ou anúncio rejeitado, não é detalhe menor.

## Índice por flag

| `--formato` | `--plataforma` | Seção de `formatos.md` |
|---|---|---|
| `sales_letter` | (não aplicável) | §1 |
| `post_social` | `linkedin` | §2.1 |
| `post_social` | `instagram` | §2.2 |
| `post_social` | `youtube` | §2.3 |
| `post_social` | `substack` | §2.4 |
| `meta_ads` | (não aplicável) | §3 |

## Como usar em cada papel do pipeline

- **`redator-copy` (etapa 3):** escreva já dentro do limite mecânico da seção — não é
  ajuste de revisão, é restrição de primeira versão. Preste atenção especial ao "corte de
  preview" de cada formato (ex.: 125 caracteres no Instagram, ~210 no LinkedIn desktop): a
  abertura da peça precisa funcionar sozinha até esse ponto.
- **`revisor-final` (etapa 7):** use o checklist de `formatos.md` §4 como critério objetivo
  de aprovação/reprovação — é a mesma lista para qualquer formato, os números específicos
  vêm da seção indexada acima.

## Nota de confiabilidade dos números

`formatos.md` documenta a data e a natureza das fontes (agregadores de terceiros, não
documentação oficial de plataforma — ver `formatos.md`, cabeçalho). Para qualquer decisão de
Meta Ads com orçamento relevante, sinalize ao usuário que vale reconfirmar o limite mecânico
na documentação oficial antes de publicar — a skill não faz essa reconfirmação sozinha.
