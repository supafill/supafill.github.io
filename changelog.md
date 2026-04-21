---
permalink: /changelog/
title: Changelog
---

## [1.4.0] - 2026-04-20

### Added
- In-popup feedback form — click "Feedback" in the popup footer to send a bug report or feature request without leaving the extension
- Radio selector for bug vs feature, title + description fields, optional email, opt-in version/browser context attachment
- Form submits via Web3Forms (free tier 250/month, no login required)
- Client-side rate limit: 3 submissions per hour per install, tracked locally in `storage.local`

### Privacy
- Updated `PRIVACY_POLICY.md` to disclose opt-in feedback data flow to web3forms.com
- Firefox `data_collection_permissions.optional` declares personallyIdentifiableInformation, personalCommunications, technicalAndInteraction (only when user submits feedback)

## [1.3.1] - 2026-04-20

### Fixed
- Multi-person forms (e.g., booker + multiple guests) now get distinct personas per person. Fields are grouped by name-path scope (`booker.*` vs `rooms[0].guests[0].*` vs `rooms[0].guests[1].*`) instead of DOM container. Previously all name fields across different people received the same values because `<div class="section-card">`-style layouts did not match the legacy container heuristic, collapsing every field into one persona.

## [1.3.0] - 2026-04-20

### Breaking
- Ignored-field patterns now use word-boundary matching instead of substring. Short patterns like `pw` or `pass` that previously matched inside `password` no longer do. To restore substring behavior for a specific pattern, wrap it in regex syntax: `/pw/` instead of `pw`. Review your ignored-field list in Settings after upgrading.

### Added
- Rich-text editor support via `beforeinput` InputEvent dispatch — TipTap/ProseMirror, Lexical, Draft.js, CKEditor 5 now fill correctly
- `storage.sync` quota overflow handling — transparent fallback to `storage.local` with user-facing warning
- `onSettingsChanged` subscription API — options/popup/content pages stay in sync live
- Seedable persona generator (`setSeed`) for reproducible test data and demos
- Vitest test suite (42 tests) covering detector, generators, ignore patterns
- Biome lint/format with auto-fix
- GitHub Actions CI: typecheck, lint, test, build Chrome + Firefox, upload artifacts
- Dedicated per-locale files under `lib/locales/` with dynamic loader (`loadLocale`)
- `/regex/flags` syntax for ignored-field patterns

### Changed
- Controlled `<select>` elements now fill correctly on React/Vue (native setter pattern)
- Field visibility detection uses `checkVisibility()` with label fallback — radios/checkboxes hidden behind custom-styled labels now detected
- Detector scoring weighted per-attribute (name 3×, id/autocomplete 2×, placeholder/aria-label 1.5×, label 1×) — removed hardcoded name pre-check duplication
- Ignored-field matching uses word-boundary regex — `pw` no longer matches `password`
- Password generation uses `crypto.getRandomValues` instead of `Math.random`
- Firefox `strict_min_version` lowered to `115.0` (ESR compatibility)
- Toast notifications announce via `role="status"` + `aria-live="polite"`

### Fixed
- MV3 service worker safety: removed top-level `setupContextMenus()` race, added `onStartup` listener
- Removed dead `defaultPassword` setting and stale `get-user-state` message handler

### Dev
- `packageManager` pinned to `bun@1.3.4`
- Removed unused `jsdom` dependency (tests run on happy-dom)

## [1.2.1] - 2025-01-02

### Improved
- Replaced emoji icons with custom SVG icons in popup and toast notifications for a more professional look
- Unified styling between Settings and Help pages using shared CSS
- Keyboard shortcuts section now displays side-by-side layout
- Help page sections are now collapsible for a cleaner, more compact view
- Consistent tab titles format (SupaFill - Settings, SupaFill - Help)
- Custom dropdown in Add Custom Field modal now uses NeoBrutalism styling
- Generator field defaults to "Custom Value" when adding new field rules

### Fixed
- Toast notification icons now display correctly regardless of website's light/dark mode
- Field list items now have equal spacing on both sides
- Modal popup is now properly centered

## [1.2.0] - 2024-12-31

### Added
- Custom Value option for field rules - now you can specify a fixed value (e.g., always use "123123123" for password fields)
- Dynamic keyboard shortcuts display - shows actual configured shortcuts instead of defaults

### Improved
- Keyboard shortcuts now display as readable text (CTRL+SHIFT+E) instead of symbols

## [1.1.0] - 2024-12-30

### Added
- Custom dropdown UI with NeoBrutalism styling for locale selector
- Country flag emojis to locale dropdown for easier identification
- Romanized names for CJK locales (Japanese, Korean, Chinese) - email and username fields now use romanized versions (e.g., tanaka.taro@example.com)
- Context menu separators for better visual grouping between fill and clear actions
- Ignored fields now support checkboxes and match against label text

### Fixed
- "Fill this field" now correctly overwrites existing values on repeated use

## [1.0.0] - 2024-12-29

### Added
- Initial release
- Smart form detection (name, email, phone, address, etc.)
- Fill text inputs, selects, radio buttons, checkboxes, and textareas
- WYSIWYG editor support (CKEditor, Quill, etc.)
- Iframe support
- Consistent persona generation per form
- 10 locale support: English, German, French, Spanish, Italian, Portuguese (Brazil), Japanese, Korean, Chinese (Simplified), Indonesian
- Keyboard shortcuts (Ctrl+Shift+E to fill, Ctrl+Shift+L to clear)
- Context menu integration
- Custom field rules
- Ignored fields patterns
- NeoBrutalism UI design
- Toast notifications
