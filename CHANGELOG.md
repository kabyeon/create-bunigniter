# Changelog

All notable changes to create-bunigniter are documented in this file.

## [0.3.7] — 2026-07-01

### Changed

- **Entry point reference updated** — `dev.ts` → `main.ts` to align with bunigniter v0.5.4 entry point rename. The generated minimal package.json now references `main.ts` as the development entry point.

---

## [0.3.6] — 2026-06-29

### Added

- **`--yes` / `-y` flag** — Skip interactive prompts and use defaults (CI-friendly).
- **Bun version check** — Validates Bun >=1.3.0 before proceeding with scaffold.

### Changed

- **Simplified workflow** — Creates minimal package.json, then delegates to `bun run bi init --yes` for full scaffolding.

---

## [0.3.5] — 2026-06-28

### Added

- Initial release with basic project scaffold functionality.
- Interactive prompts for project name and configuration.
- Automatic `bun install` after project creation.

[0.3.7]: https://github.com/nexus-ts/create-bunigniter/compare/v0.3.6...v0.3.7
