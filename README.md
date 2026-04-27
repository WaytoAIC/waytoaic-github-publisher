# waytoaic-github-publisher

## 🚀 Way to AIC | 通往 AI 电商之路
---
### 🌐 官网 Website
- https://waytoaic.com
- https://www.waytoaic.com
---

### 👥 社群招募 Community
`Way to AIC 社群招募 | WaytoAIC.com`

<p align="center">
  <img src="https://github.com/user-attachments/assets/d9f8bbf4-2056-4780-975d-86c885b52bab" width="70%">
</p>

---

### 📣 公众号 WeChat Official Account
`维正 WaytoAIC`

<p align="center">
  <img src="https://github.com/user-attachments/assets/71c71a5c-e68a-4f30-9afb-f2b056619991" width="300">
</p>

---

### 🧠 知识星球 Xiaozhixing
`AI电商之路 WaytoAIC`

<p align="center">
  <img src="https://github.com/user-attachments/assets/9eccef07-0e84-45a7-a415-affcb18c928d" width="200">
  <img src="https://github.com/user-attachments/assets/4e99fbc3-1981-4fee-b113-c9821141102d" width="400">
</p>

---

### 🧩 About Way to AIC

**AIC = AI Commerce**

在 AI 重塑商业的时代，我们希望和每一个拥抱 AI 的卖家：

- 找到场景
- 定义问题
- 积累能力
- 设计系统

共同通往 AI 电商之路。

> Way to AIC 不是教学，不是工具，
> 而是一条所有电商人共同走的进化之路。

### WaytoAIC 理念 | Principles

| 中文 | English |
|---|---|
| 场景先于方法 | Context before method |
| AI 的价值来自真实业务场景，而不是技术本身。 | AI creates value through real business contexts, not through technology alone. |
| 问题先于答案 | Problem before answer |
| 定义问题，比拥有工具更重要。 | Defining the problem matters more than collecting tools. |
| 系统胜过技巧 | System over tricks |
| 技巧是术，系统才是道，决定卖家的上限。 | Tricks are tactical; systems define long-term leverage and ceiling. |
| 共创优于独行 | Co-creation over solo progress |
| 我们相信，真正的进化发生在共同探索的过程中。 | Real evolution happens through shared exploration. |

---

中文 | [English](#english)

## Quick Install

```bash
# Codex
curl -fsSL https://raw.githubusercontent.com/WaytoAIC/waytoaic-github-publisher/v1.0.1/install.sh | bash -s -- --target codex --ref v1.0.1
```

```bash
# OpenClaw
curl -fsSL https://raw.githubusercontent.com/WaytoAIC/waytoaic-github-publisher/v1.0.1/install.sh | bash -s -- --target openclaw --ref v1.0.1
```

```bash
# OpenClaw workspace-local skills/
curl -fsSL https://raw.githubusercontent.com/WaytoAIC/waytoaic-github-publisher/v1.0.1/install.sh | bash -s -- --dest "$(pwd)/skills" --ref v1.0.1
```

复制即用。安装后重启 Codex / OpenClaw。

---

一个把“本地 skill -> GitHub 仓库 -> tag -> GitHub Release”流程标准化的发布型 skill。

它适用于两种情况：

- 现有 skill 更新后重新推送 GitHub
- 新 skill 从零创建并首次公开发布

## 中文

### 这个 skill 会帮你做什么

- 审核当前 skill 仓库状态
- 区分技能安装目录与实际要发布的目标仓库目录，避免在错误路径执行 `git` / `gh`
- 维护符合 Way to AIC 风格的 README 顶部品牌前缀
- 补齐 `install.sh`、`CHANGELOG.md`、license、release notes
- 创建 GitHub 仓库并推送 `main`
- 打版本 tag 并创建 GitHub Release
- 区分“source-available”与 OSI 定义的 open source

### 内置内容

- 主 skill 入口：[SKILL.md](./SKILL.md)
- 发布流程清单：[references/GITHUB_PUBLISH_FLOW.md](./references/GITHUB_PUBLISH_FLOW.md)
- README 品牌前缀模板：[assets/README_PREFIX_WAYTOAIC.md](./assets/README_PREFIX_WAYTOAIC.md)

### 一键安装

安装最新版：

```bash
curl -fsSL https://raw.githubusercontent.com/WaytoAIC/waytoaic-github-publisher/main/install.sh | bash -s -- --target codex
```

固定到版本：

```bash
curl -fsSL https://raw.githubusercontent.com/WaytoAIC/waytoaic-github-publisher/v1.0.1/install.sh | bash -s -- --target codex --ref v1.0.1
```

### 推荐使用方式

直接在 Codex 里说：

- `按 Way to AIC GitHub 发布流程把这个 skill 发到 GitHub`
- `把这个现有 skill 更新后推送到 GitHub，并发一个 release`
- `新建一个 skill，并按 Way to AIC 流程建仓、打 tag、发 release`

### 许可说明

- 当前仓库是公开可见、可学习和可使用的 `source-available` 仓库
- 默认不允许商用
- 基于本 skill 或本仓库开发后再对外分发功能，也需要公开对应源码

---

## English

This skill standardizes the publishing workflow from local skill folder to GitHub repository, version tag, and GitHub Release.

It is designed for two common cases:

- updating an existing skill and pushing the new version to GitHub
- creating a brand-new skill and publishing it for the first time

### What it helps with

- auditing the current skill repository state
- separating the installed skill directory from the actual publish target repo so git operations run in the right place
- keeping the Way to AIC brand prefix at the top of the README
- preparing `install.sh`, `CHANGELOG.md`, license files, and release notes
- creating the GitHub repository and pushing `main`
- tagging versions and publishing GitHub Releases
- using the correct `source-available` wording when commercial use is restricted

### Included files

- Main skill entry: [SKILL.md](./SKILL.md)
- Publish flow checklist: [references/GITHUB_PUBLISH_FLOW.md](./references/GITHUB_PUBLISH_FLOW.md)
- Reusable README prefix: [assets/README_PREFIX_WAYTOAIC.md](./assets/README_PREFIX_WAYTOAIC.md)

### Note

- This repository follows the Way to AIC publishing baseline and is meant to be reused across future skill repositories.
