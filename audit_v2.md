# Drift v2 -- QA Audit Report

**Auditor:** Nash (OpenClaw QA)
**Date:** 2026-03-29
**File:** `index.html` (1623 lines) | `sw.js` (13 lines)
**Scope:** Multiple Habits, Weekly Insights, Data Export, regressions, a11y

---

## Score: 82 / 100

Solid v2 upgrade. Core architecture (per-habit isolation, migration, tabs) is well done. Several P2 issues around a11y semantics and one P1 around XSS in the add-habit modal.

---

## P1 -- Critical

### P1-1: innerHTML XSS in Add Habit modal (line 1139)

`onAddHabit()` builds the modal input via `elModalText.innerHTML = '<input ...'` -- this itself is safe for the injected input element, BUT the **delete modal** path uses `escapeHtml()` properly (line 1396). The actual risk is that if any future code path sets modal text from user input via innerHTML without escaping, it becomes exploitable. More importantly, the **export** function (line 1489) writes `h.name` raw into the text blob -- this is safe for `.txt` but the habit name is never sanitized on input. A habit name like `<img src=x onerror=alert(1)>` would render harmlessly in `.value` (input element) and `.textContent` (tabs), so the current code is safe by accident. **Downgraded to P2** on re-analysis -- see P2-1.

**Revised: No active P1 issues.**

---

## P2 -- Important

### P2-1: innerHTML usage in modal (line 1139)

`onAddHabit()` uses `elModalText.innerHTML` to inject an `<input>` element. While no user-controlled data flows into this specific call, this pattern is fragile. If the modal is ever reused with user data in innerHTML without escaping, XSS results. Should use `document.createElement('input')` and `appendChild()` instead.

**Fix:** Replace innerHTML with DOM API.

### P2-2: Tab `role="tab"` without `role="tabpanel"` (line 902-1125)

Tabs have `role="tablist"` and individual `role="tab"` with `aria-selected`, which is good. However:
- No `role="tabpanel"` on the content area
- No `aria-controls` on tabs linking to the panel
- No `id` attributes on tabs for `aria-labelledby` on the panel
- The "+" add button inside the tablist has no `role="tab"` but sits inside a `role="tablist"`, which is a WCAG violation (only `role="tab"` children are valid inside `role="tablist"`)

**WCAG:** 4.1.2 Name, Role, Value (AA)

### P2-3: Weekly insights trend division by zero edge case (line 1276)

When `prevWeekDone === 0` and `weekDone > 0`, the code correctly shows "new" (line 1273-1274). However, when `prevWeekDone > 0` and `weekDone === 0`, the trend shows "-100%" which is technically correct but could be more user-friendly ("no activity this week"). Minor UX issue.

### P2-4: Long press to delete only works on habit name, not discoverable (lines 1376-1387)

The delete action is triggered by long-pressing the habit name input. There is no visible UI affordance (no delete button, no swipe hint). Users may never discover this. The delete confirmation modal is well-implemented (escapeHtml, focus trap, Escape to close, click-outside-to-close), but the trigger is hidden.

**Fix:** Add a visible delete option (e.g., context menu on tab, or small icon button).

### P2-5: `drift-welcome-cta` button missing `focus-visible` (line 831-851)

The welcome overlay CTA button has `:hover` and `:active` styles but no `:focus-visible` outline. Keyboard users cannot see focus on this button.

**WCAG:** 2.4.7 Focus Visible (AA)

### P2-6: Welcome overlay not keyboard-dismissable and no focus trap

The welcome overlay (`#drift-welcome`) shows on first visit but:
- Has no focus trap (Tab can go behind the overlay)
- No `role="dialog"` or `aria-modal="true"`
- No Escape key handler

The main modal correctly implements all of these, but the welcome overlay does not.

**WCAG:** 2.1.2 No Keyboard Trap (A), 1.3.1 Info and Relationships (A)

---

## P3 -- Minor / Cosmetic

### P3-1: `tabindex` not set on tabs for keyboard navigation

Tab widgets should support arrow-key navigation between tabs (`tabindex="0"` on active tab, `tabindex="-1"` on inactive tabs, with ArrowLeft/ArrowRight handlers). Currently all tabs are `<button>` elements (focusable by default), so Tab key works, but the ARIA Authoring Practices tab pattern is not fully implemented.

