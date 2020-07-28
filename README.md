# 接口文档

DPOA API 文档说明



# 接口返回值定义

所有接口均遵守`HTTP请求规范`，但不严格遵守`Http status`的返回标准，如：新增不会返回`201`，还是使用`200`

## 查询

### 列表

- 参数

  所有的列表查询均采用后端分页，参数传递需要在使用表单传递`page`以及`size`字段

- 返回值

  查询列表的返回值统一以如下格式返回：

  ```json
  {
      "total":0,
      "content":[{}]
  }
  ```

### 普通查询

- 参数

  参数参考具体的API

- 返回值

  ```json
  {
      "data":{},
      "message":""
  }
  ```

## 其他接口

- 参数

  参考具体API

- 返回值

  ```json
  {
      "data":{},
      "message":""
  }
  ```

## 异常情况

所有非`200`状态码均会使用特殊的返回格式，但`http status`会根据不同类型的错误而不同，如果参数错误的异常会是`400`等。

- 异常返回格式

  ```json
  {
      "data":{},
      "message":""
  }
  ```



# 更新记录

## 2020-07-08

- [【查看详情】](poa/poaController.md#POA上传)POA上传参数更新，包含`grantor`,`prepared`变更为`grantorInfo`,`preparedInfo`.
- [【查看详情】](notary/notaryController.md#上传Notary)Notary上传`uploader`参数确认
- [【查看详情】](share/shareController.md)分享模块部分API文档
- [【查看详情】](user/userController.md)用户相关部分API文档

## 2020-07-10

- [【查看详情】](user/userController.md#条件查询用户)新增按条件查询用户列表API，可选参数：角色，姓名，电话，email，生日
- [【查看详情】](poa/poaController.md#参数)POA上传参数更新，`assossor`现在为直接选择，只需要上传`assossor id`
- [【查看详情】](auditlog/auditLogController.md)新增audit log api文档

## 2020-07-12

- [【查看详情】](poa/poaController.md#获取指定POA的consent)新增POA Consent相关API

## 2020-07-13

- [【查看详情】](requests/sendRequestController.md)新增发送请求API文档
- [【查看详情】](dict/dictController.md)新增数据字典API文档
- [【查看详情】](requests/requestsController.md#按类别查询request列表)Request按类别查询Request列表

## 2020-07-14

- [【查看详情】](notary/notaryController.md#更新notary的状态)新增更新Notary状态的API
- [【查看详情】](requests/requestsController.md#接受或拒绝请求)新增接受或拒绝某个文档的访问权限的请求
- [【查看详情】](compose/templateController.md)新增compose的template列表查询API
- [【查看详情】](compose/categoryController.md)新增compose的category API
- [【查看详情】](compose/preMeetingController.md)新增compose的premeeting API

## 2020-07-15

- [【查看详情】](poa/poaController.md#ready状态的POA变更为activated)新增将compose提交的poa激活
- [【查看详情】](compose/poaComposeDraft.md)新增compose保存poa数据API

## 2020-07-16

- [【查看详情】](auth/authController.md#refresh token)新增refresh token API
- [【查看详情】](poa/poaController.md#按ID查询POA信息)新增按POA ID查询POA

## 2020-07-18

- [【查看详情】](notice/noticeController.md)新增通知相关API

## 2020-07-20

-  [【查看详情】](notary/notaryController.md#按ID查询Notary)新增按id查询notary信息API

## 2020-07-27

- [【查看详情】](notary/notaryController.md)新增notarize文件

## 2020-07-28

- [【查询详情】](poa/remark.md)POA操作权限说明
- [【查看详情】](user/userController.md#选择用户角色)新增选择用户角色API