---
name: fds-design-system
description: Flipster Design System (FDS) skill. Provides design auditing (token/component usage validation), decision context Q&A, and usage guide (token recommendations, component specs). Triggers on "check my design", "is this color right?", "why was this decided?", "which token should I use?", "component spec", "FDS rules", "review my UI", "design audit", or any FDS-related question.
---

# Flipster Design System (FDS) — Audit · Context · Guide

A skill for ensuring correct usage of the FDS internal design system.

## Two Modes

### 1. Audit Mode

Triggered when the user shares a Figma file, code, or screenshot for review.

**Workflow:**
1. Load all relevant reference files
2. If Figma MCP is available: call `get_design_context` → `get_screenshot`
3. Run audit against the checklists defined in each reference file
4. Output results in the Audit Report format

**Audit Report Format:**
```
## FDS Audit Report

### Overall Score: XX/100
[One-line summary]

### 🔴 Critical Issues
- [Issue]: [What's wrong] → Fix: [How to fix] → Why: [Reason]

### 🟡 Warnings
- [Issue]: [What's wrong] → Suggestion: [Recommendation]

### 🟢 Tips
- [Suggestion for improvement]

### ✅ What's Working Well
- [Positive observations]

### 🎯 Top 3 Priority Fixes
1. [Most important fix]
2. [Second fix]
3. [Third fix]
```

**Audit Categories:**

| # | Category | Reference File |
|---|---|---|
| 1 | Color & Tokens | color.md |
| 2 | Typography | typography.md |
| 3 | Spacing | spacing.md |
| 4 | Corner Radius | corner-radius.md |
| 5 | Component Naming & Usage | components.md |
| 6 | Interaction States (hover/disabled) | color.md |
| 7 | Icon Usage & Naming | icons.md |
| 8 | Figma Structure & Token Health | components.md |

---

### 2. Q&A Mode (Guide & Context)

Triggered when the user asks about FDS rules, token usage, component behavior, or design decisions.
Examples: "which token should I use?", "how do I use this component?", "why was this decided?", "what are FDS rules?"

**Workflow:**
1. Load the relevant reference file based on the question domain
2. Answer directly using the rules, specs, and context (including "Why" notes) in the reference
3. Include specific token names, values, and usage examples when possible

**Response Principles:**
- Always recommend semantic tokens first
- Provide **clear recommendations with reasoning**, not "either works"
- For component questions, include specs, usage rules, and caveats
- For "why" questions, look for `> **Why...**` blockquotes in reference files — these contain decision context and alternatives considered
- If no context exists for a question, respond: "No decision context has been recorded for this item yet. If you know the background, share it and I'll add it to the relevant reference file."

---

## Reference Files

Load the relevant file based on what's being audited or asked about:

| Domain | File |
|---|---|
| Color tokens, palette, semantic colors, gradients | `references/color.md` |
| Typography, font scale, Monospace | `references/typography.md` |
| Spacing values, grid rules | `references/spacing.md` |
| Border radius | `references/corner-radius.md` |
| Logo, favicon, app icon | `references/logo.md` |
| Layout, screen sizes, artboards, breakpoints | `references/layout.md` |
| Icons, naming, types, addition process | `references/icons.md` |
| Button (hierarchy, color, size, usage guide) | `references/button.md` |
| Text Button (usage, inline link vs text button, dashed underline) | `references/text-button.md` |
| Icon Button (hierarchy, icon color, touch area) | `references/icon-button.md` |
| Tabs (type, size, states, badge, border) | `references/tabs.md` |
| Badge (type, anatomy, color usage, non-clickable) | `references/badge.md` |
| Status Badge (red dot / green dot, lifecycle) | `references/status-badge.md` |
| Checkbox (states, touch area, error, overflow) | `references/checkbox.md` |
| Radio Button (single selection, touch area, error, overflow) | `references/radio-button.md` |
| Toggle (states, size, touch area) | `references/toggle.md` |
| Segmented Control (size, segments, states, overflow, disabled) | `references/segmented-control.md` |
| Dropdown Chip (type, highlight selection, radius, spacing, usecase) | `references/dropdown-chip.md` |
| Choice Chip (selected/unselected, content types, badge, spacing) | `references/choice-chip.md` |
| Spinner (color, Lottie animation, loading indicator) | `references/spinner.md` |
| Snackbar (type, placement, consecutive, edge cases) | `references/snackbar.md` |
| Other components, naming convention, Figma structure | `references/components.md` |

> Decision context and rationale ("Why was this decided?") are embedded directly in each reference file as `> **Why...**` blockquotes — no separate history file needed.

For a full audit, load all reference files.

---

## FDS Overview

- **Dark mode only** — No light mode tokens exist
- **Font**: Pretendard
- **Base unit**: 4px (multiples of 4 preferred, even numbers acceptable)
- **Component naming**: `ComponentName/Variant/State` (e.g. `Button/Primary/Default`)
- **Token priority**: Semantic token first → Palette token as fallback → Never hardcode hex values
- **Library**: Use only `❖ Flipster Design System` (Archived and TEST libraries are prohibited)

---

## Figma MCP Workflow

When auditing a Figma file:
1. `get_design_context` — Retrieve design info for the target node
2. `get_screenshot` — Visual verification
3. **Check if each component is an FDS component** (see FDS Component Detection below)
4. Check fills/colors against semantic token values
5. Check spacing and radius values against recommended scales
6. Output results in the Audit Report format

---

## FDS Component Detection

When auditing a node, determine whether it is a valid FDS component using these signals:

### ✅ Is an FDS component if ALL of the following are true:
- Layer type is `INSTANCE`
- `mainComponent.remote === true` (from an external library, not local)
- Component name follows `ComponentName/Variant/State` pattern (e.g. `Button/Primary/Default`)
- Source library is `❖ Flipster Design System`

### 🟡 Not using FDS component if ANY of the following:
- Layer type is `FRAME`, `RECTANGLE`, `GROUP`, or other raw node (not an instance)
- Layer name is generic (e.g. `Frame 12`, `Rectangle`, `Group 7`, `btn`, `button-old`)
- `mainComponent.remote === false` (local component, not from FDS library)
- Source library is `Flipster UI Component Library "22` (archived) or `⚠️ TEST` (test only)

### How to check via Figma MCP (`use_figma`):
```js
const node = figma.getNodeById("NODE_ID");
if (node.type === "INSTANCE") {
  const main = await node.getMainComponentAsync();
  return {
    isInstance: true,
    isRemote: main.remote,
    componentName: main.name,
    // Check if name follows ComponentName/Variant/State pattern
    followsNaming: /^[A-Za-z ]+\/[A-Za-z ]+\/[A-Za-z ]+$/.test(main.name)
  };
} else {
  return { isInstance: false, layerType: node.type, layerName: node.name };
}
```

### Output guidance:
- If `isInstance: false` → 🟡 Not using FDS component — flag and suggest the correct FDS component
- If `isRemote: false` → 🟡 Local component — not from FDS library
- If source library is archived → 🔴 Using archived library — must replace

When Figma MCP is not available, ask the user to share:
- A screenshot
- CSS values from Figma's Inspect panel
- Specific token names or hex values in use

---

## Adding Decision Context

When a user shares new decision context, add it to the **relevant reference file** (not a separate history file) using this format:

```markdown
> **Why [decision topic]?** [Reason and context]. [Alternative] was considered but rejected — [why].
```

Place it directly below the related rule or spec as a blockquote.
