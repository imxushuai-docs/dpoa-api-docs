# 保存compose draft

保存compose draft草稿

## URL

```http
POST /api/poadraft/draft
```

## 参数

以下参数以`request body`提交

- grantor
- templateId
- categories
- assessor
- flag：固定值`draft`

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

# 查询grantor的poa draft

查询grantor的poa draft

## URL

```http
GET /api/poadraft/grantor/{grantorId}
```

## 参数

以下参数在路径上提交

- grantorId

## 返回值

```json
{
    poa draft info
}
```

# compose poa finalize

compose poa finalize

## URL

```http
POST /api/poadraft/finalize
```

## 参数

以下参数在`request body`提交

- grantor
- templateId
- categories
- assessor
- flag：固定值`finalize`

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

