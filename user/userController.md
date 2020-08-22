# 新数据结构对应老数据结构

- lastName：givenName
- firstName：surname
- sex：extension_b5c04d56d76b4ae085b6a3c7b5379c26_sex
- DOB：Azure ad不支持，先不管
- email：按我给你说的优先级来取
- phoneNumber：extension_b5c04d56d76b4ae085b6a3c7b5379c26_phoneNumber
- address1：streetAddress
- address2：extension_b5c04d56d76b4ae085b6a3c7b5379c26_address2
- city：city
- postalCode：postalCode
- provinceOrTerritory：state
- role：extension_b5c04d56d76b4ae085b6a3c7b5379c26_role

# 条件查询用户

按条件分页查询用户列表，条件包含：角色，名称，手机号码，email，生日

##  URL

```http
GET /api/user/query/role
```

## 参数

以下参数以表单上传：

- lastName
- firstName
- phoneNumber
- email
- dateOfBirth
- roleName：用户角色
  - ROLE_GRANTOR
  - ROLE_SDM
  - ROLE_LAWYER
  - ROLE_ASSESSOR
  - ROLE_THIRD_PARTY
  - ROLE_NOTARY
  - ROLE_WITNESS
- page
- size

## 返回值

```json
{
    "content": [
        {
            "id": "402880e57323449c0173234b4deb0100",
            "username": "test@test.com",
            "lastName": "test",
            "firstName": "test",
            "sex": "male",
            "dateOfBirth": "2020-07-09T16:00:00.000+0000",
            "email": "test@test.com",
            "phoneNumber": "123456",
            "address1": "test address 1",
            "address2": "test address 2",
            "city": "test city",
            "provinceOrTerritory": "test province or territory",
            "postalCode": "1234",
            "source": "LocalSystem",
            "activeCode": null,
            "status": "Activated",
            "additionalInfo": null,
            "createdTime": "2020-07-07T02:22:44.000+0000",
            "updatedTime": "2020-07-07T02:22:46.000+0000",
            "roles": null
        }
    ],
    "total": 1
}
```

# 查询当前登录用户信息

查询当前登录的用户信息

## URL

```http
GET /api/user/current
```

## 参数

无

## 返回值

```json
{
    "id": "402880e57323449c0173234b4deb0100",
    "username": "test@test.com",
    "lastName": "test",
    "firstName": "test",
    "sex": "male",
    "dateOfBirth": "2020-07-09T16:00:00.000+0000",
    "email": "test@test.com",
    "phoneNumber": "123456",
    "address1": "test address 1",
    "address2": "test address 2",
    "city": "test city",
    "provinceOrTerritory": "test province or territory",
    "postalCode": "1234",
    "source": "LocalSystem",
    "activeCode": null,
    "status": "Activated",
    "additionalInfo": null,
    "createdTime": "2020-07-07T02:22:44.000+0000",
    "updatedTime": "2020-07-07T02:22:46.000+0000",
    "roles": null
}
```

# 选择用户角色

当用户角色为空时，需要先选择用户角色

## URL

```http
POST /api/user/choose/role
```

## 参数

以下参数在`request body`提交

- userId：user id
- roleName：角色名称
  - ROLE_GRANTOR
  - ROLE_SDM
  - ROLE_ASSESSOR
  - ROLE_THIRD_PARTY
  - ROLE_NOTARY
  - ROLE_WITNESS

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

# 创建用户

创建用户

## URL

```http
POST api/user/create
```

## 参数

参考顶部新的用户数据格式

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

# 更新用户

更新用户信息

## URL

```http
POST api/user/update
```

## 参数

参考顶部新的用户数据格式

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

# 修改密码

修改当前登录用户的密码

## URL

 ```http
POST api/user/change/password
 ```

## 参数

以`request body`提交

- password

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

# 获取用户general consent

获取用户的general consent

## URL

```http
GET api/user/general/consent
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

# 确认general consent

用户选择同意或是拒绝general consent

## URL

```http
POST api/user/change/consent
```

## 参数

以`request body`提交

- id
- consent
- flag
- userId：当前登录的用户ID

## 返回值

```json
{
    "data":null,
    "message":"success"
}
```

