# FDS Icon Reference

## Overview

- **Platform availability**: iOS ✅, Android ✅, Web ✅
- **Base grid**: 24×24px (can be adjusted based on purpose)
- **Two types**: Normal (monochrome, color changeable) and Color (fixed multi-color)

**Export formats by platform:**

| Platform | Format |
|---|---|
| iOS | PDF |
| Android | SVG, PNG |
| Web | SVG |

---

## Naming Convention

Icons follow a strict naming pattern for export filenames to match code naming:

| Rule | Example |
|---|---|
| Lowercase English only | `check-circle-icon` ✅, `CheckCircle` ❌ |
| Spaces replaced with `-` | `arrow-up-right-icon` |
| Normal type: no type suffix | `check-circle-icon` |
| Color type: `-color-` suffix | `clock-caution-color-icon` |

> **Why this convention?** Export filenames must match code naming exactly. The `-icon` suffix and `-color-` marker ensure clear distinction between types and consistent imports.

---

## Icon Types

### Normal Icons
- Monochrome (single color)
- **Color can be changed** via `content/*` tokens
- Icon color should follow the same semantic token rules as text (see color.md)

### Color Icons
- Multi-color, pre-defined appearance
- ⚠️ **Color CANNOT be changed** — they are fixed as designed
- Used for status indicators, VIP badges, brand marks, etc.

> **Why separate Color icons?** Some icons require multi-color to convey meaning (e.g. caution = yellow + red accents). Allowing color changes would break their intended communication.

---

## Icon Categories & Full List (171 icons)

### arrow (28)
Directional icons: chevrons, arrows, carets, swap, trending

| Icon Name |
|---|
| `chevron-left-icon` |
| `chevron-right-icon` |
| `chevron-up-icon` |
| `chevron-down-icon` |
| `chevron-double-left-icon` |
| `chevron-double-right-icon` |
| `chevron-double-up-icon` |
| `chevron-double-down-icon` |
| `arrow-left-icon` |
| `arrow-right-icon` |
| `arrow-up-icon` |
| `arrow-down-icon` |
| `arrow-up-right-icon` |
| `arrow-up-left-icon` |
| `arrow-down-right-icon` |
| `arrow-down-left-icon` |
| `arrow-trending-up-icon` |
| `arrow-trending-down-icon` |
| `arrow-path-icon` |
| `arrow-bend-double-icon` |
| `arrows-right-left-icon` |
| `arrows-up-down-icon` |
| `arrows-pointing-out-icon` |
| `arrows-pointing-in-icon` |
| `arrows-swap-icon` |
| `caret-up-icon` |
| `caret-down-icon` |
| `caret-up-down-icon` |

### chart (13)
Trading and data visualization icons

| Icon Name |
|---|
| `chart-bar-icon` |
| `chart-box-icon` |
| `chart-view-switch-icon` |
| `chart-expand-icon` |
| `chart-collapse-icon` |
| `candlestick-icon` |
| `pie-chart-icon` |
| `donut-chart-icon` |
| `trading-icon` |
| `copy-trading-icon` |
| `price-alert-icon` |
| `recurring-icon` |
| `orderbook-view-switch-icon` |

### circle (10)
Circle-enclosed status and action icons

| Icon Name |
|---|
| `check-circle-icon` |
| `x-circle-icon` |
| `plus-circle-icon` |
| `minus-circle-icon` |
| `question-circle-icon` |
| `caution-circle-icon` |
| `information-circle-icon` |
| `swap-circle-icon` |
| `user-circle-icon` |
| `circle-stack-icon` |

### others (92)
General UI icons — the largest category

**Actions**
| Icon Name |
|---|
| `search-icon` |
| `x-mark-icon` |
| `plus-icon` |
| `minus-icon` |
| `check-icon` |
| `share-icon` |
| `share-2-icon` |
| `copy-icon` |
| `edit-icon` |
| `trash-icon` |
| `filter-icon` |
| `download-icon` |
| `scan-icon` |
| `link-icon` |
| `slash-icon` |

**Navigation & Layout**
| Icon Name |
|---|
| `menu-icon` |
| `home-icon` |
| `external-link-icon` |
| `logout-icon` |
| `view-grid-icon` |
| `layout-icon` |
| `pip-icon` |
| `pip-exit-icon` |

