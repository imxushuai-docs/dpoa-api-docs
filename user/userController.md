# 查询grantor

查询grantor列表

##  URL

```http
GET /api/user/query/grantor
```

## 参数

以下参数以表单上传：

- grantorLastName
- grantorFirstName
- grantorEmail
- grantorDateOfBirth
- page
- size

## 返回值

```json
[{
    grantorInfo...
}]
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
    userinfo...
}
```

