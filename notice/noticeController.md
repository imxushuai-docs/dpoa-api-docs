# 查询当前登录用户的未读通知

查询当前登录的用户的未读通知列表

## URL

```http
GET /api/notice
```

## 参数

无

## 返回值

```json
[{
    noticeInfo
}]
```

noticeInfo字段解释：

- id
- receiverId：消息接收者ID
- receiverName：消息接收者Name
- operatorId：消息发送者ID
- operatorName：消息发送者Name
- action：操作
- targetType：被操作的对象类型
- targetId：被操作的对象ID
- createdTime：消息发送时间
- type：消息类型
- state：消息状态（此API比返回未读消息）
  - Unread：未读
  - Readed：已读

# 已读当前用户所有未读消息

设置当前登录用户的所有未读消息为已读

## URL

```http
GET /api/notice/read
```

## 参数

无

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

