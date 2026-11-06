# ÉPICO 8 — QA e piloto real

**Depende de:** Épico 7 (pipeline completo funcionando com ideias de teste sintéticas)
**Entrada:** uma ideia real do founder, ainda não publicada

## Objetivo

Validar o pipeline com uma ideia real (não fictícia), ponta a ponta, e usar o resultado do
gate humano para calibrar as skills/subagentes antes de considerar o pipeline pronto para uso
recorrente.

## Escopo

- Rodar `/copy-gary-halbert` com uma ideia real de copy do founder, para o formato que ele
  priorizar (provavelmente a isca paga ou o FVDT, dado o estágio atual do funil —
  ver `../../../../strategy/FUNIL.md` §5).
- Acompanhar o founder no gate humano (etapa 8) real — não simulado.
- Se o founder pedir ajuste: deixar o loop rodar normalmente (não pular etapas "para agilizar
  o piloto") — o objetivo do piloto é justamente testar o loop sob uso real.
- Registrar no `changelog.md` da execução o que precisou de ajuste e por quê — esse
  changelog vira o primeiro dado real para calibrar `formatos.md`/`gary_halbert.md` se algum
  critério se mostrar errado na prática (ex.: limite de caracteres que a plataforma mudou
  desde a pesquisa do Épico 2, ou tom que o revisor-estilo classificou errado).
- Ao aprovar, a peça entra em `_insumos/exemplos_aprovados/<formato>/` conforme a convenção
  já documentada em `exemplos_aprovados/README.md`.
- Pós-piloto: revisão conjunta com o founder do que funcionou/não funcionou no pipeline em
  si (não só na peça) — decidir se algum subagente precisa de ajuste antes do próximo uso.

## Fora de escopo

Qualquer mudança estrutural grande no pipeline (isso viraria um novo épico, não um ajuste de
piloto). Publicação real da peça em qualquer plataforma externa — o pipeline entrega o texto
aprovado; publicar no LinkedIn/Meta/Hotmart/etc. é ação manual do founder, fora do escopo
deste repositório.

## Critérios de aceite

- Dado uma ideia real do founder, quando o pipeline completo roda, então chega à etapa 8 com
  uma peça que o founder considera pelo menos "editável" (não precisa ser aprovada de
  primeira — precisa ser útil o suficiente para editar em vez de descartar).
- Dado que o founder aprova (com ou sem ajustes), quando a execução conclui, então a peça
  está em `_insumos/exemplos_aprovados/<formato>/` com o frontmatter correto.
- Dado qualquer atrito real encontrado (limite de plataforma errado, tom fora do esperado,
  dado que deveria estar em `[VERIFICAR]` e não estava), quando o piloto termina, então esse
  atrito está documentado (no `changelog.md` da execução ou em nota separada) para virar
  correção nos insumos.

## Testes obrigatórios

- Execução real, não simulada — o "teste" deste épico é o uso genuíno pelo founder.
- Conferir, após aprovação, que o frontmatter da peça em `exemplos_aprovados/` bate com o
  schema de `exemplos_aprovados/README.md`.
- Conferir que a branch `copy/<slug>` foi mergeada em `main` e a ideia moveu para
  `_insumos/ideias/processadas/`.

## Gate — pipeline considerado pronto para uso recorrente quando:

- [ ] Uma execução real (não sintética) completou até aprovação ou abandono deliberado.
- [ ] Qualquer atrito encontrado está documentado e, se aplicável, corrigido nos insumos
      (`formatos.md`, `gary_halbert.md`, `CONTEXT.md`).
- [ ] O founder confirma que usaria o pipeline de novo para a próxima peça sem supervisão
      extra além do gate humano padrão.

## Boas práticas aplicadas

Piloto com dado real antes de declarar "pronto" (nenhum teste sintético substitui uso real);
loop de aprendizado fechado — atrito do piloto retroalimenta os insumos, não fica só como
nota perdida na conversa.
