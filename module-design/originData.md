# 原始数据

## 原始数据模块代码流程设计

* 原始数据模块通过 `OriginDataView`组件以及`TableView` 表格模块（/pages/originData/componets） 呈现页面。
* 通过 container 的中间容器 `OriginDataContainer` 以及 `TableContainer` \(/pages/originData/containers\) 连接`redux`管理的数据  参考 [redux全局变量定义](/data-structure/reduxquan-ju-shu-ju-ding-yi.md)。
* 并且使用 `/admin/dataPointManager/search` 接口请求原始数据，使用`reloadTable` 方法封装。

## 原始数据的搜索功能代码逻辑

* 选择搜索类型，在输入框里输入的内容会放到`condition.searchText`变量里。
* 然后传给`reloadTable` 方法中的 `test`变量，使用`/admin/dataPointManager/search` 接口即可请求到对应的数据。

## 原始数据的历史趋势图代码逻辑

* 在`OriginDataView`组件中加入 `HistoryModal` 组件，通过`showHistoryModal`方法（/pages/originData/moduls/OriginDataModual）将选择的点名传给`HistoryModal` 组件并使其显示出来。



