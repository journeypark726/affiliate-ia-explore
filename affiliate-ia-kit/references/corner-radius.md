# FDS Corner Radius Reference

> ⚠️ **These are recommended values, not enforced tokens.**
> Violations are flagged as warnings, not critical issues.
>
> **Why recommended, not enforced?** Component size and context require flexibility.
>
> **Why `full` = 1000px?** Use `1000px` for fully rounded pill shapes — not `9999px` or `50%`.

---

## Recommended Scale

| Token | Value | Typical Usage |
|---|---|---|
| `radius-0` | 0px | Sharp corners — tables, dense data UIs |
| `radius-4` | 4px | Small elements — badges, tags, small chips |
| `radius-8` | 8px | Buttons, inputs, small cards |
| `radius-12` | 12px | Medium cards, dropdowns |
| `radius-16` | 16px | Large cards, panels |
| `radius-24` | 24px | Modals, bottom sheets |
| `radius-28` | 28px | Large containers |
| `full` | 1000px | Pills — chips, toggles, fully rounded elements |

---

## Audit Behavior

```
🟡 Warning — Non-recommended radius value
  Found: border-radius: 10px
  → 10px is not in the FDS recommended radius scale.
  Suggested alternatives:
  - radius-8  (8px)  — if subtle rounding is needed
  - radius-12 (12px) — if a rounder feel is needed
  Note: This is a recommended value, not an enforced token.
```
