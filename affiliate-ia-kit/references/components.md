# FDS Component Reference

## Component Naming Convention

All FDS components follow this pattern:
```
ComponentName/Variant/State
```

Examples:
- `Button/Primary/Default`
- `Button/Primary/Hover`
- `Icon button/Default/Disabled`
- `Radio Button/Selected/Default`

### Figma Health Signals
| Signal | Meaning |
|---|---|
| Layer named `Button/Primary/Default` | ✅ Using FDS component correctly |
| Layer named `Frame 12` or `Rectangle` | 🟡 Not using components — flag |
| Layer marked as Detached | 🟡 Component instance detached from library |

---

## Active Library

Use only components from **❖ Flipster Design System**.

| Library | Status |
|---|---|
| ❖ Flipster Design System | ✅ Current — use this |
| Flipster UI Component Library "22 | 🗄️ Archived — do not use |
| ⚠️ TEST | 🧪 Test only — do not use in production |

---

## Component Specs & Guidelines

> Each component includes **specs**, **usage rules**, and **caveats**.
> Items marked `[TODO]` need detailed specs to be added.

---

### Button
→ See dedicated file: `references/button.md`

---

### Text Button
→ See dedicated file: `references/text-button.md`

---

### Icon Button
→ See dedicated file: `references/icon-button.md`

---

### Radio Button

**Purpose:** Single selection option

**States:** Selected, Unselected, Disabled

**Specs:**
| Property | Value |
|---|---|
| Default label style | `Text/L/Regular` |
| 2+ line labels | Align radio button to top, gap 4px |

**Usage Rules:**
- Label text size and color can be adjusted based on context
- For 2+ line labels: must top-align with gap 4px

**Context & History:**
- [TODO]

---

### Checkbox

**Purpose:** Multi-selection option

**States:** Checked, Unchecked, Indeterminate, Disabled

**Specs:**
| Property | Value |
|---|---|
| Default label style | `Text/L/Regular` |
| 2+ line labels | Align checkbox to top, gap 4px |

**Usage Rules:**
- Same label rules as Radio Button
- Indeterminate state is used for partial selection

**Context & History:**
- [TODO]

---

### TopAppBar

**Purpose:** Top navigation bar for screens

**Specs:**
| Property | Value |
|---|---|
| Contains | Back navigation, title, optional actions |
| [TODO] | Height, padding, and detailed specs |

**Context & History:**
- [TODO]

---

### Alert Banner

**Purpose:** Full-width informational or warning message

**Specs:**
| Property | Value |
|---|---|
| Position | Top of screen or section |
| [TODO] | Height, padding, icon specs, etc. |

**Context & History:**
- [TODO]

---

### Snackbar

**Purpose:** Transient feedback message (max 2 lines)

**Specs:**
| Property | Value |
|---|---|
| Max lines | 2 |
| 1-line message | No period at end |
| 2+ line message | Period at end of last sentence |
| App/Mobile web bottom offset | **64px** |
| Desktop bottom offset | **48px** |

**Usage Rules:**
- Verify correct bottom offset per device
- Check Appearances frame setting for proper offset

**Caveats:**
- ⚠️ Offset values differ by device — App 64px / Desktop 48px, don't mix them up

> **Why different offsets?** Mobile accounts for the bottom navigation bar (64px). Desktop sits closer to the screen edge (48px).

---

### Loading

**Purpose:** Loading indicator for async operations

**Specs:**
| Property | Value |
|---|---|
| Scope | Component-level, section-level, or full-page |
| [TODO] | Size, color, animation specs |

**Context & History:**
- [TODO]

---

### TooltipTrigger

**Purpose:** Trigger element that activates a tooltip on interaction

**Usage Rules:**
- Always pair with descriptive tooltip content

**Specs:**
- [TODO — trigger area, activation method, position rules]

**Context & History:**
- [TODO]

---

## Component Addition Template

Use this format when documenting new components:

```markdown
### [Component Name]

**Purpose:** [One-line description]

**Variants:** [List of variants]
**States:** [List of states]

**Specs:**
| Property | Value |
|---|---|
| [Property name] | [Value] |

**Usage Rules:**
- [Rule 1]
- [Rule 2]

**Caveats:**
- [Caveat]

**Context & History:**
- **Added**: YYYY-MM-DD
- **Why it was created**: [Problem it solves]
- **Key decisions**: [Decisions and rationale]
- **Known constraints / future plans**: [Limitations or plans]
```

---

## Figma Audit Checklist

```
🔴 Critical
- Component from Archived or TEST library used in production design
- Component naming convention not followed (must be ComponentName/Variant/State)

🟡 Warning
- Layer named generically (Frame 12, Rectangle, Group 7) — not using components
- Detached component instance found
- Icon Button used alongside a standard Button in the same action group
- Text Button used for inline sentence links (use Underline text style instead)
- Snackbar bottom offset not matching device spec (App: 64px / Desktop: 48px)
- Radio Button or Checkbox with 2+ line label not top-aligned with gap 4px

🟢 Tip
- Consider replacing raw layers with the matching FDS component
- Reattach detached component instances where possible
```
