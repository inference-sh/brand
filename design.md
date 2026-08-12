---
version: alpha
name: inference.sh
description: design system for inference.sh (Inference Shell Inc.)
colors:
  accent: "#FF569D"
  accent-secondary: "#5415FF"
  green: "#00D08A"
  yellow: "#FFF14C"
  lavender: "#F08AFF"
  lime: "#E3FF00"
  blue: "#1CAEFF"
  red: "#FF3333"
  orange: "#FF9900"
  background-light: "#FAFAFA"
  foreground-light: "#0F0F0F"
  background-dark: "#0F0F0F"
  foreground-dark: "#F5F5F5"
  muted-light: "#F0F0F0"
  muted-dark: "#262626"
  border-light: "#DDDDDD"
  border-dark: "#262626"
typography:
  headline:
    fontFamily: Sentient
    fontWeight: 300
    lineHeight: 1.1
    letterSpacing: -0.02em
  body:
    fontFamily: Mona Sans
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.6
  body-strong:
    fontFamily: Mona Sans
    fontSize: 16px
    fontWeight: 700
    lineHeight: 1.6
  wordmark:
    fontFamily: Hack
    fontWeight: 400
  code:
    fontFamily: DM Mono
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
rounded:
  sm: 4px
  md: 6px
  lg: 8px
  xl: 12px
  full: 16px
spacing:
  base: 16px
  xs: 4px
  sm: 8px
  md: 16px
  lg: 32px
  xl: 64px
---

# inference.sh design system

## overview

developer-native, all-lowercase, technically precise. the brand is built around a penrose-inspired logo mark, four primary colors, and a serif/sans type pairing. confident tone, no corporate stiffness, no emojis.

### logo

a penrose-inspired shape. three interlocking triangular paths forming impossible geometry. the inner strokes use green, purple, and yellow; the outer border uses pink. the gradient version fills these paths with three gradient pairs.

the wordmark is `inference shell` set in hack (monospace), always lowercase, composed alongside the logo mark with `gap-2` spacing. never embedded in the logo SVG.

### primary colors

- **pink** `#FF569D` — primary accent. links, selection, active states, CTAs, sidebar highlights.
- **purple** `#5415FF` — secondary accent. comparison tables, developer-facing CTAs, gradient pairings with pink.
- **green** `#00D08A` — success, pricing, infrastructure.
- **yellow** `#FFF14C` — highlight, attention, energy.

### surfaces

light: `#FAFAFA` background, `#0F0F0F` text. dark: `#0F0F0F` background, `#F5F5F5` text.

### fonts

- **sentient** (serif, weight 300) — all headings
- **mona sans** (sans-serif, weights 400/500/700) — body, UI, navigation
- **hack** (monospace, weight 400) — wordmark only
- **dm mono** (monospace, weights 400/500/700) — code blocks, terminal output

## colors

### brand palette

four primary colors, each mapping to a product dimension.

