# Prompt de implementação — pipeline `gary_halbert`

> Use este arquivo como prompt de partida para a sessão (ou sessões) de Claude Code que vai
> implementar o pipeline. Cole o conteúdo abaixo da linha `---` diretamente no Claude Code,
> rodando a partir da raiz deste repositório (`pipelines/gary_halbert/`). Pode ser
> uma sessão por épico ou uma sessão contínua que avança épico a épico — ambos funcionam,
> desde que cada épico só comece depois do Gate do anterior estar marcado.

---

Implemente o pipeline de copy Syntaxis descrito em `CLAUDE.md` (leia primeiro, é a fonte da
arquitetura completa: 9 etapas, 6 subagentes, 3 skills de referência, convenção de Git e
estado).

**Ordem de implementação:** siga `specs/epicos/epico-01-fundacao.md` até
`epico-08-qa-piloto.md`, nessa ordem — cada um declara suas dependências, escopo, critérios
de aceite no formato Dado/Quando/Então, testes obrigatórios e um Gate que precisa estar
100% checado antes de avançar para o próximo. Não pule etapas nem implemente épicos fora de
ordem, mesmo que pareça mais rápido — o Épico 7 (orquestração) depende de todo subagente do
Épico 3–6 já funcionar isoladamente, e testar isso fora de ordem esconde bugs de integração.

**Ao concluir cada épico:**
1. Rode os "Testes obrigatórios" do arquivo do épico.
2. Confirme item a item o "Gate" — não avance com item pendente.
3. Peça confirmação explícita ao usuário antes de seguir para o próximo épico (mesmo que os
   testes automatizados passem — alguns critérios de aceite, principalmente nos Épicos 7 e 8,
   dependem de julgamento humano sobre qualidade de copy, não só execução correta).
4. Commit por épico (`feat(<escopo-do-épico>): ...`), seguindo a convenção descrita em
   `CLAUDE.md` §Git — branch de trabalho, nunca direto em `main`.

**Convenções a respeitar em todo código/conteúdo gerado:**
- Todo subagente novo segue o formato de frontmatter já usado no repositório irmão
  `../../pipelines/hemingway/.claude/agents/` (`name`, `description` com gatilho de
  uso claro, `tools`, `skills`, `model: inherit`) — leia pelo menos um exemplo de lá antes de
  escrever o primeiro agente daqui.
- Toda skill que escreve arquivo ou dispara pipeline leva `disable-model-invocation: true`
  (regra herdada do ecossistema, ver `CLAUDE.md` §Regras invioláveis).
- Nenhum insumo em `_insumos/` (raiz `Syntaxis/`) é copiado para dentro deste repositório —
  sempre referenciado por caminho relativo. Se um épico parecer exigir cópia, pare e
  pergunte antes de copiar.
- Nenhum dado numérico (preço, estatística, limite de plataforma) entra em código ou skill
  sem vir de um dos arquivos-fonte listados em `CLAUDE.md` §Fonte única — inclusive nos
  exemplos de teste usados para validar os épicos.
- O gate humano (etapa 8) é código real usando `AskUserQuestion` — não um placeholder "TODO:
  perguntar ao usuário". Se a etapa 8 não puder ser implementada de verdade na sessão atual
  (ex.: ferramenta indisponível), pare o Épico 7 e avise, não implemente um substituto que
  aprove sozinho.

**Primeiro passo concreto:** comece pelo Épico 1. Ele não tem código, só estrutura e
documentação — é rápido, e todo épico seguinte depende do schema de `estado.json` que ele
define.
