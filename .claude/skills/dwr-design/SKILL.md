---
name: dwr-design
description: Design system for the DWR (Digiwaxx Radio) site at radio.digiwaxx.com. Use for any change to index.html or pre-release-radio-model.html, including copy, new sections, layout, colors, buttons or calls to action, so every edit keeps the same Musosoup-style layout and naming.
---

# DWR design system

The page is a landing page for DWR (Digiwaxx Radio), the pre-release engine at radio.digiwaxx.com. Its layout follows the Musosoup homepage model the user chose, but the page is primarily white space: only the nav and hero are navy. Every section after the hero is white, separated by thin lines, with near-black headings, one amber accent, white bordered cards, product mockups instead of illustrations, pilot plan cards and an FAQ. Follow the user's latest instruction first, then this file.

## Naming

- The product is **DWR**. Spell it out as "DWR (Digiwaxx Radio)" in the hero copy, meta description, FAQ answer and footer; use "DWR" elsewhere. The logo is the amber "DWR" mark followed by "Digiwaxx Radio".
- "Digiwaxx" alone means the company (for example "Why Digiwaxx", "Digiwaxx-led pre-release").

## Files

- `index.html` is the source. `pre-release-radio-model.html` is an exact copy: after every edit run `cp index.html pre-release-radio-model.html`.
- All CSS lives in the single `<style>` block. Fonts load from Google Fonts: Poppins (headings, buttons) and DM Sans (body).

## Tokens

| Token | Value | Use |
|---|---|---|
| `--navy` | `#0b1026` | Nav and hero only |
| `--slate` | `#1f2937` | Near-black for headings and labels (no blue) |
| `--mist` | `#f6f7f8` | Small neutral fills inside cards only, never full bands |
| `--amber` | `#f5a524` | Buttons, step numbers, accent in the hero |
| `--amber-ink` | `#a15f00` | Accent text on white (kickers, highlights) |
| `--text` / `--muted` | `#18202f` / `#5a6577` | Body text on light |
| `--on-dark` / `--on-dark-muted` | `#eef1f8` / `#a9b1c7` | Text on navy |

Headlines pair a plain clause with a `<span class="accent">` clause.

## Section order

1. Sticky navy nav with links and a white "Plan your pre-release" button.
2. Hero (`.hero.dark`): headline, DWR intro, white CTA; studio photo with two floating cards (part 01 pre-save, part 07 spin counted) and stat chips (9 parts, 5 categories, 1 report).
3. Channel row (white): the real channels a DWR record goes to. Never add partner logos or names that are not confirmed.
4. `#how` (white): the new-record flow in four numbered stages, then four navy promise tiles.
5. `#parts` (white): the nine parts as tiles in five categories (Build the fan base 01-02, Get the story out 03-04, Learn and target 05-06, Prove the airplay 07-08, Keep it on air 09). Each tile has a number, title, description and "Added value" line.
6. `#details` (white): zigzag rows, one per part, each with copy on one side and an HTML mockup on the other (campaign page, kit page, press page, send-out, rating, affinity rings, spin log + RSS item, show card). Kickers start with the category name.
7. Reach pills, Why Digiwaxx, `#report` (report inside a light bordered "screen"), `#pilot` (Spotify pilot and Apple Music plan cards), `#faq` (`<details>` accordion) and footer, all white.

## Rules

- Every CTA says "Plan your pre-release →" and points to `#pilot` (the pilot card's button points to `#top`).
- Do not invent numbers, prices, testimonials, artist names, schedules or partner names. Mark examples as examples and targets as targets. Keep the "not guaranteed" and "pilot target" disclaimers.
- Keep the page primarily white. Do not add navy, blue or grey-blue bands after the hero; the user rejected them as too blue.
- Must work at 390px wide with no horizontal scroll; grids collapse to one column at 640px.
- Keep visible focus states and the `prefers-reduced-motion` rule.
- Before committing, screenshot the page at 1280px and 390px (Chromium is at `/opt/pw-browsers/chromium`) and check both.
