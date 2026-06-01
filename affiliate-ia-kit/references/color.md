# FDS Color System Reference

## Overview

FDS is a **dark mode only** system. Light mode tokens do not exist.
The base background starts at `#111111` and layers get progressively lighter as elevation increases.

> **Why dark mode only?** The Flipster product is designed around a dark interface. Light mode support was unnecessary, so no light mode tokens were ever created.

**Token usage priority:**
1. **Semantic tokens first** — always check `content/`, `background/`, `border/` tokens first
2. **Palette tokens as fallback** — only when no suitable semantic token exists
3. **Never hardcode hex values** — even when using palette tokens, reference by token name

---

## Color Role Definitions (FDS Domain)

| Color | Role | Usage Context |
|---|---|---|
| **Red** | Short / Sell / Negative | Sell orders, losses, negative states, errors |
| **Green** | Long / Buy / Positive | Buy orders, profit, positive states, success |
| **Lime** | Primary CTA / Nudge | Primary emphasis, key actions, promotions |
| **Blue** | Brand / Secondary Nudge | Main branding, info, secondary emphasis |
| **Gold (gradient)** | VIP | VIP-related features |
| **Purple (gradient)** | Promotion | Promotional campaigns |

### Key Rules

**Red & Green are directional — never decorative**
- Red = falling / loss / sell → `content/accent/sell`, `content/state/negative`
- Green = rising / profit / buy → `content/accent/buy`, `content/state/positive`
- Using these colors for decoration creates meaning confusion — always flag
- **Why:** As a financial product, colors carry directional meaning (up/down). Unrestricted color usage was considered but rejected due to risk of meaning confusion.

**Profit/revenue values → prefer Green**
- Profit rates, P&L, positive position values → `content/state/positive` or `content/accent/buy`
- Green is generally preferred for profit. Blue or Lime should not be used for financial gain values.
- If used intentionally in a different color, verify there's no risk of meaning confusion.

**Lime vs Blue emphasis hierarchy**
- **Lime** = 1st priority emphasis color. Strong chroma — use sparingly.
  - Product screens: only one Lime emphasis element per screen
  - Marketing/promotion pages: broader use allowed to match page tone
  - Two or more Lime elements on the same screen dilutes the effect → flag as warning
- **Blue** = 2nd priority emphasis color. Used when Lime is already present or for secondary nudge.
  - Info elements, secondary CTAs, links, brand moments
- Lime and Blue must not be used at equal hierarchy on the same screen (visual confusion)
- **Why this hierarchy?** Lime's high chroma dilutes emphasis when used multiple times. Unrestricted Lime usage was considered but rejected due to visual clutter.

**Semantic token → palette token suggestion behavior**
When a palette token is used directly, suggest the appropriate semantic token:
```
🟡 Warning — Palette token used directly
  Found: blue/500 (#0a84ff)
  → Suggested semantic alternatives:
    - content/accent/info        (text/icon — informational emphasis)
    - background/accent/primary  (button backgrounds, primary actions)
    - border/accent/info         (borders with info emphasis)
  If none fit, using the palette token directly is acceptable.
```

---

## Primitive Palette

### Blue
| Token | Hex |
|---|---|
| `blue/50` | `#0e1927` |
| `blue/100` | `#0d2643` |
| `blue/200` | `#0f3458` |
| `blue/300` | `#0e457c` |
| `blue/400` | `#0c5cac` |
| `blue/500` | `#0a84ff` ← primary brand blue |
| `blue/600` | `#33a0ff` |
| `blue/700` | `#5cb8ff` |
| `blue/800` | `#85ceff` |
| `blue/900` | `#ade1ff` |

### Gray
| Token | Hex |
|---|---|
| `gray/Black` | `#000000` |
| `gray/0` | `#111111` |
| `gray/50` | `#1c1c1c` |
| `gray/100` | `#222222` |
| `gray/200` | `#2a2a2a` |
| `gray/300` | `#3a3a3a` |
| `gray/400` | `#484848` |
| `gray/500` | `#606060` |
| `gray/600` | `#7b7b7b` |
| `gray/700` | `#959595` |
| `gray/800` | `#b4b4b4` |
| `gray/900` | `#eeeeee` |
| `gray/White` | `#ffffff` |

### Red (Short / Sell / Negative)
| Token | Hex |
|---|---|
| `red/50` | `#291111` |
| `red/100` | `#431514` |
| `red/200` | `#581e1a` |
| `red/300` | `#7c241f` |
| `red/400` | `#ac2c25` |
| `red/500` | `#ff3b30` ← primary |
| `red/600` | `#ff6759` |
| `red/700` | `#ff9182` |
| `red/800` | `#ffb7ab` |
| `red/900` | `#ffdcd4` |

