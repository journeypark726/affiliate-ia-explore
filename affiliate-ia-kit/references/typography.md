# FDS Typography Reference

## Base Settings

| Property | Value |
|---|---|
| Font Family | `Pretendard` |
| Weight/Regular | `400` |
| Weight/SemiBold | `600` |
| Weight/Bold | `700` |

> Only these three weights are used in FDS. Never use other weight values.
>
> **Why Pretendard?** Supports both Korean and English, offers variable font, and provides a wide range of weights.
>
> **Why only 3 weights?** Excessive weights blur visual hierarchy. Three levels provide sufficient differentiation. Adding Medium (500) was considered but rejected — too similar to Regular (400).

---

## iOS Line-Height Note

iOS applies line-height in `pt` units separately.
For **Display** and **Title** scales, apply **-2pt** from the Figma value for visual balance.
Text scale line-heights apply as-is.

---

## Display Scale

Bold only. Desktop and Mobile sizes differ.

| Token | Weight | Desktop | Mobile | Line-height | iOS line-height |
|---|---|---|---|---|---|
| `Display/XXL` | Bold | 64px | 40px | 112% | 45pt (-2) |
| `Display/XL` | Bold | 48px | 32px | 112% | 36pt (-2) |
| `Display/L` | Bold | 32px | 28px | 112% | 31pt (-2) |

---

## Title Scale

SemiBold only. Desktop and Mobile sizes differ for `Title/L` only.

| Token | Weight | Desktop | Mobile | Line-height | iOS line-height |
|---|---|---|---|---|---|
| `Title/L` | SemiBold | 28px | 24px | 112% | 27pt (-2) |
| `Title/M` | SemiBold | 24px | 24px | 112% | 27pt (-2) |
| `Title/S` | SemiBold | 20px | 20px | 112% | 22pt (-2) |
| `Title/XS` | SemiBold | 18px | 18px | 112% | 20pt (-2) |

> **Note:** `Title/L` and `Title/M` are both 24px on mobile.
> If 28px is needed on mobile, use `Display/L` instead.

---

## Text Scale

Desktop and Mobile sizes are identical.

| Token | Weight | Size | Line-height | iOS line-height |
|---|---|---|---|---|
| `Text/L/Strong` | SemiBold | 16px | 135% | 22pt |
| `Text/L/Regular` | Regular | 16px | 135% | 22pt |
| `Text/L/Underline Strong` | SemiBold | 16px | 135% | 22pt |
| `Text/M/Strong` | SemiBold | 14px | 140% | 20pt |
| `Text/M/Regular` | Regular | 14px | 140% | 20pt |
| `Text/M/Underline Strong` | SemiBold | 14px | 140% | 20pt |
| `Text/S/Strong` | SemiBold | 12px | 140% | 17pt |
| `Text/S/Regular` | Regular | 12px | 140% | 17pt |
| `Text/S/Underline Strong` | SemiBold | 12px | 140% | 17pt |
| `Text/XS/Strong` | SemiBold | 11px | 140% | 15pt |
| `Text/XS/Regular` | Regular | 11px | 140% | 15pt |
| `Text/XXS/Strong` | SemiBold | 10px | 140% | 14pt |
| `Text/XXS/Regular` | Regular | 10px | 120% | 12pt |

### Underline Rules
- SemiBold weight only — never Regular
- Available only on `Text/S`, `Text/M`, `Text/L` (12px–16px)
- `Text/XS` and `Text/XXS` do not have an Underline variant

> **Why SemiBold only?** Regular + underline lacks sufficient visual emphasis. Underline at XS/XXS sizes reduces readability significantly.

---

## Monospace Scale

Used for **numeric/financial data only**. Token structure mirrors the standard Text/Title scale.

> **Why Monospace for numbers only?** Ensures visual stability and alignment for real-time changing values. Applying Monospace to body text degrades readability.

### Title (Monospace)

| Token | Weight | Desktop | Mobile | Line-height | iOS line-height |
|---|---|---|---|---|---|
| `Monospace/Title/L` | SemiBold | 28px | 24px | 112% | 27pt (-2) |
| `Monospace/Title/M` | SemiBold | 24px | 24px | 112% | 27pt (-2) |
| `Monospace/Title/S` | SemiBold | 20px | 20px | 112% | 22pt (-2) |
| `Monospace/Title/XS` | SemiBold | 18px | 18px | 112% | 20pt (-2) |

