# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Vengeance Ventures company website — a German-language business site for web technologies, automation, and DevOps services. Built with Hugo (Hugoplate theme) + Tailwind CSS. Content is in German despite the `content/english/` directory path (inherited from Hugoplate boilerplate).

## Commands

- **Dev server:** `npm run dev` (runs `hugo server`)
- **Production build:** `npm run build` (runs `hugo --gc --minify --forceSyncStatic`)
- **Preview production locally:** `npm run preview`
- **Format code:** `npm run format` (Prettier with go-template plugin for `.html` files)
- **Update Hugo modules:** `npm run update-modules`

## Prerequisites

- Hugo Extended v0.145+
- Node v22+
- Go v1.24+

## Architecture

### Configuration (split config pattern)

- `hugo.toml` — base config, plugins (CSS/JS), build settings, outputs, markup
- `config/_default/params.toml` — site params: logo, SEO metadata, contact form (Formspree), cookies, navigation button
- `config/_default/languages.toml` — single language (English code, German content)
- `config/_default/menus.en.toml` — navigation structure (main menu with Services dropdown, footer links)
- `config/_default/module.toml` — Hugo module imports (gethugothemes modules for search, PWA, images, icons, SEO, shortcodes, etc.)
- `config/development/server.toml` — dev server redirects (currently commented out)

### Content

All content lives in `content/english/`. The homepage (`_index.md`) uses front matter YAML to define banner, features sections (with anchors for in-page navigation: `#automation`, `#bots`, `#devops`). Other pages: `about/`, `contact/`, `pages/` (imprint, privacy policy).

Reusable sections (call-to-action, testimonials) are in `content/english/sections/`.

### Theme & Styling

- Theme: `themes/hugoplate/` — layouts, partials, SCSS, JS
- Colors and fonts: `data/theme.json` (primary `#6D0303`, fonts: Anek Tamil / Signika)
- Social links: `data/social.json`
- Custom SCSS overrides: `assets/scss/custom.scss`
- Tailwind config: `tailwind.config.js` (Tailwind v3)

### Deployment

Deploys to **GitHub Pages** via `.github/workflows/main.yml` on push to `main`. Output directory: `public/`.

### Key Details

- Contact form submits to Formspree (`xgvoybdn`)
- Google Analytics ID: `G-JP1XQJE6WD`
- Tailwind CSS is processed via PostCSS with autoprefixer; Hugo's `buildStats` + cache busters handle CSS purging
- Hugo modules are managed via Go modules (`go.mod`); the theme itself is also a Hugo module
