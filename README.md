# Planifyr

A mobile-first daily planner and calendar with Azerbaijani and Russian interfaces. Open `index.html` in a modern browser; no build step or internet connection is required.

## Features

- Add, edit, complete and delete tasks, with undo for deletion.
- Daily and weekly recurring tasks; month, week and day calendars.
- Search, priority and status filters, and productivity statistics.
- Light and dark themes, keyboard navigation and responsive layouts.
- Azerbaijani/Russian language selection, persisted locally.
- JSON backup and restore.

## Data storage

Tasks are stored in the browser under `smart_planner_tasks`; theme and language preferences use `theme` and `planifyr_language`. No backend or account is required.

Browser storage is scoped to its origin; local-file behavior can also depend on the browser and file path. Moving the app to another URL, renaming a local file or switching browsers may require exporting and restoring a backup. Export important data before moving or replacing the app.

## Verification

See [the test report in Azerbaijani](TEST_REPORT.az.md) for tested scenarios and known testing limitations. Physical mobile devices and manual screen-reader testing have not been covered.

## Bundled dependencies

Tailwind-generated CSS and Lucide icons are embedded in the HTML for offline use. Dependency notices are in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
