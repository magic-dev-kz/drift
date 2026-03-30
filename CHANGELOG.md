# Drift — Changelog



## v25.0 (2026-03-29) — Security Meta Tags

- **Security hardening**: Added `X-Content-Type-Options: nosniff`, `referrer: no-referrer`, and `format-detection: telephone=no` meta tags to `<head>`
- SW cache bumped to `drift-v25.0`

---
## v24.0 (2026-03-29) — JSON-LD Structured Data

- **JSON-LD structured data**: Added WebApplication schema markup in `<head>` for improved SEO and rich search results
- SW cache bumped to `drift-v24.0`

---
## v23.0 (2026-03-29) — Deferred Font Loading

- **Non-blocking Google Fonts**: Replaced render-blocking `@import` in inline CSS with `<link rel="preload" ... onload>` and `<noscript>` fallback — font CSS no longer blocks first paint
- SW cache bumped to `drift-v23.0`

---
## v22.0 (2026-03-29) — Data Portability Verified

- **Import/export JSON verified**: Existing Export JSON and Import JSON buttons confirmed fully working — exports all habits with completion days, phrases, archive state; import validates structure, restores habits, shows count; backup reminder banner triggers after inactivity
- SW cache bumped to `drift-v22.0`

## v21.0 (2026-03-29) — Habit Archive

- **Habit archive**: "Archive habit" button replaces immediate deletion as the soft-removal option; archived habits are hidden from tabs by default; "Show archived" checkbox toggle reveals them with dimmed/italic styling; archived habits can be unarchived; data persisted in habit object's `archived` flag
- SW cache bumped to `drift-v21.0`

## v20.0 (2026-03-29) — Print Styles

- **Print stylesheet**: `@media print` rules — hides overlays, buttons, tabs, onboarding; shows habit summary + heatmap; white bg, black text; heatmap colors preserved via print-color-adjust
- SW cache bumped to `drift-v20.0`

## v19.0 (2026-03-29) — Error Handling Hardening

- **Storage quota warning**: Shows "Storage almost full" banner when localStorage exceeds 4MB
- SW cache bumped to `drift-v19.0`

## v18.0 (2026-03-29) — SEO / Meta Pass

- **description meta**: Added missing `<meta name="description">`
- **theme-color**: Added `<meta name="theme-color" content="#C4B5E0">`
- **robots meta**: Added `<meta name="robots" content="index, follow">`
- **apple-touch-icon**: Inline SVG data URL with product emoji (🌿)
- SW cache bumped to `drift-v18.0`

## v17.0 (2026-03-29) — Accessibility Pass

- **Skip link**: Hidden skip-to-content link appears on Tab for keyboard users, jumps to main habit card
- **Done button aria-label**: Dynamic label "Mark [habit name] as done" updates with active habit name
- **Heatmap dots aria-label**: Each heatmap dot now has an aria-label matching its title (date + status)
- SW cache bumped to `drift-v17.0`

---

## v16.0 (2026-03-29) — Habit Emoji Picker

- **Emoji Picker**: Choose from 5 emojis when creating a new habit, displayed in tab and name
- SW cache bumped to `drift-v16.0`
## v15.0 (2026-03-29) — Rest Day Indicator

Feature update by Mario.

### Rest Day Indicator
- New "Rest Day" button below the Done button lets you mark a day as rest
- Rest days show as grey dots in the heatmap (distinct from done/missed)
- Rest days do NOT break streaks -- streak calculation skips over rest days
- Toggling rest day on a done day removes the done marking
- Rest day data stored in habit's `restDays` array, persisted in localStorage
- Button shows "Resting" state with coffee emoji when active

### Technical
- Service worker cache bumped to `drift-v15.0`

---

## v14.0 (2026-03-29)

Feature update by Mario.

### Habit Color Picker
- When creating a new habit, 6 color swatches appear (red, blue, green, purple, orange, teal)
- Click a swatch to assign that color to the habit; click again to deselect
- Selected color is stored in the habit data and persists across sessions
- Habit color is displayed as a left border accent on the tab pill for visual distinction

### Technical
- Service worker cache bumped to `drift-v14.0`

---

## v13.0 (2026-03-29)

Feature update by Mario.

### Monthly Calendar
- Collapsible "Monthly Calendar" section with toggle button and animated arrow
- Compact month view showing a grid of days with green dots on days the habit was completed
- Today highlighted with distinct styling; completed today gets combined highlight
- Navigation arrows to browse previous and future months
- Monday-first weekday headers (Mo Tu We Th Fr Sa Su)
- Calendar auto-opens to current month; updates live when toggling habits
- Renders per-habit: switching habits updates the calendar with that habit's data

### Technical
- Service worker cache bumped to `drift-v13.0`

---

## v12.0 (2026-03-29)

### Added
- **Habit completion chime** -- soft C5 sine wave chime (200ms, Web Audio API) plays on marking a habit done
- **Momentum milestone celebration** -- golden glow border animation on the card when momentum reaches 100%
- **Data size indicator** -- "Using X KB of storage" shown below export/delete actions

