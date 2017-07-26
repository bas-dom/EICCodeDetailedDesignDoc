# 任务管理模块代码流程设计

原始数据模块通过 `TaskManageView`组件和`TabelView` 组件（/pages/taskManage/componets） 呈现页面。

通过 `container` 的中间容器 `TaskManageContainer` \(/pages/taskManage/containers\) 连接`redux`管理的数据  参考 [redux全局变量定义](/data-structure/reduxquan-ju-shu-ju-ding-yi.md)。

并且使用 `/dataTask/get`接口请求任务列表，使用`reloadTable` 方法封装。

# 新建任务的代码逻辑

点击新建按钮后，通过`showModal`方法（/pages/taskManage/moduls/TaskManageModule），会展示出`TaskModalView`模态框。

使用`createAddTaskFunction` 方法（/pages/taskManage/moduls/TaskManageModule），通过`/dataTask/new`接口将数据发送给后台。

# 任务操作的代码逻辑

切换任务状态（开启／停止），使用`editTask`方法（/pages/taskManage/moduls/TableModule），通过`/dataTask/edit `接口请求到该用户的所有详细信息。

点击修改时，触发`showEditModal` 方法（/pages/taskManage/moduls/TaskManageModule），会展示出`TaskModalView`模态框。使用`createEditTaskFunction` 方法（/pages/taskManage/moduls/TaskManageModule），通过`/dataTask/edit` 接口将修改的数据传到后台。

点击删除时，使用`delTask` 方法（/pages/userManage/moduls/TableModule），通过`/dataTask/delete` 接口将任务删除。

# 



