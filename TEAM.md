# JJXS_Studio — 内容生产系统使用说明

> 本仓库包含团队共享的内容生产工作流配置。
> 配合 Proma 桌面 Agent 使用，安装后 CLAUDE.md 和 skills 自动生效。

## 一、初次安装

### 1. 安装 Proma
从 [GitHub Releases](https://github.com/ErlichLiu/Proma/releases) 下载最新版桌面应用并安装。

### 2. 克隆本仓库
```bash
cd ~/.proma/agent-workspaces/default/
mv workspace-files workspace-files.bak   # 备份原有配置（如果有）
git clone <本仓库地址> workspace-files
```

### 3. 配置模型通道
打开 Proma → 设置 → 通道，添加你的 API provider：
- DeepSeek：`https://api.deepseek.com`（Anthropic 兼容）
- 或使用 Proma 官方通道（含 Claude/GPT/Gemini 等）

⚠️ **绝对不要把 API key 提交到仓库。** 各自配置。

### 4. 下载模板
分镜表模板等大文件存放在仓库的 `templates/` 目录中，克隆后自动获得。

### 5. 验证
打开 Proma → 新建 Agent 会话，问一句"我现在的角色是什么"。
如果回答包含"东星斑 / 幕后搭档 / B站数码科技内容生产"，说明 CLAUDE.md 已加载成功。

---

## 二、日常工作流

0. **资讯输入**：每天早上 08:00 自动抓取科技资讯到 `JJXS_Studio/00-Inbox/`
1. **选题**：从资讯池发现选题或自由提出
2. **立项**：在 Proma 中说"立项 <产品名>"
3. **产品资料**：Proma 自动收集产品规格、评测、社区反馈
4. **脚本**：Proma 根据产品资料生成脚本骨架或口播稿
5. **审稿**：Raymond 审稿确认
6. **分镜表**：脚本定稿后，Proma 生成分镜表（xlsx）
7. **拍摄发布**：人工执行
8. **复盘**：发布后 Proma 根据数据做四层复盘

---

## 三、角色说明

| 角色 | 负责阶段 | 需要在 Proma 中做的事 |
|------|---------|---------------------|
| **Raymond（主理人）** | 审稿、复盘确认 | 最终判断，系统不替代 |
| **脚本写手** | 产品资料→脚本→分镜 | 按 CLAUDE.md 工作流推进 |
| **编辑** | 稿件 review | 检查内容标准和引用纪律 |
| **视频制作** | 分镜执行 | 按分镜表拍摄和剪辑 |

---

## 四、更新同步

系统迭代时，Raymond 会推送更新到本仓库。你只需要：

```bash
cd ~/.proma/agent-workspaces/default/workspace-files
git pull
# 重启 Proma 或新建会话，新规则自动生效
```

---

## 五、隐私与安全

- **本仓库为 Private**，仅团队成员可访问
- **不要提交**：API key、memory、.env、个人配置文件
- `.gitignore` 已配置保护规则
- 如有疑问联系 Raymond

---

## 六、常见问题

**Q: 我的 Proma 运行结果和队友不一样？**
A: memory 每人独立，模型偏好和写作风格可以在自己的 Proma memory 系统里补充。

**Q: 怎么给系统提交改进建议？**
A: 在仓库提 Issue 或直接联系 Raymond。经验验证后会固化到 CLAUDE.md 并推送给全员。
