# FDS Spacing Reference

> ⚠️ **These are recommended values, not enforced tokens.**
> Violations are flagged as warnings, not critical issues.
> Audit feedback should guide toward these values, not enforce them strictly.

---

## Rules

- **Mobile and Desktop values are identical**
- **Odd numbers are not allowed** — always flag as Critical
- **Multiples of 4 are preferred** as the base unit
- **Other even numbers are acceptable** when necessary (e.g. 6px, 10px, 14px)

> **Why 4px base?** 4px grid provides consistent rhythm. Odd values cause sub-pixel rendering issues.
>
> **Why recommended, not enforced?** Layout needs flexibility. Even numbers like 6px and 10px are acceptable when 4-base values don't fit the context.

---

## Recommended Scale

| Token | Value |
|---|---|
| `spacing-2` | 2px |
| `spacing-4` | 4px |
| `spacing-8` | 8px |
| `spacing-10` | 10px |
| `spacing-12` | 12px |
| `spacing-16` | 16px |
| `spacing-20` | 20px |
| `spacing-24` | 24px |
| `spacing-32` | 32px |
| `spacing-40` | 40px |
| `spacing-48` | 48px |
| `spacing-64` | 64px |
| `spacing-80` | 80px |
| `spacing-96` | 96px |
| `spacing-160` | 160px |

---

## Audit Behavior

```
🔴 Critical — Odd spacing value
  Found: padding: 13px
  → Odd numbers are not allowed in FDS.
  Suggested alternatives:
  - spacing-12 (12px)
  - spacing-16 (16px)

🟡 Warning — Non-recommended spacing value
  Found: gap: 6px
  → 6px is not in the recommended scale, but is acceptable as an even number.
  If 4px feels too tight and 8px too loose, 6px is fine.

🟢 Tip — Consider aligning to the 4-base scale
  Found: margin: 10px
  → spacing-10 exists in the scale — this is acceptable.
  If adjustable, spacing-8 or spacing-12 would better align
  with the 4-base system.
```
