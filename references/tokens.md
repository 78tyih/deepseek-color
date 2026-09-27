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

## Five palettes (DeepSeek-inspired)

Five ready-made palette sets, each a complete swap of base / ink / soft-text / tint / accent. Showcase pages live in `templates/palettes/`. To reskin any template, override these five variables.

### P1 深潜蓝 Deep Dive Blue — AI 产品与官网（DeepSeek 主色系）

```css
--paper: #F5F7FB;  --ink: #0E1B3D;  --ink-soft: #5A6B8C;
--tint:  #A9BCE0;  --glaze: #DCE5F5; --accent: #4D6BFE;
--hairline: rgba(14,27,61,.14);
```

### P2 鲸鱼浅青 Whale Cyan — 数据产品与开发者工具

```css
--paper: #F2F8F9;  --ink: #12333B;  --ink-soft: #4A6A72;
--tint:  #A8CFD6;  --glaze: #DDEEF0; --accent: #00B3F4;
--hairline: rgba(18,51,59,.14);
```

### P3 深夜机房 Midnight Cluster — 暗色科技 / 大屏 / 硬件发布

```css
--paper: #0D1420;  --ink: #E8EDF5;  --ink-soft: #8B99AF;
--tint:  #2A3A52;  --glaze: #16202F; --accent: #5B8CFF;
--hairline: rgba(232,237,245,.16);
```

### P4 雾灰银 Silver Mist — 金融与企业官网（最克制）

```css
--paper: #F4F4F2;  --ink: #1A1D21;  --ink-soft: #5C615E;
--tint:  #C6CBC9;  --glaze: #E4E5E1; --accent: #4D6BFE;
--hairline: rgba(26,29,33,.14);
```

### P5 珊瑚信号 Coral Signal — 消费级 AI 与内容产品（暖）

```css
--paper: #FBF6F1;  --ink: #2B1D18;  --ink-soft: #7A6157;
--tint:  #E3C4B5;  --glaze: #F0E4DA; --accent: #FF5A3C;
--hairline: rgba(43,29,24,.14);
```

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
