# 上传文件

上传文件

## URL

```http
POST /api/file/upload/{containerName}
```

## 参数说明

下列参数放在请求路径上：

- containerName：要存的数据类型，目前不太清楚具体有多少个值。需要前端做的时候提供。目前已知：
  - POA
  - Notary

下列参数放在表单：

- file：需要上传的文件

## 返回值

```json
{
    "id":"",
    "fileName":"",
    "containerName":"",
    "blobName":""
}
```

