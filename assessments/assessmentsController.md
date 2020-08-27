# Assessments 数据结构

```json
{
    "id": "id",
    "name":"对应client",
    "fileId":"fileId",
    "date":"对应Date",
    "status":"status",
    "requestsId":"requestsId",
    "poaId":"poaId",
    "submittedDate":"submittedDate",
    "assessorId":"assessorId",
    "grantorId":"grantorId",
    "type":"type",
    "fileIdStr":"对应Assessment number"
}
```



#  查询Assessments列表 

按条件分页查询Assessments列表

##  URL

```http
GET /api/assessments/list
```

## 参数 

以下参数在表单中提交

- lastName
- phoneNumber
- email
- fileId
- submittedDateFrom：日期时间格式， 01-01-2020 15:00:00
- submittedDateTo：日期时间格式， 01-01-2020 15:00:00
- status
  - New
  - Accepted
  - Decline
  - Complate
- fileId

## 返回值

```json
{
    "total":0,
    "content":[]
}
```

# 保存Assessments文件

Assessor提交文件

## URL

```http
POST api/assessments
```

## 参数

以下参数在`request body`i提交

- id
- fileId
- type

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

