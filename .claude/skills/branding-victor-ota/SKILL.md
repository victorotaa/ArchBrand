---
name: branding-victor-ota
description: >-
  Método autoral de branding de Victor Ota — briefing estratégico de marca com
  instrumento de arquétipo cruzado de Mark & Pearson (12 arquétipos, 4
  quadrantes), ramificação condicional e resultado revelador (não
  determinístico). Use ao conduzir descoberta/briefing de marca, definir
  arquétipo · persona · MVV (missão/visão/valores) · personalidade · jornada, ou
  ao criar/editar/rodar a ferramenta de briefing (index.html, single-file
  autocontido). Também para portar o método a outros contextos mantendo a
  identidade visual e as regras de processo do Victor.
---

# Método autoral de branding — Victor Ota

Briefing estratégico de marca em HTML single-file, 100% autocontido (imagens e
logos em base64, sem build, sem dependências além do Google Fonts). É o método
autoral do Victor, derivado do fluxo real que ele roda no Tripetto:
**ramificação condicional** que se adapta ao tipo de marca e conduz o cliente
por descoberta → arquétipo → resultado, terminando no download de um `.json` com
as respostas.

A ferramenta viva é **`index.html` na raiz deste repositório** (deploy estático
zero-config na Vercel). Esta skill é o mapa para rodá-la, editá-la e replicá-la
sem reler ~700 linhas.

## Quando usar

- Conduzir um briefing/descoberta de marca com um cliente (ou consigo mesmo).
- Adicionar/refinar perguntas seguindo o fluxo real do Tripetto (segmento a
  segmento).
- Ajustar o instrumento de arquétipos, a persona, o MVV ou a jornada.
- Portar o método para outro repo/produto preservando identidade e regras.

## O fluxo (ramificação condicional)

```
Método (intro: roda dos 12 arquétipos)
  → tipo de marca: nova / existente / produto / holding
    → pessoal (marca pessoal) / corporativa
      → MVV já definido? sim → envio do MVV | não → definir Missão/Visão/Valores
        → Persona
          → Personalidade de Marca
            → Arquétipo cruzado (Mark & Pearson) → refino (Arquétipo II)
              → Jornada do Usuário
                → Resultado (top-2 arquétipos + sinais cruzados) → baixa .json
```

Cada tela pertence a uma `section`; `STAGE_MAP` agrega as sections nos 10
estágios macro da sidebar (só visualização, não clicável):

```
Início · Marca · Motivação · Propósito · Persona · Personalidade · Arquétipo · Jornada · Fechamento · Resultado
```

## O instrumento de arquétipos (Mark & Pearson)

12 arquétipos em 4 quadrantes de motivação. Coletados via
`archetype-checklist`; `computeArchetypeScores()` conta o checklist e revela os
**top-2** + sinais cruzados (quadrante escolhido, refino, estilo de comunicação
do cliente, "por onde a marca passa"). É **revelador, não determinístico** —
regra explícita do Victor: o resultado ilumina, não sentencia.

| Quadrante | Motivação | Arquétipos |
|---|---|---|
| **Plenitude** | Anseio pelo paraíso / plenitude | Inocente · Sábio · Explorador |
| **Maestria** | Deixar uma marca no mundo | Herói · Fora da Lei · Mago |
| **Pertencimento** | Conexão com os outros | Amante · Bobo da Corte · Homem Comum |
| **Estabilidade** | Prover estrutura ao mundo | Prestativo · Criador · Governante |

`ARCHETYPE_STATEMENTS` guarda 6 frases por arquétipo (72 no total),
intercaladas por `buildShuffledStatements()` para não agrupar visualmente por
arquétipo e reduzir viés de resposta.

## Arquitetura técnica (JS vanilla, um `<script>` no fim do `<body>`)

- **`QUESTIONS`** — array de `{id, section, type, title, help, cond, options,
  dynamicOptions, dynamicTitle, placeholder, scales}`. `cond(state.answers)`
  decide a visibilidade de cada tela (é o motor da ramificação).
