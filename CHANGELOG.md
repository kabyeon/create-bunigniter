# Changelog

## 0.6.1

### Fix

- **Pin bunigniter version to `^0.6`** — Previously, `bun add bunigniter` installed the latest version without any constraint, which could pull an incompatible major/minor bump. The install command now explicitly specifies `bunigniter@^0.6` to ensure only 0.6.x compatible versions are installed, preventing unexpected breakages when running `bunx create-bunigniter@latest <project-name>`.
