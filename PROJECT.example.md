# PROJECT.example.md — 本地项目身份模板

> 复制本文件为 `PROJECT.md`，填入你的本地信息。PROJECT.md 不进 GitHub。

## 当前项目

**content-system** — 内容生产系统规则仓库

## 仓库关系

| 仓库 | 角色 | 是否本地 |
|------|------|---------|
| content-system | 规则引擎（工作流、Skills、模板） | ✅ 本仓库 |
| Raymondstudio | Obsidian 内容资产（选题、资料、脚本等产出） | ❌ 另一个项目 |

## 本地路径

- **Obsidian vault**：`<你的 Obsidian vault 完整路径>`
- **规则仓库（content-system）**：`~/.proma/agent-workspaces/{workspace}/workspace-files/`

## Obsidian 目录结构

```
<你的 Obsidian vault>/
├── 00-Inbox/
├── 01-选题/
├── 02-产品资料/
├── 03-脚本/
├── 04-分镜表/
├── 05-复盘/
└── 99-Archive/
```
