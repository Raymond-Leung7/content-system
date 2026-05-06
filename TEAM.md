# JJXS_Studio — 内容生产系统使用说明

> 本仓库包含团队共享的内容生产工作流配置。
> 配合 Proma 桌面 Agent 使用，安装后 CLAUDE.md 和 skills 自动生效。

## 一、初次安装

### 1. 安装 Proma
从 [GitHub Releases](https://github.com/ErlichLiu/Proma/releases) 下载最新版桌面应用并安装。

### 2. 配置 Proma 工作区

本系统需要 **三个 Proma 工作区**，分别承担不同角色：

| # | 工作区名称 | Slug | 角色 | 必要 Skills | 思考模式 |
|---|-----------|------|------|-----------|---------|
| 1 | **研究与资料** | research | 研究员 | xlsx, pdf, find-skills | 开启 |
| 2 | **脚本与分镜** | script | 脚本写手 | xlsx, brainstorming, executing-plans | 开启 |
| 3 | **管理与复盘** | management | 管理员 | tool-builder, find-skills, xlsx | 默认关闭 |

在 Proma 中创建这三个工作区（设置 → 工作区 → 新建），记录各自的 Slug。

### 3. 克隆本仓库到各工作区

每个工作区都需要本仓库的配置。在 Shell 中执行或让 Agent 执行：

```bash
# 对每个工作区依次执行
for ws in research script management; do
  cd ~/.proma/agent-workspaces/$ws/
  git clone https://github.com/Raymond-Leung7/content-system.git workspace-files
done
```

> 如果已有默认工作区（`default`），也需要执行：设置该工作区的 `workspace-files` 指向本仓库。

### 4. 配置模型通道
打开 Proma → 设置 → 通道，添加你的 API provider：
- DeepSeek：`https://api.deepseek.com`（Anthropic 兼容）
- 或使用 Proma 官方通道（含 Claude/GPT/Gemini 等）

⚠️ **绝对不要把 API key 提交到仓库。** 各自配置。

### 5. 下载模板
分镜表模板等大文件存放在仓库的 `templates/` 目录中，克隆后自动获得。

### 6. 创建 Obsidian 目录
新用户需在本地创建 Obsidian 内容目录。Agent 可代为执行：
- 路径：见 `PROJECT.md` 中的 Obsidian vault 路径（每个团队成员自定义，不进 GitHub）
- 必要子目录：`00-Inbox`, `01-选题`, `02-产品资料`, `03-脚本`, `04-分镜表`, `05-复盘`, `99-Archive`

### 7. 验证
打开 Proma → 切换到每个工作区 → 新建 Agent 会话，问 Agent：
- **"列出当前工作区配置"** — 应返回当前区的角色、Skills、思考模式
- **"跑一次部署审计"** — Agent 应对照 CLAUDE.md 检查所有 infrastructure 项

---

## 二、日常工作流

0. **资讯输入**：每天早上 08:00 自动抓取科技资讯到 Obsidian vault 的 `00-Inbox/`（vault 路径见 `PROJECT.md`）
1. **选题**：从资讯池发现选题或自由提出
2. **立项**：在 Proma 中说"立项 <产品名>"
3. **产品资料**：Proma 按产品资料模板收集规格、评测、社区反馈。同一品牌的产品会复用品牌知识库（`02-产品资料/品牌库/`），避免重复研究品牌背景
4. **脚本**：Proma 根据产品资料生成脚本骨架或口播稿
5. **审稿**：主理人审稿确认
6. **分镜表**：脚本定稿后，Proma 生成分镜表（xlsx）
7. **拍摄发布**：人工执行
8. **复盘**：发布后 Proma 根据数据做四层复盘

---

## 三、角色说明

| 角色 | 负责阶段 | 需要在 Proma 中做的事 |
|------|---------|---------------------|
| **主理人** | 审稿、复盘确认 | 最终判断，系统不替代 |
| **脚本写手** | 产品资料→脚本→分镜 | 按 CLAUDE.md 工作流推进 |
| **编辑** | 稿件 review | 检查内容标准和引用纪律 |
| **视频制作** | 分镜执行 | 按分镜表拍摄和剪辑 |

---

## 四、更新同步

系统迭代时，主理人会推送更新到本仓库。你只需要：

```bash
cd ~/.proma/agent-workspaces/default/workspace-files
git pull
# 重启 Proma 或新建会话，新规则自动生效
```

---

## 五、隐私与安全

- **本仓库**仅团队成员可访问
- **不要提交**：API key、memory、.env、个人配置文件
- `.gitignore` 已配置保护规则
- 如有疑问联系主理人

---

## 六、常见问题

**Q: 我的 Proma 运行结果和队友不一样？**
A: memory 每人独立，模型偏好和写作风格可以在自己的 Proma memory 系统里补充。

**Q: 怎么给系统提交改进建议？**
A: 在仓库提 Issue 或直接联系主理人。经验验证后会固化到 CLAUDE.md 并推送给全员。
