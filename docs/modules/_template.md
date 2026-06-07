# {{MODULE_NAME}} Module

> 本文档用于复杂模块。简单模块只需登记在 `memory-bank/moduleMap.md`，不必为每个目录创建文档。

## 模块定位

- 模块类型：`{{BUSINESS_OR_INFRASTRUCTURE}}`
- 源码范围：`{{SOURCE_GLOB}}`
- 主要维护方：`{{OWNER_OR_TEAM}}`
- 模块状态：`{{ACTIVE_DEPRECATED_OR_MIGRATING}}`

## 职责

- `{{RESPONSIBILITY_1}}`
- `{{RESPONSIBILITY_2}}`

## 不负责

明确模块边界，避免 AI 把相邻模块的逻辑放到这里。

- `{{OUT_OF_SCOPE_1}}`
- `{{OUT_OF_SCOPE_2}}`

## 关键文件

只记录理解或修改模块时必须优先阅读的文件，不维护全量文件列表。

| 文件或 glob | 作用 | 修改注意事项 |
|-------------|------|--------------|
| `{{PATH}}` | `{{PURPOSE}}` | `{{CHANGE_WARNING}}` |

## 入口与注册

| 类型 | 路径或标识 | 说明 |
|------|------------|------|
| 应用入口 | `{{APPLICATION_ENTRY}}` | `{{ENTRY_DESCRIPTION}}` |
| 路由或命令注册 | `{{REGISTRATION_POINT}}` | `{{REGISTRATION_DESCRIPTION}}` |
| 后台任务或订阅 | `{{BACKGROUND_ENTRY}}` | `{{BACKGROUND_DESCRIPTION}}` |

## 公开接口

记录允许其他模块使用的函数、类型、事件、端点或包入口。

| 接口 | 类型 | 使用方 | 稳定性或兼容要求 |
|------|------|--------|------------------|
| `{{PUBLIC_INTERFACE}}` | `{{FUNCTION_TYPE_EVENT_OR_API}}` | `{{CONSUMERS}}` | `{{COMPATIBILITY_RULE}}` |

## 依赖关系

### 本模块依赖

- `{{DEPENDENCY_1}}` — `{{WHY_NEEDED}}`
- `{{DEPENDENCY_2}}` — `{{WHY_NEEDED}}`

### 依赖本模块

- `{{CONSUMER_1}}` — `{{HOW_USED}}`
- `{{CONSUMER_2}}` — `{{HOW_USED}}`

### 禁止依赖

- `{{FORBIDDEN_DEPENDENCY_RULE}}`

## 数据与状态

- 核心数据结构：`{{CORE_DATA_TYPES}}`
- 数据存储：`{{STORAGE_LOCATION}}`
- 缓存或本地状态：`{{CACHE_OR_LOCAL_STATE}}`
- 数据所有权：`{{DATA_OWNER}}`

## 主要流程

```text
{{INPUT_OR_TRIGGER}} -> {{VALIDATION}} -> {{CORE_PROCESS}} -> {{PERSISTENCE_OR_EVENT}} -> {{OUTPUT}}
```

## 错误与边界情况

- `{{ERROR_CASE_1}}`
- `{{ERROR_CASE_2}}`
- `{{RETRY_OR_FALLBACK_RULE}}`

## 测试

| 测试类型 | 路径或命令 | 重点覆盖 |
|----------|------------|----------|
| 单元测试 | `{{UNIT_TEST_GLOB_OR_COMMAND}}` | `{{UNIT_TEST_SCOPE}}` |
| 集成测试 | `{{INTEGRATION_TEST_GLOB_OR_COMMAND}}` | `{{INTEGRATION_TEST_SCOPE}}` |

## 修改检查清单

- [ ] 是否改变公开接口或数据格式
- [ ] 是否需要更新应用入口、路由、Provider、中间件或后台任务注册
- [ ] 是否影响依赖模块或跨模块数据流
- [ ] 是否需要数据库迁移、缓存兼容或历史数据处理
- [ ] 是否更新 `memory-bank/moduleMap.md`
- [ ] 是否更新 API、数据库、客户端或部署文档
