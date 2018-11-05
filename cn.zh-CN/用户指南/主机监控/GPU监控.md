# GPU监控 {#concept_ysn_byq_32b .concept}

GPU监控数据可以通过两种方式查询：云监控控制台和API。

## 通过云监控控制台查询GPU监控数据 {#section_hcc_4mr_32b .section}

在您购买ECS的GPU计算型实例后，只需安装[GPU驱动](../../../../intl.zh-CN/用户指南/实例/创建实例/创建GPU计算型实例.md#)和云监控插件的1.2.28版本，即可查看GPU相关监控图表、配置监控图表或设置报警规则。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15414093876845_zh-CN.png)

**查看监控图表**

若要查看GPU相关监控图表，执行如下步骤：

1.  登录[云监控控制台](https://cloudmonitor.console.aliyun.com)。
2.  点击导航栏中的**主机监控**。
3.  在**GPU监控**页面查询GPU相关监控图表，如下图所示。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15414093876696_zh-CN.png)

**配置监控图表**

1.  登录[云监控控制台](https://cloudmonitor.console.aliyun.com)。
2.  点击导航栏中的**Dashboard**。
3.  在**Dashboard**页面单击**创建监控大盘**。
4.  在弹出的对话框中，输入新建监控大盘名称后，单击**创建**。
5.  在刷新的页面中，单击**添加图表**。
6.  在**添加图表**页面，选择您需要的图表类型，然后选择**监控项**，如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15414093876698_zh-CN.png)

7.  在下拉菜单中选择您需要的监控指标，此处以实例维度GPU温度为例，如下图所示。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15414093876699_zh-CN.png)

**设置报警规则**

为新增GPU监控指标添加报警规则的方式同为ECS的其他指标添加相同。推荐通过创建模板后将模板应用于分组的方式批量添加GPU报警规则。详情参见[最佳实践报警模板](../../../../intl.zh-CN/最佳实践/报警模板最佳实践.md#)。

**监控指标说明**

GPU相关监控指标提供如下三个维度的数据：GPU、实例、分组。

**GPU维度监控指标**

GPU维度的监控指标采集每个GPU层面的监控数据。GPU维度的监控指标如下表所示。

|MetricName|单位|名称|dimensions|
|:---------|:-|:-|:---------|
|gpu\_memory\_freespace|Byte|GPU维度显存空闲量|instanceId,gpuId|
|gpu\_memory\_totalspace|Byte|GPU维度显存总量|instanceId,gpuId|
|gpu\_memory\_usedspace|Byte|GPU维度显存使用量|instanceId,gpuId|
|gpu\_gpu\_usedutilization|%|GPU维度GPU使用率|instanceId,gpuId|
|gpu\_encoder\_utilization|%|GPU维度编码器使用率|instanceId,gpuId|
|gpu\_decoder\_utilization|%|GPU维度解码器使用率|instanceId,gpuId|
|gpu\_gpu\_temperature|℃|GPU维度GPU温度|instanceId,gpuId|
|gpu\_power\_readings\_power\_draw|W|GPU维度GPU功率|instanceId,gpuId|
|gpu\_memory\_freeutilization|%|GPU维度显存空闲率|instanceId,gpuId|
|gpu\_memory\_useutilization|%|GPU维度显存使用率|instanceId,gpuId|

**实例维度监控指标**

实例维度监控指标对单个ECS实例上的多个GPU监控数据做最大值、最小值、平均值的聚合，便于查询实例层面的整体使用情况。

|MetricName|单位|名称|dimensions|
|:---------|:-|:-|:---------|
|instance\_gpu\_decoder\_utilization|%|实例维度GPU解码器使用率|instanceId|
|instance\_gpu\_encoder\_utilization|%|实例维度GPU编码器使用率|instanceId|
|instance\_gpu\_gpu\_temperature|℃|实例维度GPU温度|instanceId|
|instance\_gpu\_gpu\_usedutilization|%|实例维度GPU使用率|instanceId|
|instance\_gpu\_memory\_freespace|Byte|实例维度GPU显存空闲量|instanceId|
|instance\_gpu\_memory\_freeutilization|%|实例维度GPU显存空闲率|instanceId|
|instance\_gpu\_memory\_totalspace|Byte|实例维度GPU显存总量|instanceId|
|instance\_gpu\_memory\_usedspace|Byte|实例维度GPU显存使用量|instanceId|
|instance\_gpu\_memory\_usedutilization|%|实例维度GPU显存使用率|instanceId|
|instance\_gpu\_power\_readings\_power\_draw|W|实例维度GPU功率|instanceId|

**分组维度监控指标**

分组维度监控指标对单个应用分组里的多个ECS 实例的监控数据做最大值、最小值、平均值的聚合，便于查询集群层面的整体使用情况。

|MetricName|单位|名称|dimensions|
|:---------|:-|:-|:---------|
|group\_gpu\_decoder\_utilization|%|分组维度GPU解码器使用率|groupId|
|group\_gpu\_encoder\_utilization|%|分组维度GPU编码器使用率|groupId|
|group\_gpu\_gpu\_temperature|℃|分组维度GPU温度|groupId|
|group\_gpu\_gpu\_usedutilization|%|分组维度GPU使用率|groupId|
|group\_gpu\_memory\_freespace|Byte|分组维度GPU显存空闲量|groupId|
|group\_gpu\_memory\_freeutilization|%|分组维度GPU显存空闲率|groupId|
|group\_gpu\_memory\_totalspace|Byte|分组维度GPU显存总量|groupId|
|group\_gpu\_memory\_usedspace|Byte|分组维度GPU显存使用量|groupId|
|group\_gpu\_memory\_usedutilization|%|分组维度GPU显存使用率|groupId|
|group\_gpu\_power\_readings\_power\_draw|W|分组维度GPU功率|groupId|

## 通过API查询GPU监控数据 {#section_iq4_gnr_32b .section}

-   详见[QueryMetricList](../../../../intl.zh-CN/API参考/QueryMetricList.md#)。
-   参数说明：Project参数的取值为acs\_ecs\_dashboard。Metric及Dimensions的取值，请参考上述表格中的GPU指标。

