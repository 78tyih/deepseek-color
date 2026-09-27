# Slava Style — Design Tokens

## Color tokens

```css
:root {
  /* bases */
  --paper:      #F4F2EE;  /* warm off-white */
  --paper-2:    #ECE9E3;  /* slightly deeper neutral */
  --ink:        #1A1A1A;
  --ink-soft:   #55534E;
  --night:      #121212;
  --night-2:    #1C1C1A;
  --paper-on-night: #EDEAE4;

  /* morandi tints (desaturated, for fills/illustration blocks) */
  --sage:       #A8B5A0;
  --dusty-blue: #8FA3B0;
  --terracotta: #C4A484;
  --blush:      #CBB3AD;
  --moss:       #7C8471;
  --taupe:      #B0A79B;

  /* accent — choose exactly ONE per project */
  --accent-orange: #FF4D00;
  --accent-cobalt: #2B4EFF;
  --accent-lime:   #D8FF3E; /* dark themes only */

  --hairline: rgba(26,26,26,.14);
  --hairline-dark: rgba(237,234,228,.16);
}
```

Usage ratios: base 70–85%, morandi tints 10–25%, accent < 5%.

## Type scale

| Role | Size | Weight | Extras |
|---|---|---|---|
| Display | clamp(3rem, 8vw, 7.5rem) | 500–600 | letter-spacing -0.03em, line-height 1.02 |
| H2 | 32–48px | 500 | -0.02em |
| Body | 15–17px | 400 | line-height 1.6, color ink-soft |
| Micro label | 11–12px | 500 | uppercase, letter-spacing 0.12em |
| Index number | display serif, e.g. "01" | 400 | may be outlined (webkit-text-stroke) |

Fonts: display = "Playfair Display" / "Cormorant Garamond" (editorial serif) or "Space Grotesk" / "Inter Tight" (modern grotesque); body = "Inter", system-ui. CJK: "Noto Serif SC" display, "Noto Sans SC" body.

## Signature moves

1. Headline with ONE italic serif word or ONE accent-colored word.
2. Kicker pattern: `01 — Collection` with 32px hairline before it.
3. Vertical rotated text at section edge (`writing-mode: vertical-rl`).
4. Image overlapping headline by ~10–20% with radius 20–24px.
5. Outlined (stroke-only) oversized word behind a section as decoration, opacity ≤ 0.08.
6. Buttons: pill shape, outline hairline on light themes; solid accent only for the primary CTA.
7. Dividers: full-width 1px hairlines instead of card shadows.

## Spacing

- Section padding: 120–180px vertical on desktop.
- Grid: 12 cols, 24px gutters — but always offset at least one element by 1 col or 40–80px.
- Max content width 1280–1440px.
