# 使用Dashboard {#concept_kfq_5nv_tdb .concept}

云监控的 Dashboard 功能提供用户自定义查看监控数据的功能。用户可以在一张监控大盘中跨产品、跨实例查看监控数据，将相同业务的不同产品实例集中展现。

## 查看监控大盘 {#section_fqv_sqv_tdb .section}

您可以通过查看监控大盘，来快速了解各个云产品的资源使用情况。

**说明：** 

-   云监控默认会为用户初始化 ECS 监控大盘，展示 ECS 部分监控数据。
-   用户可自定义添加其他云产品监控数据。

-   操作步骤
    1.  登录[云监控控制台。](https://cloudmonitor.console.aliyun.com)
    2.  点击导航栏中的 **Dashboard**。
    3.  在**当前监控大盘**的下拉菜单中选择需要的大盘。通过选择不同的大盘，可切换大盘视图。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6124/994_zh-CN.png)


## **创建监控大盘** {#section_fw2_htv_tdb .section}

当您的业务比较复杂，默认的 ECS 监控大盘无法满足您的监控可视化需求时，您可以创建新的监控大盘，自定义需要展示的图表。

-   操作步骤
    1.  登录[云监控控制台。](https://cloudmonitor.console.aliyun.com)
    2.  点击导航栏中的 **Dashboard**。
    3.  点击页面右上角的**创建监控大盘**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6124/996_zh-CN.png)

    4.  输入监控大盘名称，点击**创建**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6124/997_zh-CN.png)

    5.  页面会自动跳转到新创建的监控大盘页面，您就可以开始自由添加各种监控图表了。

## 添加图表 {#section_xzb_rwv_tdb .section}

当前支持用户在监控大盘上添加主要云产品指标和用户的业务监控指标。

当您的应用使用了多款云产品时，可将相关云产品的指标通过添加图表的形式添加在同一张监控大盘上，全局查看相关云产品的监控数据。

当您通过云监控API上报了自己的业务监控数据后，可以为该监控数据添加监控图表，进行可视化展示。

-   操作步骤
    -   [添加图表](../../../../intl.zh-CN/用户指南/Dashboard/添加图表.md#)。
    -   [添加日志监控](../../../../intl.zh-CN/用户指南/Dashboard/添加日志监控.md#)。

## 删除监控大盘 {#section_lw1_z1w_tdb .section}

**说明：** 

-   删除监控大盘时，会关联删除页面上设置的所有监控图表。
-   删除监控大盘后，监控大盘相关数据无法恢复。
-   进行监控大盘删除需要谨慎。

-   操作步骤
    1.  登录[云监控控制台。](https://cloudmonitor.console.aliyun.com)
    2.  点击导航栏中的 **Dashboard**。
    3.  点击页面右上角的**删除当前大盘**，删除监控大盘。

## 修改监控大盘名称 {#section_nn5_ydw_tdb .section}

-   操作步骤
    1.  登录[云监控控制台。](https://cloudmonitor.console.aliyun.com)
    2.  点击导航栏中的 **Dashboard**。
    3.  鼠标悬浮在监控大盘名称上，右侧会出现**修改名称**选项。
    4.  ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6124/1019_zh-CN.png)

