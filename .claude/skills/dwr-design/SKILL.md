---
name: dwr-design
description: Design system for the DWR (Digiwaxx Radio) site at radio.digiwaxx.com. Use for any change to index.html or pre-release-radio-model.html, including copy, new sections, layout, colors, buttons or calls to action, so every edit keeps the same click-funnel look and naming.
---

# DWR design system

The page is a click-funnel style landing page for DWR (Digiwaxx Radio), the pre-release engine that lives at radio.digiwaxx.com. Follow the user's latest instruction first, then this file.

## Naming

- The product is **DWR**. Spell it out once as "DWR (Digiwaxx Radio)" in the hero copy, footer and meta description; use "DWR" everywhere else.
- "Digiwaxx" alone means the company (for example "Digiwaxx automatically publishes"), not the station.

## Files

- `index.html` is the source. `pre-release-radio-model.html` is an exact copy: after every edit run `cp index.html pre-release-radio-model.html`.
- All CSS lives in the single `<style>` block in the head. Add new rules before the `@media print` block.

## Tokens

| Token | Value | Use |
|---|---|---|
| `--purple` | `#6d28d9` | Accent, primary buttons, CTA strips, flow nodes |
| `--purple-dark` | `#4c1d95` | `band-purple` sections, group labels |
| `--lavender` | `#f6f1ff` | `band-soft` sections, chips |
| `--ink` | `#17131d` | Text, `band-dark` sections, announcement bar |
| `--muted` | `#696373` | Body copy on light backgrounds |
| `--line` | `#e8e0f3` | Borders |
| light accent on dark | `#c4b5fd` | Eyebrows, highlights and links on dark or purple bands |

Type: Georgia serif (`.display`, `h3`) for headlines; the system sans stack for body. Headlines pair a black clause with a `<span class="purple">` clause.

## Funnel structure

1. `.announce` bar at the very top with one link to `#pilot`.
2. Sticky nav with section links and a `.nav-cta` button.
3. Hero with one primary `btn primary big` CTA and one secondary `btn big`.
4. `#eight`: the nine parts as a connected `.flow`, grouped into five categories (`.flow-group`: Build the fan base 01-02, Get the story out 03-04, Learn and target 05-06, Prove the airplay 07-08, Keep it on air 09). Each step has a title, a description and a `.value` "Added value" line. Section eyebrows start with the category name.
5. `#journey` (`band-dark`): how a new record moves through DWR in four `.stage` columns (Record added, Pre-release goes live, On air and in front of fans, Release day and report). Each item carries the part number it belongs to.
6. One section per part, alternating backgrounds for variety: plain white, `band-soft`, `band-dark`, `band-purple`. Never put two sections with the same band next to each other.
7. `.cta-strip` bands between groups repeat the one CTA: "Plan your pre-release →" linking to `#pilot`.
8. Report, Why Digiwaxx, What's next, then the `#pilot` sign-up as the final CTA.

## Rules

- Every CTA says "Plan your pre-release →" and points to `#pilot`.
- Do not invent numbers, prices, testimonials, schedules or partner names. Mark targets as targets. Keep the existing "not guaranteed" and "pilot target" disclaimers.
- Numbered markers only for real sequences (the nine parts, step lists).
- Must work at 390px wide with no horizontal scroll; grids collapse to one column at 640px.
- Keep visible focus states and the `prefers-reduced-motion` rule.
- Before committing, screenshot the page at 1280px and 390px (Chromium is at `/opt/pw-browsers/chromium`) and check both.
