# JJXS_Studio — 内容生产系统

Proma Agent 工作流配置，用于数码科技内容的生产管理。

## 快速开始

发给 Proma Agent：

```
请把团队的内容生产系统配置到我的工作区。

1. 备份当前配置（如果有）
2. 从 GitHub 克隆系统仓库：https://github.com/Raymond-Leung7/content-system.git
3. 验证 CLAUDE.md 已加载成功
```

## 搭建内容仓库

1. 安装 [Obsidian](https://obsidian.md/)，本地创建自己的仓库
2. 发给 Proma Agent：

```
这是我的 Obsidian 目录：<你的路径>，请帮我建好需要的文件夹
```

自动创建的结构：

```
00-Inbox/  01-选题/  02-产品资料/  04-脚本/  05-分镜表/  06-复盘/  99-Archive/
```

## 日常维护

| 操作 | 对 Proma 说 |
|------|------------|
| 推送配置到仓库 | `请把我的本地配置推送到内容系统仓库` |
| 拉取最新配置 | `帮我拉取最新的系统配置` |
| 查看仓库状态 | `帮我看看内容系统仓库有什么变更` |

## 仓库内容

```
CLAUDE.md         — 工作流规则、内容标准、引用纪律
TEAM.md           — 团队使用说明
.context/
  team-note.md    — 竞品库、技能清单、踩坑记录
templates/        — 分镜表模板等
.gitignore        — 隐私保护（memory/、API key、配置不提交）
```
