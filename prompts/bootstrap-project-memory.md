# Bootstrap Project Memory Prompt

把下面这段提示词复制给 AI，让它读取你的真实项目，并把本模板改造成适合该项目的版本。

```text
你现在要为这个项目生成一套 AI 项目记忆文件。请先遵守以下规则：

1. 不要一开始读取整个项目。
2. 先读取根目录文件列表、README、package/配置文件、主要入口文件和已有 docs。
3. 如果项目很大，只按需读取关键文件。
4. 先输出你准备读取哪些文件，以及为什么读取。
5. 根据目录结构、应用入口、路由或命令注册、依赖关系、公开接口和测试位置识别项目模块。不要只根据文件夹名称猜测模块职责。
6. 先生成模块地图，再按模块读取必要代码；不要为了建立文档扫描每个实现文件。
7. 读取后，生成或更新以下文件：
   - AGENTS.md
   - memory-bank/projectbrief.md
   - memory-bank/activeContext.md
   - memory-bank/systemPatterns.md
   - memory-bank/moduleMap.md
   - memory-bank/techContext.md
   - memory-bank/progress.md
   - backlog/TASK-001-template.md
   - docs/modules/<module>.md（只为复杂模块创建）
   - docs/api.md（如果项目有 API）
   - docs/database.md（如果项目有数据库）
   - docs/mobile.md 或 docs/frontend.md（如果项目有客户端）

生成要求：

- 内容必须适合当前项目，不要保留模板占位符。
- AGENTS.md 必须写清楚 AI 每次任务开始前要读哪些文件。
- AGENTS.md 必须要求 AI 先用 moduleMap 定位受影响模块，再读取对应模块文档和代码。
- AGENTS.md 必须要求 AI 写代码前输出 Implementation Plan，并等待人类确认。
- Implementation Plan 必须包含受影响模块、关键入口和跨模块影响。
- AGENTS.md 必须要求 AI 完成任务后更新当前任务文件和 memory-bank/progress.md。
- systemPatterns.md 只记录系统级架构、模块关系、依赖方向和跨模块数据流。
- moduleMap.md 记录模块名称、代码范围、关键入口、职责、直接依赖、测试位置和详细文档链接。
- 模块代码范围优先使用目录或 glob 表达，只列理解模块所需的关键文件，不要生成容易过期的全量文件清单。
- docs/modules/<module>.md 应记录模块职责、不负责的范围、关键文件、入口与注册、公开接口、依赖、数据、主要流程和测试。
- 小型项目或简单模块可以只维护 moduleMap，不强制为每个目录创建模块文档。
- 共享代码必须记录主要维护模块和使用方。
- 不要编造不存在的技术栈、命令或架构。
- 不确定的信息和模块归属标记为“待确认”。
- 不要改业务代码，只生成或更新文档。

完成后，请列出：

- 你读取了哪些文件
- 你生成或修改了哪些文件
- 识别出了哪些模块，以及每个模块的主要代码范围
- 哪些信息仍然需要我确认
```

## 使用建议

第一次在新项目中使用时，建议让 AI 只做文档生成，不要同时改业务代码。等 `AGENTS.md` 和 `memory-bank/` 稳定后，再开始具体开发任务。
