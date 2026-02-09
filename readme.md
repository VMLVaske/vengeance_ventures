# Vengeance Ventures

Company website for Vengeance Ventures – Web-Technologien & Automatisierungen.

Built with [Hugo](https://gohugo.io/) + [Tailwind CSS](https://tailwindcss.com/) using the [Hugoplate](https://github.com/zeon-studio/hugoplate) theme.

## Prerequisites

- [Hugo Extended v0.145+](https://gohugo.io/installation/)
- [Node.js v22+](https://nodejs.org/)
- [Go v1.24+](https://go.dev/doc/install)

## Development

```bash
npm install
npm run dev
```

The dev server runs at `http://localhost:1313`.

## Build

```bash
npm run build
```

Output goes to `public/`.

## Other Commands

- `npm run preview` — Production preview with live reload
- `npm run update-modules` — Update Hugo modules
- `npm run format` — Format code with Prettier

## Deployment

Deploys to GitHub Pages via GitHub Actions on push to `main`.

## Customization

- **Site config:** `hugo.toml`
- **Site params:** `config/_default/params.toml`
- **Colors & fonts:** `data/theme.json`
- **Social links:** `data/social.json`
- **Navigation:** `config/_default/menus.en.toml`
- **Content:** `content/english/`

## License

MIT — based on [Hugoplate](https://github.com/zeon-studio/hugoplate) by [Zeon Studio](https://zeon.studio/).
