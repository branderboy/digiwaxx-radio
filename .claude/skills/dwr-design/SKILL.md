---
name: dwr-design
description: Design system for the DWR (Digiwaxx Radio) site at radio.digiwaxx.com, borrowed from the branderboy/digiwaxx repo (promote.digiwaxx.com). Use for any change to index.html or pre-release-radio-model.html, including copy, new sections, layout, colors, buttons or calls to action.
---

# DWR design system

DWR (Digiwaxx Radio) uses the real Digiwaxx design from the `branderboy/digiwaxx` repo (promote.digiwaxx.com: `index.html` and `assets/light.css`). It is NOT `branderboy/new-digiwaxx`; that is a different project and must not be used. Follow the user's latest instruction first, then this file.

## Look

Digiwaxx is a reference, not a copy. The DWR page takes its palette, type and real assets: white space broken up by soft light rose sections, raspberry accents and buttons, dark plum chrome (nav, hero, footer), one dark CTA block for the pilot. No yellow: the user asked for it to be dropped.

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
| `--wash` / `--wash-line` | `#faf3f7` / `#f0e0e9` | Light rose sections and small fills (the user approved light rose) |
| `--line` | `#ecdce5` | Card borders |
| `--body` / `--muted` | `#43303b` / `#83707c` | Body text |
| `--pink` | `#d4a0a0` | Accent on dark: hero highlight, pulse dot, kickers and checkmarks in the pilot block |

## Art direction

Always apply `.claude/skills/visual-art-direction/SKILL.md` as well. The user rejected boxed, card-heavy layouts ("everything is blocks", "doesn't tell a story").

- Concept: the page reads like the liner notes of one record, from studio to release day. Editorial type on white, rules instead of boxes, one dark radio-night band.
- Signature element: the five acts (Act I to Act V) with huge pale rose numerals down the left, like a tracklist. Keep boldness there; keep everything else restrained.
- No cards, rose fill bands, filled chips or dark result bars. Use hairline rules (`--line`), 2px plum-ink rules to open a list, tables, definition lists and columns split by thin rules.
- The only framed elements are the product mockups (kit page, press page, spin log) and the report document.
- No accent-colored words in section headings (hero and the pull quote excepted). Eyebrow labels only where they carry meaning.
- Keep the hero exactly as it is.

## Components

- Nav: `rgba(13,5,13,.92)` with blur, uppercase links, white `nav-cta`.
- Hero (unchanged): magenta-to-plum gradient, eyebrow badge with pulse dot, uppercase H1 with dusty pink clause, white button, studio photo with two floating cards, stats row, Digiwaxx skyline along the base.
- `.chapter`: white section separated from the next by a hairline.
- `.journey`: the four-stage process as ruled columns (big magenta stage number, title, summary, steps with In / part number / Out in accent type, result line under a magenta rule).
- `.act`: three-column story block (sticky act head, parts, one visual). `.act-photo` is the full-bleed DJ booth band used for Act V.
- `.report-doc`: the sample report as a document (magenta top rule, big 500 target, table).
- `.pilot-band`: full-bleed dark band with the DJ booth photo; plans as two columns split by a rule.
- FAQ: hairline list.
- Footer: `#0d050d` dark chrome.

## Real Digiwaxx assets in use

- Logo: `branderboy/digiwaxx/assets/logo.png` in the nav and footer; `favicon.svg` (headphones mark) as the tab icon.
- Skyline and radio tower SVG: the `body::after` background from `branderboy/digiwaxx/index.html`, placed along the bottom of the DWR hero.
- DJ booth photo: `branderboy/digiwaxx/assets/video_thumbnail1.webp`, behind the Act V band (`.act-photo`) and the pilot band (`.pilot-band`) under a plum overlay.
- Not used: `100000SONGS.webp` / `digidata.png`. They carry Digiwaxx statistics that DWR cannot claim.

## Story order

Hero → channel credits line → the problem (statement + three ruled points) → pull quote → how it works (`.journey`) → five acts (I Build the fan base 01-02, II Get the story out 03-04, III Learn and target 05-06, IV Prove the airplay 07-08, V Keep it on air 09 on the photo band) → release day report → why Digiwaxx → pilot band → FAQ → footer.

## Rules

- Keep the story order and the hero as they are unless the user asks to change them.
- Primarily white space. Light rose only as a faint tint (report document, mockup chips). No navy, blue or yellow anywhere.
- Every CTA says "Plan your pre-release" and points to `#pilot` (the pilot card's button points to `#top`).
- Do not invent numbers, prices, testimonials, artist names, schedules or partner names. Mark examples as examples and targets as targets. Keep the "not guaranteed" and "pilot target" disclaimers.
- Must work at 390px wide with no horizontal scroll; grids collapse to one column at 640px.
- Keep visible focus states and the `prefers-reduced-motion` rule.
- Before committing, screenshot at 1280px and 390px (Chromium is at `/opt/pw-browsers/chromium`). Google Fonts are blocked in the sandbox, so headings render in a fallback there.
