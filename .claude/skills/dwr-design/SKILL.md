---
name: dwr-design
description: Design system for the DWR (Digiwaxx Radio) site at radio.digiwaxx.com, borrowed from the branderboy/digiwaxx repo (promote.digiwaxx.com). Use for any change to index.html or pre-release-radio-model.html, including copy, new sections, layout, colors, buttons or calls to action.
---

# DWR design system

DWR (Digiwaxx Radio) uses the real Digiwaxx design from the `branderboy/digiwaxx` repo (promote.digiwaxx.com: `index.html` and `assets/light.css`). It is NOT `branderboy/new-digiwaxx`; that is a different project and must not be used. Follow the user's latest instruction first, then this file.

## Look

Digiwaxx is a reference, not a copy. The DWR page takes its palette, type and real assets: white space broken up by soft light purple sections, raspberry accents and buttons, dark plum chrome (nav, hero, footer), one dark CTA block for the pilot. No yellow: the user asked for it to be dropped.

## Naming

- The product is **DWR**. Spell it out as "DWR (Digiwaxx Radio)" in the hero copy, meta description, FAQ answer and footer; use "DWR" elsewhere.
- The logo is the real Digiwaxx logo (`branderboy/digiwaxx/assets/logo.png`, embedded as a data URI) followed by a raspberry "DWR" tag.
- "Digiwaxx" alone means the company.

## Files

- `index.html` is the source. `pre-release-radio-model.html` is an exact copy: after every edit run `cp index.html pre-release-radio-model.html`.
- Fonts from Google Fonts, same as digiwaxx: Barlow Condensed (headings, uppercase, 700/800) and DM Sans (body).
- When editing CSS with a Python `re.sub`, pass the replacement as a function or escape backslashes; otherwise CSS escapes like `\2713` get corrupted.

## Tokens (from digiwaxx)

| Token | Value | Use |
|---|---|---|
| `--plum-ink` | `#1a0a18` | Headings, dark text |
| `--plum` / `--plum-deep` | `#3a0e2a` / `#140812` | CTA block and show card gradient |
| `--magenta` | `#6b0a3d` | Hero top, big step numbers |
| `--accent` | `#9c2b5a` | Kickers, highlights, links on white |
| `--wash` / `--wash-line` | `#f6f1ff` / `#e8e0f3` | Light purple sections and small fills (the user asked for light purple, not rose) |
| `--line` | `#e8e0f3` | Card borders |
| `--body` / `--muted` | `#43303b` / `#83707c` | Body text |
| `--pink` | `#d4a0a0` | Accent on dark: hero highlight, pulse dot, kickers and checkmarks in the pilot block |

## Components

- Nav: `rgba(13,5,13,.92)` with blur, uppercase links, white `nav-cta`.
- Hero: centered, magenta-to-plum gradient, `eyebrow-badge` with `pulse-dot`, uppercase H1 with the Digiwaxx text shadow and a dusty pink `.highlight` clause, white `btn-big` with `btn-subtext`, studio photo with two floating cards, `hero-stats` row (9 parts, 5 categories, 1 report).
- `.btn`: raspberry (`--accent`) with white text on light sections; white with plum text inside the hero, nav and `.cta-block`. Barlow Condensed 800 uppercase.
- Process timeline (`.process` in `#how`): four stages joined by a line, each with a magenta number, a one-line summary, a white list of steps tagged with chips (`.chip.in` what the artist provides, `.chip.part` the DWR part number, `.chip.out` what comes back), and a dark "Result" bar. Rows align across stages with `subgrid`; a legend explains the chips. Keep this structure when editing the process.
- Cards and tiles: white, `--line` border, radius 16px, raspberry hover border.
- `.cta-block`: the one dark island (plum gradient) holding the pilot plan cards.
- Footer: `#0d050d` dark chrome.

## Real Digiwaxx assets in use

- Logo: `branderboy/digiwaxx/assets/logo.png` in the nav and footer; `favicon.svg` (headphones mark) as the tab icon.
- Skyline and radio tower SVG: the `body::after` background from `branderboy/digiwaxx/index.html`, placed along the bottom of the DWR hero.
- DJ booth photo: `branderboy/digiwaxx/assets/video_thumbnail1.webp`, behind the show card (09) and the pilot `.cta-block` under a plum overlay.
- Not used: `100000SONGS.webp` / `digidata.png`. They carry Digiwaxx statistics that DWR cannot claim.

## Section order and backgrounds

Hero (dark) → channels (white) → `#how` (light purple) → `#parts` (white) → `#details` zigzag with mockups (white) → reach pills (light purple) → Why Digiwaxx (white) → `#report` (light purple) → `#pilot` dark CTA block on white → `#faq` (white) → footer (dark).

## Rules

- Keep the current layout and the hero as they are unless the user asks to change them.

- Primarily white space with the light purple sections. No navy, blue or yellow anywhere.
- Every CTA says "Plan your pre-release" and points to `#pilot` (the pilot card's button points to `#top`).
- Do not invent numbers, prices, testimonials, artist names, schedules or partner names. Mark examples as examples and targets as targets. Keep the "not guaranteed" and "pilot target" disclaimers.
- Must work at 390px wide with no horizontal scroll; grids collapse to one column at 640px.
- Keep visible focus states and the `prefers-reduced-motion` rule.
- Before committing, screenshot at 1280px and 390px (Chromium is at `/opt/pw-browsers/chromium`). Google Fonts are blocked in the sandbox, so headings render in a fallback there.
