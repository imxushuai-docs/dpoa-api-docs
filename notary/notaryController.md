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
- uploaderInfo：待确定具体内容
- witnessList：witness列表，为数组，数组元素格式待确定
- createdIn：创建于什么地方
- NotarizedIn：在什么地方公证

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

## 返回值

```json
[{
    notaryInfo...
}]
```



