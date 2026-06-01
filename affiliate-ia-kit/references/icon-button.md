# FDS Icon Button Reference

**Purpose:** An icon button lets the user perform an action with a tap or a click using an icon only, without a text label.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Hierarchy** | `Primary`, `Secondary`, `Tertiary`, `Quaternary` |
| **Size** | `Large`, `Medium`, `Small` |
| **State** | `Enabled`, `Hover` (=Pressed), `Focus` (Web only), `Disabled` |

---

## Hierarchy & Visual Style

| Hierarchy | Visual | Usage |
|---|---|---|
| Primary | Blue filled circle | Highest emphasis icon action |
| Secondary | Blue outlined circle (no fill) | Medium emphasis icon action |
| Tertiary | Dark gray filled circle | Low emphasis icon action |
| Quaternary | Icon only, no container | Minimal emphasis, no background |

> **Focus state** is for web only — not applicable on iOS/Android.

---

## Component Rules

**Fixed (do not change):**
- Container height
- Icon size
- Border color

**Changeable:**
- Icon color
- Touch area (default = component size: Large 48×48, Medium 32×32, Small 24×24)

---

## Icon Color Customization

Icon color can be customized across all hierarchy types (Primary, Secondary, Tertiary, Quaternary).

**Hover state:** Always opacity 60%, regardless of hierarchy or icon color — this is fixed and cannot be changed.

**Color icons (Fixed color):** Even when using a color icon (e.g. `-color-icon`), the hover opacity 60% rule still applies. The icon color itself remains fixed.

**Semantic tokens available for icon color:**
`content/accent/info`, `content/accent/buy`, `content/accent/sell`, `content/accent/new`, `content/accent/promotion`, `content/state/positive`, `content/state/negative`, `content/state/warning`

---

## When to Use Icon Button

- Icon-only action in a compact space where the action is unambiguous
- Standalone icon action (e.g. close, share, bookmark, settings)

## When NOT to Use Icon Button

- When the action needs a label for clarity → use Button or Text Button instead
- When pairing with a standard Button in the same action group → causes visual hierarchy confusion

> **Why standalone only?** Pairing Icon Button with a standard Button in the same action group creates visual hierarchy confusion. Icon Button is for space-constrained, unambiguous single actions only.

---

## Non-FDS Icon Button Detection Guide

```
🟡 Warning — Non-FDS Icon Button detected

  Found: [layer name]
  → This does not appear to be an FDS Icon Button component.

  How to fix:
  - Replace with the FDS Icon Button component from ❖ Flipster Design System
  - Map to the correct hierarchy: Primary / Secondary / Tertiary / Quaternary
  - Map to the correct size: Large / Medium / Small
```

---

## How to Detect "Button-like" Icons

Before flagging an icon, first determine whether it's acting as a button.

**Strong signals that an icon is button-like:**
- Icon name is `chevron-down-icon` or `chevron-right-icon` — these are almost always interactive
- Icon has a Prototype interaction attached
- Icon is in a typical interactive position (header, top-right of card, tab bar, list row trailing)
- Icon is wrapped in a transparent touch-area frame

**Signals that an icon is NOT a button:**
- Decorative icon alongside text (e.g. leading icon in an input field)
- Status indicator icon (e.g. checkmark, badge)
- Category icon in a list item

---

## Audit Checklist

```
🔴 Critical
- Plain icon used as a button without the Icon Button component
  → Most common designer mistake — if an icon is tappable/clickable, it must use the FDS Icon Button component
  → Key signal: chevron-down-icon or chevron-right-icon used without Icon Button component wrapper
  → Fix: wrap with Icon Button component (Primary / Secondary / Tertiary / Quaternary)
- Icon Button paired with a standard Button in the same action group
  → Icon Button must be used as a standalone action only

🟡 Warning
- Non-FDS Icon Button detected (manually styled icon acting as a button)
- Icon inside is not an FDS icon (layer name doesn't end in -icon)
- Hierarchy not one of the 4 types (Primary, Secondary, Tertiary, Quaternary)
- Focus state applied on iOS/Android (Focus is for web only)
- Hover state opacity not at 60% for a customized icon color

🟢 Tip
- If the action is ambiguous without a label, consider using a labeled Button instead
```
