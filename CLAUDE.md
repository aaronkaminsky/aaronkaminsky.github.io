# aaronkaminsky.github.io

Personal homepage for Aaron Kaminsky, served via GitHub Pages at the custom domain `foggysunrise.xyz` (see `CNAME`). Pushing to `main` deploys live — there is no staging environment.

## Stack

- Jekyll 3.9 (see `Gemfile`), built and served by GitHub Pages.
- `bundle exec jekyll serve` for local preview (defaults to `http://localhost:4000`).
- No JS framework or build step beyond Jekyll/Liquid templating.

## Current page structure

- `index.md` is the only page: a single centered `.glass-card` over a fullscreen hero photo (`assets/images/foggy_sunrise_hero.jpg`), no header/footer nav. `_layouts/default.html` always renders this `layout-minimal` body.
- An earlier multi-section design (header/footer nav, hero/projects-grid/hobbies-grid sections) was scaffolded but never used by any page, then removed (`_includes/header.html`, `_includes/footer.html`, and the corresponding CSS) — `style.css` now only contains what `index.md` actually uses. If a fuller multi-page site is wanted later, it'll need to be rebuilt rather than un-commented.
- `_data/projects.yml` and `_data/links.yml` drive the link buttons on the homepage.

## Design notes

- Dark, glassmorphic aesthetic. Only the CSS variables actually in use remain in `:root` (`--bg-primary`, `--accent-cyan`, `--text-primary`, `--transition-smooth`) — don't reintroduce a larger token palette unless new components actually consume it.
- The `.glass-card` text uses brighter hardcoded colors (`#c7d2e0`, `#aab6c6`) plus a `text-shadow` rather than `--text-primary`/a muted gray, because the card sits on a photo background rather than a flat dark one — muted tones weren't legible there.
- `favicon.png` is a small sun-over-waves icon; the sun disc is filled solid yellow (not just an outline) so it reads clearly at favicon size.

## Workflow

- This repo has no CI — verify locally with `bundle exec jekyll serve` before pushing.
- `main` is the only branch that matters; pushing it deploys to production immediately.
