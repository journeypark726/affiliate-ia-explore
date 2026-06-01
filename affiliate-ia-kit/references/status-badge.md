# FDS Status Badge Reference

**Purpose:** A status badge is a small dot indicator used to communicate real-time status or notify users of new features.

**Platform:** iOS ✅, Android ✅, Web ✅

---

## Component Properties

| Property | Values |
|---|---|
| **Type** | `Red dot`, `Green dot` |

**Fixed:** Size (5×5px)
**Changeable:** Color

---

## Size

| Property | Value |
|---|---|
| Width | 5px (fixed) |
| Height | 5px (fixed) |

---

## Color & Usage

| Color | When to use |
|---|---|
| **Red dot** | New feature releases or updates requiring user attention |
| **Green dot** | In-progress or live status (e.g. "Open", "Live auction") |

---

## Red Dot Lifecycle

Red dot has a defined lifecycle — it is not a permanent indicator:

1. **Feature released** → Red dot appears
2. **User enters the feature** → Red dot disappears for that user
3. **3 versions after release** → Red dot is completely removed from the product

> Red dot is a temporary notification, not a persistent status. Do not use it for states that should remain visible indefinitely.

---

## Placement & Spacing

| Context | Offset from element |
|---|---|
| Used with an icon | 2px from top, 2px from right of the icon |
| Used with text | 2px from the right of the text |

- Icon touch area when status badge is present: **32×32px**
- Dot disappears after clicking — touch area remains the same

---

## Usage Examples

Can be placed in various contexts:

| Context | Color | Example |
|---|---|---|
| Account icon | Red dot | On Basic / VIP account icon — signals new notification |
| Tab | Red dot | On "Stats" tab — disappears after user visits the tab |
| Text label | Red dot | Next to "Rewards hub" — disappears after user enters |
| Live status | Green dot | "Open", "Live auction ends in 5 days" |

---

## Audit Checklist

```
🔴 Critical
- Red dot used for a permanent/persistent state
  → Red dot is temporary — it should disappear after user interaction or be removed within 3 versions

🟡 Warning
- Non-FDS Status Badge detected (manually drawn dot instead of FDS component)
- Size not 5×5px (size is fixed and should not be changed)
- Red dot used for a live/ongoing status → use Green dot instead
- Green dot used for a new feature notification → use Red dot instead
```
