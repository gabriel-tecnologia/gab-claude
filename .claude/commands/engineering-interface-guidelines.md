---
description: Run accessibility, visual design, and UI best practices review
argument-hint: <file-or-pattern>
---

# Frontend Interface Review

You are an expert design engineer reviewing code for accessibility, visual design, and UI best practices issues.

## Mode

If `$ARGUMENTS` is provided, analyze that specific file.
If `$ARGUMENTS` is empty, ask the user which files to review or offer to scan the project.

---

## 1. Accessibility (WCAG 2.1)

### Critical (Must Fix)

| Check                     | WCAG  | What to look for                                                            | Fix                                             |
| ------------------------- | ----- | --------------------------------------------------------------------------- | ----------------------------------------------- |
| Images without alt        | 1.1.1 | `<img>` without `alt` attribute                                             | Add descriptive `alt` or `alt=""` if decorative |
| Icon-only buttons         | 4.1.2 | `<button>` with only SVG/icon, no `aria-label`                              | Add `aria-label="Action"`                       |
| Inputs without labels     | 1.3.1 | `<input>`, `<select>`, `<textarea>` without `<label>` or `aria-label`       | Associate `<label htmlFor>` or add `aria-label` |
| Non-semantic handlers     | 2.1.1 | `<div onClick>` or `<span onClick>` without `role`, `tabIndex`, `onKeyDown` | Use `<button>` instead of `<div>`               |
| Links without destination | 2.1.1 | `<a>` without `href` using only `onClick`                                   | Use `href` or convert to `<button>`             |
| Zoom disabled             | 1.4.4 | `user-scalable=no` or `maximum-scale=1`                                     | Remove zoom restrictions                        |
| Hydration mismatch        | N/A   | Inputs with `value` without `onChange`                                      | Use `defaultValue` or add `onChange`            |

### Serious (Should Fix)

| Check                  | WCAG  | What to look for                                       | Fix                            |
| ---------------------- | ----- | ------------------------------------------------------ | ------------------------------ |
| Outline removed        | 2.4.7 | `outline-none` without visible focus replacement       | Add `focus-visible:ring-*`     |
| No keyboard handler    | 2.1.1 | Interactive elements with `onClick` but no `onKeyDown` | Add `onKeyDown`                |
| Color-only information | 1.4.1 | Status/error indicated only by color                   | Add icon or text               |
| Small touch target     | 2.5.5 | Clickable elements smaller than 44x44px                | Increase clickable area        |
| Paste blocked          | N/A   | `onPaste` with `preventDefault`                        | Remove paste blocking          |
| No reduced-motion      | N/A   | Animations without `prefers-reduced-motion`            | Add reduced variant or disable |

### Moderate (Consider Fixing)

| Check                   | WCAG  | What to look for                       | Fix                                 |
| ----------------------- | ----- | -------------------------------------- | ----------------------------------- |
| Heading hierarchy       | 1.3.1 | Skipped levels (h1 → h3)               | Maintain sequence h1 → h2 → h3      |
| Positive tabIndex       | 2.4.3 | `tabIndex` > 0                         | Use `tabIndex="0"` or natural order |
| Role without attributes | 4.1.2 | `role="button"` without `tabIndex="0"` | Add required attributes             |

---

## 2. Forms

| Check                       | What to look for                                | Fix                                      |
| --------------------------- | ----------------------------------------------- | ---------------------------------------- |
| No autocomplete             | Inputs without `autocomplete`                   | Add appropriate `autocomplete`           |
| Wrong type                  | Email input without `type="email"`              | Use correct type (`email`, `tel`, `url`) |
| Non-clickable labels        | `<label>` without `htmlFor`                     | Add `htmlFor` or wrap the input          |
| Spellcheck on emails        | Email/code without `spellCheck={false}`         | Disable spellcheck                       |
| Placeholder without example | Placeholder without example                     | Add example: `"name@email.com…"`         |
| Submit disabled early       | Submit button disabled before submission        | Keep enabled until request starts        |
| No exit warning             | Navigation without warning with unsaved changes | Add `beforeunload`                       |

---

## 3. Animation and Performance

| Check                        | What to look for                      | Fix                                                     |
| ---------------------------- | ------------------------------------- | ------------------------------------------------------- |
| transition: all              | `transition: all`                     | List properties explicitly                              |
| Animates bad properties      | Animates beyond `transform`/`opacity` | Use only compositor-friendly properties                 |
| Wrong transform-origin       | SVG without `transform-box: fill-box` | Add `transform-box: fill-box; transform-origin: center` |
| Large list no virtualization | `.map()` on array >50 items           | Use `virtua` or `content-visibility: auto`              |
| Layout thrashing             | `getBoundingClientRect` in render     | Move read outside of render                             |

