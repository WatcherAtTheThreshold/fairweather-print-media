# Fairweather Print Media Catalog

A web-based catalog management system for Fairweather Productions print artwork.

## Features

- **Editable Catalog** — Click to edit artist, status, price, Etsy URLs, notes, and descriptions
- **Expandable Rows** — Click rows to reveal detailed notes and description fields
- **Auto-Save** — Changes persist automatically in browser localStorage
- **Multi-Format Export** — Export to CSV, JSON, or printable format
- **Image Management** — Browse thumbnails, view full-size web images

## File Structure

- `index.html` — Main catalog editor application
- `catalog-data.json` — Master data file (default/fallback data)
- `Art-for-Prints/` — High-resolution print files (.tif)
- `Art-for-Prints-Web/` — Web-optimized images (.jpg)
- `Art-for-Prints-Thumbnails/` — Thumbnail images (.jpg)
- `etsy-description-template.md` — Template for Etsy listings

## Usage

1. Open `index.html` in a web browser
2. Click any cell to edit values
3. Click a row to expand and edit notes/descriptions
4. Changes save automatically to localStorage
5. Export data using the toolbar buttons:
   - **CSV** for spreadsheet editing
   - **JSON** for backups
   - **Print** for physical records

## Data Persistence

Data is stored in browser localStorage and persists across sessions. Export JSON regularly as a backup. Use "Import JSON" to restore from backup files.

## Development

Built with vanilla HTML, CSS, and JavaScript. No build process required.

---

**Fairweather Productions** — Art Print Catalog Management
