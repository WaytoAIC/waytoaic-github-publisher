---
name: waytoaic-github-publisher
description: Standard workflow for creating a new Codex/OpenClaw skill repo or updating an existing one and publishing it to GitHub. Use when the user wants to push a skill to GitHub, refresh a skill repo, create README/install/license/release materials, add the Way to AIC README prefix, tag a version, or publish a GitHub Release.
---

# Way to AIC GitHub Publisher

Use this skill when the task is about shipping a skill repository, not when the user only wants to edit the skill logic.

## Path model

- Treat the directory containing this `SKILL.md` as `skill_dir`. Use it only for bundled helper files such as `assets/README_PREFIX_WAYTOAIC.md` and `references/GITHUB_PUBLISH_FLOW.md`.
- Treat the repository being published as `repo_dir`. This is usually the user's current workspace git root or an explicit path provided by the user.
- Resolve relative helper paths against `skill_dir`, not against the user's current working directory and not against `repo_dir`.
- Run `git`, `gh`, tagging, release, and push commands inside `repo_dir`. Do not run publish commands inside the installed skill copy unless the user explicitly says this skill folder itself is the repo to maintain.
- If the current workspace is not a git repo, do not start with `git status`. First identify `repo_dir`, then continue the audit there.

## Default Way to AIC baseline

- Put the Way to AIC prefix block at the top of the README. Copy from [assets/README_PREFIX_WAYTOAIC.md](assets/README_PREFIX_WAYTOAIC.md) unless the user says not to.
- Treat the current `WaytoAIC/reddit-market-monitor` README prefix as the visual baseline for Way to AIC repos: keep the emoji section titles, centered image HTML, and image widths unless the user provides a newer baseline.
- Public repos should default to bilingual Chinese/English README and release notes unless the user asks for a single language.
- Prefer one-command installation with `install.sh` supporting `--target codex`, `--target openclaw`, `--dest`, `--ref`, and `--repo`.
- Maintain `CHANGELOG.md` with an `Unreleased` section.
- If commercial use is forbidden, describe the repo as source-available rather than OSI open source.
- Preserve any user-improved README presentation. Treat the current layout as the visual baseline and patch around it instead of rewriting the page from scratch.

## First pass audit

1. Identify `repo_dir`.
2. Read [references/GITHUB_PUBLISH_FLOW.md](references/GITHUB_PUBLISH_FLOW.md) from `skill_dir` before editing.
3. If `repo_dir` is a git repo, run `git status --short -b` there. If it is not a git repo yet, inspect the folder first and treat it as a possible first-publish path.
4. Inspect `README.md`, `CHANGELOG.md`, `install.sh`, license files, and current release state inside `repo_dir`.
5. Check GitHub auth with `gh auth status`.
6. Decide which path applies:
   - existing skill update
   - new skill creation and first publish

## Editing rules

- Use small patches and preserve user writing when it is already stronger than the old version.
- Keep README top sections readable on GitHub mobile and desktop.
- When the repo belongs to the Way to AIC umbrella, keep the brand prefix above project-specific install instructions.
- When copying helper content, load it from `skill_dir/assets/...` or `skill_dir/references/...` rather than assuming those paths exist inside `repo_dir`.
- When copying the Way to AIC prefix, preserve the hosted `github.com/user-attachments/assets/...` image URLs from the template and verify them if images appear broken.
- Only embed screenshots, logos, or QR codes when you have real file paths or stable hosted URLs.
- If release notes are updated, keep the Chinese and English sections aligned.

## Execution rules

- For existing repositories, update docs first, then versioning artifacts, then push.
- For new repositories, create the skill package first, then the public repo surface, then publish.
- Validate before pushing: YAML/script syntax, installer smoke test, and git cleanliness.
- If the user asks for a tag or GitHub Release, do not leave the repo in a half-published state. Push commits first, then tag, then publish or update the release.
- If the installed skill copy and the target publish repo are different locations, always read helpers from `skill_dir` and write changes only to `repo_dir`.

## Report back

Return a short summary covering:

- what changed
- whether the repo is pushed
- current tag and release status
- anything still missing, such as auth, assets, or version choice
