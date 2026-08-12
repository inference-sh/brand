# design system

## logo

a penrose-inspired shape — three interlocking triangular paths forming impossible geometry. represents convergence: apps, skills, knowledge, agents, connectors, compute fitting together as one coherent platform.

### variants

| file | use |
|------|-----|
| `logo/logo-gradient.svg` | primary mark. gradient fills. hero sections, splash screens, keynotes. |
| `logo/logo-stroke.svg` | full-size stroke version. four brand colors on transparent. presentations, large format. |

### usage rules

- minimum clear space: 1x the logo height on all sides
- minimum size: 32px
- do not rotate, stretch, add drop shadows, or place on busy backgrounds without sufficient contrast
- do not rearrange or separate the inner triangles from the outer border
- the logo is always used without a wordmark lockup — the wordmark "inference.sh" is set in hack and placed separately

### wordmark

set in **hack** (monospace). always lowercase: `inference.sh`. the wordmark is not embedded in the logo SVG — compose it alongside the logo mark with appropriate spacing.

alternative short forms: `infsh`, `belt` (CLI name).

## colors

### brand palette

four primary colors, each mapping to a product dimension. **pink is the primary accent** — used for links, selection, active states, and the default brand touch point.

| name | hex | hsl | role |
|------|-----|-----|------|
| **pink** | `#FF569D` | `330 100% 67%` | **primary accent**. links, selection, active states, CTAs. |
| green | `#00D08A` | `161 100% 41%` | secondary. success, growth, infra. |
| purple | `#5415FF` | `255 100% 54%` | tertiary. depth, premium, developer. |
| yellow | `#FFF14C` | `56 100% 65%` | highlight. attention, warnings, energy. |

### extended palette

| name | hex | hsl |
|------|-----|-----|
| lavender | `#F08AFF` | `291 100% 77%` |
| lime | `#E3FF00` | `69 100% 50%` |
| blue | `#1CAEFF` | `201 100% 55%` |
| red | `#FF3333` | `0 100% 60%` |
| orange | `#FF9900` | `36 100% 50%` |
| teal | `#00D08A` | `161 100% 41%` |

### logo gradients

three gradient pairs used in the gradient logo:

| gradient | from | to |
|----------|------|----|
| yellow → pink | `#FFF14C` | `#FF569D` |
| lavender → purple | `#F08AFF` | `#5415FF` |
| yellow → green | `#FFF14C` | `#00D08A` |

### ui surfaces

light mode:

| token | hsl | use |
|-------|-----|-----|
| background | `0 0% 98%` | page background (`#FAFAFA`) |
| foreground | `0 0% 5.9%` | body text (`#0F0F0F`) |
| primary | `0 0% 9%` | buttons, strong text (`#171717`) |
| muted | `0 0% 94.1%` | secondary surfaces (`#F0F0F0`) |
| muted-foreground | `0 0% 40%` | secondary text (`#666666`) |
| border | `0 0% 86.8%` | borders, dividers (`#DDDDDD`) |
| destructive | `0 84.2% 60.2%` | errors, deletions |

dark mode:

| token | hsl | use |
|-------|-----|-----|
| background | `0 0% 5.9%` | page background (`#0F0F0F`) |
| foreground | `0 0% 96%` | body text (`#F5F5F5`) |
| primary | `0 0% 96%` | buttons, strong text |
| muted | `0 0% 14.9%` | secondary surfaces (`#262626`) |
| muted-foreground | `0 0% 65.9%` | secondary text |
| border | `0 0% 14.9%` | borders, dividers |

accent color across both modes: **brand-pink** (`#FF569D`). used for links, text selection highlight, sidebar active state, interactive hover states.

### color usage conventions

- links: `text-brand-pink`, visited: `text-brand-pink/80`
- text selection: pink background with primary-foreground text
- announcement banners: `gradient from-brand-purple to-brand-pink`
- charts (dark mode): pink, green, purple, lavender, yellow — maps to brand palette
- hardware vendors: green=nvidia, orange=amd, blue=intel, purple=gpu, pink=cpu

## typography

all lowercase. the brand is lowercase-native across site, blog, social, and product UI. headlines, navigation, CTAs — all lowercase.

