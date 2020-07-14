# 查询request列表

查询当前登录用户的request列表

## URL

```http
GET /api/requests/list
```

## 参数

无

## 返回值

```json
{
    "incomingRequests":[{
        requestInfo...
    }],
    "sendOutRequests":[{
        requestInfo...
    }]
}
```

# 按类别查询request列表

按类别查询当前登录用户的request列表

## URL

```http
GET /api/request/list/{type}
```

## 参数

以下参数在请求路径上提交

- type
  - incoming
  - sendOut

## 返回值

```json
{
    "content":[],
    "total":0
}
```



# 查看请求详情

查询指定请求的详细信息

## URL

```http
GET /api/requests/view/{requestId}
```

## 参数

以下参数在请求路径传递：

- requestId：请求ID

## 返回值

```json
{
    senderInfo:{
        
    },
    recipientInfo:{
        
    },
    poaInfo:{
        
    },
    requestInfo...
}
```

# 接受或拒绝请求

接受或拒绝某个文档的访问权限请求

## URL

```http
GET /api/requests/process/{requestsId}/{result}
```

## 参数

以下参数在路径上提交

- requestsId：请求ID
- result：接受或拒绝
  - Accepted：接受
  - Declined：拒绝

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

