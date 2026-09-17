# zensical-media-zoom

**Este README está escrito em português (Brasil) e em inglês.**  
**This README is available in Brazilian Portuguese and English.**

- [Português (Brasil)](#português-brasil)
- [English](#english)

---

## Português (Brasil)

Visualizador leve de zoom e pan em tela cheia para **diagramas Mermaid** e **imagens** no corpo dos artigos em sites [Zensical](https://github.com/zensical/zensical).

Dois arquivos estáticos (CSS + JS), sem build: copie para o seu projeto e registre no `zensical.toml`.

![Demonstração: zoom em imagem e diagrama Mermaid](media-zoom-demo.gif)

### Recursos

- Clique ou teclado (Enter / Espaço) no diagrama ou na imagem para abrir o overlay em tela cheia
- Arrastar para mover; zoom pela barra de ferramentas, roda do mouse ou teclas `+` / `-`
- Funciona com Mermaid renderizado em **Shadow DOM fechado** (move o host `div.mermaid` em vez de clonar o SVG)
- Ícone de tela cheia por alguns segundos quando o conteúdo entra na viewport; também no hover / foco
- Reinicializa na navegação instantânea (assinatura em `document$`)
- Ignora imagens dentro de links, emoji e blocos Mermaid

### Requisitos

- [Zensical](https://github.com/zensical/zensical) com navegação instantânea
- Mermaid habilitado via fence customizado em `pymdownx.superfences` no `zensical.toml`

### Instalação

1. Copie deste repositório para a pasta `docs/` do seu site:

   ```text
   javascripts/media-zoom.js   → docs/javascripts/media-zoom.js
   stylesheets/media-zoom.css  → docs/stylesheets/media-zoom.css
   ```

2. No `zensical.toml`:

   ```toml
   extra_css = ["stylesheets/media-zoom.css"]
   extra_javascript = ["javascripts/media-zoom.js"]

   [project.markdown_extensions.pymdownx.superfences]
   custom_fences = [
     { name = "mermaid", class = "mermaid", format = "pymdownx.superfences.fence_code_format" }
   ]
   ```

3. Gere ou sirva o site e teste uma página com Mermaid ou imagem no artigo.

### Personalização

- **Textos de acessibilidade**: strings em `media-zoom.js`
- **Limites de zoom**: `MAX_SCALE_IMAGE` (8) e `MAX_SCALE_MERMAID` (16) no início do JS
- **Estilo**: variáveis CSS do tema Zensical (`--md-default-bg-color`, etc.)

### Licença

MIT — veja [LICENSE](LICENSE).

---

## English

Lightweight zoom and pan fullscreen viewer for **Mermaid diagrams** and **inline images** in [Zensical](https://github.com/zensical/zensical) documentation sites.

Two static files (CSS + JS), no build: copy into your project and register them in `zensical.toml`.

![Demo: zoom on image and Mermaid diagram](media-zoom-demo.gif)

### Features

- Click or keyboard (Enter / Space) on a diagram or image to open a fullscreen overlay
- Pan with pointer drag; zoom with toolbar buttons, mouse wheel, or `+` / `-` keys
- Works with Mermaid rendered inside a **closed Shadow DOM** (moves the `div.mermaid` host instead of cloning SVG)
- Brief fullscreen hint when content enters the viewport; hint on hover / focus
- Re-initializes on instant navigation (`document$` subscription)
- Skips images inside links, emoji, and Mermaid blocks

### Requirements

- [Zensical](https://github.com/zensical/zensical) with instant navigation
- Mermaid enabled via `pymdownx.superfences` custom fence in `zensical.toml`

### Installation

1. Copy from this repository into your site’s `docs/` folder:

   ```text
   javascripts/media-zoom.js   → docs/javascripts/media-zoom.js
   stylesheets/media-zoom.css  → docs/stylesheets/media-zoom.css
   ```

2. In `zensical.toml`:

   ```toml
   extra_css = ["stylesheets/media-zoom.css"]
   extra_javascript = ["javascripts/media-zoom.js"]

   [project.markdown_extensions.pymdownx.superfences]
   custom_fences = [
     { name = "mermaid", class = "mermaid", format = "pymdownx.superfences.fence_code_format" }
   ]
   ```

3. Build or serve the site and test a page with Mermaid or an inline image.

### Customization

- **Accessibility strings** in `media-zoom.js`
- **Zoom limits**: `MAX_SCALE_IMAGE` (8) and `MAX_SCALE_MERMAID` (16) at the top of the JS file
- **Styling** uses Zensical theme CSS variables (`--md-default-bg-color`, etc.)

### License

MIT — see [LICENSE](LICENSE).
