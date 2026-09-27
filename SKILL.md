---
name: slava-style
description: Replicates the visual design style of Slava Kornilov (creative director of Geex Arts) — editorial, magazine-like web/UI design with desaturated Morandi palettes on black/white/gray bases, oversized expressive typography, broken asymmetric grids, image-text interweaving, generous whitespace, and one small high-contrast accent color. Use when the user asks for "Slava style", "Kornilov style", a luxury/editorial/fashion-style landing page or website, Morandi-palette UI, 莫兰迪配色设计, 杂志感排版, 图文穿插/错落布局页面, or any website/widget/poster for official sites, finance, or AI products that should feel clean, quiet-luxury and professional rather than flashy.
---

# Slava Style (Kornilov / Geex Arts)

Design like Slava Kornilov: quiet-luxury editorial interfaces. Calm desaturated surfaces, magazine-grade typography, broken grids — never flashy effects or saturated color piles.

## Core principles

1. **Base first, accent once.** Build the whole page on a near-neutral base (off-white or near-black + grays). Add ONE high-contrast accent (e.g. vivid orange, electric blue) used sparingly — a button, an underline, a single word. Accent coverage < 5% of the viewport.
2. **Typography is the hero.** Huge display headings (clamp 48–120px), tight tracking (-0.02em to -0.04em), often mixing serif display + sans body. Mix font weights inside one headline to create rhythm; italicize or accent ONE word.
3. **Break the grid.** Offset columns, overlap images with text blocks, rotate small labels 90°, let elements bleed to the edge. Keep an invisible alignment spine so it feels intentional, not messy.
4. **Whitespace is a component.** Leave 30–50% of sections empty. Never fill every slot of a grid.
5. **Lightweight chrome.** Hairline borders (1px, low opacity), soft or zero shadows, large border-radius on media (16–28px), pill tags, thin outlined buttons. No gradients-on-gradients, no neon glows, no heavy glassmorphism.
6. **Motion is subtle.** Slow fades, gentle parallax, slight scale on hover. Nothing bouncy.

## Palette

Full token list with CSS variables: read `references/tokens.md` when building.

Quick defaults:
- Light base: `#F4F2EE` (warm paper), text `#1A1A1A`
- Dark base: `#121212`, text `#EDEAE4`
- Morandi tints (sage `#A8B5A0`, dusty blue `#8FA3B0`, terracotta `#C4A484`, blush `#CBB3AD`) for cards/illustration blocks — desaturated, never pure
- Accent (pick ONE per project): `#FF4D00` orange-red, `#2B4EFF` cobalt, or `#D8FF3E` lime on dark

## Typography

- Display: serif with character (e.g. "Playfair Display", "Cormorant Garamond") or a bold grotesque ("Space Grotesk", "Inter Tight") — pick one family per project, plus "Inter"/system for body
- CJK fallback: 思源宋体 (Noto Serif SC) for display, 思源黑体 (Noto Sans SC) for body
- Scale: display 64–120px, section titles 32–48px, body 15–17px, micro-labels 11–12px uppercase with letter-spacing 0.12em
- Micro-labels, index numbers ("01 —"), and rotated side-text are signature decorations

## Layout recipes

- **Hero**: oversized headline split over 2–3 lines, one italic/accented word; image card overlapping the headline's lower-right; small caps kicker with hairline rule
- **Editorial feed**: alternate text block / image block with 1-column offset; vary image aspect ratios (4:5, 3:2, 1:1); big index numbers
- **Stats/features**: hairline-divided rows, big serif numbers, tiny uppercase labels
- **Cards**: flat fill with Morandi tint or 4%-opacity neutral, 20px+ radius, no shadow, content bottom-aligned with generous padding

## Anti-patterns (never do)

- No saturated multi-color palettes, no rainbow gradients
- No heavy drop shadows, neumorphism, or busy backgrounds
- No perfectly symmetric uniform grids of identical cards
- No more than one accent color; never accent + Morandi tint on the same element

## Five palettes (DeepSeek-inspired)

Five complete palette sets (base/ink/soft/tint/glaze/accent) are defined in `references/tokens.md` under "Five palettes", each with a showcase page in `templates/palettes/` (`p1`–`p5`, previews alongside as `.png`). When the user names a mood or scenario, pick one and swap the CSS variables — never mix two palettes:

- **P1 深潜蓝** `#4D6BFE` accent — AI products, official sites (DeepSeek primary blue family)
- **P2 鲸鱼浅青** `#00B3F4` accent — data products, dev tools
- **P3 深夜机房** `#5B8CFF` accent on `#0D1420` — dark tech, dashboards, hardware launches
- **P4 雾灰银** `#4D6BFE` accent on neutral grays — finance, corporate, most restrained
- **P5 珊瑚信号** `#FF5A3C` accent on warm sand — consumer AI, content products

## Skinning any skeleton (template × palette)

To apply a palette to any existing skeleton: copy the skeleton HTML and inject a `<style>` block (AFTER the base.css link) overriding the variables — `--paper, --paper-2, --ink, --ink-soft, --accent, --hairline` plus the morandi slots (`--sage, --dusty-blue, --terracotta, --blush, --taupe, --moss` → palette tint/glaze). For the dark palette P3 also flip `--night/--night-2/--paper-on-night/--hairline-dark` and swap `rgba(26,26,26,.04)` neutral fills for `rgba(232,237,245,.06)`. Watch relative paths: pages placed in `templates/skins/` must reference base.css as `../../assets/base.css`. Working examples: `templates/skins/hero-*.html` (5 skins) and `templates/skins/09-pricing-x-midnight-cluster.html`, `02-editorial-feed-x-whale-cyan.html`, `06-poster-social-x-deep-dive-blue.html`.

## Output guidance

When producing HTML/CSS (websites, widgets, posters), start from `assets/base.css` — it encodes the palette variables, type scale and layout utilities described here. Deliver real content, not lorem ipsum.

## Template library

Ready-made starting points in `templates/` — copy the closest one and adapt instead of composing from scratch:

- `01-hero-editorial.html` — landing hero: oversized headline + accent word + bleeding media card + outlined decoration word
- `02-editorial-feed.html` — image-text interleaved feed with stroke index numbers
- `03-stats-dark.html` — dark stats section with serif numerals and hairline dividers
- `04-cards-offset.html` — offset Morandi-tinted card trio
- `05-landing-full.html` — full landing page combining 01–04 + CTA
- `06-poster-social.html` — 4:5 social poster for sharing
- `07-perform-tv.html` — dark consumer-electronics product page with spec rows
- `08-gpu-server-networking.html` — technical reference page: comparison table + topology blocks
- `09-pricing.html` — pricing page with sunken dark featured tier + FAQ rows
- `10-docs-reference.html` — developer docs: sticky side nav + dark code blocks + accent callout

Each template has a rendered preview in `templates/previews/`. Check the preview first when deciding which template fits the request.
