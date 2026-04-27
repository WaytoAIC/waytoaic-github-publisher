# GitHub Publish Flow

Use this checklist when publishing a skill repository under the Way to AIC workflow.

## 0. Scope and path resolution

- `skill_dir`: the installed folder that contains this reference file, the README prefix template, and other bundled helpers.
- `repo_dir`: the repository that will actually be edited, committed, pushed, tagged, or released.
- Resolve helper files such as `assets/README_PREFIX_WAYTOAIC.md` relative to `skill_dir`.
- Run git and GitHub operations inside `repo_dir`, not inside `skill_dir`, unless the user explicitly wants to maintain the skill package repo itself.
- If the current workspace is not a git repo, identify `repo_dir` before running `git status --short -b`.

## 1. Existing skill update

| Step | Action | Notes |
|---|---|---|
| Audit | Review `git status`, README, changelog, installer, license, and current releases. | Preserve user-polished README layout instead of replacing it. |
| Skill update | Apply the actual logic or documentation changes first. | Keep edits scoped and testable. |
| README refresh | Keep the Way to AIC prefix at the top and preserve bilingual install guidance. | Reuse `assets/README_PREFIX_WAYTOAIC.md` when needed; preserve its hosted images and widths. |
| Changelog | Update `Unreleased` with user-visible changes. | Keep entries compact and release-friendly. |
| Validation | Run syntax checks, YAML parsing, or installer smoke tests. | Use the smallest realistic verification that proves the change. |
| Git push | Commit with a clear message and push `main`. | Confirm the worktree is clean afterward. |
| Release | If requested, cut a new tag and create or update a GitHub Release. | Push commits before tagging. |

## 2. New skill creation and first publish

| Step | Action | Notes |
|---|---|---|
| Skill package | Create `SKILL.md` first, then add only the references, scripts, and assets that are truly needed. | Keep the skill concise. |
| README | Start with the Way to AIC prefix, then add quick install, use cases, structure, and license notes. | Default to bilingual CN/EN; keep the prefix visual style aligned with `WaytoAIC/reddit-market-monitor`. |
| Public repo files | Add `.gitignore`, `CHANGELOG.md`, `install.sh`, and license files if the repo is meant to be shared. | The install path should work for Codex and OpenClaw. |
| License wording | If usage is allowed but commercial use is blocked, say source-available. | Avoid calling it open source in the OSI sense. |
| Git setup | Initialize git, create `main`, commit, and verify `gh auth status`. | Run `gh auth setup-git` when push auth needs wiring. |
| Repo creation | Use `gh repo create ... --public --source=. --remote=origin --push`. | Make the description clear and functional. |
| Release | Tag the first stable version, then create a GitHub Release with bilingual notes. | Prefer `v1.0.0` for the first public stable release. |

## 3. Minimum public repo surface

| File | Purpose |
|---|---|
| `README.md` | Project entry page with brand prefix, install instructions, and bilingual overview |
| `SKILL.md` | Actual skill instructions |
| `install.sh` | One-command installation flow |
| `CHANGELOG.md` | Release-friendly change history |
| `.gitignore` | Clean repository defaults |
| `LICENSE.md` | Base license text |
| `ADDITIONAL_TERMS.md` | Project-specific restrictions when needed |

## 4. Validation checklist

| Area | Check |
|---|---|
| Git | `git status --short -b` is understood before work and clean after push |
| Auth | `gh auth status` succeeds before any GitHub operations |
| Syntax | Relevant YAML, shell, Node, or Python files parse cleanly |
| README images | Hosted prefix image URLs return a valid response before push |
| Installer | `install.sh` works against a temp destination or test skill directory |
| Release | Tag, release URL, and remote branch state all match |

## 5. Publishing defaults

- Default branch: `main`
- Release style: bilingual Chinese/English
- README style: top brand block with the Way to AIC image prefix, quick install near the top, then Chinese and English sections
- Install examples: include both `main` and version-pinned commands when useful
- Final user summary: concise and outcome-first
