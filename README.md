# Tapp Amps Website

Official website for **Tapp Amps** — handcrafted boutique guitar amplifiers from Borlänge, Sweden.

Built with [Jekyll](https://jekyllrb.com/).

## Development

```bash
bundle install                    # Install dependencies
bundle exec jekyll serve          # Dev server at http://localhost:4000
bundle exec jekyll build          # Production build to _site/
```

## Adding Content

- **New amp model:** Create a `.md` file in `_amps/` and add it to `_data/navigation.yml`
- **New album:** Create a `.md` file in `_albums/` with cover image and streaming links
- **Images:** Place in `assets/images/amps/`, `assets/images/albums/`, or `assets/images/brand/`

See [CLAUDE.md](CLAUDE.md) for full documentation.
