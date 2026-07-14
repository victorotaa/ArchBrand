# ArchBrand / Jarvis-OS

## Doutrina de Execução Segura — Vídeo (HyperFrames)
- Vídeo programático = HyperFrames (Apache 2.0). Nunca Remotion sem decisão explícita (licença paga p/ 4+ pessoas).
- Skills: `samais-video` (marca travada), `archbrand-video` (arquétipo-derivada), `hyperframes` (contrato oficial HeyGen).
- Pre-flight obrigatório: `npx hyperframes doctor` (Node 22+, FFmpeg) antes de qualquer render.
- Ordem de trabalho: draft → `lint` (zero erros) → `preview` → `render`. Nunca renderizar sem lint verde.
- Determinismo (inegociável): sem Math.random/Date.now/performance.now/setInterval/setTimeout/requestAnimationFrame/repeat:-1/stagger from:"random". Contadores via objeto + onUpdate. Grain via radial-gradient CSS.
- Contrato: `.scene.clip` + data-*; `.scene-content`; `window.__timelines["main"]` = data-composition-id; head na ordem gsap→core→shader-transitions; âncoras de shader com opacity:0 + primeira âncora com tl.set opacity:1; ~95% hard cuts.
- Pipeline Samais: `samais-municipal-study` → objeto DADOS → render (batch por município); B-roll Higgsfield como `<video muted playsinline>` de fundo.
