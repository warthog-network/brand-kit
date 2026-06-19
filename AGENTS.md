# AGENTS.md

Brand kit repository for Warthog Network. Asset-only — no source code, build, test, or lint commands.

## Contents

- `Fonts/Montserrat.zip` — official brand font (extract to use).
- `Guideline/WT_Guidelines.pdf` — full brand guidelines (logo usage, spacing, do/don't). Read this before producing brand assets.
- `Warthog_2024.ai` — editable Adobe Illustrator source for the logo system.
- `Warthog_2024.pdf` — flattened preview of the AI file.
- `SVGs/` — vector logos (use these for any digital/print work).
- `PNGs/` — raster previews at `@4x` (use only when SVG is not an option).
- `DISCORD.png` — pre-sized Discord banner.

## SVG / PNG layout

Both formats are organized by logo variant, then by color scheme:

- **Variants (subfolders / filename prefix):** `Circle`, `Short`, `Stacked`, `Ticker`. The unprefixed files in `SVGs/` and the `Full*` files in `PNGs/` are the full horizontal lockups.
- **Color schemes (filename suffix):**
  - `Black` — primary, monochrome on light backgrounds.
  - `Yellow` / `Yellow-19` / `Yellow_1` — primary mark in brand yellow (see "Naming quirks" below).
  - `White` — for dark backgrounds (only on `Short` and `Ticker` variants).
  - `BW` / `BW-07` — black-and-white fallback (no yellow).
  - `Negative` — inverted for dark backgrounds, keeps brand colors.
  - `Negative Yellow` — inverted with yellow as the dominant fill.

Pick the variant + scheme that matches the target surface. Do not recolor — use the prebuilt variant.

## Color palette

Sourced from `Guideline/WT_Guidelines.pdf` (page 10, "COLOURS"). Palette is tuned for **electronic displays** (web, mobile, presentations, video); print output may shift slightly.

### Primary palette

| Hex       | Role                                            | CMYK      | Pantone   |
|-----------|-------------------------------------------------|-----------|-----------|
| `#FDB913` | Brand yellow — primary                          | `30, 100` | `1375 C`  |
| `#E79300` | Orange                                          | —         | —         |
| `#F25C05` | Red-orange                                      | —         | —         |
| `#F20544` | Red / pink                                      | —         | —         |
| `#000000` | Black                                           | —         | —         |
| `#FFFFFF` | White                                           | `0, 0, 0, 0` | —     |
| `#E9E9E9` | Light gray — **backgrounds only**, not for marks | —         | —         |

### Gradients (all end on `#FDB913`)

- `#F25C05 → #FDB913`
- `#E79300 → #FDB913`
- `#F20544 → #FDB913`

### Secondary / accent colors

Used in supporting illustration (page 2 hero): `#22D3B1` (teal) and `#033298` (deep blue). Treat as decorative accents only — they do not appear in the logo SVG tokens.

### SVG file tokens (`.st0`–`.st3`)

Every exported SVG defines only these four CSS tokens — they are a strict subset of the primary palette:

| Token | Hex       | Matches palette    |
|-------|-----------|--------------------|
| st0   | `#F8F8F9` | near `#FFFFFF`     |
| st1   | `#FDB913` | brand yellow       |
| st2   | `#231F20` | near-black (off `#000000`) |
| st3   | `#FFFFFF` | white              |

`#231F20` is intentionally not pure `#000000` — the logo's near-black and the paper off-white `#F8F8F9` are softer than the guideline primaries. When producing new assets in code/design tools, use the SVG tokens as exported; do not "normalize" them back to `#000000` / `#FFFFFF`.

### Usage rules (from the guideline)

- Never use colors outside the approved palette on the logo (logo restriction, page 7).
- For dark/colored photo backgrounds, place the logo on a square white plate (the "Negative" variants already provide this).
- The "Wireframe" / B&W treatment is the fallback for maximum contrast over busy textures.

## Typography

Montserrat only (provided in `Fonts/Montserrat.zip`). Unzip before referencing weights in design files. Per the guidelines: **Montserrat Bold** for titles, **Montserrat (Family)** for text blocks.

## Naming quirks (do not "clean up")

- `SVGs/Stacked/Warthog_2024_Stacked Yellow-19.svg` and `PNGs/Stacked/Stacked Yellow_1@4x.png` are intentional surviving variants from earlier iterations. Do not delete them; they are tracked on purpose alongside the current `Yellow` versions.
- `SVGs/Warthog_2024_BW-07.svg` and `PNGs/Full BW_1@4x.png` likewise: the `-07` / `_1` suffixes are not noise.
- Filenames use `@4x` to denote 4x export scale on PNGs.
- macOS `.DS_Store` files are tracked; leave them alone.

## Conventions

- Vector source for any new logo derivative: edit `Warthog_2024.ai`, then re-export both the SVG (in the matching `SVGs/<Variant>/` folder) and the PNG (`PNGs/<Variant>/` at `@4x`).
- New color schemes should follow the existing naming (`<Variant> <Scheme>@4x.png`, `Warthog_2024_<Variant> <Scheme>.svg`) and use only the four palette colors above.
- Branch: `master`. No CI, no pre-commit hooks, no formatter.

## Discord banner

`DISCORD.png` is sized for Discord server banners; do not upscale it. For higher fidelity, recreate from `Warthog_2024.ai` and export at target dimensions.
