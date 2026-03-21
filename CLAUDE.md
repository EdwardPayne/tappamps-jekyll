# Tapp Amps Website — CLAUDE.md

## Project Overview

Static website for **Tapp Amps**, a boutique guitar amplifier brand based in Borlänge, Sweden.
Built with **Jekyll** and hosted as a static site.

## Tech Stack

- **Generator:** Jekyll 4.4.1
- **Language:** Ruby 3.1.3 (ARM macOS)
- **Styling:** SASS (custom dark theme, no framework)
- **Fonts:** Google Fonts — Oswald (headings), Inter (body)

## Quick Commands

```bash
bundle exec jekyll serve          # Dev server at http://localhost:4000
bundle exec jekyll build           # Build to _site/
bundle exec jekyll serve --drafts  # Include draft posts
```

## Directory Structure

```
├── _amps/                  # Amp model pages (collection)
│   ├── marzian.md
│   ├── marzian-mini.md
│   └── iratus.md
├── _albums/                # Album/artist entries (collection)
│   ├── aeon-aeons-black.md
│   ├── souldrainer-architect.md
│   ├── sabaton-carolus-rex.md
│   └── ... (17 albums total)
├── _data/
│   └── navigation.yml      # Top nav menu structure
├── _includes/
│   ├── header.html          # Site header + nav
│   └── footer.html          # Site footer + social links
├── _layouts/
│   ├── default.html         # Base layout (HTML shell)
│   ├── page.html            # Generic page layout
│   ├── amp.html             # Single amp detail page
│   ├── album.html           # Single album page
│   └── albums.html          # Albums listing page
├── _sass/
│   └── main.scss            # All styles (dark theme)
├── assets/
│   ├── css/style.scss       # SASS entry point
│   ├── logos/               # SVG logos (tapp.svg, tappamps.svg)
│   └── images/
│       ├── amps/            # Amp product photos
│       ├── albums/          # Album artwork
│       └── brand/           # Favicon, brand assets
├── index.html               # Homepage
├── amps.html                # Amps listing page
├── albums.html              # Albums listing page
├── about.md                 # About page
├── contact.html             # Contact page
├── _config.yml              # Jekyll configuration
├── Gemfile                  # Ruby dependencies
└── CLAUDE.md                # This file
```

## Adding a New Amp

1. Create a new `.md` file in `_amps/` (e.g., `_amps/new-model.md`)
2. Use this front matter template:

```yaml
---
title: "Model Name"
slug: model-name
wattage: 100
type: "All-Tube Head"
excerpt: "Short description for cards."
images:
  - /assets/images/amps/model-front.jpg
specs:
  Power Output: "100W"
  Tubes: "EL34 power section"
  # ... more specs
order: 4 # Controls display order
---
```

3. Add the model to `_data/navigation.yml` under the Amplifiers submenu
4. Add photos to `assets/images/amps/`

## Adding a New Album

1. Create a new `.md` file in `_albums/` (e.g., `_albums/band-album-name.md`)
2. Use this front matter:

```yaml
---
title: "Album Title"
artist: "Artist Name"
cover_image: /assets/images/albums/band-album-name.jpg
spotify_url: "https://open.spotify.com/album/..."
youtube_url: "https://youtube.com/..."
---
```

3. Add album art to `assets/images/albums/`

## Maintenance Mode

The site has a built-in maintenance/coming-soon page controlled by a flag in `_config.yml`:

```yaml
maintenance: true   # Show coming-soon page
maintenance: false  # Show full site
```

When enabled, `_layouts/default.html` replaces all page content with a centered logo, tagline, and social links. Styles are in the `.maintenance` BEM block in `_sass/main.scss`.

## Key Configuration

- **Maintenance mode:** `_config.yml` → `maintenance: true/false`
- **Logo:** `_config.yml` → `logo: /assets/logos/tappamps.svg`
- **Social links:** `_config.yml` → `social.facebook`, `social.instagram`
- **Contact email:** `_config.yml` → `email`
- **Navigation:** `_data/navigation.yml`

## Theme Colors (in `_sass/main.scss`)

- Background: `#0d0d0d`
- Card background: `#141414`
- Accent (gold): `#c9a84c`
- Text: `#e0e0e0`
- Muted text: `#888`

## Current Amp Models

| Model        | Wattage | Type          |
| ------------ | ------- | ------------- |
| Marzian      | 100W    | All-Tube Head |
| Marzian Mini | 30W     | All-Tube Head |
| IRATUS       | 100W    | All-Tube Head |

## Notes

- All amps are built on request only (boutique / limited edition)
- Logo: SVG in `assets/logos/tappamps.svg`, displayed with `filter: invert(1)` (black SVG → white on dark bg)
- Social media icons (SVG) in both header and footer (Facebook, Instagram, Email)
- Album grid uses compact 200px-min cards, scales to many entries
- Image aspect ratios: amp images use 16:9, album covers use 1:1
- **Production build:** Always use `bundle exec jekyll build` — `jekyll serve` overrides the `url` to localhost
- GitHub repo: `git@github.com:EdwardPayne/tappamps-jekyll.git`
