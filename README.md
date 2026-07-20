# Briefing de Marca — Victor Ota

Briefing de marca interativo, *single-file* (HTML puro, sem build nem dependências
de runtime além das fontes do Google Fonts). Implementa o método autoral de
branding de Victor Ota — de ramificação condicional: da base do negócio à
personalidade, até revelar o **arquétipo predominante** da marca (os 12
arquétipos de Mark & Pearson, organizados em quatro quadrantes: Plenitude,
Maestria, Pertencimento e Estabilidade).

Ao final, o usuário baixa um `.json` com as respostas.

## Deploy

Site estático. `index.html` na raiz — deploy *zero-config* na Vercel
(conecte o repositório ou faça upload do arquivo). Nenhum passo de build.

## Estrutura

- `index.html` — aplicação completa e autocontida: identidade visual, roda dos
  arquétipos, fontes e lógica, tudo embutido (imagens em base64). Funciona
  offline, sem servidor.
- `vercel.json` — configuração mínima de deploy estático.

## Identidade

Paleta e tipografia do Manual de Marca de Victor Ota — quase-preto `#0F0F10`,
ouro `#C3A262`, creme `#F7F4E8`; Red Hat Display + Syne (statements). Estética
*dark-luxury* com o ouro como único acento cromático. **"Marca que marca."**