- **pink (#FF569D):** the primary accent across the entire product. links, text selection, sidebar active state, interactive hover states, CTA buttons, announcement banner gradients. visited links use pink at 80% opacity.
- **purple (#5415FF):** secondary accent. used for developer-facing CTAs (paired with pink for "for agents" / "for humans" split), comparison table headers, gradient overlays (`from-brand-purple to-brand-pink`), and decorative blurs.
- **green (#00D08A):** success states, pricing checkmarks, GPU pricing values, nvidia branding, terminal success messages.
- **yellow (#FFF14C):** highlight and attention. used in logo gradients and chart palettes.

### extended palette

- **lavender (#F08AFF):** logo gradient intermediate, chart color in dark mode.
- **lime (#E3FF00):** high-energy accent, sparingly used.
- **blue (#1CAEFF):** intel branding, subscription charts.
- **red (#FF3333):** destructive actions, error states.
- **orange (#FF9900):** AMD branding.
- **teal (#00D08A):** CLI command highlighting, terminal output.

### logo gradients

three gradient pairs used in the gradient-fill logo:

| from | to | use |
|------|----|-----|
| `#FFF14C` | `#FF569D` | yellow to pink |
| `#F08AFF` | `#5415FF` | lavender to purple |
| `#FFF14C` | `#00D08A` | yellow to green |

### ui surface tokens

light mode:

| token | value | use |
|-------|-------|-----|
| background | `#FAFAFA` | page background |
| foreground | `#0F0F0F` | body text |
| primary | `#171717` | buttons, strong text |
| muted | `#F0F0F0` | secondary surfaces |
| muted-foreground | `#666666` | secondary text |
| border | `#DDDDDD` | borders, dividers |
| destructive | `hsl(0 84.2% 60.2%)` | errors, deletions |

dark mode:

| token | value | use |
|-------|-------|-----|
| background | `#0F0F0F` | page background |
| foreground | `#F5F5F5` | body text |
| primary | `#F5F5F5` | buttons, strong text |
| muted | `#262626` | secondary surfaces |
| muted-foreground | `hsl(0 0% 65.9%)` | secondary text |
| border | `#262626` | borders, dividers |

dark mode chart colors map to the brand palette: pink, green, purple, lavender, yellow.

## typography

all lowercase. the brand is lowercase-native across site, blog, social, and product UI. headlines, navigation, CTAs — all lowercase.

- **headings (sentient, weight 300):** all h1-h6, hero text, display text. for marketing heroes, standard tailwind sizes (text-5xl through text-8xl) are used. for body-level headings, the custom scale applies.
- **body (mona sans, weight 400/500/700):** all body copy, UI text, navigation.
- **wordmark (hack, weight 400):** the `inference shell` wordmark in the navbar, footer, and og cards only.
- **code (dm mono, weight 400/500/700):** code blocks, terminal output, technical values.

### type scale (body/UI text)

| token | size |
|-------|------|
| tiny | 0.725rem |
| xs | 0.8rem |
| sm | 0.9rem |
| base | 1rem |
| lg | 1.15rem |
| xl | 1.5rem |
| 2xl | 1.8rem |

marketing hero headings use standard tailwind sizes (text-3xl through text-8xl) beyond this scale.

### font loading

- mona sans: google fonts (400, 500, 700)
- dm mono: google fonts (400, 500, 700)
- sentient: fontshare (300, 400, 500, 700)
- hack: cdnjs (400, preloaded)

### og / social cards

- background: `#FAFAFA`
- title: sentient 300, `#111111`
- description: mona sans 400, `#666666`
- accent eyebrow: `#FF569D`
- wordmark: hack 400, `inference shell`

## layout

8px base grid. the product uses shadcn/ui component primitives with tailwind CSS v4.

### radius scale

| token | value |
|-------|-------|
| sm | `calc(0.5rem - 4px)` |
| md | `calc(0.5rem - 2px)` |
| lg | `0.5rem` |
| xl | `calc(0.5rem + 2px)` |
| 2xl | `calc(0.5rem + 4px)` |
| full | `calc(0.5rem + 8px)` |

## components

### cta button (ghost ring style)

the primary marketing CTA uses a ring-based ghost style, not a solid fill:

```
ring-2 ring-brand-pink/50 bg-brand-pink/10 text-foreground
hover:bg-brand-pink/20 hover:ring-brand-pink/70 rounded-full
```

secondary CTAs use the same pattern with `brand-purple`.

### backdrop card

marketing page content cards use frosted glass:

```
backdrop-blur-sm bg-card/40 border-border/60
```

### terminal chrome

macOS-style window chrome with red/yellow/green dots for terminal mockups, code examples, and product previews.

## logo assets

### mark variants

the logo mark is exported in two container shapes, two rendering styles, multiple background options, and grayscale alternatives.

**container shapes:**
- `circle-logo-*` — circular crop with centered mark, used for avatars and profile images
- `rect-logo-*` — rectangular crop, used for app icons and square placements

**rendering styles:**
- `*-fill-*` — gradient-filled paths (the primary mark)
- `*-outline-*` — stroke-only paths in brand colors

**backgrounds:**
- no suffix — dark background (`#0F0F0F`)
- `*-light*` — light background (`#FAFAFA`)
- `*-transparent*` — transparent background
- `*-grayscale` — monochrome version

### svg variants (logo/svgs/)

all 512x512, ready to use:

| file | shape | style | background |
|------|-------|-------|------------|
| `circle-logo-fill.svg` | circle | gradient fill | dark |
| `circle-logo-fill-light.svg` | circle | gradient fill | light |
| `circle-logo-fill-transparent.svg` | circle | gradient fill | transparent |
| `circle-logo-fill-dark-grayscale.svg` | circle | grayscale fill | dark |
| `circle-logo-fill-light-grayscale.svg` | circle | grayscale fill | light |
| `circle-logo-fill-transparent-grayscale.svg` | circle | grayscale fill | transparent |
| `circle-logo-outline-dark.svg` | circle | color stroke | dark |
| `circle-logo-outline-light.svg` | circle | color stroke | light |
| `circle-logo-outline-transparent.svg` | circle | color stroke | transparent |
| `circle-logo-outline-transparent-dark.svg` | circle | white stroke | transparent |
| `circle-logo-outline-transparent-light.svg` | circle | dark stroke | transparent |
| `circle-logo-outline-dark-grayscale.svg` | circle | grayscale stroke | dark |
| `circle-logo-outline-light-grayscale.svg` | circle | grayscale stroke | light |
| `rect-logo-fill.svg` | rect | gradient fill | dark |
| `rect-logo-fill-light.svg` | rect | gradient fill | light |
| `rect-logo-fill-transparent.svg` | rect | gradient fill | transparent |
| `rect-logo-fill-dark-grayscale.svg` | rect | grayscale fill | dark |
| `rect-logo-fill-light-grayscale.svg` | rect | grayscale fill | light |
| `rect-logo-fill-transparent-grayscale.svg` | rect | grayscale fill | transparent |
| `rect-logo-outline-dark.svg` | rect | color stroke | dark |
| `rect-logo-outline-light.svg` | rect | color stroke | light |
| `rect-logo-outline-transparent.svg` | rect | color stroke | transparent |
| `rect-logo-outline-transparent-dark.svg` | rect | white stroke | transparent |
| `rect-logo-outline-transparent-light.svg` | rect | dark stroke | transparent |
| `rect-logo-outline-dark-grayscale.svg` | rect | grayscale stroke | dark |
| `rect-logo-outline-light-grayscale.svg` | rect | grayscale stroke | light |

### png exports (logo/pngs/)

same variants as SVG, exported at 16, 32, 64, 128, 256, 512, 1024px. naming: `{variant}{size}.png`.

### wordmark pngs (logo/pngs/)

| pattern | content |
|---------|---------|
| `wordmark-domain{size}.png` | `inference.sh` text |
| `wordmark-company{size}.png` | `Inference Shell` text |
| `wordmark-company-legal{size}.png` | `Inference Shell Inc.` text |
| `logo-wordmark-domain{size}.png` | logo mark + `inference.sh` |
| `logo-wordmark-company{size}.png` | logo mark + `Inference Shell` |
| `logo-wordmark-company-legal{size}.png` | logo mark + `Inference Shell Inc.` |

sizes: 64, 128, 256, 512px.

### raw source svgs (logo/)

- `logo-gradient.svg` — the original gradient mark (385x339 viewBox, no container)
- `logo-stroke.svg` — the original stroke mark (399x350 viewBox, no container)

### logo usage rules

- minimum clear space: 1x the logo height on all sides
- minimum size: 32px
- do not rotate, stretch, add drop shadows, or recolor
- do not separate the inner triangles from the outer border
- navbar: 24x24 mark + wordmark at 18px, `gap-2`
- footer: 24x24 mark + wordmark at `text-lg`, `gap-2`

## motion

### logo animation

stroke-dash drawing across six paths (three inner, three outer).

- technique: `stroke-dasharray: 500, 500`, offset animates `-500` to `0` to `500`
- duration: 2s default (variants: 3s small, 8s ambient)
- stagger: 0.05s between paths
- glow: `feGaussianBlur stdDeviation="5"`, opacity 0.8
- dark mode: `mix-blend-mode: screen` on glow, `lighten` on overlay

### loader variants

| variant | size | speed |
|---------|------|-------|
| standard | 240px | 2s |
| small | 60px | 3s |
| ambient | - | 8s |

### landing page animations

- ticker scroll: 40-45s linear infinite
- ring quarters: 90deg steps, 8s
- aurora drift: 14s alternate
- comet streaks: 26-31s vertical
- flicker in/out: 8s staccato

## do's and don'ts

- do use pink as the default accent for any new component
- do keep all text lowercase (headlines, navigation, CTAs, product UI)
- do use sentient for headings and mona sans for body, never mix their roles
- don't use emojis in product writing
- don't use "revolutionary," "game-changing," or exclamation points
- don't use title case where lowercase works
- don't place the logo on busy backgrounds without sufficient contrast
- don't create new color values outside the brand palette for UI elements
