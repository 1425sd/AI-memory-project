# AGENTS.md

## 项目说明

这是一个 AI 项目记忆模板仓库。把本仓库中的文件复制到任意项目后，AI 助手可以按统一规则读取项目上下文、生成任务计划、执行变更并沉淀项目记忆。

使用到具体项目时，请把本文件中的占位说明替换为该项目自己的说明。

## 项目结构模板

```text
.
├── AGENTS.md              # AI 协作规则
├── backlog/               # 任务文件
├── docs/                  # 项目文档
├── memory-bank/           # 项目长期记忆
├── prompts/               # 可复用提示词
└── <your-project-files>    # 真实项目代码
```

## AI 工作流程

每次开始任务前，AI 必须先读取以下文件：

1. `memory-bank/projectbrief.md`
2. `memory-bank/activeContext.md`
3. `memory-bank/systemPatterns.md`
4. `memory-bank/techContext.md`
5. 当前 backlog 任务文件

不要一开始读取整个项目。只在需要时读取相关代码文件。

如果当前没有 backlog 任务文件，先基于 `backlog/TASK-001-template.md` 创建一个任务文件，并让用户确认任务范围。

## 写代码前

AI 必须先输出 `Implementation Plan`，包含：

- 准备修改哪些文件
- 为什么要修改这些文件
- 每一步准备怎么做
- 可能的风险
- 准备运行哪些测试、检查或构建命令

人类确认后，AI 才能开始改代码。

## 写代码时的规则

- 不要重构无关代码
- 不要删除已有功能，除非任务明确要求
- 不要随意改公开 API、数据格式或数据库 schema
- 涉及 API 变化时，必须更新 `docs/api.md`
- 涉及本地存储、缓存或客户端平台行为变化时，必须更新对应文档，例如 `docs/mobile.md`
- 涉及架构变化时，必须更新 `memory-bank/systemPatterns.md`
- 新增全局状态、Provider、中间件、服务入口或后台任务时，必须确认是否需要在应用入口注册
- 遇到用户已有改动时，不要回滚；先理解并在其基础上工作

## 完成任务后

AI 必须更新：

1. 当前任务文件的 `Implementation Notes`
2. 当前任务文件的 `Files Changed`
3. `memory-bank/progress.md`
4. 如有架构变化，更新 `memory-bank/systemPatterns.md`
5. 如有 API、数据库、移动端、部署等变化，更新 `docs/` 下对应文档

## 常用命令

把本节替换为真实项目命令，例如：

```bash
npm install
npm run dev
npm run typecheck
npm run lint
npm test
```

## 关键约定

把本节替换为真实项目最重要的约定，例如：

- API 请求统一入口
- 环境变量命名
- 数据库迁移规则
- 代码风格
- 测试策略
- 发布流程