### Yellow (Warning)
| Token | Hex |
|---|---|
| `yellow/50` | `#281e0e` |
| `yellow/100` | `#422f0e` |
| `yellow/200` | `#574012` |
| `yellow/300` | `#7a5712` |
| `yellow/400` | `#a87613` |
| `yellow/500` | `#faad14` ← primary warning |
| `yellow/600` | `#ffc53d` |
| `yellow/700` | `#ffd666` |
| `yellow/800` | `#ffe58f` |
| `yellow/900` | `#fff1b8` |

### Green (Long / Buy / Positive / Profit)
| Token | Hex |
|---|---|
| `green/50` | `#112116` |
| `green/100` | `#15351e` |
| `green/200` | `#1c4827` |
| `green/300` | `#216331` |
| `green/400` | `#288740` |
| `green/500` | `#34c759` ← primary |
| `green/600` | `#59d474` |
| `green/700` | `#82e093` |
| `green/800` | `#afedb9` |
| `green/900` | `#e1fae4` |

### Lime (Primary CTA / Nudge)
| Token | Hex |
|---|---|
| `lime/50` | `#1f2600` |
| `lime/100` | `#313a00` |
| `lime/200` | `#4b5700` |
| `lime/300` | `#6e7f00` |
| `lime/400` | `#9fb800` |
| `lime/500` | `#cfe600` ← primary |
| `lime/600` | `#edff00` ← bright accent |
| `lime/700` | `#eeff66` |
| `lime/800` | `#f6ffaa` |
| `lime/900` | `#fcffdd` |

### Indigo
| Token | Hex |
|---|---|
| `indigo/50` | `#121524` |
| `indigo/100` | `#171f3b` |
| `indigo/200` | `#1f2a4e` |
| `indigo/300` | `#25366d` |
| `indigo/400` | `#2e4696` |
| `indigo/500` | `#3e63dd` ← primary |
| `indigo/600` | `#678aeb` |
| `indigo/700` | `#94b2f7` |
| `indigo/800` | `#c2d6ff` |
| `indigo/900` | `#ebf2ff` |

---

## Semantic Tokens

### CONTENT — Text, Icons, Labels

**Default (text hierarchy)**
| Token | Value | Usage |
|---|---|---|
| `content/default/level-0` | `#000000` | Inverse text — on white/light backgrounds (e.g. white-bg CTA label) |
| `content/default/level-1` | `#7b7b7b` | Tertiary text |
| `content/default/level-2` | `#959595` | Quaternary text |
| `content/default/level-3` | `#b4b4b4` | Disabled/inactive text |
| `content/default/level-4` | `#eeeeee` | Default body text |
| `content/default/level-5` | `#ffffff` | Inverse text — on colored backgrounds (e.g. Blue/Lime/Red CTA label) |

> **Inverse pattern:**
> - Colored background CTA → `background/accent/primary` + `content/default/level-5`
> - White background CTA → `background/default/level-4` + `content/default/level-0`

**Accent**
| Token | Value | Usage |
|---|---|---|
| `content/accent/info` | `#0a84ff` | Info, links |
| `content/accent/info-hover` | `#0c5cac` | |
| `content/accent/sell` | `#ff3b30` | Sell / Short |
| `content/accent/sell-hover` | `#ac2c25` | |
| `content/accent/buy` | `#34c759` | Buy / Long |
| `content/accent/buy-hover` | `#288740` | |
| `content/accent/promotion` | `#cfe600` | Promotion nudge |
| `content/accent/promotion-hover` | `#6e7f00` | |
| `content/accent/VIP` | `#ffe6a8` | VIP features (gold tone) |

**State**
| Token | Value |
|---|---|
| `content/state/positive` | `#34c759` |
| `content/state/positive-hover` | `#288740` |
| `content/state/negative` | `#ff3b30` |
| `content/state/negative-hover` | `#ac2c25` |
| `content/state/warning` | `#faad14` |
| `content/state/warning-hover` | `#a87613` |

**Interaction**
| Token | Value | Note |
|---|---|---|
| `content/interaction/hover` | `#ffffff52` (32%) | Single token — see adjustment guide below |
| `content/interaction/disabled` | `#ffffff29` (16%) | Single token — see adjustment guide below |

---

### BACKGROUND

**Default (elevation layers)**
| Token | Value | Usage |
|---|---|---|
| `background/default/level-0` | `#111111` | Base page background (lowest layer) |
| `background/default/level-1` | `#1c1c1c` | Cards, panels |
| `background/default/level-2` | `#2a2a2a` | Mid-layer surfaces |
| `background/default/level-3` | `#3a3a3a` | Top-layer surfaces |
| `background/default/level-4` | `#ffffff` | **Inverse** background — selected chips, high-contrast areas |

