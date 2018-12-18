# 如何创建容器服务Kubernetes Pod报警 {#concept_hr3_hhx_bgb .concept}

云监控新增容器服务Kubernetes版报警功能，本文将为您介绍如何对Kubernetes的Pod及一组Pod的聚合指标设置报警规则。

## 创建Kubernetes的报警模板 {#section_ehp_vqx_bgb .section}

1.  登录[云监控控制台](https://cloudmonitor.console.aliyun.com)。
2.  单击左侧导航栏中**报警服务**下的**报警模板**，进入**报警模板**页面。
3.  单击右上角的**创建报警模板**按钮，进入创建报警模板页面。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78698/154510168134067_zh-CN.png)

4.  配置模板信息：产品名称选择容器服务-Kubernetes版，并配置相关监控项。
5.  单击**添加**按钮，完成创建报警模板。

## 将模板应用在Kubernetes分组上 {#section_n4k_2rx_bgb .section}

1.  登录[云监控控制台](https://cloudmonitor.console.aliyun.com)。
2.  单击左侧导航栏中**报警服务**下的**报警模板**，进入**报警模板**页面。
3.  选择上面创建的Kubernetes模板，单击操作栏中的**应用到分组**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78698/154510168134071_zh-CN.png)

4.  选择需要创建报警规则的分组，单击**确认**按钮即可。

## 修改接收报警通知的联系人组（可选） {#section_ezq_fyy_bgb .section}

Kubernetes应用分组的报警通知会默认发送给“云账号报警联系人”分组，如果您所有的Kubernetes应用报警通知只需要发送给同一个联系人组，则直接修改“云账号联系人”分组中的接收人即可。

**直接修改联系人组操作步骤：**

1.  登录[云监控控制台](https://cloudmonitor.console.aliyun.com)。
2.  单击左侧导航栏中**报警服务**下的**报警联系人**，进入**报警联系人**页面。
3.  单击**报警联系组**页签，切换到报警联系组页面。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78698/154510168134072_zh-CN.png)

4.  单击修改图标，进入编辑组页面，修改联系人后，单击**确定**按钮即可。

如果您不同的Kubernetes应用的报警通知，需要发送给不同联系人组，则需要进入应用分组，修改应用分组关联的报警联系人组。

**通过应用分组修改关联联系人组操作步骤：**

1.  登录[云监控控制台](https://cloudmonitor.console.aliyun.com)。
2.  单击左侧导航栏中**应用分组**，进入**应用分组**页面。
3.  通过搜索找到Kubernetes的分组，单击分组名称，进入分组详情页。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78698/154510168134079_zh-CN.png)
4.  单击修改图标，修改联系人组后，单击**确定**即可，该分组中的所有报警通知，将发送给新的报警联系人组。

如果您需要修改多个Kubernetes应用分组的联系人组，可以通过OpenAPI工具进行修改。

**通过OpenAPI工具修改联系人组操作步骤：**

1.  登录[OpenAPI Explore](https://api.aliyun.com)。
2.  在左侧云产品列表中，单击**云监控**，在搜索框中输入UpdateMyGroups，在搜索结果中单击该API，进入修改应用分组的API调用页面。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78698/154510168134114_zh-CN.png)
3.  在GroupId输入框中，输入需要修改的分组ID。
4.  在ContactGroups输入框中，输入需要接收报警通知的联系人组。
5.  单击**发起调用**按钮即可。