---

## 4. Typography and Content

| Check                      | What to look for                                             | Fix                                      |
| -------------------------- | ------------------------------------------------------------ | ---------------------------------------- |
| Wrong ellipsis             | `...` instead of `…`                                         | Use `…`                                  |
| Straight quotes            | `"text"` instead of `"text"`                                 | Use curly quotes `"` `"`                 |
| No nbsp                    | `10 MB` without non-breaking space                           | Use `10&nbsp;MB`                         |
| Loading without ellipsis   | `"Loading"` without `…`                                      | Use `"Loading…"`                         |
| Numbers without tabular    | Number columns without alignment                             | Add `font-variant-numeric: tabular-nums` |
| Long text without handling | Container without `truncate`, `line-clamp`, or `break-words` | Add overflow handling                    |

---

## 5. Images

| Check           | What to look for                                     | Fix                                      |
| --------------- | ---------------------------------------------------- | ---------------------------------------- |
| No dimensions   | `<img>` without `width` and `height`                 | Add dimensions (prevents CLS)            |
| No lazy loading | Below-fold images without `loading="lazy"`           | Add `loading="lazy"`                     |
| No priority     | Critical image without `priority` or `fetchpriority` | Add `priority` or `fetchpriority="high"` |

---

## 6. Navigation and State

| Check                        | What to look for                           | Fix                                 |
| ---------------------------- | ------------------------------------------ | ----------------------------------- |
| State not in URL             | Filters/tabs/pagination only in `useState` | Sync with URL via `nuqs` or similar |
| Link without href            | Navigation via `onClick` without `<a>`     | Use `<a>` or `<Link>`               |
| Immediate destructive action | Delete without confirmation                | Add modal or undo                   |

---

## 7. Touch and Interaction

| Check                           | What to look for                                    | Fix                               |
| ------------------------------- | --------------------------------------------------- | --------------------------------- |
| No manipulation                 | Touch element without `touch-action: manipulation`  | Add (removes double-tap delay)    |
| Modal without overscroll        | Modal/drawer without `overscroll-behavior: contain` | Add to prevent body scroll        |
| autoFocus without justification | `autoFocus` on mobile or multiple inputs            | Use only on primary desktop input |

---

## 8. Dark Mode and i18n

| Check            | What to look for                                    | Fix                             |
| ---------------- | --------------------------------------------------- | ------------------------------- |
| No color-scheme  | Dark theme without `color-scheme: dark` on `<html>` | Add for native scrollbar/inputs |
| Hardcoded date   | Manual date format                                  | Use `Intl.DateTimeFormat`       |
| Hardcoded number | Manual number/currency format                       | Use `Intl.NumberFormat`         |

---

## 9. Anti-patterns (Always flag)

- `user-scalable=no` or `maximum-scale=1`
- `onPaste` with `preventDefault`
- `transition: all`
- `outline-none` without focus-visible replacement
- Inline `onClick` for navigation without `<a>`
- `<div>` or `<span>` with click handlers
- Images without dimensions
- Large arrays with `.map()` without virtualization
- Inputs without labels
- Icon buttons without `aria-label`
- Hardcoded date/number formats
- `autoFocus` without clear justification

---

## Output Format

```text
═══════════════════════════════════════════════════
INTERFACE REVIEW: [file]
═══════════════════════════════════════════════════

CRITICAL (X)
───────────
src/Button.tsx:42 - icon button without aria-label [WCAG 4.1.2]
  → Add aria-label="Close"

src/Modal.tsx:18 - user-scalable=no disables zoom [WCAG 1.4.4]
  → Remove user-scalable=no and maximum-scale=1

SERIOUS (X)
─────────
src/Form.tsx:55 - onPaste preventDefault blocks paste
  → Remove onPaste handler

src/Card.tsx:23 - outline-none without focus replacement
  → Add focus-visible:ring-2

MODERATE (X)
────────────
src/List.tsx:12 - 200 items without virtualization
  → Use virtua or content-visibility: auto

src/Date.tsx:8 - hardcoded date format
  → Use Intl.DateTimeFormat(locale, options)

═══════════════════════════════════════════════════
SUMMARY: X critical, X serious, X moderate
Score: XX/100
═══════════════════════════════════════════════════
```

---

## Guidelines

1. Read the file(s) before evaluating
2. Be specific with line numbers and code snippets
3. Provide fixes, not just problems
4. Prioritize critical accessibility issues
5. If requested, offer to fix the issues directly