- **Tipos suportados**: `intro` (tela do método, com a roda), `text`, `email`,
  `url`, `textarea`, `radio` (aceita `dynamicOptions`), `checkbox`,
  `scale-grid`, `archetype-checklist`, `statement` (citação/transição, sem
  input, tipografia Syne ExtraBold), `result`.
- **Dados**: `ARCH` (12 arquétipos + quadrante), `QUADRANTS` (com `intro` e
  `phrases`), `COMM_STYLE`, `RECOGNITION_PHRASES`, `INCOME_BRACKETS`,
  `CHANNELS`, `ARCHETYPE_STATEMENTS`.
- **Estado**: `state = {i, answers}`; `visibleQuestions()` filtra por `.cond`;
  `render()` desenha a tela atual + sidebar (`renderSidebar`) + progress.
- **Saída**: `downloadResults()` gera o `.json` via Blob, sem backend.
- **Assets inline (base64)**: `WHEEL_ARQUETIPOS` (roda dos 12 arquétipos, tela de
  intro), foto de fundo (Basílica de São Pedro, escurecida, na `.bg-fixed`), e
  os logos `OTA_LOCKUP_HORIZONTAL` (topbar — OTA em ouro / VICTOR branco) e
  `OTA_LOCKUP_COMPACT` (empilhado, usado na intro).

## Identidade visual (Manual de Marca Victor Ota — ver `:root`)

- **Cores**: canvas `#0F0F10`, surface `#1C1C1D`/`#2C2C2C`, **ouro `#C3A262`
  (único acento)**, tan `#DAC5A5`, texto primário `#F7F4E8`. Bordas em rgba do
  creme.
- **Tipografia**: **Red Hat Display** (títulos SemiBold / corpo Light) em tudo,
  EXCETO as telas `statement`, que usam **Syne ExtraBold**.
- **Estética**: dark-luxury / liquid glass (topbar, sidebar, inputs, opções,
  checklist, barra de navegação, data-cards do resultado). Slogan
  "marca que marca" sutil ao lado do logo.

## Regras de processo (manter ao editar)

1. **Toda pergunta tem uma `help`/subline curta** orientando o teor da resposta.
   Padrão seguido em quase todas — mantenha ao adicionar novas.
2. **Trabalhar segmento por segmento** a partir do fluxo real do Tripetto. Se
   chegar screenshot de flow-diagram/preview, cruze a lógica seguindo o padrão
   das seções existentes.
3. **Resultado é revelador, não determinístico.** Não transforme o instrumento
   de arquétipos em teste de resultado fechado.
4. **O arquivo permanece 100% autocontido.** Assets novos entram em base64
   inline; nada de dependência externa que quebre offline.
5. **Captura completa — o dado bruto é o produto.** O envio (e-mail) e o download
   sempre carregam **todas as respostas** (`state.answers` inteiro), não só o
   arquétipo/resultado. O `briefing_completo_json` no envio nunca pode ser
   resumido ou podado — o cruzamento posterior depende do dado total.

## Testar antes de entregar (obrigatório)

Sempre validar via **Playwright headless** antes de considerar pronto:

- Chromium do ambiente: `/opt/pw-browsers/chromium` (ou o caminho versionado
  `/opt/pw-browsers/chromium-1194/chrome-linux/chrome`), com
  `NODE_PATH=/opt/node22/lib/node_modules`; importe o playwright pelo caminho
  absoluto do `index.js`.
- Screenshot em **desktop (1440px)** e **mobile (390px)**.
- **Smoke test** do fluxo completo até o download do `.json` (intro → ramifica →
  arquétipo → resultado → download).

## Deploy

`index.html` na raiz, sem build. Deploy estático zero-config na Vercel a partir
de `main` (`vercel.json`: `cleanUrls`, `trailingSlash: false`).

- **Produção (ao vivo):** https://chronos-two-eta.vercel.app — projeto `chronos`
  (time `samais`), conectado ao repo; cada push em `main` re-deploya sozinho.
