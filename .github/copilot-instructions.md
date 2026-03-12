---
applyTo: "**"
---

# Tapp Amps Website — Copilot Instructions

## Project Context

This is a Jekyll static website for **Tapp Amps**, a boutique guitar amplifier brand from Borlänge, Sweden.
The site uses a custom dark theme with SASS, no CSS framework.

## Architecture

- **Jekyll collections:** `_amps` (amplifier models), `_albums` (artist recordings)
- **Layouts:** `default` → `page`, `amp`, `album`, `albums`
- **Navigation:** Data-driven via `_data/navigation.yml` with dropdown support
- **Styling:** Single SASS file `_sass/main.scss` with BEM-style naming

## Conventions

- Dark theme: background `#0d0d0d`, accent gold `#c9a84c`
- Font stack: Oswald for headings (uppercase), Inter for body
- BEM-like CSS class naming: `.block__element--modifier`
- Amp pages use front matter for specs, wattage, type, images, order
- Album entries use front matter for artist, amp_used, cover_image, spotify/youtube URLs
- All images go in `assets/images/{amps,albums,brand}/`
- Navigation changes require editing `_data/navigation.yml`

## Adding Content

- New amp: create `.md` in `_amps/`, add to `_data/navigation.yml` submenu
- New album: create `.md` in `_albums/` with cover_image and streaming links
- New page: create `.md` or `.html` at root with `permalink:` in front matter

## Build

```bash
bundle exec jekyll serve   # local dev
bundle exec jekyll build   # production build to _site/
```

## Key Files

- `_config.yml` — site settings, social links, email, collections
- `_sass/main.scss` — all styles
- `_data/navigation.yml` — menu structure
- `_layouts/amp.html` — amp detail template (specs table, gallery, CTA)
- `_includes/header.html` — logo + responsive nav
