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

系统更新后，告诉 Proma：**"帮我拉取最新的系统配置"**。
