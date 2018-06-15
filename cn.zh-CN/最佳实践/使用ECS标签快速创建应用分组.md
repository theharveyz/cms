# 使用ECS标签快速创建应用分组 {#concept_ikz_rwq_zdb .concept}

## 应用场景 {#section_kfd_ywq_zdb .section}

应用分组为您提供了方便的 ECS 实例分组管理功能，从而按业务线来管理报警规则、查看监控数据，可以迅速提升运维效率。

如果您的ECS实例已经通过ECS 标签分类管理，则在创建云监控的应用分组时，可以通过标签快速创建应用分组，不再需要重复对实例分组的过程。

## 实战案例 {#section_lfd_ywq_zdb .section}

您已经对ECS实例通过标签分类后，可以通过以下方式快速创建云监控应用分组。

1.  登录云监控控制台，进入[应用分组页面](https://cms.console.aliyun.com/#/groups/category=&region=&instanceIds=)。
2.  点击页面右上角的**创建组**按钮，进入创建分组页面。
3.  填写应用分组的名称。
4.  选择ECS所在的地域。（使用标签功能时，需要指定地域）
5.  点击**标签**，通过标签快速过滤出需要添加到应用分组中的ECS 实例。
6.  选择报警通知对象等其他信息后保存分组。
7.  ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6239/5219_zh-CN.png)


如果标签对应的ECS实例发生了变化，比如对新购买的机器打了标签，或者修改了机器原有的标签，可以进入应用分组的详情页面，点击**同步ECS标签**按钮，将为您同步这些修改。同步后，应用分组里只有创建分组时选择的标签对应的ECS实例。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6239/5220_zh-CN.png)

