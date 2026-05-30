
## Quick Start

```bash
# Clone
git clone https://github.com/southwellmedia/velocity.git my-project
cd my-project

# Install (requires Node 22.12+)
pnpm install

# Configure
cp .env.example .env

# Develop
pnpm dev
```

Or use the CLI for the full experience including i18n:

```bash
pnpm create velocity-astro my-project
```

---

## Commands

| Command | Description |
|---------|-------------|
| `pnpm dev` | Start dev server |
| `pnpm build` | Production build |
| `pnpm preview` | Preview production build |
| `pnpm check` | Astro type checker |
| `pnpm lint` | ESLint |
| `pnpm format` | Prettier |
| `pnpm test` | Vitest |
| `pnpm test:e2e` | Playwright E2E |

---

## Project Structure

```
src/
  components/
    ui/           # 31 UI components (form, data-display, feedback, overlay, etc.)
    patterns/     # 7 composed patterns (ContactForm, SearchInput, StatCard, etc.)
    layout/       # Header, Footer, ThemeToggle, Analytics
    blog/         # ArticleHero, BlogCard, ShareButtons, RelatedPosts
    landing/      # Credibility, TechStack, FeatureTabs, and more
    seo/          # SEO, JsonLd, Breadcrumbs
  content/        # Blog posts, authors, FAQs
  config/         # Site and navigation config
  styles/         # Global CSS and design tokens
  pages/          # Routes, API endpoints, OG image generation
```

---

## Configuration

**Site config**: `src/config/site.config.ts` — name, description, URL, social links

**Design tokens**: `src/styles/tokens/` — colors, typography, spacing

**Themes**: `src/styles/themes/` — switch between `default` and `midnight`, or create your own

**Environment**: `.env` — see `.env.example` for available variables

View all components at `/components` in development.

---

## Contributing

1. Fork the repo
2. Create a feature branch
3. Ensure `pnpm lint` and `pnpm check` pass
4. Open a PR

---

## License

MIT — see [LICENSE](LICENSE) for details.

---

**Links**: [Docs](https://github.com/southwellmedia/velocity-docs) | [CLI](https://github.com/southwellmedia/create-velocity-astro) | [Astro](https://docs.astro.build) | [Tailwind v4](https://tailwindcss.com/docs)

**Built by [Southwell Media](https://southwellmedia.com)**
