# 数据库文档模板

> 如果项目没有数据库，可以删除此文件，或改成数据文件、缓存、队列、搜索索引文档。

## 数据存储概览

| 存储 | 用途 | 技术 | 位置 |
|------|------|------|------|
| `{{STORE_NAME}}` | `{{PURPOSE}}` | `{{TECH}}` | `{{LOCATION}}` |

## 主数据库

技术：

`{{PRIMARY_DATABASE_TECH}}`

Schema 位置：

`{{SCHEMA_PATH}}`

### 数据模型

#### `{{MODEL_NAME}}`

说明：

`{{MODEL_DESCRIPTION}}`

| 字段 | 类型 | 说明 |
|------|------|------|
| `id` | `{{TYPE}}` | 主键 |
| `{{FIELD}}` | `{{TYPE}}` | `{{DESCRIPTION}}` |

### 关系

- `{{RELATION_1}}`
- `{{RELATION_2}}`

## 本地存储或缓存

- `{{LOCAL_STORE_1}}`
- `{{CACHE_1}}`

## 迁移

迁移命令：

```bash
{{MIGRATION_COMMAND}}
```

生成客户端或类型：

```bash
{{GENERATE_COMMAND}}
```

## 种子数据

```bash
{{SEED_COMMAND}}
```

## 备份与恢复

- 备份：`{{BACKUP_RULE}}`
- 恢复：`{{RESTORE_RULE}}`
- 数据保留策略：`{{RETENTION_RULE}}`
