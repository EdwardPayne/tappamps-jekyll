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
│   └── placeholder-album.md
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
│   └── images/
│       ├── amps/            # Amp product photos
│       ├── albums/          # Album artwork
│       └── brand/           # Logo, favicon, brand assets
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

1. Create a new `.md` file in `_albums/` (e.g., `_albums/album-name.md`)
2. Use this front matter:

```yaml
---
title: "Album Title"
artist: "Artist Name"
amp_used: "Tapp Amps Marzian"
cover_image: /assets/images/albums/album-cover.jpg
spotify_url: "https://open.spotify.com/album/..."
youtube_url: "https://youtube.com/..."
year: 2024
---
```

3. Add album art to `assets/images/albums/`

## Key Configuration

- **Social links:** `_config.yml` → `social.facebook`, `social.instagram`
- **Contact email:** `_config.yml` → `email`
- **Navigation:** `_data/navigation.yml`
- **Logo:** Set `logo:` in `_config.yml` and place file in `assets/images/brand/`

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
- Logo placeholder is in the header — replace `logo-text` span with an `<img>` when logo file is provided
- Set `logo: /assets/images/brand/logo.png` in `_config.yml` when available
- Placeholder album entries should be replaced with real data
- Image placeholders display "Photo coming soon" / "Album Art" text