### font stack

| role | font | weight | use |
|------|------|--------|-----|
| body | mona sans | 400, 500, 700 | all body copy, UI text, navigation |
| headings | sentient | 300 | h1–h6, display text, hero titles |
| logo/wordmark | hack | 400 | the `inference.sh` wordmark only |
| code | dm mono | 400, 500, 700 | code blocks, terminal output, technical values |

### loading

- mona sans: [google fonts](https://fonts.google.com/specimen/Mona+Sans) (400, 500, 700)
- dm mono: [google fonts](https://fonts.google.com/specimen/DM+Mono) (400, 500, 700)
- sentient: [fontshare](https://www.fontshare.com/fonts/sentient) (300, 400, 500, 700)
- hack: [cdnjs](https://cdnjs.cloudflare.com/ajax/libs/hack-font/3.3.0/web/hack.min.css) (400)

### type scale

| token | size |
|-------|------|
| tiny | 0.725rem |
| xs | 0.8rem |
| sm | 0.9rem |
| base | 1rem |
| lg | 1.15rem |
| xl | 1.5rem |
| 2xl | 1.8rem |

### og / social cards

- background: `#FAFAFA`
- title: sentient 300, `#111111`
- description: mona sans 400, `#666666`
- accent eyebrow: brand-pink `#FF569D`
- wordmark: hack 400

## motion

### logo animation

the animated logo uses stroke-dash drawing. each of the six paths (three inner, three outer) draws on and off in sequence.

- technique: `stroke-dasharray: 500, 500` with offset animating from `-500` → `0` → `500`
- duration: 2s ease-in-out, infinite loop
- stagger: 0.02s between paths
- glow: `feGaussianBlur stdDeviation="5"`, opacity 0.8
- dark mode: `mix-blend-mode: screen` on glow layer, `lighten` on overlay

### loader variants

| variant | size | speed | style |
|---------|------|-------|-------|
| standard | 240px | 3s | animated glow |
| fast | 240px | 1s | animated glow |
| small | 60px | 3s | animated glow |
| small fast | 60px | 1s | animated glow |
| mono | 240px | 3s | monochrome glow |
| small mono | 60px | 3s | monochrome glow |
| ambient | - | 8s | slow decorative |
| static | - | - | no animation |

### ui transitions

- accordion expand/collapse: 0.2s ease-out
- typing indicator: 1.4s bounce, translateY(-4px) at 30%
- login gradient rotation: 40s linear infinite (360deg)
- login gradient crossfade: 5s cycle through three gradient pairs

### landing page

- ticker scroll: 40–45s linear infinite
- ring quarters: 90deg steps, 8s
- aurora drift: 14s alternate
- comet streaks: 26–31s vertical
- flicker in/out: 8s staccato

## spacing & radius

- base radius: `0.5rem`
- sm: `calc(radius - 4px)`
- md: `calc(radius - 2px)`
- lg: `radius`
- xl: `calc(radius + 4px)`
- 2xl: `calc(radius + 4px)`
- full: `calc(radius + 8px)`

## voice & tone

technically precise, developer-native, confident. no exclamation points, no "revolutionary," no emojis. treats the reader as a peer. all lowercase where possible. short-form (X/social) is sparse, almost poetic.

full voice guidelines: see `brand.md` in the main repo.

## asset checklist

what's available and what to request from the team:

**included in this repo:**
- [x] logo mark — gradient fill (SVG)
- [x] logo mark — four-color stroke, full size (SVG)

**export on request** (source files in the product repo):
- [ ] logo mark — PNG exports at 16, 32, 64, 128, 256, 512, 1024px
- [ ] favicon — ICO and PNG (currently base64-embedded in product)
- [ ] og card template — React component, exportable
- [ ] animated logo — requires the React component (`logo-base.tsx`)
- [ ] wordmark lockups — logo + "inference.sh" in hack, horizontal and stacked
- [ ] color swatches — ASE/CLR/Sketch palette files
- [ ] presentation template — keynote/google slides with brand fonts and colors
- [ ] document template — word/google docs with brand fonts and heading styles
