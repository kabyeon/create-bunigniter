# Changelog

## 0.6.3

### Fix

- **Remove manual `npm publish` to prevent CI conflict** — Previously, the version was manually published to npm before the GitHub Actions workflow ran, causing the CI publish step to fail with `E403 Forbidden` (duplicate version). This release is now published exclusively through the GitHub Actions workflow on release events.

## 0.6.2

### Fix

- **Add `#!/usr/bin/env bun` shebang** — Without the shebang line, `bunx` created a shell symlink that tried to execute `index.ts` as a plain shell script, causing a silent exit with code 1. The shebang ensures the file is executed by the Bun runtime.

## 0.6.1

### Fix

- **Pin bunigniter version to `^0.6`** — Previously, `bun add bunigniter` installed the latest version without any constraint, which could pull an incompatible major/minor bump. The install command now explicitly specifies `bunigniter@^0.6` to ensure only 0.6.x compatible versions are installed, preventing unexpected breakages when running `bunx create-bunigniter@latest <project-name>`.
