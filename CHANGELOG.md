# Changelog

All notable changes to this project will be documented in this file.

The format is intentionally simple and optimized for release notes and repository readers.

## [Unreleased]

### Changed

- Clarified the skill's path model so helper files resolve from the installed skill directory while git and release commands run in the actual target repository
- Updated README and installer defaults to use the canonical `WaytoAIC/waytoaic-github-publisher` GitHub path

## [v1.0.1] - 2026-03-20

### Changed

- Quieted installer fallback behavior so version-pinned installs no longer print a harmless `404` before succeeding

## [v1.0.0] - 2026-03-20

First public release.

### Added

- Initial `waytoaic-github-publisher` skill
- Standard workflow for both existing skill updates and first-time skill publishing
- Reusable Way to AIC README prefix template
- One-command installation script for Codex and OpenClaw
- Bilingual README, release-friendly changelog, and source-available licensing files
