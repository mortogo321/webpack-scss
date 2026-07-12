# Webpack + Sass HTML Mockup

A static, multi-page HTML/CSS mockup built with a custom Webpack build pipeline — demonstrates asset bundling, Sass compilation, and multi-entry HTML generation without a UI framework.

## What's inside

- Four static pages: a dashboard/list view (`index.html`), an item detail view (`detail.html`), and two create/form views (`create.html`, `create-card.html`), each rendered via `HtmlWebpackPlugin`
- A shared sidebar/navbar layout with Sass partials for layout sections (`_navbar`, `_sidebar`, `_footer`, `_main`) and a page-specific stylesheet
- TypeScript-aware entry point (`src/index.js`) compiled through Babel
- Separate Webpack configs for development and production builds, merged from a common base config

## Tech stack

- Webpack, webpack-dev-server, webpack-merge
- Sass (`sass-loader`) with PostCSS/Autoprefixer
- Babel (`@babel/preset-env`, `@babel/preset-typescript`) for JS/TS transpilation
- TypeScript (type-checking only, via `tsc`)
- HtmlWebpackPlugin, MiniCssExtractPlugin, CopyWebpackPlugin, CleanWebpackPlugin

## Project structure

```
config/                  Webpack configs (common, dev, prod)
src/
  index.js               Entry point
  index.html              Dashboard / list page
  detail.html             Item detail page
  create.html             Create page
  create-card.html        Create-card page
  scss/                   Sass partials and page styles
  assets/                 Images and static JS
webpack.config.js         Picks dev/prod config based on NODE_ENV
```

## Quickstart

Dependencies are managed with Bun (see `bun.lock`).

```
bun install
bun run start
```

Then open http://localhost:8080.

### Build

```
bun run build:dev     # development build
bun run build:prod    # production build
```

Build output is written to `dist/`.

### Type-check

```
bun run typecheck
```

## Pages

- `index.html` — main list/dashboard view
- `detail.html` — detail view for a single item
- `create.html` / `create-card.html` — create/form views
