# Fitsmiles Prize Wheel

A static HTML/CSS/JS prize wheel with an admin panel. Configure segments and titles directly in the browser—no redeployments.

## Live Usage
- Open `Home.html` to use the wheel.
- Open `admin.html` for configuration.

## Features
- Fixed wheel sizes: 8, 10, or 12 segments.
- Per-segment Name/Type/Color editors.
- Two-line curved text rendering with ellipsis for long labels.
- Confetti and sounds support (recognized by the wheel if keys are present).
- Config stored in `localStorage`; main wheel auto-reloads changes.

## Admin
- Default password: `FITSMILES` (change `ADMIN_PASSWORD` in `admin.html`).
- Buttons are at the bottom-right of the Wheel Configuration panel: Save above Open.

## Storage Keys
- `wheelSegments` (string[])
- `wheelColors` (string[] hex)
- `wheelOutcomes` ("prize" | "fitsmiles" | "fail")
- `wheelTitle` (string)
- `wheelOrgName` (string)
- Optional recognized by Home (legacy/advanced): `wheelEnableSounds`, `wheelEnableConfetti`, `wheelSpinDuration`.

## Development
- Pure client-side. Works on static hosting (GitHub Pages).
- See `ADMIN-GUIDE.md` for detailed instructions.

## Recent Changes
- Fix: “No win” segments no longer mirror edits across slices; templates now create independent objects.
