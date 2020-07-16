# 登录

使用第三方登录。目前仅集成microsoft(Azure AD) login

## URL

```http
POST /api/auth/login
```

## 参数

以`json`格式传递下列参数

- username：用户名（非第三方登录使用）
- password：密码（非第三方登录使用）
- token：第三方登录后获取到的 `token`
- source：用户来源，取值为以下四种
  - Google
  - Facebook
  - AzureAD
  - LocalSystem

## 返回值

```json
{
    "id": "cce872f3-d22d-4db1-8514-e5eabd891392",
    "username": null,
    "email": null,
    "roles": [
        "ROLE_USER"
    ],
    "accessToken": "eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJjY2U4NzJmMy1kMjJkLTRkYjEtODUxNC1lNWVhYmQ4OTEzOTIiLCJpYXQiOjE1OTQwMDI4NDEsImV4cCI6MTU5NDAwNjc0MX0.zPvtXa-k8uuSqOiEDiZ_0lyngm12C3Y8w9yxCY4LBvsvz3ZFE7hS9opmMnqqJxWcjqJmE-resi9aknhvBZKxsQ",
    "tokenType": "Bearer"
}
```

后续调用`API`，需要在请求的`header`带上`accessToken`

`Authorization:Bearer token`

# 注册

注册账号到系统，仅系统内部用户会使用该功能。 （即source = LocalSystem的账号）

## URL

```http
POST /api/auth/register
```

## 参数

以`json`格式传递下列参数

- email：邮箱
- source：用户来源，固定为：`LocalSystem`
- userEntity：该字段是个对象，提交用户详细信息，如下
  - lastName：名（必填）
  - firstName：姓（必填）
  - sex：性别
  - dateOfBirth：出生日期（必填）
  - phoneNumber：手机号码（必填）
  - address1：地址
  - address2：备用地址
  - city：所在城市
  - provinceOrTerritory：所在省市或地区
  - postalCode：邮政编码

## 返回值

```json
{
    "id"："1e8d6a5bcc783a0a49901af3eaee174",
    "lastName":"smith",
    "firstName":"john",
    "sex":"male",
    "dateOfBirth":"2020-07-02",
    "phoneNumber":"12345678901",
    "address1":"",
    "address2":"",
    "city":"xxxxx",
    "provinceOrTerritory":"canada",
    "postalCode":"123456",
    "source":"LocalSystem"
}
```

# refresh token

refresh token

## URL

```http
POST /api/auth/refreshToken
```

## 参数

以下参数在`request body`提交

- refreshToken

## 返回值

```json
{
    "id": "402880e57323449c0173234b4deb0100",
    "username": "test@test.com",
    "email": "test@test.com",
    "refreshToken": "eyJhbGciOiJIUzUxMiJ9.eyJpYXQiOjE1OTQ4ODc2NzEsImV4cCI6MTU5NDg4OTQ4MX0.d71nuIgSe9BiXiw0IQFvba9_abnxHpZlHTeHUewStM8cLtM-Qt7ySFTPVdEHx6kD2sGexUJm2UrngmumdpqqEA",
    "roles": [
        "ROLE_LAWYER",
        "ROLE_GRANTOR",
        "ROLE_SDM",
        "ROLE_ASSESSOR",
        "ROLE_THIRD_PARTY",
        "ROLE_NOTARY"
    ],
    "accessToken": "eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiI0MDI4ODBlNTczMjM0NDljMDE3MzIzNGI0ZGViMDEwMCIsImlhdCI6MTU5NDg4ODE0NiwiZXhwIjoxNTk0ODg4MTc2fQ.ssiI_JWdinrFwP4WPGw8lcKY6ZjlUE-4gZY9dkvqv-U3LE8N6OqjV2L-o4Nl0JIMmX6vVDz0o4IaQvAtgbGBLw",
    "tokenType": "Bearer"
}
```

