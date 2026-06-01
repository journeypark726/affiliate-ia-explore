# FDS Button Reference

**Purpose:** A button lets the user perform an action with a tap or a click.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Hierarchy** | `Primary`, `Secondary` |
| **Size** | `Large`, `Medium`, `Small` |
| **Color** | `Accent`, `Neutral`, `Buy`, `Sell` |
| **State** | `Enabled`, `Hover` (=Pressed), `Focus`, `Disabled` |
| **Show icon** | `true`, `false` |
| **Sub Label** | `true`, `false` |
| **Full radius** | `On`, `Off` |

---

## Component Rules

**Fixed (do not change):**
- Container Height
- Container Radius
- Font Size
- Icon Size

**Changeable:**
- Width
- Container Color
- Text Color
- Border Color
- Icon Color

---

## Hierarchy × Color Combinations

**Primary** — Color is changeable across all 4 color types:
| Color | Visual | Usage |
|---|---|---|
| Accent | Blue filled | **The** main CTA — Flipster's primary brand color. Use for the single most important action on the page. |
| Neutral | White/Gray filled | Primary action when multiple buttons exist on the same page. Flipster's sub color. |
| Buy | Green filled | Trade page Buy-exclusive action |
| Sell | Red filled | Trade page Sell-exclusive action |

> **Accent vs Neutral guidance:**
> - **Accent** = the strongest emphasis. Recommend limiting to **one per page** for the most critical action.
> - **Neutral** = still a primary button, but lower visual weight. Use when **multiple primary buttons** appear on the same page.
> - If a page has only one main CTA → Accent. If a page has several actions → Neutral for most, Accent for the single most important one (or all Neutral if no clear priority).

> **When to use Primary/Accent:**
> - A page has only one action (e.g. "Done" on a confirmation screen)
> - Guiding the user toward the most important action (e.g. "Deposit Crypto" among several options)

**Secondary** — Color is changeable across all 4 color types:
| Color | Visual | Usage |
|---|---|---|
| Accent | Blue outlined | Secondary emphasis action |
| Neutral | Gray outlined | Default secondary — most common |
| Buy | Green outlined | Secondary Buy action |
| Sell | Red outlined | Secondary Sell action |

> **When to use Secondary:**
> - Paired with a Primary button for a lower-priority action (e.g. "Cancel" next to "Confirm")
> - Standalone low-importance action (e.g. "Sign out")

---

## When to Use White (Neutral) Buttons

White buttons (`Primary/Neutral`) can replace `Secondary` outline buttons in these cases:

1. **Multiple buttons displayed in a list** — When blue (Accent) buttons would be visually too strong, use white buttons to reduce noise (e.g. "Verify", "Deposit", "Trade" in a task list)
2. **Content-heavy pages** — When a `Secondary` outline button doesn't stand out enough among dense content, a white button provides better visibility (e.g. "Turn on", "Unstake")

---

## Adding New Button Colors

The 4 colors (Accent, Neutral, Buy, Sell) are the only available options. To add a new color, **semantic tokens must be updated first** in the design system. Custom colors cannot be applied directly to the button component.

---

## States

- **Enabled** — Default interactive state
- **Hover (=Pressed)** — Same visual treatment for hover and pressed
- **Focus** — Keyboard/accessibility focus ring
- **Disabled** — The same disabled style is applied across all color types

> **Why unified disabled style?** Prevents visual confusion — disabled buttons should look uniformly inactive regardless of their original color.

---

## Sizes

| Size | Height (fixed) | Min Width (text only) | Min Width (with icon) | Notes |
|---|---|---|---|---|
| Large | 48px | 61px | 81px | Supports Sub Label (Primary/Large only) |
| Medium | 40px | 50px | 70px | Standard size |
| Small | 32px | 40px | 58px | Supports Full radius (pill shape) |

> **Min width is a default guideline** — it can be freely adjusted depending on the context. These are not enforced values.

---

## Anatomy

**Primary:**
- Slots: Text only (1 line), Text only (2 lines — with Sub Label), Icon + Text
- An image asset can be placed in the icon spot
- When adding a logo image, **it must first be registered to the icon library**

