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
- Signature element: the hero, with the studio photo as a full-bleed background under a plum gradient. Keep everything else restrained.
- One number per part (1-9). No section-level numerals (no "1-6", "7-8" or a second "9") and no letters (A/B/C/D) on the new-record stages; the user rejected both.
- No cards, rose fill bands, filled chips or dark result bars. Use hairline rules (`--line`), 2px plum-ink rules to open a list, tables, definition lists and columns split by thin rules.
- The only framed elements are the product mockups (kit page, press page, spin log) and the report document.
- No accent-colored words in section headings (hero and the pull quote excepted). Eyebrow labels only where they carry meaning.
- Keep the hero as it is now unless the user asks.

## Components

- Nav: `rgba(13,5,13,.92)` with blur, uppercase links, white `nav-cta`.
- Hero: the studio photo is the hero background (`right center/cover`), under a left-to-right plum gradient (solid plum on the left where the photo is blank, clear on the right over the artist) plus a dark fade at the bottom. Left-aligned eyebrow badge with pulse dot, uppercase H1 "We are the pre-release app" with a dusty pink clause, white "See how it works" button, stats row 6 / 2 / 1, Digiwaxx skyline along the base. On phones the gradient runs bottom to top.
- `.chapter`: white section separated from the next by a hairline.
- `.journey.process-cards`: the new-record flow as four process cards (the user asked for cards here): white, 6px radius, magenta top rule, stage title and summary, steps tagged with their part number, result line under a magenta rule, arrows between cards (down arrows on phones). No stage numbers or letters.
- `.act` with `.solo-grid`: section head on the left (title and one line, no numeral), numbered parts on the right. `.act-photo` is the full-bleed DJ booth band used for the show.
- `.report-doc`: the sample report as a document (magenta top rule, big 500 target, table).
- `.pilot-band`: full-bleed dark band with the DJ booth photo; plans as two columns split by a rule.
- FAQ: hairline list.
- Footer: `#0d050d` dark chrome.

## Real Digiwaxx assets in use

- Logo: `branderboy/digiwaxx/assets/logo.png` in the nav and footer; `favicon.svg` (headphones mark) as the tab icon.
- Skyline and radio tower SVG: the `body::after` background from `branderboy/digiwaxx/index.html`, placed along the bottom of the DWR hero.
- DJ booth photo: `branderboy/digiwaxx/assets/video_thumbnail1.webp`, behind the Act V band (`.act-photo`) and the pilot band (`.pilot-band`) under a plum overlay.
- Not used: `100000SONGS.webp` / `digidata.png`. They carry Digiwaxx statistics that DWR cannot claim.

## Content: the user's real info only

The page presents only what the user supplied. Do not add invented or borrowed claims, figures, sample screens or pilot terms.

- DWR (Digiwaxx Radio) is the pre-release app, live at radio.digiwaxx.com.
- The pre-release app, parts 1-6, in this order: 1 get pre-saves and followers; 2 the artist creates a kit page that gives context to the newly released song (in-studio clips etc.); 3 DWR automatically publishes a press page on Google News and related; 4 it then gets sent out to the music seeders (theme pages, reposters, fan clubs and related to the music journey); 5 people rate and give feedback via account signup; 6 it promotes the artist's sound to the people with the most affinity.
- The station: 7 the radio station lives on SpinCounts; 8 the station is converted to an RSS feed. Outside tracking: Digital Radio Tracker (DRT), tracking is free and DRT charges per report.
- The show: 9 a repeatable show like a chart show, example "We Play Independent Music."
- "Added value" lines per part were requested by the user.
- Removed as not from the user: the sample report and 500 target, Spotify pilot terms, Apple Music, Why Digiwaxx, FAQ, the problem section, hero floating cards, sample mockups, DRT's 5,000+ station figure.

## Page order

Hero (layout unchanged; copy "We are the pre-release app") → what DWR is (`#what`) → the pre-release app 1-6 (`#app`) → the station 7-8 (`#station`) → the show 9 on the photo band (`#show`) → a new record in DWR (`#flow`) → radio.digiwaxx.com (`#start`) → footer.

## Rules

- Keep the story order and the hero as they are unless the user asks to change them.
- Primarily white space. Light rose only as a faint tint (report document, mockup chips). No navy, blue or yellow anywhere.
- Do not add CTA buttons that lead nowhere. The hero button goes to `#app`; the nav button goes to `#start`.
- Do not invent numbers, prices, testimonials, artist names, schedules or partner names. Mark examples as examples and targets as targets. Keep the "not guaranteed" and "pilot target" disclaimers.
- Must work at 390px wide with no horizontal scroll; grids collapse to one column at 640px.
- Keep visible focus states and the `prefers-reduced-motion` rule.
- Before committing, screenshot at 1280px and 390px (Chromium is at `/opt/pw-browsers/chromium`). Google Fonts are blocked in the sandbox, so headings render in a fallback there.
