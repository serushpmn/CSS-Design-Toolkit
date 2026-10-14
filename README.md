# CSS Design Toolkit

Offline CSS style library, component playground, and design toolkit. Browse reusable CSS, preview it safely, customize generators, and copy HTML/CSS for WordPress, WooCommerce, React, or plain HTML — without leaving your machine.

**314 styles · 16 categories · IndexedDB persistence · PWA offline cache**

## Quick start

```bash
npm install
npm run dev
```

Open the URL Vite prints (usually `http://localhost:5173`).

| Command | Purpose |
| --- | --- |
| `npm run dev` | Development server with hot reload |
| `npm run build` | Typecheck and write a static site to `dist/` |
| `npm run preview` | Serve the production build over HTTP |
| `npm test` | Run Vitest unit and interface tests |
| `npm run lint` | Run oxlint |
| `npm run icons` | Regenerate PWA PNG icons |

Requirements: **Node.js 20+** and a current Chromium, Firefox, or Safari browser.

## Features

- Searchable catalog across names, tags, categories, descriptions, and CSS text
- Filters for difficulty, motion, CSS-only vs JavaScript, light/dark fit
- Live sandboxed previews with copy, download, fullscreen, and replay
- Animation timing controls that update the generated CSS immediately
- Labs for shadows, gradients, patterns, and animation presets
- Favorites, named collections, and custom snippets
- Design tokens with local contrast checks and CSS variable export
- Light/dark theme, backup/restore as JSON, offline PWA support

## Why no Tailwind in the catalog?

The app UI is hand-written CSS (`src/styles/app.css`). Catalog snippets are plain CSS so you can paste them into any project without a utility build step. Icons come from bundled `lucide-react`. Fonts use the system stack only — no Google Fonts or CDN.

## Documentation

| Doc | Contents |
| --- | --- |
| [docs/ADDING_STYLES.md](docs/ADDING_STYLES.md) | How to add or edit catalog styles |
| [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) | Folder layout, routing, data model |
| [docs/OFFLINE.md](docs/OFFLINE.md) | Offline install and PWA checklist |
| [docs/BROWSER_SUPPORT.md](docs/BROWSER_SUPPORT.md) | Progressive CSS features and fallbacks |
| [docs/BACKUP.md](docs/BACKUP.md) | Favorites, collections, import/export |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Contribution workflow |

## Project layout

```text
src/
  components/   App shell, cards, editors, preview, settings
  data/         Style drafts, categories, catalog assembly
  lib/          Search, CSS/shadow/gradient helpers, storage, routes
  state/        IndexedDB-backed store and reducer
  styles/       Application chrome CSS
  views/        Library, detail, labs, tokens, collections
  test/         Vitest setup and tests
public/         Favicon, manifest, PWA icons
scripts/        Icon generator
```

## Offline usage (short)

1. `npm run build && npm run preview`
2. Open the local URL once so the service worker installs
3. Disable the network and reload

Do **not** open `dist/index.html` via `file://`. See [docs/OFFLINE.md](docs/OFFLINE.md).

## License

Private project (`private: true` in `package.json`). Adjust licensing before publishing.
