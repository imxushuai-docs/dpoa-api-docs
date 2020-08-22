# 查询指定文档的操作日志

查询指定POA的操作日志

## URL

```http
GET /api/auditlog/query/{entityId}/{type}
```

## 参数

以下参数以表单提交

- page
- size
- entityId：poa id或notary id
- type：查询的文档类型
  - Notary
  - PoA

## 返回值

```json
{
    "content":[{
        "id":"",
        "type":"",
        "entityId":"",
        "userIp":"",
        "action":"",
        "message":"",
        "userId":"",
        "actionTimestamp":""
    }],
    "total":1
}
```

# 记录操作日志

记录用户操作日志，如：下载，打印POA等操作

## URL

```http
POST /api/auditlog/record
```

## 参数

在`request body`中提交

- entityId：POA ID或者notary id
- entityType：PoA或者Notary
- action：操作，Download/Print等

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

