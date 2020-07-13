# 申请POA访问权限

发送请求到POA创建人，申请POA的访问权限

## URL

```http
POST /api/poa/send/request
```

## 参数

下列参数以`request body`提交

- reason：request 原因
- poaId：请求的poaId

## 返回值

```json
{
    "data":null,
    "message":""
}
```

