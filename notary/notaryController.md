# 上传Notary

上传Notary

## URL

```http
POST /api/notary/upload
```

## 参数

以下参数用`json`格式以`request body`上传：

- type：Document Type，文档类型
- uploadNotaryFileType：上传的文档类型，有以下值
  - ORIGINAL_DOCUMENT
  - CERTIFIED_NOTARIZED
  - PHOTO_COPY
- uploaderInfo：对象
  - lastName
  - firstName
  - sex
  - dateOfBirth
  - email
  - phoneNumber
  - address1
  - address2
  - provinceOrTerritory
  - city
  - postalCode
- witnessList：数组，数组字段如下
  - lastName
  - firstName
  - sex
  - dateOfBirth
  - email
  - phoneNumber
  - address1
  - address2
  - provinceOrTerritory
  - city
  - postalCode
- createdIn：创建于什么地方
- NotarizedIn：在什么地方公证
- fileId：文件id

## 返回值

与上传的数据基本一致。

# 查询Notary列表

查询notary列表

## URL

```http
GET /api/notary/query
```

## 参数

- lastName
- phoneNumber
- email
- dateOfBirth
- fileId
- timeOfNotarization
- notaryPublic
- page
- size

## 返回值

```json
{
    "total":10,
    "content":[{
        notaryInfo...
    }]
}
```

# 更新notary的状态

更新指定notary的状态值

## URL

```http
POST /api/notary/status
```

## 参数

以下参数在`request body`提交

- notaryId：notary id
- status：变更后的status值

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```



# 按ID查询Notary

按ID查询Notary

## URL

```http
GET /api/notary/query/{notaryId}
```

## 参数

- notaryId

## 返回值

```json
{
    "data":{
        notaryInfo
    },
    "message":"success"
}
```