**Status & Alerts**
| Icon Name |
|---|
| `alert-icon` |
| `alert-check-icon` |
| `alert-slash-icon` |
| `eye-icon` |
| `eye-slash-icon` |
| `in-progress-icon` |
| `signal-icon` |
| `network-icon` |
| `network-unstable-icon` |

**User & Identity**
| Icon Name |
|---|
| `user-icon` |
| `users-icon` |
| `identification-icon` |
| `address-book-icon` |
| `fingerprint-icon` |
| `passkey-icon` |

**Content & Communication**
| Icon Name |
|---|
| `document-text-icon` |
| `document-history-icon` |
| `document-search-icon` |
| `chat-bubble-icon` |
| `mail-icon` |
| `announcement-icon` |
| `newspaper-icon` |
| `translate-icon` |
| `code-bracket-icon` |

**Security & Privacy**
| Icon Name |
|---|
| `lock-closed-icon` |
| `lock-open-icon` |
| `shield-check-icon` |
| `shield-lock-icon` |
| `shield-star-icon` |
| `shield-privacy-icon` |
| `phishing-icon` |

**Finance & Trading**
| Icon Name |
|---|
| `asset-icon` |
| `database-icon` |
| `trend-icon` |
| `global-trend-icon` |
| `prevent-liquidation-icon` |
| `money-bag-icon` |
| `withdrawal-icon` |
| `card-icon` |
| `airdrop-icon` |

**Rewards & Gamification**
| Icon Name |
|---|
| `star-outline-icon` |
| `star-fill-icon` |
| `gift-icon` |
| `trophy-icon` |
| `crown-icon` |
| `medal-icon` |
| `sparkles-icon` |
| `rocket-icon` |

**Misc**
| Icon Name |
|---|
| `calendar-icon` |
| `calendar-days-icon` |
| `clock-icon` |
| `setting-icon` |
| `qr-code-icon` |
| `tag-icon` |
| `coupon-icon` |
| `tools-icon` |
| `bolt-icon` |
| `flag-icon` |
| `global-icon` |
| `hand-pointer-icon` |
| `heart-icon` |
| `heart-broken-icon` |
| `photo-icon` |
| `camera-icon` |
| `ellipsis-vertical-icon` |
| `ellipsis-horizontal-icon` |
| `devices-icon` |
| `device-mobile-icon` |
| `device-desktop-icon` |

### logos (6)
Social media and brand icons

| Icon Name |
|---|
| `twitter-icon` |
| `instagram-icon` |
| `facebook-icon` |
| `youtube-icon` |
| `telegram-icon` |
| `whatsapp-icon` |

### Color — fixed multi-color (20)
Status and special-purpose icons with fixed colors — **color CANNOT be changed**

**Clock Status**
| Icon Name |
|---|
| `clock-caution-color-icon` |
| `clock-error-color-icon` |
| `clock-success-color-icon` |

**Document Status**
| Icon Name |
|---|
| `document-caution-color-icon` |
| `document-error-color-icon` |
| `document-success-color-icon` |

**User Status**
| Icon Name |
|---|
| `user-caution-color-icon` |
| `user-error-color-icon` |
| `user-check-color-icon` |

**VIP**
| Icon Name |
|---|
| `user-vipstatus-basic-account-color-icon` |
| `user-vipstatus-basic-logo-color-icon` |
| `user-vipstatus-vip-account-color-icon` |
| `user-vipstatus-vip-logo-color-icon` |

**Ranking**
| Icon Name |
|---|
| `crown-1st-color-icon` |
| `crown-2nd-color-icon` |
| `crown-3rd-color-icon` |

**Funds**
| Icon Name |
|---|
| `funds-plus-color-icon` |
| `funds-caution-color-icon` |
| `funds-error-color-icon` |

**Other**
| Icon Name |
|---|
| `new-color-icon` |

### 📦 Icon Box (one-time use, NOT system icons)

| Icon Name |
|---|
| `checkbox-check-icon` |
| `donut-chart-icon` |
| `auction-icon` |

### logos
Social media and brand icons

