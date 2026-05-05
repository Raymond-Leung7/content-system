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

- [Proma](https://github.com/ErlichLiu/Proma) 桌面 Agent 应用
- 模型通道（DeepSeek / 其他 Anthropic 兼容 API）

## 快速开始

```bash
cd ~/.proma/agent-workspaces/default
mv workspace-files workspace-files.bak
git clone https://github.com/Raymond-Leung7/content-system.git workspace-files
```

打开 Proma → 新建 Agent 会话 → CLAUDE.md 自动加载。

## 维护

系统更新后团队成员执行 `git pull` 获取最新规则。
