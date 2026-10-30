# Clay

A warm, paper-like theme for the [Markdown Viewer](https://github.com/simov/markdown-viewer) browser extension, tuned for math-heavy notes. It switches between a soft off-white and a warm dark gray with your system's appearance.


| Light | Dark |
| :---: | :---: |
| ![Light mode](screenshots/light.png) | ![Dark mode](screenshots/dark.png) |

## Features

- **Follows your system.** Light and dark palettes switch automatically with macOS / Windows appearance.
- **Readable line length.** With Content Width set to `AUTO`, text is capped at 920px and centered. Other width options still work.
- **Math-friendly.** Calm heading sizes, comfortable line height, and long display formulas scroll horizontally instead of overflowing.
- **Self-contained syntax colors.** Code highlighting is defined by the theme itself, so code stays readable even when the extension loads the code palette for the wrong color scheme (for example after switching appearance without reloading the page).
- **Small.** About 5 KB after minification, well within the extension's 8 KB limit for custom themes.

## Install

1. Install [Markdown Viewer](https://chromewebstore.google.com/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk) and, for local files, turn on **Allow access to file URLs** in `chrome://extensions` → Markdown Viewer → Details.
2. Download [`clay.css`](clay.css) (open it, then use the download button, or save the raw file).
3. Click the extension icon → **Advanced Options** → **Settings**.
4. Set **Content Theme** to `CUSTOM`, upload `clay.css`, and set **Color Scheme** to `AUTO`.
5. Reload any open Markdown page.

### Recommended settings

| Section | Option | Value |
| --- | --- | --- |
| Content | `mathjax`, `toc`, `autoreload`, `syntax` | on |
| Compiler (markdown-it) | `cjk`, `footnote`, `mark`, `tasklists` | on |
| Theme | Content Width | `AUTO` |

Want smaller text? Press <kbd>Cmd</kbd> + <kbd>-</kbd> (or <kbd>Ctrl</kbd> + <kbd>-</kbd>) on a Markdown page. Chrome remembers the zoom level for local files.

## Known limitation

Formulas inside headings appear as raw TeX (for example `$L^p$`) in the table of contents sidebar. The extension intentionally skips math rendering there, so a theme cannot change it.

## Try it

Open [`sample.md`](sample.md) in Chrome with the theme installed. It covers math, code, tables, quotes, task lists, and footnotes.

## Build cost

This theme was vibe-coded with an AI assistant (Claude Opus 5.5). Listing the cost helps you decide whether to fork this or build your own:

| | Approx. |
| --- | --- |
| Model calls | ~50 |
| Tokens processed | ~11M (mostly cached context re-reads) |
| Tokens generated | ~26K |
| Input-equivalent cost | ~1.6M tokens (cache reads 0.1x, cache writes 2x, output 5x) |

This covers designing the theme, rendering test notes in light and dark mode, and fixing the issues found along the way (unreadable code in light mode, overly long lines, centered table headers). It excludes publishing this repository.

## License

[MIT](LICENSE)
