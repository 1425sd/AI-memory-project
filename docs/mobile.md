# 客户端文档模板

> 如果项目不是移动端，可以把本文件改成 Web、桌面端、CLI 或前端文档。

## 平台支持

| 平台 | 最低版本 | 状态 | 备注 |
|------|----------|------|------|
| `{{PLATFORM}}` | `{{MIN_VERSION}}` | `{{STATUS}}` | `{{NOTE}}` |

## 技术方案

- 框架：`{{CLIENT_FRAMEWORK}}`
- 路由：`{{ROUTING}}`
- 状态管理：`{{STATE_MANAGEMENT}}`
- 样式方案：`{{STYLING}}`
- UI 组件库：`{{UI_LIBRARY}}`

## 页面或界面结构

```text
{{CLIENT_ENTRY}}
├── {{SCREEN_OR_ROUTE_1}}
├── {{SCREEN_OR_ROUTE_2}}
└── {{SCREEN_OR_ROUTE_3}}
```

## 状态管理

| 状态模块 | 文件 | 职责 |
|----------|------|------|
| `{{STATE_NAME}}` | `{{FILE_PATH}}` | `{{RESPONSIBILITY}}` |

## 本地存储与缓存

- `{{LOCAL_STORAGE_1}}`
- `{{LOCAL_STORAGE_2}}`
- `{{CACHE_RULE}}`

## 网络请求

统一请求入口：

```text
{{API_CLIENT_PATH}}
```

调用约定：

- `{{NETWORK_RULE_1}}`
- `{{NETWORK_RULE_2}}`

## 离线与异常体验

- `{{OFFLINE_RULE_1}}`
- `{{ERROR_UI_RULE_1}}`

## 构建与运行

```bash
{{INSTALL_COMMAND}}
{{DEV_COMMAND}}
{{BUILD_COMMAND}}
```
