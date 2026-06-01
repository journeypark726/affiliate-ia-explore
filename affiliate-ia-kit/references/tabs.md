# FDS Tabs Reference

**Purpose:** Tabs organize content across different screens and views.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Type** | `Scrollable`, `Fixed` |
| **Size** | `Large`, `Medium`, `Small` |
| **State** | `Selected`, `Unselected` × `Enabled`, `Hover` (=Pressed), `Focus` (Web only) |

---

## Type

| Type | Tab count | Behavior |
|---|---|---|
| Scrollable | Unlimited | Tabs overflow horizontally and can be scrolled |
| Fixed | **Max 4** | Tabs are evenly distributed across the full width |

> ⚠️ Fixed type supports a maximum of 4 tabs. Use Scrollable if more tabs are needed.

---

## Size

| Size | Height (fixed) |
|---|---|
| Large | 48px |
| Medium | 44px |
| Small | 38px |

---

## States

| State | Selected | Unselected |
|---|---|---|
| Enabled | ✅ | ✅ |
| Hover (=Pressed) | ❌ Not applied | ✅ Uses `content/interaction/hover` |
| Focus (Web only) | ✅ | ✅ |

> **Key rule:** Hover(=Pressed) state is NOT applied when a tab is Selected. Selected state takes priority.

> **Focus** is for web only — do not apply on iOS/Android.

---

## Border

| Type | Bottom border | Token |
|---|---|---|
| Scrollable | On / Off (toggleable) | `border/default/level-1` |
| Fixed | Always on | `border/default/level-1` |

- Selected tab indicator: `border/default/level-4`
- **Fixed type cannot turn off the bottom border** — it is always on

---

## Status Badge

- Available on **Unselected** state only — not shown when tab is Selected
- Disappears when the tab is clicked (i.e. becomes Selected)
- Can be toggled on/off via component property

> ⚠️ Do not show a status badge on a Selected tab — this is not supported.

---

## Touch Area

Touch area = Tab size (both Scrollable and Fixed).

- **Scrollable:** touch area matches the individual tab item width
- **Fixed:** touch area matches the full divided section width

---

## Padding & Badge

Tab items have built-in horizontal padding. When a red dot badge is present, the padding on both sides is adjusted equally to keep the tab label visually centered.

> Do not manually adjust tab padding. The component handles spacing automatically, including when a badge is present.

**Focus ring spacing:** 1px offset (Web only) — built into the component.

---

## Content Overflow (Fixed type)

When screen width ≥ 360px — tab labels display in full, no clipping.

When screen width < 360px — label text overflows:

| Platform | Behavior |
|---|---|
| Web / Android | Wraps up to 2 lines, ellipsis (`...`) beyond that |
| iOS | Font auto-resizes to 80% — no wrapping |

> This is handled automatically — no design adjustment needed. But be aware that long tab labels may clip on small screens.

---

## Background Color

- Default: `BG/Level 0`
- **Changeable** — can be freely adjusted per context, including transparency
- **Font color is fixed** — only the background can be changed

---

## Animation

When a tab is selected, the tab bar scrolls to position the selected tab based on its location:
- **Start position** — selected tab aligns to the left
- **Center position** — selected tab aligns to the center
- **End position** — selected tab aligns to the right

The bottom content associated with the tab updates simultaneously with the tab transition.

> This behavior is built into the component — no manual scroll handling needed in design.

---

## Edge Case: Disabled Tab

When a tab needs to be disabled, two options are available:

| Option | Behavior |
|---|---|
| Option 1 | Remove the tab entirely — do not show it |
| Option 2 | Keep the tab visible but show an alert dialog when tapped ("Page unavailable") |

> Option 2 is for cases where removing the tab is technically difficult. The preferred approach is Option 1 (remove the tab).

---

## Non-FDS Tabs Detection Guide

```
🟡 Warning — Non-FDS Tabs component detected

  Found: [layer name]
  → This does not appear to be an FDS Tabs component.

  How to fix:
  - Replace with the FDS Tabs component from ❖ Flipster Design System
  - Choose the correct type: Scrollable (unlimited) / Fixed (max 4 tabs)
  - Choose the correct size: Large (48px) / Medium (44px) / Small (38px)
```

---

## Audit Checklist

```
🔴 Critical
- Fixed type used with more than 4 tabs
  → Use Scrollable type instead, or reduce tab count to 4 or fewer
- Hover state applied on a Selected tab
  → Selected state takes priority — Hover must not be applied simultaneously

🟡 Warning
- Non-FDS Tabs component detected
- Focus state applied on iOS/Android (Focus is for web only)

🟢 Tip
- If tabs look too large or too small for the context, note that 3 sizes are available:
  Large (48px) / Medium (44px) / Small (38px) — choose the size that fits the layout
```