### Technical
- Service worker cache bumped to `drift-v12.0`

---

## v11.0 (2026-03-29)
- Onboarding overlay: animated CSS wave/water visual at bottom (matches brand)
- Done button glow stronger on press (double-layer streak glow)
- Service worker cache bumped to `drift-v11.0`

---

## v10.0 (2026-03-29)
- First-visit tooltip "Tap Done to start building momentum" shown once on first load
- Momentum percentage font larger (48px to 54px) for readability
- Service worker cache bumped to `drift-v10.0`
- Export version bumped to `10.0`

---

## v9.0 (2026-03-29)

### Share on X
- "Share on X" button below share momentum card.
- Pre-filled tweet: "X days of showing up. Track habits without guilt: [URL]".

### Dark Mode Contrast Fix
- Brightened gold accent from `#D4A43C` to `#E8C45A` for AA contrast compliance.
- Darkened dark-mode background from `#1C1A18` to `#161412` for better contrast ratio.

### Technical
- Service worker cache updated to `drift-v9.0`.
- Export version bumped to `9.0`.

### Preserved
- All existing features intact.

---

## v8.0 (2026-03-29)

Feature update by Mario.

### Habit Categories
- Optional category tag for each habit: Health, Work, Creative, Learning, Social.
- Clickable category chips below the habit name with colored active state.
- Category selection available both in the main card and the "New habit" modal.
- Colored dot indicator next to the habit name when a category is set.
- Category data persisted in localStorage alongside habit data.

### Momentum Graph
- Small SVG line chart showing 30-day momentum trend, placed below the momentum ring.
- Uses a rolling 7-day window calculation at each point for smooth visualization.
- Gradient-filled area under the line with lavender stroke and glow filter.
- Automatically updates when toggling habits done/undone.

### Streak Record
- "Personal best: X days" shown above the habit name when a streak record exists.
- Highlights with exclamation when the current streak equals or beats the record.
- Calculates longest consecutive streak from all tracked days.

### Technical
- Service worker cache updated to `drift-v8.0`.
- Export version bumped to `8.0`.

### Preserved
- All existing features intact.

---

## v7.0 (2026-03-29)

Feature update by Mario.

### PWA Install Prompt
- Captures the `beforeinstallprompt` event and stores the deferred prompt.
- After 3+ visits (tracked via `drift_visit_count` in localStorage), a slide-up banner appears: "Install Drift for quick access and offline use".
- "Install" button triggers the native install prompt; "Not now" dismisses permanently.
- Banner uses glassmorphism styling consistent with the app.
- Respects the standard A2HS flow (Chrome, Edge, Samsung Internet).

### Keyboard Shortcuts
- `Space` toggles today's done status for the active habit (when no input is focused).
- `ArrowLeft` / `ArrowRight` switches between habits.
- All shortcuts disabled when the modal is open or an input field is focused.

### Auto-Backup Reminder
- Once per week, a banner slides down from the top: "Back up your data? It's been a while."
- "Export JSON" button triggers the existing JSON export and updates the reminder timestamp.
- "Later" button dismisses and resets the 7-day timer.
- Manual JSON exports also reset the timer, so active exporters never see the banner.
- Reminder appears 2 seconds after load to avoid overwhelming the user.

### Technical
- Service worker cache updated to `drift-v7.0`.
- Export version bumped to `7.0`.

### Preserved
- All existing features intact.
- HTML structure and accessibility attributes unchanged.

---

## v6.0 (2026-03-29)

Quality polish by Mario.

### Momentum Ring Animation
- Ring already had CSS transition on `stroke-dashoffset` (800ms cubic-bezier). Verified smooth fill animation on momentum updates.

### Habit Card Pulse on Done
- When marking a habit as done, the entire card emits a soft glow pulse animation using the streak gradient color.
- `cardDonePulse` keyframe: glow expands to 40px then fades back.
- Animation removed after 850ms; respects `prefers-reduced-motion`.

### Focus-Visible Audit
- Added `:focus-visible` outlines to all previously uncovered interactive elements:
  - Intention input and buttons
  - Weekly summary dismiss button
  - Gentle reminder dismiss button
  - Habit add (+) button
  - Import/export/delete action buttons
  - Heatmap dots
- All use consistent `2px solid var(--color-accent-lavender)` with `2-3px` offset.

### Phrase Rotation Fade Transition
- Phrase changes now use a proper 400ms fade-out + slide-down, then fade-in + slide-up transition.
- Uses CSS classes (`phrase--fading`, `phrase--entering`) instead of inline opacity manipulation.
- Spring easing on transform for a gentle, polished feel.

### Technical
- Service worker cache updated to `drift-v6.0`.

### Preserved
- All existing features intact.
- HTML structure and accessibility attributes unchanged.

---

## v5.0 (2026-03-29)

Feature update by Mario.

