# TASK-003: 泛化为 AI 项目记忆模板仓库

## 基本信息

| 字段 | 值 |
|------|-----|
| 状态 | 已完成 |
| 优先级 | 高 |
| 预估工时 | 1h |
| 负责人 | AI + 用户 |
| 创建日期 | 2026-06-04 |

## 描述

将当前项目文档从具体业务项目说明，改造成可以上传 GitHub 并复用到其他项目的 AI 项目记忆模板仓库。

模板应帮助 AI 读取用户项目后，根据统一结构生成适合该项目的 `AGENTS.md`、`memory-bank/`、`backlog/` 和 `docs/` 文档。

## 目标

- [x] 新增 GitHub 仓库首页说明
- [x] 将 `AGENTS.md` 改为通用 AI 协作规则
- [x] 将 `memory-bank/` 改为可填写模板
- [x] 将 `docs/` 改为通用文档模板
- [x] 新增 bootstrap prompt，指导 AI 为任意项目生成专属版本
- [x] 提供用户自行执行的 Git 命令

## Implementation Plan

### 准备修改的文件

- `README.md` — 新建 GitHub 首页，说明模板用途和使用方式
- `AGENTS.md` — 泛化为通用 AI 协作规则
- `memory-bank/*.md` — 泛化项目长期记忆模板
- `docs/*.md` — 泛化 API、客户端、数据库文档模板
- `backlog/TASK-001-template.md` — 优化任务模板
- `backlog/TASK-002-example-bootstrap-project-memory.md` — 新增通用示例任务
- `backlog/TASK-003-generalize-template-repo.md` — 记录本次改造任务
- `prompts/bootstrap-project-memory.md` — 新增项目记忆生成提示词
- `.gitignore` — 新增适合模板仓库的忽略规则

### 步骤

1. 新建 `README.md` 和 `.gitignore`
2. 将 `AGENTS.md` 中的具体项目约定抽象为通用规则
3. 将 `memory-bank/` 改为占位符模板
4. 将 `docs/` 改为可选文档模板
5. 新增 bootstrap prompt
6. 检查是否仍有原项目专属内容残留

### 风险

- 过度泛化会降低模板可操作性
- 如果保留具体项目名称，上传后会误导使用者
- 当前目录不是 git 仓库，Git 初始化和远程推送需要用户自行执行

### 测试/验证

- 检查 Markdown 文件是否存在
- 搜索原项目专属词汇残留
- 不运行代码测试，因为本次只修改文档模板

## Implementation Notes

- 推荐仓库名为 `ai-project-memory-template`。
- 保留了 `AGENTS.md`、`memory-bank/`、`backlog/`、`docs/` 这组核心结构。
- 新增 `prompts/bootstrap-project-memory.md`，作为把模板迁移到任意项目时的启动提示词。
- 没有执行 git 初始化、commit、remote 或 push，用户希望自己学习并手动操作。

## Files Changed

- `README.md` — 新增模板仓库说明和 GitHub 上传命令
- `AGENTS.md` — 改为通用 AI 协作规则
- `.gitignore` — 新增常见忽略规则
- `memory-bank/projectbrief.md` — 改为项目简介模板
- `memory-bank/activeContext.md` — 改为当前上下文模板
- `memory-bank/systemPatterns.md` — 改为架构模式模板
- `memory-bank/techContext.md` — 改为技术上下文模板
- `memory-bank/progress.md` — 更新为模板仓库进度
- `docs/api.md` — 改为 API 文档模板
- `docs/mobile.md` — 改为客户端文档模板
- `docs/database.md` — 改为数据库文档模板
- `backlog/TASK-001-template.md` — 优化任务模板
- `backlog/TASK-002-sync-service-improvement.md` — 移除旧项目专属任务
- `backlog/TASK-002-example-bootstrap-project-memory.md` — 新增通用示例任务
- `backlog/TASK-003-generalize-template-repo.md` — 新增本次任务记录
- `prompts/bootstrap-project-memory.md` — 新增项目记忆生成提示词

## 备注

Git 相关操作由用户自行执行。
