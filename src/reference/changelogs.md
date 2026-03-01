# Changelog

This page tracks notable changes to ScriptSense.

---

## v2.16.0 — 2026-02-27

### Highlights
- Final UI improvements (3/3).
- Added a new `theme` command and configuration for editing the UI theme.

### Added
- `theme` command + theme configuration options.

### Changed
- UI polish pass (final round).

---

## v2.15.0 — 2026-02-26

### Highlights
- More UI improvements (2/3).
- Fixed a graph UI crash caused by a small construction bug.

### Fixed
- Graph UI no longer crashes due to a minor UI construction issue.

### Changed
- UI polish pass (part 2).

---

## v2.14.1 — 2026-02-25

### Highlights
- UI improvements (1/3).
- Fixed MyersDiff and the `diff` command.

### Fixed
- MyersDiff implementation.
- `diff` command behavior.

### Changed
- UI polish pass (part 1).

---

## v2.13.0 — 2026-02-16

### Changed
- GraphViewer now uses `Path2D` instead of segmented frames.
- GraphViewer settings were removed.
- The workspace is now scanned by the indexer.

### Added
- `diff` command.

---

## v2.12.0 — 2026-02-16

### Added
- `docs` command now opens the internal knowledge base (GitHub Pages).
- `tasks` now supports `global` and `local` scope (show tasks only in the current project).
- `tasks` now has its own hub.

### Changed
- DependencyInjector now ignores `for` statements.

### Fixed
- `report` now recovers user input if an error occurs.

---

## v2.11.3 — 2026-02-07

### Added
- Terminal search bar.
- Terminal timestamps.
- Terminal filters.

### Fixed
- Instance parameters passed between scripts are now analyzed correctly.
- `strip` now ignores compiler directives (e.g. `--!native`, `--!strict`, etc.).

---

## v2.9.5 — 2026-01-30

### Fixed
- Several command-related issues.

---

## v2.9.2 — 2026-01-28 to 2026-01-29

### Added
- `ignore` now includes descendants of selected instances.
- `ignore` now supports `undo` and `redo`.

### Changed
- Internals were restructured/refactored.
- Improved image-upload logic in `report`.

### Fixed
- Import suggestions no longer trigger while typing inside a multi-line comment.

---

## v2.17.0 — 2026-03-01

### Highlights
- Introduced command suggestions and inline hints.
- The command palette now guides input with contextual autocomplete.

### Added
- Inline command suggestions while typing.
- Autocomplete support for:
  - Commands
  - Arguments
  - Themes
  - Sessions
  - Help pages
  - Scripts
  - And other supported entities

### Changed
- The command palette now actively assists with input instead of acting as a passive terminal.

> Notes: This update makes ScriptSense feel significantly more interactive and beginner-friendly.

## v2.8.1 — 2026-01-27

### Added
- Support for `relative` paths (in addition to `absolute`) for shared module roots.
- Welcome message for new users.
- Tooltips for items in the notification hub.

### Changed
- `info` notifications now use blue instead of green.

---

## v2.7.4 — 2026-01-26

### Added
- `UseDedicatedSpecFolder` config.
- `test` command now uses a dedicated folder for spec files.
- `test` now supports a `quick` argument to temporarily test a script immediately.

### Changed
- Greatly increased the GraphViewer canvas size.

---

## v2.6.3 — 2026-01-25

### Added
- `changelog` command (you’re looking at it!).
- `report` command now has its own dedicated menu.
- `AutoRefactor` config to allow automatic refactors on-the-fly (without needing the terminal).
- Now using TestEZ for the `test` and `runtests` commands.
- `strip` can now select multiple scripts and supports undo/redo.

> Notes: “I wonder why I haven’t done this earlier”
