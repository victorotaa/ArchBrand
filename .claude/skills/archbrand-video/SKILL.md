---
name: archbrand-video
description: Produz vídeo de marca para clientes ArchBrand via HyperFrames (HTML→MP4 determinístico), com paleta, tipografia e linguagem de movimento DERIVADAS do arquétipo junguiano do cliente. Use para reel de marca, abertura de identidade, manifesto animado, vídeo de lançamento de qualquer cliente ArchBrand. Diferente de samais-video: aqui nada é travado — tudo deriva do arquétipo + brand guide do cliente.
license: MIT
---

# ArchBrand — Vídeo de marca por arquétipo (HyperFrames)

## Princípio
O movimento não é decoração: é semântica de marca. Ease e shader carregam a emoção do arquétipo dominante do cliente (cf. princípios de motion da HeyGen; Val Head, *Designing Interface Animation*). Uma marca Herói e uma marca Sábio nunca se movem igual.

## Stack
HyperFrames (Apache 2.0 — sem threshold, seguro para trabalho comercial por cliente). Loop: `doctor → lint → preview → render`. Contrato na skill `hyperframes` e no CLAUDE.md.

## Intake (antes de compor)
1. Nome do cliente + arquétipo(s) dominante(s) + brand guide (paleta/tipografia/tom).
2. Derivar tokens: `--bg / --ink / --accent` da paleta do cliente; par tipográfico do guia (peso com contraste dramático, 300 vs 900).
3. Selecionar vocabulário de ease + shader pela tabela abaixo.
Se faltar arquétipo, perguntar UMA questão com opções concretas.

## Mapa Arquétipo → Movimento (12 arquétipos junguianos)
| Arquétipo | Paleta tende a | Ease dominante | Shader | Pacing |
|---|---|---|---|---|
| Herói | contraste alto, ouro/vermelho | power4.out, expo.out | cinematic-zoom | rápido, ascendente |
| Sábio | azuis/neutros frios | sine.inOut, power2.out | cross-warp-morph | contemplativo, holds |
| Fora-da-lei | preto/alerta, neon pontual | power4.out, steps() | glitch, chromatic-split | agressivo, cortes secos |
| Inocente | claros, pastéis | sine.inOut, back.out | light-leak | suave |
| Explorador | terrosos, âmbar | expo.out, power3.out | whip-pan | dinâmico |
| Criador | vibrante controlado | back.out(1.6) | domain-warp | lúdico |
| Governante | monocromo nobre, ouro | power2.out | sdf-iris | majestoso, hold longo |
| Mago | índigo/roxo, gradiente sutil | sine.inOut, expo.out | gravitational-lens, swirl-vortex | hipnótico |
| Amante | quentes, vinho/rosé | sine.inOut | ripple-waves, light-leak | íntimo, lento |
| Cuidador | suaves, verde/azul calmo | power1.out, sine.inOut | cross-warp-morph | acolhedor |
| Bobo | saturado, alto contraste | back.out(2), elastic (leve) | whip-pan | rápido, surpresa |
| Cara-comum | neutros acessíveis | power2.out | hard cuts | direto, sem firula |

## Composição
Mesmos skeletons/contrato do HyperFrames. Escolher formato (reel 9:16, teaser 16:9) pelo canal. Parametrizar copy/paleta por cliente num objeto `MARCA` no topo, para reuso entre peças do mesmo cliente.

## Regra
Máx. 2–3 shaders por peça. Tipografia: sem defaults preguiçosos; peso com contraste dramático; mínimos 60px headline / 20px corpo / 16px label; `tabular-nums` em números.
