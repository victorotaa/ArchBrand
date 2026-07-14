# Chronos · QA interno do moodboard

**Data:** 2026-07-13

**Status F5:** `in_validation`

**Status do logotipo:** `background`

## Tese testada

Longevidade ativa com acompanhamento integrado: técnica sem frieza, força sem
espetáculo e premium sem ostentação.

## Estrutura

- 30 imagens incorporadas ao HTML.
- 6 territórios conceituais, com 5 imagens e 1 herói em cada.
- Conceito revelado por hover e foco; sempre visível em touch.
- Sem referências ou créditos no artefato apresentado ao cliente.

## Consistência documental

- Moldura visual alinhada às fases 1–4: fundo preto, dourado, Syne e Red Hat Display.
- Largura, topbar, hero, chips, kickers, cards e footer seguem o documento de marca.
- Marinho, azul, terracota e areia aparecem como conteúdo da identidade estudada,
  não como uma interface paralela à apresentação.

## Teste de categoria

**Leitura pretendida:** espaço de longevidade ativa com avaliação, orientação e
progressão individual.

**Leituras a evitar:**

1. clínica geriátrica ou reabilitação passiva;
2. academia premium convencional;
3. estética antienvelhecimento ou luxo escuro.

## Swap test

| Troca possível | Risco | Elemento que impede a troca |
|---|---|---|
| Academia convencional | esforço e equipamentos genéricos | maturidade real, avaliação e acompanhamento como heróis |
| Clínica de fisioterapia | proximidade técnica e mobilidade | força ativa, constância e vida fora do tratamento |
| Wellness de luxo | atmosfera silenciosa e tons profundos | gesto funcional, suor contido e ausência de ostentação |

**Resultado:** `pass with risks`. O território é coerente; a produção própria
deverá substituir o repertório stock por pessoas, espaço e equipe da Chronos
para tornar a direção proprietária.

## Contraste dos pares usados em texto

| Fundo | Texto | Ratio | Resultado |
|---|---|---:|---|
| Marinho `#0F1F39` | Creme `#F4ECDD` | 14,03:1 | AA/AAA |
| Marinho 2 `#1A2C4E` | Creme `#F4ECDD` | 11,81:1 | AA/AAA |
| Azul `#3E78B2` | Branco `#FFFFFF` | 4,63:1 | AA normal |
| Dourado `#CBA152` | Marinho `#0F1F39` | 6,87:1 | AA normal |
| Terracota `#B4623F` | Preto `#000000` | 4,76:1 | AA normal |
| Areia `#D9CBB3` | Marinho `#0F1F39` | 10,31:1 | AA/AAA |
| Neutro `#8A97AC` | Marinho `#0F1F39` | 5,57:1 | AA normal |

## Verificação técnica

- Desktop `1440 × 900`: 30/30 imagens carregadas, sem overflow.
- Mobile `390 × 844`: 30/30 imagens carregadas, sem overflow.
- 30 cards navegáveis por teclado.
- Overlay: opacidade `0 → 1` ao receber foco.
- Regra `prefers-reduced-motion` presente.
- Console: sem erros relevantes.

Capturas de QA são artefatos locais e não integram a apresentação.
