# AI Project Memory Template

一个给 AI 编程助手使用的项目上下文模板。把这套文件放进任意项目后，AI 可以先读取项目记忆、任务 backlog 和文档骨架，再根据你的确认一步一步改代码。

推荐仓库名：`ai-project-memory-template`

## 这个模板解决什么问题

很多 AI 助手第一次进入项目时，会缺少这些上下文：

- 这个项目到底要做什么
- 当前做到哪一步
- 技术栈、目录结构和架构约定是什么
- 修改代码前应该先问什么、先读什么
- 完成任务后要把决策记录到哪里

这个仓库提供一套轻量文件约定，让 AI 在开始动手前先建立项目记忆，并在每次任务结束后更新这些记忆。

## 目录结构

```text
.
├── AGENTS.md                         # AI 协作规则
├── backlog/                          # 任务文件
│   ├── TASK-001-template.md           # 任务模板
│   └── TASK-002-example-bootstrap-project-memory.md
├── docs/                             # 可选项目文档模板
│   ├── api.md
│   ├── database.md
│   └── mobile.md
├── memory-bank/                      # 项目长期记忆
│   ├── activeContext.md
│   ├── progress.md
│   ├── projectbrief.md
│   ├── systemPatterns.md
│   └── techContext.md
└── prompts/
    └── bootstrap-project-memory.md    # 让 AI 为你的项目生成专属版本的 prompt
```

## 推荐使用方式

1. 复制这些文件到你的项目根目录。
2. 打开 `prompts/bootstrap-project-memory.md`。
3. 把里面的 prompt 发给 AI，让它读取你的项目并生成适合你的版本。
4. 审核 AI 写出的 `AGENTS.md`、`memory-bank/*`、`docs/*` 和 backlog 文件。
5. 以后每次让 AI 改代码，都要求它遵守 `AGENTS.md`。

## 工作流约定

每次任务开始前，AI 应该先读取：

- `memory-bank/projectbrief.md`
- `memory-bank/activeContext.md`
- `memory-bank/systemPatterns.md`
- `memory-bank/techContext.md`
- 当前 backlog 任务文件

写代码前，AI 必须先输出 `Implementation Plan`，说明要改哪些文件、为什么改、怎么验证，以及可能的风险。你确认后，AI 再开始修改。

任务完成后，AI 应该更新：

- 当前任务文件的 `Implementation Notes`
- 当前任务文件的 `Files Changed`
- `memory-bank/progress.md`
- 如有架构变化，更新 `memory-bank/systemPatterns.md`

## 适合什么项目

这个模板不绑定具体技术栈，适合：

- Web 应用
- 移动端应用
- 后端服务
- CLI 工具
- 数据处理项目
- AI 应用
- 个人长期维护项目


