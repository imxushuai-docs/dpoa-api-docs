# POA上传

上传POA

## URL

```http
POST /api/poa/upload
```

## 参数

下列参数以`json`格式在`request body`提交：

- **type**：POA的上传方式，有以下两种值
  - upload
  - compose
- **uploadPoaFileType**：上传的POA文件类型，有以下值：
  - ORIGINAL_DOCUMENT
  - CERTIFIED_NOTARIZED
  - PHOTO_COPY
- **grantorInfo**：grantor，对象，字段如下：
  - lastName
  - firstName
  - sex
  - dateOfBirth
  - **email**
  - phoneNumber
  - address1
  - address2
  - provinceOrTerritory
  - city
  - postalCode
- **preparedInfo**：上传人，为对象
  - lastName
  - firstName
  - sex
  - dateOfBirth
  - **email**
  - phoneNumber
  - address1
  - address2
  - provinceOrTerritory
  - city
  - postalCode
- **poaType**：poa类型，有以下值：
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
- **fileId**：上传的文件ID

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

# 获取指定POA的consent

获取指定POA的consent

## URL

```http
GET /api/poa/consent/{poaId}
```

## 参数

以下参数在路径上提交

- poaId：poa id

## 返回值

```json
{
    "data": [
        {
            "id": "1",
            "consent": "[{\"order\":1,\"content\":\"All references to my Lawyer or the Company herein shall include any successor or relacement lawyer(s)/law firm or future custodian of the documents referenced in this Consent and Direction for whatever reason('Cusodian'),however, such Custodian shall be bound by the terms of this Consent and Direction.\"},{\"order\":2,\"content\":\"I am providing this Consent and Direction freely, voluntarily without duress or threat from any other person, understanding and appreciating its intent to be relied on, even after my incapacity.\"},{\"order\":3,\"content\":\"The lawyer is permitted to maintain, store and keep a hardcopy or softcopy of the documents referenced in this Consent and Direction, the Lawyer is permitted to store the document electronically.\"},{\"order\":4,\"content\":\"I consent to the documents in this Consent and Direction to be uploaded/not uploaded to www.POAregistry.com. I consent to allow my name to be included in any searches of the registry with the same first name, middle name, last name and/or date of birth.\"},{\"order\":5,\"content\":\"I authorize the Lawyer to make notarial copies.\"},{\"order\":6,\"content\":\"This Consent and Direction may be executed by the undersigned in counterparts (including through the use of video witnessing) and may be delivered by facsimile or other means of electronic communication (in portable document format ('pdf') or tagged image format ('tif')) and all such counterparts, taken together, shall constitute an original document/Consent and Direction.\"}]",
            "prefix": null,
            "suffix": null,
            "status": null
        },
        {
            "id": "2",
            "consent": "[{\"order\":7,\"content\":\"On (insert date) I signed a (insert type of POA) with (insert original law firm name and lawyer). I provided (insert original law firm) with (insert number of original documents remaining with Lawyer) original documents for safekeeping and to release it in accordance with this Consent and Direction.\"},{\"order\":8,\"content\":\"I authorize and direct the Lawyer to release or provide access to one or more copies of (insert the type of POA) to (insert who the Grantor selected as being able to have a copy of the POA) upon receiving written notice of the same and are under not required to confirm capacity of said person(s) prior to releasing said information. I authorize that copies of the document may be distributed via email or any other such electronic means.\"},{\"order\":9,\"content\":\"I further authorize that verification of (insert person from paragraph 7) shall be satisfied upon the delivery of (insert valid verification I further authorize that verification of (insert person from paragraph 7) shall be satisfied upon the delivery of (insert valid verification - ex. DL or other items raised by Security Session).\"},{\"order\":10,\"content\":\"I authorize that while I am capable, upon the request of any other person or entity (other than specified in paragraph 7), the Lawyer may disclose and/or release the following information about the POA.\"},{\"order\":11,\"content\":\"I authorize that while I am incapable, upon the request of any other person or entity (other than specified in paragraph 7), the Lawyer may disclose the following information about the POA.\"},{\"order\":12,\"content\":\"Notwithstanding anything in this Consent and Direction to the contrary, I authorize my Attorney to upload the (insert type of POA) to poaregistry.com. In the event that this clause conflicts with any other provision of this Consent and Direction, then this clause shall prevail.\"},{\"order\":13,\"content\":\"I authorize the Lawyer to destroy the original copies (updates to the system) of the Power of Attorney in the event I die without the need for a death certificate.\"},{\"order\":14,\"content\":\"I or my custodian may - This is my last in time - I will either continue to upload all subsequent POAs to this platform.\"},{\"order\":15,\"content\":\"I agree that I shall notify the company - or I shall notify the Company as or I shall indemnify the company.\"},{\"order\":16,\"content\":\"We do not guarantee - the current system doesn't - lawyer doesn't guarantee that it is the last in time.\"},{\"order\":17,\"content\":\"Consent to disbursements charge.\"},{\"order\":18,\"content\":\"Lawyer to add additional terms.\"},{\"order\":19,\"content\":\"You would want to be waiving, that if they one they know has been revoked. Received a resignation form.\"},{\"order\":20,\"content\":\"Guardian appointments by the court - revoked.\"},{\"order\":21,\"content\":\"Fiting in the afidaifts.\"},{\"order\":22,\"content\":\"Create custom space for retainer.\"},{\"order\":23,\"content\":\"Consent to lawyer changing the online status (if they know the client has revoked, resignation of SDM, death of Grantor, Guardian appointed by court - because that would automatically revoke these.\"}]",
            "prefix": null,
            "suffix": null,
            "status": null
        }
    ],
    "message": "Successful operation!"
}
```

# 变更poa consent的状态

变更指定POA的指定consent的状态

## URL

```http
POST /api/poa/consent/change/status
```

## 参数

以下参数以`request body`提交

- poaId：poa id
- consentId：consent id
- status：改变后的状态，**注意：是字符串的true和false**
  - true
  - false

## 返回值

```json
{
    "data": null,
    "message": "Successful operation!"
}
```

