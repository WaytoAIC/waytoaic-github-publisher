---
name: waytoaic-github-publisher
description: Standard workflow for creating a new Codex/OpenClaw skill repo or updating an existing one and publishing it to GitHub. Use when the user wants to push a skill to GitHub, refresh a skill repo, create README/install/license/release materials, add the Way to AIC README prefix, tag a version, or publish a GitHub Release.
---

# Way to AIC GitHub Publisher

Use this skill when the task is about shipping a skill repository, not when the user only wants to edit the skill logic.

## Default Way to AIC baseline

- Put the Way to AIC prefix block at the top of the README. Copy from [assets/README_PREFIX_WAYTOAIC.md](assets/README_PREFIX_WAYTOAIC.md) unless the user says not to.
- Public repos should default to bilingual Chinese/English README and release notes unless the user asks for a single language.
- Prefer one-command installation with `install.sh` supporting `--target codex`, `--target openclaw`, `--dest`, `--ref`, and `--repo`.
- Maintain `CHANGELOG.md` with an `Unreleased` section.
- If commercial use is forbidden, describe the repo as source-available rather than OSI open source.
- Preserve any user-improved README presentation. Treat the current layout as the visual baseline and patch around it instead of rewriting the page from scratch.

## First pass audit

1. Run `git status --short -b`.
2. Inspect `README.md`, `CHANGELOG.md`, `install.sh`, license files, and current release state.
3. Check GitHub auth with `gh auth status`.
4. Decide which path applies:
   - existing skill update
   - new skill creation and first publish
5. Read [references/GITHUB_PUBLISH_FLOW.md](references/GITHUB_PUBLISH_FLOW.md) before editing.

## Editing rules

- Use small patches and preserve user writing when it is already stronger than the old version.
- Keep README top sections readable on GitHub mobile and desktop.
- When the repo belongs to the Way to AIC umbrella, keep the brand prefix above project-specific install instructions.
- Only embed screenshots, logos, or QR codes when you have real file paths or stable hosted URLs.
- If release notes are updated, keep the Chinese and English sections aligned.

## Execution rules

- For existing repositories, update docs first, then versioning artifacts, then push.
- For new repositories, create the skill package first, then the public repo surface, then publish.
- Validate before pushing: YAML/script syntax, installer smoke test, and git cleanliness.
- If the user asks for a tag or GitHub Release, do not leave the repo in a half-published state. Push commits first, then tag, then publish or update the release.

## Report back

Return a short summary covering:

- what changed
- whether the repo is pushed
- current tag and release status
- anything still missing, such as auth, assets, or version choice