**Secondary:**
- Slots: Text only, Icon + Text
- An image asset can be placed in the icon spot

---

## Special Properties

**Sub Label:**
- Available on **Primary/Large only**
- Adds a second line of text below the main label

**Full radius:**
- Turns the button into a pill shape (fully rounded)
- 현재 kit에는 **Small** 사이즈에만 적용되어 있음 (시범 운영)

| Size | 사용 가능 여부 | When to use |
|---|---|---|
| Large / Medium | 실험적 사용 가능 | 프로모션 페이지에서 실험적으로 사용 |
| Small | ✅ 공식 지원 | 프로덕트 내 chip 스타일의 버튼이 필요할 때 |

**Icon slot:**
- Can hold an FDS icon or an image asset (e.g. a logo)
- Logo images must be registered in the icon library before use

---

## Button Group

Buttons can be grouped in two layouts:
- **Vertical** — Primary on top, Secondary below
- **Horizontal** — Secondary on left, Primary on right

---

## Animation

- Button loading animation uses **Lottie (.json)** files
- Animation files are downloadable from the Figma spec

---

## Change Log

| Date | Change |
|---|---|
| 2024.09.11 | Button component updated |
| 2025.03.06 | Button text → Replaced with Monospace font |
| 2025.12.24 | Button radius changed (4 → 8), Padding changed, Full radius (Small) type updated |

> **Why Monospace for button text?** Buttons often display numeric values (prices, amounts). Monospace ensures consistent width when values change in real-time.

---

## Usage Rules
- Choose the correct Hierarchy based on action importance (Primary = main, Secondary = supporting)
- Buy/Sell colors follow the same directional rules as the color system (see color.md)
- Sub Label is restricted to Primary/Large — do not attempt on other sizes
- Full radius is restricted to Small — do not attempt on other sizes
- Disabled state looks the same across all colors — this is intentional

## Caveats
- ⚠️ Hover and Pressed share the same visual state — no separate pressed style
- ⚠️ Logo images in the icon slot must be registered in the icon library first
- ⚠️ Web-only: some button behaviors may differ (check Figma spec annotations marked *Web only*)

---

## Non-FDS Button Detection Guide

Legacy or custom buttons are sometimes used instead of the FDS Button component. When detected, guide the user to replace with the FDS version.

**How to detect non-FDS buttons:**
- Layer is NOT an instance of the FDS `Button` component set
- Layer named generically (e.g. "Rectangle", "Frame", "btn", "button-old", "CTA")
- Button-like element with manually applied fills/radius instead of component properties
- Button from an archived library (`Flipster UI Component Library "22`)

```
🟡 Warning — Non-FDS button detected

  Found: [layer name]
  → This does not appear to be an FDS Button component.

  How to fix:
  - Replace with the FDS Button component from ❖ Flipster Design System
  - Map to the correct properties:
    - Hierarchy: Primary or Secondary
    - Color: Accent / Neutral / Buy / Sell
    - Size: Large (48px) / Medium (40px) / Small (32px)

  Common legacy patterns → FDS equivalent:
  - Blue filled button → Button / Primary / Accent
  - Gray outlined button → Button / Secondary / Neutral
  - Green "Buy" button → Button / Primary / Buy
  - Red "Sell" button → Button / Primary / Sell
  - Small pill button → Button / Small / Full radius: On
```

---

## Audit Checklist

```
🔴 Critical
- Non-FDS button used (legacy or custom) — must replace with FDS Button component
- Button color not one of the 4 available (Accent, Neutral, Buy, Sell)
- Sub Label used on non-Large or non-Primary button
- Full radius property missing on Small button when pill shape is intended

🟡 Warning
- Primary/Accent used multiple times on the same page — consider using Neutral for lower-priority actions
- Button from archived library detected (Flipster UI Component Library "22)
- Button-like layer not using FDS component (manually styled rectangle/frame)
- Logo image in icon slot not registered in the icon library

🟢 Tip
- One page, one main action → Primary/Accent. Multiple actions → Primary/Neutral for most.
- For button lists (task lists, settings), consider white (Neutral) buttons over Accent to reduce visual noise
- Use Secondary for "Cancel" or low-priority actions paired with a Primary button
```
