# AGENTS.md

Brand kit repository for Warthog Network. Asset-only — no source code, build, test, or lint commands.

## Contents

- `fonts/Montserrat.zip` — official brand font (extract to use).
- `logo/` — all logo assets (SVG + PNG) in a single flat directory, plus `DISCORD.png` (pre-sized Discord banner). Use SVG for any digital/print work; use PNG only when SVG is not an option.
- `colors/` — SVG swatches for visual representation in `README.md` only. Not important for AGENTS — the hex values are already documented in the Color palette section below.
- `README.md` — visual catalogue of every variant × color-scheme combination, with clickable thumbnails.
- `Guideline/WT_Guidelines.md` and `Guideline/WT_Guidelines.pdf` — **removed**. The full brand spec is now in `README.md` (color palette, logo variants, restrictions, fonts). The PDF is no longer shipped; if you need the historical PDF, regenerate it from `Warthog_2024.ai` (which is also no longer in this repo — see "Conventions" below).
- `Warthog_2024.ai` / `Warthog_2024.pdf` — **removed**. The editable Illustrator source and its flattened preview are not tracked in this repo anymore. Recreate them from the README catalogue if needed.

## Logo directory layout

`logo/` is flat — no subfolders. Files are named `<Variant> <ColorScheme>.<ext>`, e.g. `Circle Black.png`, `Full Yellow.svg`.

**Variants (filename prefix):** `Full` (full horizontal lockup), `Circle`, `Short`, `Stacked`, `Ticker`.

**Color schemes (filename suffix):**

| Suffix | Role | Available on |
|--------|------|--------------|
| `Yellow` | Primary mark in brand yellow. | All variants |
| `Black` | Monochrome on light backgrounds. | All variants |
| `White` | For dark backgrounds. | `Short` and `Ticker` only |
| `BW` | Black-and-white fallback (no yellow). | `Full`, `Circle`, `Stacked`, `Ticker` (not `Short`) |
| `Negative` | Inverted for dark backgrounds, keeps brand colors. | `Full`, `Circle`, `Short`, `Stacked` (not `Ticker`) |
| `Negative Yellow` | Inverted with yellow as the dominant fill. | `Full`, `Circle`, `Stacked` (not `Short` or `Ticker`) |

Each combination ships as both `.svg` and `.png`. PNGs are pre-rasterized for surfaces that don't support SVG; SVGs are the canonical scalable form.

Pick the variant + scheme that matches the target surface. Do not recolor — use the prebuilt variant.

## Color palette

Sourced from the original `WT_Guidelines.pdf` (V01.A, 2023·2024, by BalkyBot). Palette is tuned for **electronic displays** (web, mobile, presentations, video); print output may shift slightly.

### Primary palette

Visual order from the guideline's 3×3 grid (read column-by-column):

| Hex | Role | CMYK | Pantone |
|-----|------|------|---------|
| `#FDB913` | Brand yellow — primary | `30, 100` | `1375 C` |
| `#F25C05` | Red-orange | — | — |
| `#000000` | Black | — | — |
| `#E79300` | Orange | — | — |
| `#FFFFFF` | White | `0, 0, 0, 0` | — |
| `#E9E9E9` | Light gray — **backgrounds only**, not for marks | — | — |
| `#F20544` | Red / pink | — | — |
| `#035AA6` | Blue — supporting illustration only | — | — |
| `#033298` | Deep blue — supporting illustration only | — | — |

`#035AA6` and `#033298` are decorative — they appear in supporting illustration but not in the logo SVG tokens.

### Gradients (all end on `#FDB913`)

- `#F25C05 → #FDB913`
- `#E79300 → #FDB913`
- `#F20544 → #FDB913`

### Usage rules

- Never use colors outside the approved palette on the logo.
- For dark/colored photo backgrounds, place the logo on a square white plate — the `Negative` variants already provide this.
- The `BW` / Wireframe treatment is the fallback for maximum contrast over busy textures.

## Logo SVG tokens

Every exported logo SVG defines only these four CSS tokens — a strict subset of the primary palette:

| Token | Hex | Matches palette |
|-------|-----|-----------------|
| `st0` | `#F8F8F9` | near `#FFFFFF` (paper off-white) |
| `st1` | `#FDB913` | brand yellow |
| `st2` | `#231F20` | near-black (off `#000000`) |
| `st3` | `#FFFFFF` | white |

`#231F20` is intentionally not pure `#000000` — the logo's near-black and the paper off-white `#F8F8F9` are softer than the guideline primaries. When producing new assets in code/design tools, use the SVG tokens as exported; do **not** "normalize" them back to `#000000` / `#FFFFFF`.

## Typography

Montserrat only (provided in `fonts/Montserrat.zip`). Unzip before referencing weights in design files. Per the guidelines: **Montserrat Bold** for titles, **Montserrat (Family)** for text blocks.

## Conventions

- **Filename pattern:** `<Variant> <ColorScheme>.<ext>` — note the **single space** between variant and color scheme, and lowercase `.png` / `.svg` extension. No `@4x` suffix, no subfolders.
- **Variant + scheme matching:** match the available-on column above. If you need a missing combination (e.g. `Ticker Negative`), don't invent one — request it.
- **New variants or color schemes** should follow the existing naming, use only the primary palette colors, and ship as both SVG and PNG.
- **Editing the master logo:** this repo no longer tracks `Warthog_2024.ai`. The README is the visual reference; if a new derivative is needed, recreate the master file outside this repo, then re-export the SVG and PNG and place them in `logo/`.
- **Discord banner:** `logo/DISCORD.png` is pre-sized. For higher fidelity, recreate outside this repo and overwrite it.
- **Branch:** `master`. No CI, no pre-commit hooks, no formatter.

## Discord banner

`logo/DISCORD.png` is sized for Discord server banners; do not upscale it. For higher fidelity, recreate the master logo and export at the target dimensions.