### Text (Monospace)

| Token | Weight | Size | Line-height | iOS line-height |
|---|---|---|---|---|
| `Monospace/Text/L/Strong` | SemiBold | 16px | 135% | 22pt |
| `Monospace/Text/L/Regular` | Regular | 16px | 135% | 22pt |
| `Monospace/Text/L/Underline Strong` | SemiBold | 16px | 135% | 22pt |
| `Monospace/Text/M/Strong` | SemiBold | 14px | 140% | 20pt |
| `Monospace/Text/M/Regular` | Regular | 14px | 140% | 20pt |
| `Monospace/Text/M/Underline Strong` | SemiBold | 14px | 140% | 20pt |
| `Monospace/Text/S/Strong` | SemiBold | 12px | 140% | 17pt |
| `Monospace/Text/S/Regular` | Regular | 12px | 140% | 17pt |
| `Monospace/Text/S/Underline Strong` | SemiBold | 12px | 140% | 17pt |
| `Monospace/Text/XS/Strong` | SemiBold | 11px | 140% | 15pt |
| `Monospace/Text/XS/Regular` | Regular | 11px | 140% | 15pt |
| `Monospace/Text/XXS/Strong` | SemiBold | 10px | 140% | 14pt |
| `Monospace/Text/XXS/Regular` | Regular | 10px | 120% | 12pt |

### When to Use Monospace ✅
- Real-time price data and change rates
- All numeric values related to amounts or values (prices, %, dates)
- Tables or areas where values update frequently — maintains visual alignment and readability

### When NOT to Use Monospace ❌
- Body text or titles where text is the primary content — do not apply Monospace to inline numbers within prose

### Mixed English + Numbers
- **Method 1 (recommended):** Apply Monospace to the entire Frame → fixed-width automatically applies to numbers only
- **Method 2:** Split into separate Frames — regular text / Monospace numbers

---

## Missing Monospace Detection Guide

When numeric/financial elements are found without Monospace applied, output the following guidance:

```
🟡 Warning — Monospace not applied to real-time/financial values

  Found: [element name] displaying numbers in regular Pretendard
  Values: [specific content — price, rate, P&L, etc.]

  → Apply Monospace font to this element.

  Why:
  - Real-time values shift digit counts — fixed-width prevents layout jitter
  - Monospace maintains visual alignment and readability for numeric data

  How to fix:
  - Apply a Monospace token to the text node (e.g. Monospace/Text/M/Regular)
  - For mixed English + numbers: apply Monospace to the entire Frame
    → numbers automatically render in fixed-width

  Common cases that require Monospace:
  - Real-time prices (e.g. $42,150.30)
  - Change rates / returns (e.g. +3.52%, -1.2%)
  - Position amounts, P&L values
  - Quantities, leverage multipliers (e.g. 10x)
  - Countdowns, timers
```

### Cases That Require Monospace

| Case | Example | Recommended Token |
|---|---|---|
| Real-time price | `$42,150.30` | `Monospace/Text/*/Regular` or `Strong` |
| Change rate / return | `+3.52%`, `-1.2%` | `Monospace/Text/*/Regular` |
| P&L / unrealized profit | `+$1,234.56` | `Monospace/Text/*/Strong` (for emphasis) |
| Quantity / leverage | `0.5 BTC`, `10x` | `Monospace/Text/*/Regular` |
| Large headline values | Total assets, main price | `Monospace/Title/*` |

---

## Audit Checklist

```
🔴 Critical
- Non-Pretendard font used
- Underline applied to Text/XS or Text/XXS
- Underline applied with Regular weight
- Font weight other than 400, 600, or 700 used

🟡 Warning
- Numeric/financial data displayed without Monospace
  → Real-time prices, change rates, P&L — must use Monospace
  → Fix: Apply Monospace token, or apply Monospace to the entire Frame
- Mobile requires 28px but Title/L used instead of Display/L
- iOS Display/Title line-height not adjusted by -2pt

🟢 Tip
- For mixed English + numbers, applying Monospace to the whole Frame
  is simpler and recommended over splitting Frames
```
