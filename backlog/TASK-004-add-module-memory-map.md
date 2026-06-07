# TASK-004: 增加模块级项目记忆地图

## 基本信息

| 字段 | 值 |
|------|-----|
| 状态 | 已完成 |
| 优先级 | 高 |
| 预估工时 | 1h |
| 负责人 | AI + 用户 |
| 创建日期 | 2026-06-07 |

## 描述

为大型、多模块项目补充模块级记忆结构，使 AI 不仅知道项目有哪些模块，还能定位每个模块的代码范围、关键入口、公开接口、依赖关系、测试位置和修改风险。

采用三级结构：

1. `memory-bank/systemPatterns.md` 记录系统级架构与模块依赖规则。
2. `memory-bank/moduleMap.md` 作为全项目模块导航索引。
3. `docs/modules/*.md` 记录复杂模块的内部边界与关键文件。

## 目标

- [x] 新增模块地图模板
- [x] 新增单模块文档模板
- [x] 明确系统架构、模块索引和模块详情的职责边界
- [x] 要求 AI 在任务开始时按模块定位上下文
- [x] 在任务计划中记录受影响模块、关键入口和跨模块影响
- [x] 更新 bootstrap prompt，使真实项目初始化时生成模块地图
- [x] 更新 README，说明模块级记忆的使用方式

## Implementation Plan

### 准备修改的文件

- `memory-bank/moduleMap.md` — 新增全项目模块索引模板
- `docs/modules/_template.md` — 新增复杂模块的详细文档模板
- `memory-bank/systemPatterns.md` — 强化系统级模块关系、依赖方向和跨模块数据流
- `AGENTS.md` — 增加模块地图读取与维护规则
- `backlog/TASK-001-template.md` — 增加受影响模块、关键入口和跨模块影响
- `backlog/TASK-002-example-bootstrap-project-memory.md` — 让示例任务覆盖模块地图
- `prompts/bootstrap-project-memory.md` — 初始化真实项目时识别并生成模块级记忆
- `README.md` — 介绍三级记忆结构和大型项目使用方式
- `memory-bank/progress.md` — 记录本次模板能力改进
- `backlog/TASK-004-add-module-memory-map.md` — 记录实施说明与变更文件

### 步骤

1. 新建模块索引和单模块详情模板，明确各字段用途。
2. 调整系统架构模板，使其只维护系统全景和模块依赖规则。
3. 更新 AI 工作流，要求先从模块地图定位，再按需读取模块文档和代码。
4. 扩展任务模板，使计划和实施记录包含模块影响。
5. 更新 bootstrap prompt，指导 AI 通过入口、目录和依赖识别模块。
6. 更新 README 和示例任务，解释新结构如何使用。
7. 检查文档路径、占位符、职责边界和维护规则是否一致。

### 风险

- 如果逐个罗列所有代码文件，模块地图会快速过期。
- 一个文件可能被多个模块共享，需要区分“所有模块”和“主要维护模块”。
- 仅凭目录结构不一定能准确识别业务模块，不确定信息必须标记为“待确认”。
- 小型项目不需要为每个目录创建模块详情文档，应允许只维护模块地图。

### 测试/验证

- 使用 `rg` 检查新增文件是否被 README、AGENTS 和 bootstrap prompt 正确引用。
- 检查模板中的模块字段、路径示例和占位符是否一致。
- 检查 `systemPatterns.md`、`moduleMap.md` 和 `docs/modules/*.md` 是否职责清晰且没有大段重复。
- 不运行代码测试或构建，因为本次只修改 Markdown 模板。

## Implementation Notes

- 建立了“系统架构、模块索引、模块详情”三级记忆结构。
- `systemPatterns.md` 只负责系统分层、模块关系、依赖方向、跨模块数据流和公共基础设施。
- `moduleMap.md` 使用目录或 glob 维护模块导航，并补充关键入口、测试范围、共享代码归属和外部系统映射。
- `docs/modules/_template.md` 只要求记录理解复杂模块所需的关键文件，避免维护全量文件清单。
- AI 工作流现在要求先通过模块地图确定影响范围，再按需读取模块文档和代码。
- 任务模板增加了受影响模块、关键入口和跨模块影响，便于计划和验证围绕模块边界展开。
- `git diff --check` 通过；仅出现 Git 的 LF/CRLF 换行提示，没有空白错误。

## Files Changed

- `memory-bank/moduleMap.md` — 新增项目模块导航索引模板
- `docs/modules/_template.md` — 新增复杂模块详细文档模板
- `memory-bank/systemPatterns.md` — 调整为系统级架构与模块关系模板
- `AGENTS.md` — 增加模块定位、计划和文档维护规则
- `backlog/TASK-001-template.md` — 增加模块影响范围与跨模块验证字段
- `backlog/TASK-002-example-bootstrap-project-memory.md` — 扩展示例任务的模块识别步骤
- `prompts/bootstrap-project-memory.md` — 增加模块识别和三级文档生成要求
- `README.md` — 说明大型项目的三级模块记忆结构
- `memory-bank/progress.md` — 记录 v0.2 模块记忆能力
- `backlog/TASK-004-add-module-memory-map.md` — 记录计划、实施结果和变更文件

## 备注

模块地图默认记录目录范围、glob 和关键文件，不维护容易过期的全量文件清单。
