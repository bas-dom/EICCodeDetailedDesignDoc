###数据报警页面代码流程设计
进入数据报警页面之后通过`/alarm/list`接口获取数据并存放在redux的全局store中，通过`TableContainer`（/pages/alarmManage/container/TableContainer.js）的容器组件将数据连接到展示组件中并显示。

###数据报警页面代码功能
1）新建一个规则点时，现根据`/tag/getThingTree`获取点位信息，并且在选择后会将当前点位保存到全局store中，然后填写规则，报警通知人的选择也会先存储到全局store中。最后通过`addRulePoint()`方法调用接口`/alarm/add`并且从redux中获取对应数据作为请求body完成规则点位的新建。

2) 修改规则点位时所用接口和代码逻辑同(1)

3）报警规则的启用和禁用使用`/alarm/add`接口

4）删除规则使用`/alarm/delete`接口完成删除