# POA上传

上传POA

## URL

```http
POST /api/poa/upload
```

## 参数

下列参数以`json`格式在`request body`提交：

- type：POA的上传方式，有以下两种值
  - upload
  - compose
- uploadPoaFileType：上传的POA文件类型，有以下值：
  - ORIGINAL_DOCUMENT
  - CERTIFIED_NOTARIZED
  - PHOTO_COPY
- grantorInfo：grantor，对象，字段如下：
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
- preparedInfo：上传人，为对象
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
- poaType：poa类型，有以下值：
  - PERSONAL_HEALTH
  - FINANCE_PROPERTY
- poaParam：当`poaType = FINANCE_PROPERTY`时，有特殊的内容需要保存，该字段为对象类型
- createdIn：poa文档创建于什么地方
- activatedIn：poa文档与什么地方生效
- timeFrom：从什么时候开始生效
- timeTo：到什么时候失效
- sdmList：数组，数组中的对象格式如下
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
- witnessList：数组，数组元素格式如下：
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
- affidavitForActivation：这也是文件，调用文件上传需要使用单独定义的`containerName`进行文件上传
- capacityAssessment：assessor id
- consentAndDirection：授权信息，可能为ID或json，待确定
- fileId：上传的文件ID

## 返回值

和上传的内容基本一致，会多出ID。

# POA更新

更新指定POA

## URL

```http
POST /api/poa/update/{poaId}
```

## 参数

以下参数在请求路径上提交：

- poaId：需要更改的POA ID

以下参数以`json`格式在`request body`中提交：

👆参考新增POA👆

## 返回值

和上传的数据基本一致。

# POA查询

查询POA

## URL

```http
GET /api/poa/query
```

## 参数

以下参数通过表单上传：

- grantorLastName
- grantorPhoneNumber
- grantorDateOfBirth
- grantorEmail
- poaFileId
- poaType
- poaStatus
- timeFrom
- timeTo

## 返回值

```json
[{
    poaInfo...
}]
```

# 修改指定POA状态

修改指定POA状态

## URL

```http
POST /api/poa/status/{poaId}/{status}
```

## 参数

以下参数在请求路径中提交：

- poaId：需要更新状态的POA ID
- status：更新为什么状态，有效的状态值如下
  - Activated
  - Revoked

## 返回值

无

