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
