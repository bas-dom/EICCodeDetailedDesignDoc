#数据分类

###数据分类代码流程设计
进入数据分类后通过`/tag/getThingTree`接口获取到左侧树形结构数据。并通过组件`TreeView`(/pages/dataClassify/components/TreeView.js)完成数据呈现。右侧表格数据根据每个节点对应的**_id**获取到不同的数据。初始默认**_id**为`" "`空字符串。并通过`/tag/thingTree/detail`接口获取到每个节点下的数据。并通过组件`TableView`(/pages/dataClassify/components/TableView.js)完成页面呈现。最后将两个组件 合并到`DataClassify`(/pages/dataClassify/components/DataClassify.js)父组件中。

###数据分类功能
1）通过`/tag/groupTree/save`接口新建一个数据分组。并且该分组不能在未分类目录下新建，当该接口body中的folderName修改后也会作为修改功能的接口。
2）通过`/tag/del`接口删除选中的数据分组。
3）选中一个数据分组后获取到当前分组的`id`并且调用`/tag/thingTree/detail`接口获取对应的数据。并将数据保存到redux的全局store中。最后通过`TableContainer`(/pages/dataClassify/containers/TableContainer.js)容器将数据传递给组件。完成表格数据的渲染。
4）表格中可以通过`/tag/moveThings`接口移动选中的点到目标数据分组。