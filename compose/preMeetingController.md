# 保存Pre Meeting

保存Pre Meeting数据

## URL

```http
POST /api/premeeting
```

## 参数

以下参数在`request body`提交

- grantor：grantor id
- informationProvidedBy
- relationshipToGrantor
- email
- phoneNumber
- methodOfDiscussion
- content：问卷调查的参数
- assessor：选择的assessor id

## 返回值

```json
{
    "data":{},
    "message":"success"
}
```

# 按grantor id查询pre meeting的数据

按grantor id查询pre meeting的数据

## URL

```http
GET /api/premeeting/{grantorId}
```

## 参数

以下参数在路径上提交

- grantorId

## 返回值

```json
{
    "data":{},
    "message":"success"
}
```

