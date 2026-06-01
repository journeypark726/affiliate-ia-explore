# FDS Toggle Reference

**Purpose:** A switch lets the user toggle an individual setting on or off.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Type** | `Unselected`, `Selected` |
| **State** | `Enabled`, `Focus` (Web only), `Disabled` |

**Fixed:** Container Height (28px), Container Radius
**Changeable:** Touch area

> Toggle has **no Hover state** and **no Error state**.

---

## Size

| Property | Value |
|---|---|
| Width | 46px (fixed) |
| Height | 28px (fixed) |

---

## Touch Area

| Property | Value |
|---|---|
| Min width | 46px |
| Min height | 28px |

Touch area is changeable — can be expanded beyond the component size if needed.

---

## States

| State | Web | App |
|---|---|---|
| Enabled | ✅ | ✅ |
| Focus | ✅ | ❌ |
| Disabled | ✅ | ✅ |

> Focus is for **web only** — do not apply on iOS/Android.
> There is **no Hover state** for Toggle.

---

## When to Use Toggle

Toggle is for **binary on/off settings only**. The key question is: does this control turn something on or off?

✅ Correct usage:
- Notifications on/off
- Dark mode on/off
- Feature enabled/disabled

❌ Incorrect usage:
- Choosing between two options (A or B) → use Radio Button instead
- Selecting from multiple options → use Checkbox instead
- Confirming an action → use Button instead

> ⚠️ If the interaction isn't clearly "on" or "off", it's likely the wrong component.

---

## Audit Checklist

```
🔴 Critical
- Toggle size changed from 46×28px
  → Size is fixed — do not resize the toggle component

🟡 Warning
- Non-FDS Toggle component detected
- Focus state applied on iOS/Android (Focus is for web only)
- Hover state applied (Toggle does not have a Hover state)
- Error state applied (Toggle does not support Error state)

🟢 Tip
- Touch area can be expanded beyond the component size for better usability
  (minimum 46×28px, but can be larger)
- Before using a toggle, ask: is this clearly an on/off setting?
  If not, consider Radio Button or Checkbox instead
```
