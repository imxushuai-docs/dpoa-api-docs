# 保存compose draft

保存compose draft草稿

## URL

```http
POST /api/poadraft/draft
```

## 参数

以下参数以`request body`提交

- grantor
- templateId
- categories
- assessor
- flag：固定值`draft`

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

# 查询grantor的poa draft

查询grantor的poa draft

## URL

```http
GET /api/poadraft/grantor/{grantorId}
```

## 参数

以下参数在路径上提交

- grantorId

## 返回值

```json
{
    poa draft info
}
```

# compose poa finalize

compose poa finalize

## URL

```http
POST /api/poadraft/finalize
```

## 参数

以下参数在`request body`提交

- grantor
- templateId
- categories
- assessor
- flag：固定值`finalize`

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

# 分步提交compose

分步提交compose

## URL

```http
POST api/poadraft/compose/step/{step}
```

## 参数

- 步骤为`1`时

  - grantor：grantor ID
  - consentList：数组，数组中的元素为对象
    - consent：consent内容
    - label：consent的label
    - status：consent的状态，字符串的`true`或者`false`

- 步骤为`2`时

  - preMeeting：此字段为对象，当前步骤主要提交pre meeting的基本数据
    - createdByName
    - createdByEmail
    - informationProvidedBy
    - relationshipToGrantor
    - email
    - phoneNumber
    - methodOfDiscussion

- 步骤为`3`时

  - preMeeting：此字段为对象，当前步骤主要提交 pre meeting的主要内容
    - content

- 步骤为`4`时

  - preMeeting：此字段为对象，当前步骤主要提交pre meeting中的assessor
    - assessor：assessor id

- 步骤为`5`时

  - poaComposeDraft：此字段为对象，当前步骤最要提交 compose选择的template以及提交的categories内容
    - templateId
    - categories

- 步骤为`6`时

  - poaComposeDraft：此字段为对象，当前步骤最要提交 compose中的affidavit数据
    - affidavitContent：为html语句，html每一对标签都必须闭合，即：`<br></br>`，不能`<br>`

- 步骤为`7`时

  此步无特殊的提交参数，只需要把第6步返回的数据提交即可。



## 返回值

```json
{
    "data":{
        "grantorInfo":{
            azure 用户数据结构
        },
        "preMeeting":{
            pre meeting数据结构
        },
        "poaComposeDraft":{
            poa compose数据结构,template和categories相关
        },
        "consentList":[
            {
                consent
            }
        ],
        ....最外层为POA的数据结构
    },
    "message":"success"
}
```

# 获取compose分步填写的信息

获取compose分步提交的信息

## URL

```http
GET api/poadraft/compose/info/{poaId}
```

## 参数

在URL上提交

- poaId：pod id

## 返回值

```json
{
    "data":{
        "grantorInfo":{
            azure 用户数据结构
        },
        "preMeeting":{
            pre meeting数据结构
        },
        "poaComposeDraft":{
            poa compose数据结构,template和categories相关
        },
        "consentList":[
            {
                consent
            }
        ],
        currentStep: 1,
        ....最外层为POA的数据结构
    },
    "message":"success"
}
```

