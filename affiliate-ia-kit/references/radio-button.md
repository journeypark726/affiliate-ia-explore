# FDS Radio Button Reference

**Purpose:** A radio button lets the user select a single option from a group.

**Platform:** iOS ✅, Android ✅, Web ✅

> ⚠️ Radio Button must be configured for **single selection only**. Use Checkbox for multi-select.

---

## Component Properties

| Property | Values |
|---|---|
| **Type** | `Unselected`, `Selected` |
| **State** | `Enabled`, `Hover` (=Pressed), `Focus` (Web only), `Disabled`, `Error` |

**Fixed:** Container Height (16px), Container Radius
**Changeable:** Touch area, Label font size & color

---

## Size

| Property | Value |
|---|---|
| Radio button size | 16×16px (fixed) |

---

## Label (Text)

- **Default:** `Text/L/Regular`
- **Changeable:** Text size and color can be adjusted per context

---

## Touch Area

- Touch area is **changeable**
- **Always applied together with the label** — touch area covers both the radio button and its label, not the radio button alone

> ⚠️ When using a radio button, verify that the touch area covers the label as well, not just the radio button icon.

---

## Overflow Content (Multiline Label)

- Labels should be kept to **a single line** whenever possible
- If a label wraps to 2 lines: add **4px padding above the radio button** (radio button top-aligns with the first line)

---

## Error Case

- **Group radio buttons:** error text is placed at the **bottom of the group**
- Error indicator: 🔴 icon + error text

---

## States

| State | Note |
|---|---|
| Enabled | Default interactive state |
| Hover (=Pressed) | Same visual for hover and press |
| Focus | Web only |
| Disabled | Non-interactive, visually de-emphasized |
| Error | Validation failed state |

> **Focus** is for web only — do not apply on iOS/Android.

---

## Audit Checklist

```
🔴 Critical
- Multiple radio buttons selected simultaneously
  → Radio Button is for single selection only — only one option can be selected at a time
- Radio Button used without label (touch area only covers the icon)
  → Touch area must always include the label

🟡 Warning
- Non-FDS Radio Button component detected
- Focus state applied on iOS/Android (Focus is for web only)
- Group error text not placed at the bottom of the group
  → Error text must be at the bottom, not next to individual radio buttons
- Multiline label without 4px top padding on the radio button
  → When label wraps to 2+ lines, add 4px padding above the radio button

🟢 Tip
- Keep labels to a single line whenever possible
- Default text style is Text/L/Regular — adjust only when context requires it
- If multiple options can be selected simultaneously, use Checkbox instead
```
