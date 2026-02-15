# Fairweather Print Media — Claude Code Guide

## Project Overview

Web-based catalog management system for Fairweather Productions print artwork. Manages inventory, Etsy listings, and product descriptions for art prints by Jessop Hunt and Shannon Hunt.

**Stack:** Vanilla HTML, CSS, JavaScript — no frameworks, no build steps. Deploys to GitHub Pages.

## Key Files

- `index.html` — Main catalog editor (editable rows, search/filter, export)
- `description-generator.html` — Etsy description builder (form → live preview → save to catalog)
- `fairweather-prints-catalog.html` — Alternative table-based catalog view
- `catalog-data.json` — Master data file (array of print objects, used as fallback when localStorage is empty)
- `images/mist-overlay.png` — Mist texture for background effect

## Data Flow

- On load, pages read from `localStorage` key `fairweather-catalog-data`; if empty, they fetch `catalog-data.json` as default
- All edits save to localStorage immediately — there is no server
- Export buttons generate CSV/JSON downloads from the in-memory `prints` array
- The description generator shares the same localStorage key, so changes sync between pages

## Design System: Gentle Machine

See `docs/design-guide.md` for the full specification. Key rules:

- **Dark blue-grey palette** — base `#1a1f2e`, no purple/gold/warm accents
- **Glassmorphism** — semi-transparent `rgba()` backgrounds + `backdrop-filter: blur()`
- **Typography** — `Cormorant Garamond` for headings, `Source Sans Pro` for body text (loaded via Google Fonts)
- **Warm text on cool surfaces** — primary text `#e8e6e1`, secondary `rgba(200, 196, 188, 0.85)`
- **Steel blue accents** — `rgba(100, 140, 180, *)` at varying opacities for borders, buttons, interactive elements
- **Mist overlay** — `images/mist-overlay.png` as a fixed background layer with `hue-rotate(200deg) saturate(0.3)`
- **Subtle interactions** — `translateY(-2px)` hover lifts, `0.25s ease` transitions, no glows or pulsing

## Image Assets

| Directory | Contents | Format |
|---|---|---|
| `Art-for-Prints/` | High-resolution originals | `.tif` |
| `Art-for-Prints-Web/` | Web-optimized display images | `.jpg` |
| `Art-for-Prints-Thumbnails/` | 60px row thumbnails | `.jpg` |

Image filenames match the `web_image` and `thumbnail` fields in `catalog-data.json`. Verify exact filenames before referencing — paths are case-sensitive on GitHub Pages.

## Catalog Data Schema

Each print object in `catalog-data.json`:

```json
{
  "filename": "example.tif",
  "title": "Example Title",
  "artist": "Jessop" | "Shannon" | "",
  "status": "Not Listed" | "Listed" | "Sold Out",
  "price": "$25.00" | "",
  "web_image": "example.jpg",
  "thumbnail": "example.jpg",
  "etsy_url": "",
  "notes": "",
  "description": ""
}
```

## Working Conventions

- All CSS is inline (`<style>` blocks) — no external stylesheets
- All JS is inline (`<script>` blocks) — no external scripts or modules
- Design tokens live in `:root` CSS custom properties at the top of each file's `<style>` block
- When adding new pages, copy the `:root` variables and mist overlay pattern from `index.html`
- Keep `catalog-data.json` as a clean default — user edits live only in localStorage
