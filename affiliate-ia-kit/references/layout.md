# FDS Layout Reference

> ⚠️ **This is a recommended guideline, not an enforced system.**
> Layout values are guidance for screen setup, artboards, and grid configuration.
> Violations are flagged as Warnings, not Critical issues.

---

## Overview

Guidance on overall layout structure, including screen size, artboard setup, and grid settings.

---

## Mobile

### Android (Primary)

| Property | Value |
|---|---|
| Default resolution | **360×800dp** |
| Minimum resolution | **360×640dp** |

> **Why Android-first?** The majority of Flipster users are on Android, so Android screen resolution is the primary design reference.

### iOS

| Property | Value |
|---|---|
| Default resolution | **375×812pt** (iPhone X) |
| Minimum resolution | **375×667pt** |

### Mobile Web

- Consider the viewport sizes displayed in iOS Safari and Android Chrome
- Browser UI elements (URL bar, bottom bar) reduce available viewport height
- Design within the visible content area, accounting for browser chrome

---

## Desktop

### Small Desktop

| Property | Value |
|---|---|
| Resolution | **1440×900px** |
| Aspect ratio | 16:10 (MacBook Air reference) |
| Default content width | **1200px** |

> **Why 1440×900?** Based on MacBook Air as the standard reference device with a 16:10 ratio.

### Large Desktop

| Property | Value |
|---|---|
| Resolution | **1920×1080px** |
| Default content width | **1200px** |
| Full-width pages | Consider **1920px** width |

> **When to use 1920px full-width:** Pages like the Trade page that use 100% width should be designed with 1920px resolution in mind. For standard pages, 1200px content width is sufficient.

---

## Breakpoints (Web)

> ⚠️ **Ready for Development** — Breakpoint definitions for responsive web.

| Breakpoint | Range | Notes |
|---|---|---|
| Mobile | (see BP section in Figma) | [TODO — extract exact values] |
| Tablet | (see BP section in Figma) | [TODO — extract exact values] |
| Small Desktop | (see BP section in Figma) | [TODO — extract exact values] |
| Large Desktop | (see BP section in Figma) | [TODO — extract exact values] |

> Breakpoint details are documented in the "BP" section of the Layout page in Figma. Exact values should be added here when confirmed.

---

## Mobile Layout Component

FDS provides a **Mobile Layout** component in Figma for consistent artboard setup:

| Variant | Properties |
|---|---|
| `OS=Android, Environment=App, Size=Large` | 360×800 |
| `OS=Android, Environment=App, Size=Small` | 360×640 |
| `OS=iOS, Environment=App, Size=Large` | 375×812 |
| `OS=iOS, Environment=App, Size=Small` | 375×667 |
| `OS=iOS, Environment=Mobile web, Size=Large` | 375×812 |
| `OS=Android, Environment=Mobile web, Size=Large` | 360×812 |

Each variant includes **Default** and **Scroll** states.

## Desktop Layout Component

| Variant | Properties |
|---|---|
| `Size=Small` | 1440×900 |
| `Size=Large` | 1920×1080 |

## Bottom Bar Component

| Variant | Properties |
|---|---|
| `Type=iOS` | iOS-style bottom navigation |
| `Type=AOS` | Android-style bottom navigation |

---

## Audit Checklist

```
🟡 Warning
- Mobile design using non-standard resolution (not 360×800 for Android or 375×812 for iOS)
- Desktop design not using 1440×900 or 1920×1080 artboard
- Full-width desktop page not considering 1920px resolution
- Mobile web design not accounting for browser chrome (URL bar, bottom bar)
- Content width exceeding 1200px on standard (non-full-width) desktop pages

🟢 Tip
- Use the FDS Mobile Layout / Desktop Layout components for consistent artboard setup
- For mobile web, verify the design works within the reduced viewport (browser UI takes space)
- Android is the primary design target — design for 360×800dp first, then adapt for iOS
- When designing for Large Desktop, verify that full-width layouts still look good at 1920px
```
