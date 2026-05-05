# 鉴机行事 — 内容生产系统

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

## 维护

**系统更新后（团队成员）：** 告诉 Proma：**"帮我拉取最新的系统配置"**。

**推送更新（系统维护者）：** 告诉 Proma：**"请把我的本地配置推送到内容系统仓库"**。Proma 会把当前 workspace-files 的改动提交并推送到 GitHub。

## 首次推送配置（系统搭建者）

如果你是第一次搭建这套系统，告诉 Proma：

> 请帮我把当前这套 Proma 配置上传到 GitHub 内容系统仓库。
> 
> 1. 初始化 workspace-files 为 Git 仓库
> 2. 添加并提交所有文件（排除个人记忆和 API key）
> 3. 推送到：`https://github.com/Raymond-Leung7/content-system.git`
