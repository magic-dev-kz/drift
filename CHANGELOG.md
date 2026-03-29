# Drift — Changelog

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