**Accent**
| Token | Value |
|---|---|
| `background/accent/primary` | `#0a84ff` |
| `background/accent/primary-hover` | `#0c5cac` |
| `background/accent/primary-tint` | `#0a84ff29` |
| `background/accent/secondary` | `#eeeeee` |
| `background/accent/secondary-hover` | `#b4b4b4` |
| `background/accent/secondary-tint` | `#eeeeee1a` |
| `background/accent/secondary-tint-hover` | `#eeeeee0d` |
| `background/accent/sell` | `#ff3b30` |
| `background/accent/sell-hover` | `#ac2c25` |
| `background/accent/sell-tint` | `#ff3b301f` |
| `background/accent/new-tint` | `#ff3b301f` ⚠️ |
| `background/accent/buy` | `#34c759` |
| `background/accent/buy-hover` | `#288740` |
| `background/accent/buy-tint` | `#34c7591f` |
| `background/accent/promotion-tint` | `#edff000f` |

> ⚠️ **`background/accent/new-tint`** currently shares the same value as `sell-tint` (`#ff3b301f`).
> This is intentional — the token is separated in anticipation of a future value change.
> Referencing by token name ensures a seamless bulk update when the value changes.
> Always reference `new-tint` by token name, never hardcode the hex value.

**State**
| Token | Value |
|---|---|
| `background/state/positive-tint` | `#34c7591f` |
| `background/state/negative-tint` | `#ff3b301f` |
| `background/state/warning-tint` | `#faad141f` |

**Interaction**
| Token | Value | Note |
|---|---|---|
| `background/interaction/hover` | `#ffffff1a` (10%) | Single token — see adjustment guide below |
| `background/interaction/disabled` | `#ffffff14` (8%) | Single token — see adjustment guide below |
| `background/interaction/dim` | `#000000b2` (70%) | Modal/overlay dim layer |

---

### BORDER

**Default**
| Token | Value |
|---|---|
| `border/default/level-1` | `#2a2a2a` |
| `border/default/level-2` | `#3a3a3a` |
| `border/default/level-3` | `#484848` |
| `border/default/level-4` | `#b4b4b4` |

**Accent**
| Token | Value |
|---|---|
| `border/accent/info` | `#0c5cac` |
| `border/accent/info-hover` | `#0e457c` |
| `border/accent/sell` | `#7c241f` |
| `border/accent/sell-hover` | `#581e1a` |
| `border/accent/buy` | `#216331` |
| `border/accent/buy-hover` | `#1c4827` |
| `border/accent/promotion` | `#6e7f00` |
| `border/accent/promotion-hover` | `#4b5700` |

**State**
| Token | Value |
|---|---|
| `border/state/negative` | `#7c241f` |
| `border/state/warning` | `#7a5712` |

**Interaction**
| Token | Value |
|---|---|
| `border/interaction/hover` | `#ffffff29` |
| `border/interaction/disabled` | `#ffffff14` |

---

## Gradients

| Token | Value | Usage |
|---|---|---|
| `Gradients/VIP` | `linear-gradient(135deg, #e4af5b 0%, #ffcc7b 10%, #fff6e9 30%, #fff6e9 40%, #ffcc7b 59.5%, #e4af5b 100%)` | VIP features |
| `Gradients/Promotion` | `linear-gradient(82.26deg, #3326c8 11.963%, #3326c8 50%, #7815db 88.037%)` | Promotional campaigns |

---

## Hover & Disabled Adjustment Guide

FDS currently defines one hover token and one disabled token each. When the default token feels too subtle (visually) or fails accessibility, suggest alternatives:

```
🟡 Warning — Interaction state may need adjustment

background/interaction/hover (#ffffff1a, 10%) — if too subtle:
  Alternatives:
  - #ffffff26 (15%) — slightly stronger
  - #ffffff33 (20%) — clearly visible hover
  - background/default/level-2 (#2a2a2a) — for list item surface hover

content/interaction/disabled (#ffffff29, 16%) — if contrast too low:
  Alternatives:
  - #ffffff3d (24%) — slightly more visible
  - content/default/level-2 (#959595) — meets 3:1 on dark backgrounds
  - gray/500 (#606060) — stronger disabled text

⚠️ Note: WCAG exempts disabled elements from contrast requirements,
but FDS recommends maintaining readability for better UX.
Always verify disabled states are still legible.
```

---

## Audit Checklist

```
🔴 Critical
- Hardcoded hex value used (no token reference)
- Red/Green used decoratively (not for sell/buy/state)
- Lime used more than once as emphasis on a product screen
- Lime and Blue used at equal hierarchy on the same screen

🟡 Warning
- Palette token used directly without checking semantic alternatives
- Profit/revenue value not using Green
- Hover/disabled token may be too subtle — suggest alternatives
- background/accent/new-tint hardcoded as hex (must stay as token)

🟢 Tip
- Consider semantic token instead of palette token (suggest specific alternatives)
- Green is generally preferred for profit/gain values
```
