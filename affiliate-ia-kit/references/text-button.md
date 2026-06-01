# FDS Text Button Reference

**Purpose:** A text button lets the user perform a low-emphasis action with a tap or a click.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Color** | `Accent`, `Neutral`, `Passive`, `Buy`, `Sell` |
| **State** | `Enabled`, `Hover` (=Pressed), `Focus`, `Disabled` |
| **Show icon** | `true`, `false` |

---

## Color Usage

| Color | Visual | Usage |
|---|---|---|
| Accent | Blue text | Primary CTA with low visual weight |
| Neutral | White text | Default low-emphasis action |
| Passive | Gray text | De-emphasized or secondary action |
| Buy | Green text | Buy-related action |
| Sell | Red text | Sell-related action |

---

## Anatomy

- **Text only** — label only
- **Icon + Text** — icon on the left of the label only

> ⚠️ Only leading icons (left side) are supported. If a trailing icon (right side) is needed, use the Text only type and manually add a separate icon next to it.

> Icon in the icon slot must be an FDS icon (layer name ending in `-icon`).

---

## Usage Examples

**Text Button** — use when the action stands alone and needs clear emphasis:
| Example | Context |
|---|---|
| "View all pending orders" | Standalone CTA at the bottom of a list |
| "Invite", "Participate" | High-priority action paired with content in a card |

**Underline (Text Link)** — use when the link lives within or alongside text:
| Example | Context |
|---|---|
| "Learn more" in an alert banner | Easier line wrapping when paired with long text |
| "Bitcoin (BTC)", "crypto portfolio" in body copy | Inline links within a sentence |

---

## Text Style Usage Guide

Three similar-looking patterns serve different purposes — choose based on the role, not the visual.

| Style | When to use | Example |
|---|---|---|
| **Underline** (font library) | Inline link or action embedded naturally within a sentence | "tiered trading fee system" in body copy |
| **Text Button** | A clearly standalone, independent action | "Close all", "Learn more" |
| **Dashed Underline** | Tooltip trigger — elements that need additional explanation or guidance | "Funding/8h" that opens a tooltip |

> **Why three separate patterns?** Each serves a distinct interaction role. Using Text Button inline in body copy causes touch target and accessibility issues. Dashed underline signals "there's more info here" — not a navigation or action. Mixing these creates unclear affordances for users.

---

## When to Use Text Button

- Standalone low-emphasis CTA (e.g. "Close all", "Learn more")
- Secondary action alongside a Primary or Secondary Button

## When NOT to Use Text Button

- Inline link within a sentence → use `Text/*/Underline Strong` text style instead
- Tooltip trigger on an element → use Dashed Underline style instead
- Main CTA on a page → use Button (Primary or Secondary)

---

## Underline Spec

> **[iOS] Implementation note:** Underline is rendered as 1px (consistent across all devices). The line is placed at the very bottom of the Text Button's full height, with text starting from the top.

---

## Font

Button text uses **Monospace** font.

> **Why Monospace?** Text Buttons often display numeric values. Monospace ensures consistent width when values change in real-time.

---

## Non-FDS Text Button Detection Guide

When a button-like text element is detected that is not an FDS Text Button component:

```
🟡 Warning — Non-FDS Text Button detected

  Found: [layer name]
  → This does not appear to be an FDS Text Button component.

  How to fix:
  - Replace with the FDS Text Button component from ❖ Flipster Design System
  - Map to the correct color: Accent / Neutral / Passive / Buy / Sell
```

---

## Audit Checklist

```
🔴 Critical
- Text Button used for inline links within body copy
  → Use Text/*/Underline Strong text style instead

🟡 Warning
- Non-FDS Text Button detected (manually styled text acting as a button)
- Color outside the 5 supported types (Accent, Neutral, Passive, Buy, Sell) applied to Text Button
  → Additional color types require a new variant to be added to the component
  → As a workaround, use Underline text style with the desired color applied directly
- Icon used in icon slot is not an FDS icon (layer name doesn't end in -icon)
- Monospace font not applied to button text

🟢 Tip
- For low-emphasis actions alongside a Primary Button, Text Button is preferred over a third Button
```
