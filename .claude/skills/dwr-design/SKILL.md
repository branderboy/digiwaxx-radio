---
name: dwr-design
description: Design system for the DWR (Digiwaxx Radio) site at radio.digiwaxx.com, borrowed from the branderboy/digiwaxx repo (promote.digiwaxx.com). Use for any change to index.html or pre-release-radio-model.html, including copy, new sections, layout, colors, buttons or calls to action.
---

# DWR design system

DWR (Digiwaxx Radio) uses the real Digiwaxx design from the `branderboy/digiwaxx` repo (promote.digiwaxx.com: `index.html` and `assets/light.css`). It is NOT `branderboy/new-digiwaxx`; that is a different project and must not be used. Follow the user's latest instruction first, then this file.

## Look

Digiwaxx's light page: white space broken up by soft light purple sections, raspberry accents, dark plum chrome (nav, hero, footer), one dark CTA block for the pilot, and the yellow gradient button as the only CTA color.

## Naming

- The product is **DWR**. Spell it out as "DWR (Digiwaxx Radio)" in the hero copy, meta description, FAQ answer and footer; use "DWR" elsewhere.
- The logo is the real Digiwaxx logo (`branderboy/digiwaxx/assets/logo.png`, embedded as a data URI) followed by a yellow "DWR" tag.
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
| `--wash` / `--wash-line` | `#faf3f7` / `#f0e0e9` | Light purple sections and small fills |
| `--line` | `#ecdce5` | Card borders |
| `--body` / `--muted` | `#43303b` / `#83707c` | Body text |
| `--yellow` / `--yellow-hi` | `#FFB800` / `#FFE066` | Primary CTA only, eyebrow pulse dot, highlight chip |
| `--pink` | `#d4a0a0` | Accent text on dark |

## Components

- Nav: `rgba(13,5,13,.92)` with blur, uppercase links, yellow `nav-cta`.
- Hero: centered, magenta-to-plum gradient, `eyebrow-badge` with `pulse-dot`, uppercase H1 with a yellow `.highlight` (inline, `box-decoration-break: clone`), yellow `btn-big` with `btn-subtext`, studio photo with two floating cards, `hero-stats` row (9 parts, 5 categories, 1 report).
- `.btn`: yellow gradient, Barlow Condensed 800 uppercase, dark text.
- Step cards (`.stages li`): white, radius 16px, big magenta Barlow number.
- Cards and tiles: white, `--line` border, radius 16px, raspberry hover border.
- `.cta-block`: the one dark island (plum gradient) holding the pilot plan cards.
- Footer: `#0d050d` dark chrome.

## Section order and backgrounds

Hero (dark) → channels (white) → `#how` (light purple) → `#parts` (white) → `#details` zigzag with mockups (white) → reach pills (light purple) → Why Digiwaxx (white) → `#report` (light purple) → `#pilot` dark CTA block on white → `#faq` (white) → footer (dark).

## Rules

- Primarily white space with the light purple sections. No navy or blue anywhere.
- Every CTA says "Plan your pre-release" and points to `#pilot` (the pilot card's button points to `#top`).
- Do not invent numbers, prices, testimonials, artist names, schedules or partner names. Mark examples as examples and targets as targets. Keep the "not guaranteed" and "pilot target" disclaimers.
- Must work at 390px wide with no horizontal scroll; grids collapse to one column at 640px.
- Keep visible focus states and the `prefers-reduced-motion` rule.
- Before committing, screenshot at 1280px and 390px (Chromium is at `/opt/pw-browsers/chromium`). Google Fonts are blocked in the sandbox, so headings render in a fallback there.