| Examples |
|---|
| `twitter-icon`, `instagram-icon`, `facebook-icon`, `youtube-icon`, `telegram-icon`, `whatsapp-icon` |

### Color (fixed multi-color)
Status and special-purpose icons with fixed colors

| Sub-group | Examples |
|---|---|
| Clock status | `clock-caution-color-icon`, `clock-error-color-icon`, `clock-success-color-icon` |
| Document status | `document-caution-color-icon`, `document-error-color-icon`, `document-success-color-icon` |
| User status | `user-caution-color-icon`, `user-error-color-icon`, `user-check-color-icon` |
| VIP | `user-vipstatus-basic-account-color-icon`, `user-vipstatus-basic-logo-color-icon`, `user-vipstatus-vip-account-color-icon`, `user-vipstatus-vip-logo-color-icon` |
| Ranking | `crown-1st-color-icon`, `crown-2nd-color-icon`, `crown-3rd-color-icon` |
| Funds | `funds-plus-color-icon`, `funds-caution-color-icon`, `funds-error-color-icon` |
| Other | `new-color-icon` |

---

## Icon Box (One-Time Use)

**Icon Box** is a separate space for storing one-time-use icons that are **not part of the system icons**.

**Rules:**
1. Before adding a new icon, check Icon Box first — a similar icon may already exist
2. One-time-use icons must be stored in Icon Box with their purpose and reference noted

> **Why Icon Box?** Prevents one-off icons from polluting the system icon library. Keeps the core set clean while still providing a managed space for special-use cases.

---

## New Icon Addition Process

| Step | Action | Who |
|---|---|---|
| 1 | Search open-source icon libraries for a suitable icon | Designer |
| 2 | If found, request component addition from the icon manager (Alec) | Designer |
| 3 | Once added to Figma library, it's immediately usable in design | — |
| 4 | Squad developer registers the icon in the dev library and shares in `#flipster-design-system` | Developer |

**Approved open-source icon libraries:**
- 🔗 Hero Icons
- 🔗 Iconoir
- 🔗 Remix Icon
- 🔗 Google Icons
- 🔗 Phosphor

> If no suitable icon is found, contact Alec with a custom design or reference.

**Important notes:**
- Dev servers require each squad's developer to register new icons separately
- Developers must be notified when new icons are added to the Figma library
- Existing icon replacement work is NOT done — new icons are applied starting from new feature work only

> **Why no retroactive replacement?** Replacing existing icons across all screens risks visual regressions and increases QA burden. New icons are applied only in new feature work to minimize risk.

---

## Audit Checklist

```
🔴 Critical
- Color type icon with color overridden (color icons must stay as designed)
- Icon naming doesn't follow convention (must be lowercase-kebab-case with -icon suffix)

🟡 Warning
- Icon name does NOT end with "-icon" → this is NOT an FDS system icon
  → Guide the user to replace it with an FDS icon
  → If the icon's purpose is clear, suggest a matching FDS icon by name
  → Example:
    Found: "close" or "close-btn" → Suggest: "x-mark-icon"
    Found: "arrow_left" → Suggest: "arrow-left-icon" or "chevron-left-icon"
    Found: "info" → Suggest: "information-circle-icon"
    Found: "delete" → Suggest: "trash-icon"
- Normal icon using hardcoded hex color instead of semantic token
- One-time-use icon placed in system icon library instead of Icon Box
- Icon size not based on 24px grid without clear justification
- Archived or deprecated icon used in new design

🟢 Tip
- Check Icon Box before requesting a new icon — it may already exist
- When using arrow/directional icons, ensure direction matches the interaction
- For status indicators, prefer Color type icons (clock-caution-color, etc.) over manually colored Normal icons
```

### Non-FDS Icon Detection Guide

When an icon name does not end with `-icon`, it is not part of the FDS system. Output the following guidance:

```
🟡 Warning — Non-FDS icon detected

  Found: [icon name or layer name]
  → This is not an FDS system icon (FDS icons always end with "-icon")

  Suggested FDS replacement: [matching-fds-icon-name]
  (Based on the icon's apparent purpose)

  How to fix:
  - Replace with the FDS icon component from ❖ Flipster Design System
  - If no matching FDS icon exists, follow the New Icon Addition Process
    (search approved libraries → request from Alec)
```
