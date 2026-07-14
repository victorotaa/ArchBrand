# AGENTS.md — ArchBrand (Codex + Claude Code)

Repositório de branding de **Victor Ota** (método autoral ArchBrand). Entregáveis de cliente em `<cliente>/` (ex.: `chronos/`), HTML single-file autocontido, deploy estático na Netlify. Doutrina de marca: skill **`branding-victor-ota`** em `.claude/skills/`.

## Regra — Coprodução OpenAI Codex × Claude Code

Este projeto é **coproduzido por dois agentes**: **OpenAI Codex** e **Claude Code (Claude)**. Os dois contribuem no mesmo repositório, se coordenam e refinam o trabalho um do outro. **Victor Ota é o hub e o decisor** — os agentes produzem; ele valida e escolhe.

> Espelho: este bloco existe também em `CLAUDE.md` (que o Claude Code lê). Manter os dois em sincronia ao editar a regra.

**Protocolo (não negociável):**

1. **Co-autoria.** Todo commit relevante credita o parceiro com trailer `Co-authored-by:` (Codex → `Co-authored-by: Codex <noreply@openai.com>`; Claude → `Co-authored-by: Claude Code <noreply@anthropic.com>`). O crédito registra a coprodução.
2. **Sincronizar antes de tocar.** Sempre `git fetch`/`pull` do `main` (ou da branch ativa) **antes de editar** — o outro agente pode ter avançado. Nunca partir de estado stale; PR mergeado = ponto de partida novo a partir do `main`.
3. **Escopo declarado, commits pequenos e focados.** Anunciar no PR/commit o que está sendo mexido, para não haver clobber. Evitar reescrever por inteiro um arquivo que o outro acabou de tocar sem sinalizar.
4. **Revisão mútua.** Cada agente pode revisar e refinar a saída do outro (passada de consistência, ajuste de contraste, encaixe de imagens, lint). É colaboração, não competição — o melhor resultado prevalece.
5. **A conversa acontece nos artefatos.** Como os dois não têm canal direto, a coordenação vive **no repositório**: descrições de PR, mensagens de commit e **handoffs `.md`** carregando estado, decisões tomadas e pendências. Manter esses artefatos atualizados é o que mantém os dois em sincronia.
6. **Decisões do Victor aguardam o Victor.** Pontos de marca/arquitetura que são dele (rota de logo, posicionamento, paleta, o que commitar) nunca são decididos por cima por um agente — sinalizar e esperar.
7. **Padrões compartilhados.** Ambos seguem a doutrina da skill `branding-victor-ota` (single-file 100% autocontido, validação visual antes de entregar, CMYK+Pantone por cor, paleta travada, fonte de afeto) e os tokens do design system vigente do cliente.
