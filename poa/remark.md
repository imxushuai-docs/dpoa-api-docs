# POA按钮权限

POA按钮权限问题

查询POA列表后，列表行中会包含一个字段`authority`，用该字段进行按钮权限判断，不同值的权限如下：

- All：包含权限如下
  - update
  - audit log
  - view
  - revoked：仅Activated状态的POA才显示此操作
  - 特殊操作：consent，仅角色为Grantor时拥有此操作
- Access：包含权限如下
  - View
  - Download
  - Print
- None或null：包含权限如下
  - Request

