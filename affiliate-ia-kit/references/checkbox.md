# FDS Checkbox Reference

**Purpose:** A checkbox lets the user select one or more options from a list.

**Platform:** iOS ✅, Android ✅, Web ✅

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
| Checkbox size | 16×16px (fixed) |

> The check icon inside uses a separate graphic (not a standard FDS icon) due to a different stroke weight.

---

## Label (Text)

- **Default:** `Text/L/Regular`
- **Changeable:** Text size and color can be adjusted per context (e.g. `Text/M/Regular`)

---

## Touch Area

- Touch area is **changeable**
- **Always applied together with the label** — the touch area covers both the checkbox and its label, not the checkbox alone

> ⚠️ When using a checkbox, verify that the touch area covers the label as well, not just the checkbox icon.

---

## Overflow Content (Multiline Label)

- Labels should be kept to **a single line** whenever possible
- If a label wraps to 2 lines: add **4px padding above the checkbox** (checkbox top-aligns with the first line)

---

## Error Case

- Single checkbox: error state applied directly on the checkbox
- **Group checkboxes:** error text is placed at the **bottom of the group**
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
- Checkbox used without label (touch area only covers the icon)
  → Touch area must always include the label

🟡 Warning
- Non-FDS Checkbox component detected
- Focus state applied on iOS/Android (Focus is for web only)
- Group error text not placed at the bottom of the group
  → Error text must be at the bottom, not next to individual checkboxes
- Multiline label without 4px top padding on the checkbox
  → When label wraps to 2+ lines, add 4px padding above the checkbox

🟢 Tip
- Keep labels to a single line whenever possible
- Default text style is Text/L/Regular — adjust only when context requires it
```
