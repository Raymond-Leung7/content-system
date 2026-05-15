# Skill 清单

> 本系统推荐安装的 Skills。读取此文件后，按工作区分配安装即可。
> 安装命令：`npx skills add <owner/repo@skill-name> -g -y`

## 研究与资料工作区

| Skill | 来源 | 功能 | 安装量 |
|-------|------|------|--------|
| market-research-analysis | manojbajaj95/claude-gtm-plugin | 市场调研、竞品分析、Porter Five Forces、TAM/SAM/SOM | ★342 |

## 脚本与分镜工作区

| Skill | 来源 | 功能 | 安装量 |
|-------|------|------|--------|
| vsl-storyboard-writer | ncklrs/startup-os-skills | 视频分镜脚本写作、镜头规划 | ★216 |

## 管理与复盘工作区

| Skill | 来源 | 功能 | 安装量 |
|-------|------|------|--------|
| bilibili-analyzer | aidotnet/moyucode | B站数据分析、视频表现分析 | ★700 |

## 全部工作区通用

| Skill | 来源 | 功能 | 所属工作区 |
|-------|------|------|-----------|
| xlsx | proma 内置 | Excel/表格文件处理 | 全部 |
| pdf | proma 内置 | PDF 文件解析 | 研究与资料 |
| find-skills | proma 内置 | 发现和安装新 Skill | 研究与资料、管理与复盘 |
| brainstorming | proma 内置 | 创意构思、头脑风暴 | 脚本与分镜 |
| executing-plans | proma 内置 | 执行计划、分步实施 | 脚本与分镜 |
| tool-builder | proma 内置 | 创建和管理 Chat 工具 | 管理与复盘 |
| humanizer-zh | .claude 生态 | 去除 AI 写作痕迹，24 种模式检测+质量评分 | 脚本与分镜（脚本润色阶段） |
| karpathy-guidelines | .claude 生态 | LLM 编码防坑指南：先想再做、最小改动、验证标准 | 管理与复盘（工具开发时） |

## 安装说明

在 Proma 中告诉 Agent：

```
请读取 skill-list 文件，根据当前工作区安装对应的 Skills。
```
