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

> 列出你本地 vault 的实际目录。注意编号可能与 CLAUDE.md 标准不同。

```
<你的 Obsidian vault>/
├── 00-Inbox/           # 资讯输入
├── 01-选题/            # 选题池
├── 02-产品资料/        # 产品研究 + 品牌库
├── 04-脚本/            # 脚本文件（编号以你本地为准）
├── 05-分镜表/          # 分镜表 xlsx
├── 06-复盘/            # 复盘报告
├── 99-Archive/         # 归档
└── ...（你本地的其他目录）
```

## 内容产出映射

> 把 CLAUDE.md 的概念目录映射到你本机的实际路径。

| 工作流阶段 | CLAUDE.md 概念 | 本机实际路径 |
|-----------|---------------|-------------|
| 产品资料 | `02-产品资料/` | `<你的 vault>/02-产品资料/` |
| 脚本 | `03-脚本/` | `<你的 vault>/04-脚本/` ← 编号以你本地为准 |
| 分镜表 | `04-分镜表/` | `<你的 vault>/05-分镜表/` |
| 复盘 | `05-复盘/` | `<你的 vault>/06-复盘/` |

> 写文件时以本表实际路径为准，不要按 CLAUDE.md 的概念编号去猜。
