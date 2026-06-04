# System Patterns

## 架构概览

用简图描述系统主要模块、数据流和外部依赖。

```text
{{CLIENT_OR_ENTRYPOINT}}
        |
        v
{{APPLICATION_LAYER}}
        |
        v
{{DATA_OR_SERVICE_LAYER}}
```

## 模块边界

记录项目的主要模块，以及它们分别负责什么。

| 模块 | 路径 | 职责 |
|------|------|------|
| `{{MODULE_NAME}}` | `{{PATH}}` | `{{RESPONSIBILITY}}` |

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
