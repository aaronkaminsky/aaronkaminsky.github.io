# aaronkaminsky.github.io

Personal homepage for Aaron Kaminsky, served via GitHub Pages at the custom domain `foggysunrise.xyz` (see `CNAME`). Pushing to `main` deploys live — there is no staging environment.

## Stack

- Jekyll 3.9 (see `Gemfile`), built and served by GitHub Pages.
- `bundle exec jekyll serve` for local preview (defaults to `http://localhost:4000`).
- No JS framework or build step beyond Jekyll/Liquid templating.

## Current page structure

- `index.md` is the live homepage. It uses `layout: default` with `minimal: true`, which renders a single centered `.glass-card` over a fullscreen hero photo (`assets/images/foggy_sunrise_hero.jpg`) — no header/footer nav.
- `_layouts/default.html` conditionally skips `header.html`/`footer.html` when `page.minimal` is set.
- `_includes/header.html`, `_includes/footer.html`, and most of `assets/css/style.css` (hero/nav/sections/project-grid/hobbies-grid styles) belong to a fuller multi-section design (About/Approach/Projects/Off the Clock) that was scaffolded but is **not currently used by any page**. Treat it as available-but-dormant scaffolding, not dead code to delete — it may be brought back for a fuller site later.
- `_data/projects.yml` and `_data/links.yml` drive the link buttons on the minimal homepage.

## Design notes

- Dark, glassmorphic aesthetic. Color tokens are CSS variables in `:root` at the top of `style.css` (`--accent-cyan`, `--text-secondary`, `--text-muted`, etc.).
- The `.glass-card` text deliberately overrides the global `--text-secondary`/`--text-muted` variables with brighter hardcoded colors (`#c7d2e0`, `#aab6c6`) plus a `text-shadow`, because the card sits on a photo background rather than the flat dark `body` background — the global muted tones weren't legible there. Don't change the global variables to "fix" this; override locally within `.glass-card` the same way.
- `favicon.png` is a small sun-over-waves icon; the sun disc is filled solid yellow (not just an outline) so it reads clearly at favicon size.

## Workflow

- This repo has no CI — verify locally with `bundle exec jekyll serve` before pushing.
- `main` is the only branch that matters; pushing it deploys to production immediately.
