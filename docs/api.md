# API 文档模板

> 如果项目没有 API，可以删除此文件，或改成 CLI/SDK/事件接口文档。

## 基础信息

| 项目 | 值 |
|------|-----|
| Base URL | `{{BASE_URL}}` |
| 认证方式 | `{{AUTH_METHOD}}` |
| 响应格式 | `{{RESPONSE_FORMAT}}` |
| API 版本 | `{{API_VERSION}}` |

## 通用约定

- 请求 Content-Type：`{{REQUEST_CONTENT_TYPE}}`
- 响应编码：`{{RESPONSE_ENCODING}}`
- 时间格式：`{{TIME_FORMAT}}`
- 分页方式：`{{PAGINATION_RULE}}`
- 幂等性约定：`{{IDEMPOTENCY_RULE}}`

## 认证

### `{{METHOD}} {{AUTH_ENDPOINT}}`

说明：

`{{AUTH_DESCRIPTION}}`

请求体：

```json
{
  "{{field}}": "{{type}}"
}
```

响应：

```json
{
  "{{field}}": "{{type}}"
}
```

## 资源接口

### `{{METHOD}} {{ENDPOINT_PATH}}`

说明：

`{{ENDPOINT_DESCRIPTION}}`

请求参数：

| 参数 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `{{name}}` | `{{type}}` | `{{yes_or_no}}` | `{{description}}` |

响应：

```json
{
  "{{field}}": "{{type}}"
}
```

## 错误响应格式

```json
{
  "error": "{{ERROR_CODE_OR_MESSAGE}}",
  "message": "{{HUMAN_READABLE_MESSAGE}}"
}
```

| 状态码 | 说明 |
|--------|------|
| 200 | 成功 |
| 400 | 请求参数错误 |
| 401 | 未认证 |
| 403 | 无权限 |
| 404 | 资源不存在 |
| 409 | 资源冲突 |
| 500 | 服务器内部错误 |

## 变更记录

| 日期 | 变更 |
|------|------|
| `{{DATE}}` | `{{CHANGE_SUMMARY}}` |
