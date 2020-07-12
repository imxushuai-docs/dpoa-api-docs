# 查询指定文档的操作日志

查询指定POA的操作日志

## URL

```http
GET /api/auditlog/query/{entityId}/{type}
```

## 参数

以下参数在路径上提交

- entityId：poa id或notary id
- type：查询的文档类型
  - Notary
  - PoA

以下参数以表单提交

- page
- size

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

