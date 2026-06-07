# System Patterns

> 本文件只记录系统级架构、模块关系和全局约束。模块代码范围与导航见 `memory-bank/moduleMap.md`，复杂模块内部说明见 `docs/modules/*.md`。

## 架构概览

用简图描述系统分层、主要模块、数据流和外部依赖。

```text
{{CLIENT_OR_ENTRYPOINT}}
        |
        v
{{APPLICATION_LAYER}}
        |
        v
{{DATA_OR_SERVICE_LAYER}}
```

## 系统分层

记录每一层允许承担的职责，以及不应越过的边界。

| 层级 | 职责 | 允许依赖 | 禁止事项 |
|------|------|----------|----------|
| `{{LAYER_NAME}}` | `{{RESPONSIBILITY}}` | `{{ALLOWED_DEPENDENCIES}}` | `{{FORBIDDEN_USAGE}}` |

## 模块关系

这里只记录模块之间的关系和约束，不重复维护模块内部文件。模块源码范围和入口统一记录在 `memory-bank/moduleMap.md`。

| 上游模块 | 关系 | 下游模块 | 约束 |
|----------|------|----------|------|
| `{{UPSTREAM_MODULE}}` | `{{CALLS_OR_PUBLISHES}}` | `{{DOWNSTREAM_MODULE}}` | `{{DEPENDENCY_RULE}}` |

## 依赖方向

- `{{DEPENDENCY_DIRECTION_RULE_1}}`
- `{{DEPENDENCY_DIRECTION_RULE_2}}`
- `{{FORBIDDEN_DEPENDENCY_1}}`

## 跨模块数据流

```text
{{ENTRY_MODULE}} -> {{PROCESSING_MODULE}} -> {{PERSISTENCE_OR_EXTERNAL_MODULE}} -> {{OUTPUT_MODULE}}
```

关键事件或调用链：

- `{{CROSS_MODULE_FLOW_1}}`
- `{{CROSS_MODULE_FLOW_2}}`

## 公共基础设施

记录被多个模块共同使用的能力，以及它们的主要维护边界。

| 基础设施 | 路径或服务 | 使用方 | 约束 |
|----------|------------|--------|------|
| `{{SHARED_CAPABILITY}}` | `{{PATH_OR_SERVICE}}` | `{{CONSUMERS}}` | `{{USAGE_RULE}}` |

## 设计模式

### 状态管理

说明项目如何管理状态，例如 Context、Redux、Zustand、服务端状态缓存、全局 store 等。

- `{{STATE_PATTERN_1}}`
- `{{STATE_PATTERN_2}}`

### 数据访问

说明 API、数据库、文件、第三方服务的访问入口和约定。

- `{{DATA_ACCESS_RULE_1}}`
- `{{DATA_ACCESS_RULE_2}}`

### 数据流

```text
{{USER_OR_SYSTEM_ACTION}} -> {{PROCESSING_STEP}} -> {{STATE_OR_STORAGE_UPDATE}} -> {{UI_OR_OUTPUT_UPDATE}}
```

## 目录结构约定

- `{{PATH_1}}` — `{{PURPOSE_1}}`
- `{{PATH_2}}` — `{{PURPOSE_2}}`
- `{{PATH_3}}` — `{{PURPOSE_3}}`

## 命名规范

- `{{NAMING_RULE_1}}`
- `{{NAMING_RULE_2}}`
- `{{NAMING_RULE_3}}`

## 错误处理

记录项目中错误处理、日志、重试、降级、用户提示等约定。

- `{{ERROR_RULE_1}}`
- `{{ERROR_RULE_2}}`
- `{{ERROR_RULE_3}}`

## 安全与权限

记录认证、授权、密钥、敏感数据处理等约定。

- `{{SECURITY_RULE_1}}`
- `{{SECURITY_RULE_2}}`