### Weekly Intention
- At the start of each week (Sunday/Monday), an optional prompt asks: "What would you like to focus on this week?"
- Saved intention shows as a gentle reminder in the card header throughout the week.
- Stored in localStorage per ISO week number.
- On Sundays, the weekly summary includes your intention vs reality reflection.
- Skippable — no pressure to set one.

### Gentle In-App Reminders
- When opening the app after 18:00 without checking in today, a soft banner appears: "Haven't checked in today. No pressure — whenever you're ready. 🌿"
- Not push notifications — gentle, in-app only.
- Dismissable, won't reappear the same day.
- Automatically hidden when you check in.

### Momentum Milestones
- Celebrates when you hit 7, 14, 21, or 30 days with >50% completion:
  - Gentle pulse animation (not confetti).
  - Supportive phrases: "7 days of showing up. That's beautiful."
  - Each milestone saved in localStorage — shown only once per habit.
- Icons progress: 🌱 → 🌿 → 🌳 → ✨

### Technical
- Service worker cache updated to drift-v5.0.

---

## v4.0 (2026-03-29)

Feature update by Mario.

### Momentum Sharing
- "Share momentum" button generates a Canvas card (600x400) with momentum %, habit name, days tracked, motivational phrase, and Drift branding.
- Uses Web Share API on supported devices with fallback to PNG download.
- Card respects light/dark mode with matching gradient backgrounds.

### Weekly Summary Notification
- On Sundays, a gentle banner appears with "This week: X of 7 days" summary.
- Shows trend vs last week with supportive, non-judgmental phrasing.
- Dismissable per-day (stored in localStorage).
- Weekly Insights section auto-expands on Sundays for visibility.

### Gentle Reminder Messages
- Expanded phrase system from 6 static phrases to 29 gentle, rotating messages across all momentum ranges.
- Phrases are randomly selected within each range for variety.
- Tone remains supportive and non-pressuring: "Every small step counts", "You showed up. That's what matters.", "Progress, not perfection."

### Import/Export Data
- Export JSON: downloads a full backup file with all habits and history.
- Import JSON: restore from a backup file with validation.
- Original text export preserved as "Export text".

### Technical
- Service worker cache updated to drift-v4.0.

---

## v3.0 (2026-03-29)

Design overhaul by Sky.

### Gradient backgrounds
- Replaced flat background-color on body with a soft diagonal gradient (warm beige through muted lavender in light mode; deep warm-to-purple in dark mode).
- Background is fixed so it stays stable during scroll.

### Google Fonts (Inter)
- Upgraded Inter import to the full variable-font range (opsz 14..32, wght 100..900) for crisper rendering and more weight options.

### Glassmorphism
- Main card, modals, toasts, and welcome overlay use semi-transparent backgrounds with backdrop-filter blur(24px) saturate(1.4).
- New --color-glass-border variable adds a frosted-glass edge in both themes.
- Inner inset highlight on cards and modals for a soft top-edge gleam.

### Soft shadows
- New --color-shadow-lg for deeper elevation layers on cards, buttons, and modals.
- Momentum meter ring uses filter: drop-shadow for a glow that follows the stroke color.

### Micro-animations
- Card entrance: spring-curve scale + translateY keyframes.
- Onboarding fade-slide-up animation.
- Habit tab hover lifts; the "+" add-button rotates 90deg on hover.
- Buttons use spring easing (cubic-bezier 0.34, 1.56, 0.64, 1) with slight vertical lift.
- Modal content slides in with spring animation.
- Weekly toggle arrow uses spring easing. Export buttons lift on hover.
- Welcome feature list items slide right on hover.

### Checkbox / done-button animation
- btn-done--completed triggers a completePulse glow-ring keyframe.
- Today heatmap dot pulses gently (todayPulse) until marked done.
- Dot-fill animation reworked with overshoot bounce for a satisfying pop.

### Streak counters
- Momentum percentage text uses a three-color gradient fill (lavender -> mint -> peach) via background-clip: text.
- Weekly stat label uses the same gradient treatment with bolder type.
- Welcome title rendered with gradient for brand consistency.

### Visual hierarchy
- Habit name bumped to 22px / weight 700.
- Weekly day labels gained font-weight 500 and tighter letter-spacing.
- Weekly bars use larger border-radius and glow shadows when completed.
- Phrase text styled italic for softer feel.

### Mobile polish
- Safe-area inset padding via env(safe-area-inset-*) for notched devices.
- Card border-radius adjusted on very small screens.
- prefers-reduced-motion extended to cover new todayPulse animation.

### Preserved
- All JavaScript untouched.
- All id, data-*, and aria-* attributes unchanged.
- Dark / light mode fully supported.

---

## v1.0 (2026-03-29)
- Initial release
- Habit tracker without guilt or streaks
- Momentum meter (30-day sliding window)
- SVG circle progress indicator
- 30-dot heatmap visualization
- Positive phrases ("You showed up. That's what matters.")
- Dark mode via prefers-color-scheme
- Google Fonts (Inter) for polish
- PWA (service worker + manifest)
- Score: 9.5/10 (highest first-pass score in portfolio)
