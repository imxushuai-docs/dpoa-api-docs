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

