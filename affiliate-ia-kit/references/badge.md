# FDS Badge Reference

**Purpose:** A badge is a small label used to convey status, category, or metadata.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Type** | `Tint`, `Outline` |
| **Anatomy** | `Text Only`, `Icon Leading`, `Icon Trailing` |
| **Color** | `Accent`, `Neutral`, `Positive`, `Buy`, `Negative`, `Sell`, `New`, `Warning`, `Promotion` |

**Fixed (do not change):**
- Container Height (20px)
- Container Radius (fully rounded)

**Changeable:**
- Icon Type

---

## Type

- **Tint** — filled background
- **Outline** — border only, no fill

> Tint and Outline share the same color visually, but use different semantic tokens.

---

## Anatomy

| Anatomy | Description |
|---|---|
| Text Only | Label only |
| Icon Leading | Icon on the left of the label |
| Icon Trailing | Icon on the right — special case for Long/Short badges only |

**Icon Trailing rules:**
- Default type: Outline. Tint can be used depending on context.
- Primarily for Long/Short badges. Other icons can be used, but **check if Icon Leading covers the use case first** before using Icon Trailing.

---

## Specs

| Property | Value |
|---|---|
| Height | 20px (fixed) |
| Min width | 1 letter minimum |
| Padding (Text Only) | 8px left / 8px right |
| Icon-text gap | 2px |
| Icon size | 12×12px |
| Text align | Center |
| Radius | Fully rounded (fixed) |
| Width | Flexible |

---

## Non-Clickable

**Badges are non-clickable components.** Do not attach interactions to a badge.

If an interactive action is needed:
- Use a different component (e.g. Text Button, Icon Button)
- Or add a separate `chevron-right-icon` next to the badge as a standalone interactive element

> ⚠️ Never make a badge itself tappable — it is a display-only component.

---

## Content Overflow

- **Multiline not supported** — badge text must fit on a single line
- Width is flexible, but **keep labels as concise as possible**

```
🟡 Warning — Badge label too long
  → Badge does not support multiline. Keep the label short and concise.
```

---

## Color Icon

By default, the icon color matches the badge color. A color icon (`-color-icon`) can be used if needed.

---

## Design Hierarchy

| Hierarchy | Type | Colors |
|---|---|---|
| 1st | Color Tint | Blue, Green, Red, Yellow, Lime |
| 2nd | Color Outline | Blue, Green, Red, Yellow, Lime |
| 3rd | Gray Tint / Outline | Gray |

---

## Design Usage (Color Guide)

| Color | Semantic usage | Examples |
|---|---|---|
| Lime | Primary / Promotion | P&L 1st, 15% APR |
| Blue | Secondary / Info | P&L 11st, Open |
| Gray | Tertiary / Info / Disabled | Perp, Spot, 100x, Closed, Beta |
| Green | Positive / Ongoing / Buy-Long | Long ↗, Ongoing |
| Red | Negative / Error / Sell-Short / New | New, Short ↘, Suspended |
| Yellow | Warning | Congested, May be delayed |

> **Why are same-colored badges using different semantic tokens?**
> Positive/Buy share the same green, and Negative/Sell/New share the same red — but each uses a separate semantic token. This allows future color changes to be applied independently per semantic role (e.g. if "New" changes to a different color later, only that token needs updating without affecting "Negative" or "Sell").

---

## Alternatives to Badge

Designers often default to badges for visual emphasis, but badges aren't always the best choice — especially when readability feels cramped or the context doesn't need a container.

If asked "the badge feels hard to read" or "is there another way to express this?", suggest these alternatives:

| Alternative | When to use |
|---|---|
| **Colored text** | When the status or label can stand alone without a container (e.g. "+3.52%" in green) |
| **Text/*/Strong** | When emphasis is needed within body copy without a visual container |
| **Icon only** | When the meaning is clear from the icon alone (e.g. a star for favorites) |
| **Colored dot** | When a simple status indicator is enough without a text label |
| **Typography hierarchy** | When the information can be de-emphasized through font size or color instead |

> The badge is one tool among many. When a badge feels visually heavy or reduces readability, consider whether plain text or color alone can communicate the same meaning more cleanly.

---

## Audit Checklist

```
🔴 Critical
- Badge used as a clickable/interactive element
  → Badges are non-clickable. Use a Text Button, Icon Button, or add a separate chevron icon for interaction.
- Badge text wraps to multiple lines
  → Badges do not support multiline. Shorten the label.

🟡 Warning
- Non-FDS Badge component detected
- Icon Trailing used with an icon other than Long/Short — check if Icon Leading covers the use case first
- Color used does not match the semantic context
  (e.g. Red badge for a non-negative, non-error, non-new state)

🟢 Tip
- Keep badge labels short and concise — badge width is flexible but long labels reduce readability
- Use Color Tint (1st hierarchy) for the most prominent badges, Outline (2nd) for secondary, Gray (3rd) for tertiary/disabled
```
