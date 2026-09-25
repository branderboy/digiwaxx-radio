---
name: visual-art-direction
description: This skill should be used whenever creating, redesigning, styling, beautifying, or significantly modifying a website, landing page, dashboard, application, component, marketing page, or other visual interface. Prevents repetitive AI-generated layouts, card grids, generic SaaS aesthetics, and recycled color systems.
version: 1.0.0
---

# Visual Art Direction

Act as a senior digital art director before acting as a frontend developer.

Do not begin by choosing components.

Begin by deciding what the page should visually FEEL like, how information should flow, what deserves visual dominance, and what makes this particular project different from the last one.

## Primary rule

Never design from a component library outward.

Design from:

1. subject matter
2. audience
3. brand
4. purpose
5. content hierarchy
6. imagery
7. typography
8. spatial composition

Components come last.

## Kill the default AI layout

Do not automatically turn content into cards.

A card must have an actual structural reason to exist:
- independently actionable object
- independently selectable object
- repeated dataset item
- movable/modular object
- object requiring clear containment

Otherwise use normal composition.

Prefer:
- editorial sections
- open layouts
- columns
- split compositions
- strong typography
- full-width imagery
- asymmetric grids
- staggered content
- horizontal bands
- vertical storytelling
- overlapping elements
- intentional whitespace
- inline statistics
- tables
- lists
- timelines
- galleries
- diagrams
- text integrated directly into the page

Do not wrap every idea in a rounded rectangle.

## Forbidden defaults

Unless the project specifically requires them, avoid:

- grids of 3 identical cards
- grids of 4 identical cards
- every section being a card
- cards inside cards
- excessive rounded corners
- one border radius used on everything
- floating white boxes over pale backgrounds
- generic dashboard tile layouts
- purple-to-blue gradients
- cyan/purple startup palettes
- identical dark navy SaaS themes
- neon glow for no reason
- glassmorphism by default
- gradient blobs
- abstract glowing circles
- icon inside colored circle above every heading
- excessive pills
- excessive badges
- giant rounded CTA containers
- generic testimonial cards
- generic pricing cards unless pricing genuinely needs comparison
- three-column "features" sections by default
- alternating icon/text blocks repeated down the page
- fake metrics used primarily as decoration
- "01 / 02 / 03" numbering unless information is sequential
- eyebrow text above every heading
- ALL CAPS micro-labels everywhere
- arrows appended to every link
- excessive drop shadows
- excessive borders
- gratuitous gradients
- repeated section composition

## Color

Do not recycle the same palette between projects.

Extract color direction from the actual brand first.

When an existing site or brand exists:
- inspect it
- identify primary, secondary, neutral and accent colors
- preserve recognizable brand equity
- extend the palette rather than replacing it arbitrarily

Use one dominant visual world.

Do not distribute five accent colors evenly just because they are available.

Color hierarchy should be intentional.

Before implementing, explicitly identify:

PRIMARY
SECONDARY
ACCENT
SURFACE
TEXT
MUTED
BORDER

Not every project needs all seven.

Avoid automatically using:
- #111827
- #0F172A
- #6366F1
- #8B5CF6
- #7C3AED

unless supported by the actual brand.

## Typography

Typography is part of the layout.

Do not default to:
- Inter
- Arial
- Roboto
- system-ui
- Space Grotesk

unless already part of the brand.

Choose typography according to the subject.

Use scale, width, weight, line-height and spacing to create hierarchy before adding containers.

A page with excellent typography and simple composition is preferable to mediocre typography surrounded by decorative UI.

Avoid highlighting random headline words with gradient text, italics, or accent colors simply to create visual interest.

## Composition

Every page needs a composition idea.

Before coding, choose one.

Examples:

Editorial:
large type + strong image + flowing sections

Utility:
dense information + strict hierarchy + minimal decoration

Luxury:
restraint + typography + large imagery + generous spacing

