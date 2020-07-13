# 数据字典列表

分页查询数据字典列表

## URL

```http
GET /api/dict/list
```

## 参数

以下参数在`request body`提交

- name：选填，按`name`模糊查询
- page
- size

## 返回值

```json
{
    "total":0,
    "content":[]
}
```

# 按NAME查询数据字典详情

按dict name查询数据字典详情

## URL

```http
GET /api/dict/detail/list/{dictName}
```

## 参数

以下参数在路径上提交

- **dictName**：dictName

## 返回值

```json
{
    "data":[
        {
            "id": "1",
            "dictId": "1",
            "label": "1",
            "value": "value",
            "orderNumber": 1,
            "createBy": "1",
            "updateBy": "1",
            "createdTime": "2020-07-13T06:12:56.000+0000",
            "updatedTime": "2020-07-13T06:12:58.000+0000"
        },
        {
            "id": "2",
            "dictId": "1",
            "label": "2",
            "value": "value",
            "orderNumber": 2,
            "createBy": "1",
            "updateBy": "1",
            "createdTime": "2020-07-13T06:13:17.000+0000",
            "updatedTime": "2020-07-13T06:13:21.000+0000"
        }
    ],
    "message":""
}
```

