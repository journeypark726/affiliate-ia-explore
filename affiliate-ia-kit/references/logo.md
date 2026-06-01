# FDS Logo Reference

## Overview

FDS provides official Logo, Favicon, and App Icon components. Always use these instead of custom or external logo assets.

**Component Sets:**

| Component | Description |
|---|---|
| `Logo` | Flipster logomark and logotype |
| `Favicon` | Web favicon |
| `App icon` | iOS and Android app icons |

> ⚠️ **Favicon and App icon components are for asset replacement only.** Use them only when updating the actual favicon or app icon. Do not use them as general UI elements.

---

## Logo Component

### Variants

**Logomark** (icon only):

| Color | Background |
|---|---|
| White | Dark backgrounds |
| Blue | Light backgrounds |
| Black | Light/white backgrounds |

**Logotype** (icon + text "Flipster"):

| Color | Background |
|---|---|
| White | Dark backgrounds |
| Blue | Light backgrounds |
| Black | Light/white backgrounds |

**Image** (logomark in container shapes):

| Shape | Colors |
|---|---|
| Square | Blue, Black, White |
| Rounded | Blue, Black, White |
| Circle | Blue, Black, White |

### Usage Rules
- Always use the FDS `Logo` component — never manually recreate the logo
- Choose the appropriate color variant based on background contrast
- White logo on dark background, Blue or Black logo on light background
- Logo source and additional brand assets are linked in the Figma file (🔗 Brand Assets)

> **Why use the FDS component?** Ensures consistent sizing, proportions, and colors across all surfaces. Manual recreation risks incorrect proportions or colors.

---

## Favicon Component

For **web favicon** replacement only.

### Export Rules
- Export as **1x PNG** files
- Use the provided sizes in the component

### Variants
- Standard favicon (Flipster logomark on blue background)

---

## App Icon Component

For **app store icon** replacement only.

### Android

| Layer | Purpose |
|---|---|
| **Foreground** | Logomark only (transparent background) |
| **Background** | Solid blue fill |
| **Full** | Combined foreground + background |
| **Monochrome** | Single-color version of the logomark |

**Export rules for Android:**
- Export as **SVG or PNG**, **512×512**
- **No radius or borders** — the OS applies an automatic 'squircle' mask

### iOS

| Asset | Size |
|---|---|
| Standard icon | (per Apple guidelines) |
| Liquid glass version | **1024×1024** |

### Export Rules Summary

| Platform | Format | Size | Notes |
|---|---|---|---|
| Android | SVG or PNG | 512×512 | No radius/borders, squircle mask auto-applied |
| iOS | PNG | Per Apple guidelines | Liquid glass ver. = 1024×1024 |

---

## Non-FDS Logo Detection Guide

When a logo element is found that doesn't use the FDS Logo component, output the following guidance:

```
🟡 Warning — Non-FDS logo detected

  Found: [layer name or description]
  → This does not appear to be an FDS Logo component.
    FDS logos use the component named "Logo" with variants (Logomark/Logotype, White/Blue/Black).

  How to fix:
  - Replace with the FDS Logo component from ❖ Flipster Design System
  - Choose the correct variant:
    - Dark background → White variant
    - Light background → Blue or Black variant
  - For contained logos (avatar, thumbnail), use the Image component (Square/Rounded/Circle)

  Signs of a non-FDS logo:
  - Layer named "logo", "flipster-logo", "brand", or similar but NOT an instance of the FDS Logo component
  - Manually drawn or imported SVG/PNG of the Flipster logomark
  - Logo with incorrect colors or proportions
```

---

## Audit Checklist

```
🔴 Critical
- Flipster logo manually recreated (not using FDS Logo component)
- Logo with incorrect colors or proportions
- App icon exported with radius/borders applied (Android should have no radius — OS handles it)

🟡 Warning
- Layer appears to be a logo but is not an instance of the FDS Logo component
  → Check layer names containing "logo", "brand", "flipster", "logomark", "logotype"
  → If not an FDS component instance, flag and suggest replacement
- White logo used on light background (low contrast)
- Blue/Black logo used on dark background (low contrast)
- Favicon or App icon component used as a general UI element (they are for asset replacement only)

🟢 Tip
- Use Logomark for icon-only contexts, Logotype when space allows the full brand name
- For avatar or thumbnail contexts, use the Image component with the appropriate shape (Square/Rounded/Circle)
- Reference the Brand Assets link in Figma for additional brand guidelines
```
