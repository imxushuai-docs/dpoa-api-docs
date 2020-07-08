# 发送分享文件的验证码

分享文件前，发送验证码用于验证是否为本人操作

## URL

```http
POST /api/share/send/verifycode
```

## 参数

无

## 返回值

```json
{
    "data":"null",
    "message":"Successful operation!"
}
```

# 分享文件email

分享poa或notary文件到指定邮箱 ，校验验证码正确才会发送

## URL

```http
GET /api/share/send2email/{verifyCode}
```

## 参数

以下参数在请求路径上提交：

- verifyCode：验证码

## 返回值

```json
{
    "data":"null",
    "message":"Successful operation!"
}
```

