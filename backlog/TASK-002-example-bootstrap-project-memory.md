# TASK-002: 示例任务 - 为真实项目生成项目记忆

> 这是一个示例任务，展示如何把本模板应用到一个真实项目中。

## 基本信息

| 字段 | 值 |
|------|-----|
| 状态 | 示例 |
| 优先级 | 中 |
| 预估工时 | 30m-1h |
| 负责人 | AI + 用户 |
| 创建日期 | YYYY-MM-DD |

## 描述

让 AI 读取一个真实项目的关键文件，并基于本模板生成适合该项目的 `AGENTS.md`、`memory-bank/`、`docs/` 和 backlog 文件。

## 目标

- [ ] AI 先说明准备读取哪些文件
- [ ] AI 读取项目关键入口和配置
- [ ] AI 生成项目专属的 memory-bank
- [ ] AI 识别主要模块并生成模块地图
- [ ] AI 为复杂模块生成模块详情文档
- [ ] AI 生成项目专属的 AGENTS.md
- [ ] AI 标记不确定信息为“待确认”

## Implementation Plan

### 准备修改的文件

- `AGENTS.md` — 写入项目专属 AI 协作规则
- `memory-bank/projectbrief.md` — 写入项目目标和能力
- `memory-bank/activeContext.md` — 写入当前状态和任务
- `memory-bank/systemPatterns.md` — 写入架构和目录约定
- `memory-bank/moduleMap.md` — 写入模块代码范围、入口和依赖导航
- `memory-bank/techContext.md` — 写入技术栈和命令
- `memory-bank/progress.md` — 写入已完成、进行中和待办
- `docs/modules/*.md` — 为复杂模块写入边界、接口和关键文件
- `docs/*.md` — 按项目实际情况生成可选文档

### 步骤

1. 读取根目录文件列表
2. 读取 README 和主要配置文件
3. 读取项目入口文件和关键目录
4. 根据目录、入口、路由、依赖和注册点识别模块
5. 总结项目结构、模块边界、技术栈、命令和风险点
6. 生成或更新模板文档
7. 让用户确认模块归属和其他待确认信息

### 风险

- 项目结构复杂时，AI 可能遗漏关键模块
- 仅凭文件夹名称推断模块职责可能产生错误
- README 或配置文件过旧时，AI 可能得到错误结论
- 不应在这个任务中修改业务代码

### 测试/验证

- 检查生成文档是否仍有模板占位符
- 检查是否编造不存在的命令或技术栈
- 检查模块地图是否使用目录/glob，而不是维护全量文件清单
- 让用户确认“待确认”条目

## Implementation Notes

这是示例任务，不代表当前仓库还有待执行的业务改造。

## Files Changed

- `AGENTS.md` — 示例中会改成项目专属规则
- `memory-bank/*.md` — 示例中会改成项目专属记忆
- `docs/modules/*.md` — 示例中会为复杂模块生成详细说明
- `docs/*.md` — 示例中会按项目实际情况改写

## 备注

可以直接使用 `prompts/bootstrap-project-memory.md` 中的提示词来执行这个任务。
