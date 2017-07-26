# 任务管理模块代码流程设计

原始数据模块通过 `TaskManageView`组件和`TabelView` 组件（/pages/taskManage/componets） 呈现页面。

通过 `container` 的中间容器 `TaskManageContainer` \(/pages/taskManage/containers\) 连接`redux`管理的数据  参考 [redux全局变量定义](/data-structure/reduxquan-ju-shu-ju-ding-yi.md)。

并且使用 `/dataTask/get `接口请求任务列表，使用`reloadTable` 方法封装。

# 新建任务的代码逻辑

点击新建按钮后，通过`showModal`方法（/pages/taskManage/moduls/TaskManageModual），会展示出`TaskModalView`模态框。

使用`createAddTaskFunction` 方法（/pages/taskManage/moduls/TaskManageModual），通过`/dataTask/new `接口将数据发送给后台。

# 任务操作的代码逻辑

切换任务状态（开启／关闭），使用`editTask`方法（/pages/taskManage/moduls/TableModule），通过`/admin/loadUsersSetting` 接口请求到该用户的所有详细信息。

使用`getRecords` 方法（/pages/userManage/moduls/UserManageModual），通过`/admin/getRecords` 接口请求该用户的操作记录。

使用`getUserProjRecords` 方法（/pages/userManage/moduls/UserManageModual），通过`/admin/userProjRecords`接口请求该用户被分配到的项目。

使用`updataUsersSetting` 方法（/pages/userManage/moduls/UserManageModual），通过`/admin/updateUsersSetting`接口将修改后的数据发送给后台。

# 