Local service:
real work + clear trust signals + direct calls to action

Entertainment:
visual rhythm + expressive imagery + controlled movement

Technical:
structured information + diagrams + code/data + precision

Retail:
product imagery + merchandising hierarchy + conversion path

These are directions, not templates.

Never use the same composition merely because it worked on another project.

## Section rhythm

Adjacent sections should not all have identical geometry.

Vary rhythm intentionally.

For example:

large visual
→ concise text
→ dense information
→ whitespace
→ comparison
→ strong CTA

rather than:

card grid
→ card grid
→ card grid
→ card grid
→ CTA card

The page should have pacing.

## Shape language

Determine shape language from the brand.

Not everything needs rounded corners.

Possible systems include:
- square
- barely rounded
- mixed radius
- sharp editorial
- circular accents
- organic
- industrial
- geometric

Use radius to communicate hierarchy rather than applying `rounded-xl` everywhere.

## Imagery

Real imagery should do meaningful visual work.

Do not shrink strong photography into tiny cards just to preserve a UI grid.

When appropriate:
- let photography bleed
- crop aggressively
- use large editorial images
- layer content against imagery
- use documentary-style images
- create irregular image rhythm

Avoid fake stock-photo perfection when the brand calls for authenticity.

## Icons

Icons are functional symbols, not decoration.

Do not add an icon to every paragraph or feature merely because an icon library exists.

Use icons when they improve recognition or navigation.

## Dashboard rule

Dashboards do not automatically mean "a page full of cards."

Differentiate:
- controls
- metrics
- trends
- status
- primary work area
- navigation
- tables
- alerts

Use hierarchy and layout instead of putting everything inside interchangeable boxes.

## Marketing-page rule

Do not automatically use:

Hero
Features cards
Stats cards
Testimonials cards
Pricing cards
FAQ
CTA box

Determine the actual persuasion sequence from the product and audience.

## Existing-site redesigns

Before changing the visual system:

1. inspect existing styles
2. inspect screenshots if available
3. identify what should remain recognizable
4. identify the weak design patterns
5. identify repeated AI-looking patterns
6. create a new composition strategy
7. then implement

Do not redesign simply by changing colors and border radius.

## Design plan before implementation

Before writing substantial JSX/CSS, internally establish:

### Visual concept
One sentence describing the art direction.

### Composition
Describe how the page is organized spatially.

### Typography
Typeface roles, scale and personality.

### Palette
Actual colors based on the project.

### Signature element
Choose ONE memorable visual idea.

Examples:
- exceptional hero photography
- unusual type scale
- distinctive navigation
- immersive product preview
- editorial grid
- interactive comparison
- unconventional page rhythm

Spend visual boldness here.

Keep supporting areas restrained.

## Repetition test

Before finishing, inspect the entire page.

Ask:

"Could I swap this project's copy with a completely unrelated startup and the design would still make sense?"

If yes, the design is too generic.

Ask:

"Am I repeatedly using containers because I need them, or because cards are easy?"

Remove unnecessary containers.

Ask:

"Are multiple sections using essentially the same layout?"

Change the composition where useful.

Ask:

"Did I choose these colors because of this brand or because I commonly generate them?"

Correct the palette if necessary.

## Screenshot critique

When browser or screenshot tools are available:

1. render the page
2. inspect the screenshot visually
3. ignore implementation effort
4. critique it like an art director
5. identify AI tells
6. revise
7. inspect again

Specifically look for:
- too many boxes
- excessive symmetry
- repeated spacing
- weak hierarchy
- random color
- generic typography
- excessive corner radius
- unnecessary decorations
- tiny imagery
- sections that feel interchangeable

Do not consider the design finished merely because the implementation works.

## Final principle

A professionally designed interface does not mean adding more UI.

Often the strongest move is removing:
- a container
- a border
- an icon
- a background
- a badge
- a shadow
- a gradient
- a column

Create hierarchy through composition first.