### P3-2: Heatmap dots have no accessible day info beyond `title`

Heatmap dots use `title` attribute for date info. Screen readers may not announce `title` reliably. Consider `aria-label` on each dot, or a visually-hidden summary.

### P3-3: Export does not sanitize habit names for file content

Export writes habit names directly into plain text (`lines.push('--- ' + h.name + ' ---')`). For `.txt` this is safe, but if export format ever changes to HTML/CSV, injection becomes possible.

### P3-4: `prefers-reduced-motion` covers all animations globally (line 855-872)

The blanket `animation-duration: 0.01ms !important` and `transition-duration: 0.01ms !important` on all elements is correct and covers all new v2 animations (weekly bar transitions, tab transitions, toast). This is a PASS.

### P3-5: No visual limit feedback at 5 habits

When max habits (5) is reached, the "+" button simply disappears. No feedback tells the user why. Consider a brief tooltip or toast.

### P3-6: `generateId()` uses `substr` (line 1048)

`String.prototype.substr` is deprecated in favor of `substring` or `slice`. Still works in all browsers but is a code quality nit.

### P3-7: Weekly bars -- "last 7 days" vs "calendar week" ambiguity

`renderWeekly()` uses "last 7 days ending today" (lines 1254-1259), not calendar week (Sun-Sat). The header says "This Week" which may confuse users expecting Mon-Sun. Minor UX mismatch.

---

## Passed Checks

| Area | Status | Notes |
|------|--------|-------|
| Data isolation between habits | PASS | Each habit has its own `days[]` array, indexed by `activeIdx`. Switching tabs calls `renderCurrent(false)` which reads from the correct `habits[activeIdx]`. |
| localStorage serialization | PASS | `JSON.stringify` / `JSON.parse` with try/catch on both load and save (lines 1012-1045). |
| v1 migration | PASS | `LEGACY_KEY` ('drift_data') migrated to new array format, old key removed (lines 1022-1036). |
| Habit deletion confirmation | PASS | Modal with "Delete" + "Cancel", escapeHtml on name, focus trap, Escape/click-outside to close. |
| Deletion data cleanup | PASS | `habits.splice(activeIdx, 1)` + `saveHabits()`. If last habit deleted, returns to onboarding. |
| Weekly insights calculation | PASS | 7-day rolling window, trend vs previous 7 days. Edge cases handled (both zero, previous zero). |
| Export includes all habits | PASS | Iterates all `habits[]` (line 1485). |
| Export XSS | PASS | Habit names go into `.textContent` (tabs, modal title via escapeHtml) and `.value` (input). Plain text export. No HTML rendering of user input. |
| Momentum meter | PASS | 30-day window, percentage calculation, color gradient, ARIA label updated. |
| Heatmap | PASS | 30 dots, today highlighted, animation on mark. |
| Particles | PASS | Spawn on mark, removed after 450ms, hidden with reduced-motion. |
| Phrases | PASS | Fade transition on change, correct bracket matching. |
| Dark mode | PASS | CSS custom properties swap correctly in `prefers-color-scheme: dark`. All v2 elements use the same variables. |
| `focus-visible` on new elements | PASS | `.habit-tab:focus-visible` (line 244), `.weekly-toggle:focus-visible` (line 480), `.export-btn:focus-visible` (line 596), `.modal-btn:focus-visible` (line 692). |
| `prefers-reduced-motion` | PASS | Global blanket rule covers all v2 transitions and animations (line 855). |
| SW cache version bumped | PASS | `sw.js` line 1: `const CACHE = 'drift-v2'` -- correctly bumped to v2, old caches purged in activate handler. |
| Max habits enforced | PASS | `MAX_HABITS = 5`, checked in `onAddHabit()` and "+" button visibility (lines 1114, 1136). |

---

## Verdict

**PASS WITH CONDITIONS**

No P1 issues. Six P2 issues, mostly accessibility (tab semantics, welcome overlay a11y, focus-visible gap). Core v2 features (multi-habit, weekly insights, export) work correctly with proper data isolation and error handling. Fix P2-2 and P2-6 before shipping to meet WCAG AA compliance.

---

*Nash / OpenClaw QA -- 2026-03-29*
