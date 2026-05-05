# JJXS_Studio — 内容生产系统

Proma Agent 工作流配置，用于数码科技内容的生产管理。

## 仓库结构

```
CLAUDE.md       — 工作流规则、内容标准、引用纪律
TEAM.md         — 团队安装使用说明
.context/
  team-note.md  — 竞品库、技能清单、踩坑记录
templates/      — 分镜表模板等（待补充）
skills/         — 自定义 Proma skill（待创建）
```

## 使用前提

- [Proma 桌面应用](https://erlichliu.github.io/Proma) 已安装
- 在设置中配置好模型通道（DeepSeek / 其他 Anthropic 兼容 API）

## 快速开始

复制以下提示词，直接发给 Proma Agent：

> 请把团队的内容生产系统配置到我的工作区。
> 
> 1. 备份当前配置（如果有）
> 2. 从 GitHub 克隆系统仓库：
>    `https://github.com/Raymond-Leung7/content-system.git`
> 3. 验证 CLAUDE.md 已加载成功

Proma 会自动完成所有操作。

### 内容仓库（每个成员独立）

系统使用的文件结构基于 `~/Documents/JJXS_Studio/` 目录：

```
00-Inbox/    — 资讯输入
01-选题/     — 选题池
02-产品资料/  — 产品研究 + 竞品分析
04-脚本/     — 脚本文件
05-分镜表/    — 分镜表 xlsx
06-复盘/     — 复盘报告
99-Archive/  — 归档
```

成员需自行在本地创建此 Obsidian 仓库，无需共享内容文件。模板位于本仓库 `templates/` 目录。

## 日常维护

| 场景 | 对 Proma 说 |
|------|------------|
| **更新本地配置到仓库** | "请把我的本地配置推送到内容系统仓库" |
| **拉取团队最新配置** | "帮我拉取最新的系统配置" |
| **查看仓库状态** | "帮我看看内容系统仓库有什么变更" |

**会推送的内容：** CLAUDE.md / TEAM.md / README.md / .gitignore / .context/team-note.md / templates/ 和 skills/ 目录下所有文件

**不会推送的内容：** 个人记忆（memory/）、API key、本地配置文件。`.gitignore` 已配置保护规则，不会误提交隐私数据。
