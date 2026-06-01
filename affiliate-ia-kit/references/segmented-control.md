# FDS Segmented Control Reference

**Purpose:** A segmented control allows users to update views of content and select between 2–4 alike options.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## When to Use Segmented Control

Segmented control is for **switching between similar views or content categories**. The key question is: does each option show a different view of the same content?

✅ Correct usage:
- Perp / Spot (different trading views)
- Chart / Stats (different content views)
- Basic user / VIP user (different account views)

❌ Incorrect usage:
- On/Off settings → use Toggle instead
- Choosing between two unrelated actions → use Radio Button or Button instead
- Options with significantly different meanings or hierarchies → use Tabs instead

> ⚠️ If the options don't represent "alike" views of the same content, it's likely the wrong component.

---

## Component Properties

| Property | Values |
|---|---|
| **Size** | `Medium`, `Small` |
| **Type** | `Unselected`, `Selected` |
| **State** | `Enabled`, `Hover` (Unselected only), `Focus` (Web only), `Disabled` |

**Fixed:** Container Height
**Changeable:** Container Width, Touch area

---

## Size

| Size | Height | Width |
|---|---|---|
| Medium | 44px (fixed) | Flexible |
| Small | 30px (fixed) | Flexible |

> All segments share equal width — individual segment widths cannot be adjusted independently.

---

## Segments

- Minimum: **2 segments**
- Maximum: **4 segments**
- Exactly 2, 3, or 4 segments only

---

## Padding

| Size | Default padding | With status badge |
|---|---|---|
| Medium | 12px | 2px |
| Small | 6px | 2px |

---

## States

| State | Note |
|---|---|
| Enabled | Default interactive state |
| Hover (=Pressed) | **Unselected only** — do not apply Hover on Selected segment |
| Focus | Web only (applies to both Selected and Unselected) |
| Disabled | Non-interactive |

> Hover token: `content/interaction/hover`
> **Focus** is for web only — do not apply on iOS/Android.
> **Hover is never applied on the Selected segment.**

---

## Content Overflow

| Platform | Medium | Small |
|---|---|---|
| Web / Android | 2 lines + ellipsis | 1 line + ellipsis |
| iOS | Font resized to 80% | Font resized to 80% |

> On Web, a tooltip appears on hover when text is truncated with ellipsis.

---

## Status Badge

- Status badge can be placed on **Unselected segments only**
- Status badge disappears after the user selects that segment

---

## Disabled Edge Case

When one or more segments need to be disabled, there are two acceptable approaches:

1. **Remove the entire segmented control** — if some segments are disabled, the whole segmented control can be removed from the UI
2. **Show an alert dialog** — if the segmented control cannot be removed, tapping a disabled segment triggers an alert explaining that the page is currently inaccessible (e.g. "Page unavailable — This page is currently inaccessible. Please try again later.")

> ⚠️ Do not leave a segment permanently disabled without explanation — use one of the two approaches above.

---

## Audit Checklist

```
🔴 Critical
- Segment count outside 2–4 range
  → Segmented Control supports exactly 2, 3, or 4 segments
- Segments with unequal widths
  → All segments must share equal width — do not adjust individually
- Height changed from fixed values (44px / 30px)
  → Height is fixed per size — do not resize vertically

🟡 Warning
- Non-FDS Segmented Control component detected
- Hover state applied on Selected segment
  → Hover (=Pressed) applies to Unselected only — never on Selected
- Focus state applied on iOS/Android (Focus is for web only)
- Status badge placed on a Selected segment
  → Status badge is for Unselected segments only
- Disabled segment left without explanation or action
  → Either remove the segment or show an alert dialog

🟢 Tip
- Width is flexible — adjust to fit the layout
- On Web, truncated text automatically shows a tooltip on hover (no extra work needed)
- For iOS overflow, the font will automatically resize to 80% — verify readability at that size
- Before using segmented control, ask: are these options similar views of the same content?
  If it's on/off → use Toggle. If options are unrelated → use Radio Button or Tabs instead
```
