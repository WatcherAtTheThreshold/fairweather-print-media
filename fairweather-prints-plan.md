# Fairweather Prints - Organization & Listing Plan

## Current Situation
- **58 print-ready .tif files** in `Art-for-Prints/` folder
- Ready to transition Etsy store to sell physical prints (11x14 matted, 8x10 image)
- Website page in progress for print sales
- Need to create product listings for each print

## Goals
1. Organize print files with consistent naming and metadata
2. Create Etsy product descriptions for all 58 prints
3. Set up simple inventory tracking system
4. Generate web-ready images for Etsy and website

---

## Phase 1: Organization & Data Structure

### Create Master Print Catalog (CSV)
**Columns:**
- `filename` - Standardized file name (no spaces, consistent capitalization)
- `title` - Display title for Etsy/website
- `artist` - Jessop or Shannon
- `status` - Not Listed / Listed / Sold Out / On Hold
- `price` - Current print price
- `etsy_url` - Link to listing once created
- `notes` - Anything special (medium of original, inspiration, best-seller, etc.)
- `description` - Full Etsy description text

**Example row:**
```
afternoon.tif, "Afternoon", Shannon, Not Listed, $25, , "Warm golden light piece", ""
```

### File Naming Standardization
**Current issues:**
- Inconsistent capitalization (FlowerPot vs forget)
- Inconsistent spacing (BirchMeadow vs Apple Blossom)
- One file has dimensions in name (BarnOwlandSnowMoon10x8.tif)

**Proposed convention:**
- All lowercase
- Hyphens instead of spaces
- No dimensions in filename
- Examples: `afternoon.tif`, `apple-blossom.tif`, `barn-owl-and-snow-moon.tif`

**Decision needed:** Do you want to rename files, or leave them as-is and just track standardized names in the CSV?

---

## Phase 2: Etsy Description Template

### Template Structure
```
[Opening hook - what makes this piece special]

[2-3 sentences about the artwork - mood, subject, style]

PRINT DETAILS:
• 8" x 10" archival print
• Matted to 11" x 14" (fits standard frames)
• Protected in clear archival bag
• Ready to frame and display

ABOUT THE ORIGINAL:
[Medium, size, inspiration - 1-2 sentences]

Each print is carefully produced to capture the depth and texture of the original painting.

[Optional: Artist signature, limited availability, pairs well with, etc.]
```

### Tone/Voice
- Warm but not flowery
- Focus on how the piece feels, what it brings to a space
- Avoid generic art-speak ("stunning," "breathtaking")
- Be specific about subject matter

### Example Description (for "Whispers in the Birches")
```
Slender white birch trunks rise through soft morning light, their delicate branches creating an intricate pattern against a gentle sky. This quiet woodland scene brings a sense of calm and natural elegance to any space.

PRINT DETAILS:
• 8" x 10" archival print
• Matted to 11" x 14" (fits standard frames)
• Protected in clear archival bag
• Ready to frame and display

ABOUT THE ORIGINAL:
Original oil painting on canvas. Inspired by early morning walks through northern birch forests where the trees seem to whisper in the breeze.

Each print is carefully produced to capture the depth and luminous quality of the original painting.
```

**Decision needed:** Adjust tone, add/remove sections, change format?

---

## Phase 3: Implementation Options

### Option A: CSV + Basic HTML (Recommended for now)
1. Create CSV with all 58 prints
2. Create simple HTML page to view/edit catalog
3. You copy to Everything Repo
4. Build out web interface later (yourself or with Claude Code)

**Pros:** Quick start, clean data, flexible future
**Cons:** Still need to manually sync CSV if editing in HTML

### Option B: CSV Only
1. Create CSV with all 58 prints
2. Edit in Google Sheets or text editor
3. Generate descriptions row by row

**Pros:** Dead simple, works anywhere
**Cons:** Less visual, harder to see progress at a glance

### Option C: Full Web App (Later)
1. Start with CSV (Option A or B)
2. Later: Build proper interface with filtering, search, bulk editing
3. Could integrate with Etsy API eventually

**Pros:** Maximum functionality
**Cons:** More work upfront, might be overkill

**Decision needed:** Which option for Phase 3?

---

## Phase 4: Web-Ready Images

Currently all images are 30-50MB .tif files (print quality). Need smaller JPEGs for web:
- Etsy: 2000px longest side, under 1MB
- Website thumbnails: 800px, under 200KB

**Process:**
- Batch convert all 58 .tif files to web-optimized JPEGs
- Save in separate folder (e.g., `Art-for-Prints-Web/`)
- Maintain same naming convention

**Decision needed:** Do this now or after descriptions are written?

---

## Workflow: Listing Prints on Etsy

Once setup is complete:
1. Open catalog (CSV or HTML)
2. Pick next "Not Listed" print
3. View the image to refresh memory
4. Fill in description using template
5. Export web JPEG
6. Create Etsy listing
7. Update catalog: mark as "Listed", add Etsy URL
8. Repeat

**Goal:** List 5-10 prints per session to avoid burnout

---

## Questions for You

1. **File renaming:** Rename actual .tif files, or just use standardized names in catalog?
2. **Template:** Does the Etsy description template feel right? Need changes?
3. **Implementation:** Option A (CSV + HTML), B (CSV only), or C (full app later)?
4. **Web images:** Create now or after descriptions?
5. **Artist attribution:** Do you want to identify who painted what publicly, or keep it under "Fairweather"?
6. **Pricing:** All same price, or different prices by size/complexity/artist?

---

## Next Steps (Your Call)

- [ ] Review and edit this plan
- [ ] Answer the questions above
- [ ] I create the CSV with all 58 prints
- [ ] I create Etsy description template (customized based on your edits)
- [ ] Optionally: I create basic HTML viewer
- [ ] You start writing descriptions
- [ ] Batch convert images when ready

---

## Notes
- Keep it simple - the goal is to make money selling prints, not build perfect systems
- Etsy listings are the bottleneck right now - focus there first
- Inventory tracking can evolve as needed
- Shannon might have input on her pieces specifically
