# 对接Grafana {#concept_x5d_cmk_zgb .concept}

本文为您介绍如何将云监控的数据添加到Grafana中进行展示。

## 背景信息 {#section_nyc_jmk_zgb .section}

云监控为云上用户提供常用云产品的监控数据和用户自定义上报的监控数据。在可视化展示层面，除了在云监控控制台查看监控图表外，您还可以将云监控的数据添加到Grafana中进行展示。

## 对接Grafana的装备工作 {#section_lxf_nmk_zgb .section}

1.  **下载安装Grafana**

    本文以CentOS为例，介绍Grafana的两种安装方式：

    安装方式一：

    `yum install https://s3-us-west-2.amazonaws.com/grafana-releases/release/grafana-5.3.0-1.x86_64.rpm`

    安装方式二：

    ```
    wget https://s3-us-west-2.amazonaws.com/grafana-releases/release/grafana-5.3.0-1.x86_64.rpm 
    sudo yum localinstall grafana-5.3.0-1.x86_64.rpm 
    ```

    Grafana的其他详细安装步骤请参见[Grafana官方文档](http://docs.grafana.org/installation/?spm=a2c63.p38356.a3.23.7f634246zuXN5l)。

2.  **启动Grafana**

    下载载安装完成后，输入命令 service grafana-server start 启动服务。


## 对接Grafana的实施步骤 {#section_ozw_pll_zgb .section}

1.  **安装云监控数据源服务插件**

    请确认Grafana的插件目录位置。例如：在CentOS的插件目录为`/var/lib/grafana/plugins/`，安装插件，重启grafana-server。

    CentOS安装命令如下：

    ```
    cd /var/lib/grafana/plugins/
    git clone https://github.com/aliyun/aliyun-cms-grafana.git 
    service grafana-server restart
    ```

    您也可以下载aliyun-cms-grafana.zip插件解压后，上传服务器的Grafana的plugins目录下，重启grafana-server即可。

    **说明：** 此插件版本目前不支持对监控数据设置报警。

2.  **配置云监控数据源插件**

    Grafana成功部署后，默认访问端口3000，用户名：admin、密码：admin。

    1.  成功登录后，进入Grafana的主页面，单击左上方的**Configuration**，在弹出的列表中选**Data Sources**。
    2.  成功进入Data Sources页面后，单击右上方的**Add data source**，添加新的数据源。
    3.  填写云监控数据源的配置项。

        |配置项|配置内容|
        |---|----|
        |datasource|Name表示名称，请自定义一个新数据源的名称。Type请选择**CMS Grafana Service**。|
        |Http| URL样例：`http://metrics.cn-shanghai.aliyuncs.com`，不同域选择请参考[云监控接入地址](../../../../../intl.zh-CN/API参考/调用API.md#section_xf3_lbv_zdb)。

 Access默认即可。

 |
        |Auth|采用默认配置即可。|
        |cloudmonitor service details|分别填写具备读取权限的AK信息。建议AK使用子帐号的AK。|

        配置示例如下图：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155177836139937_zh-CN.png)

    4.  配置完成后，单击**Save &Test**即可完成添加DataSource。
3.  **创建Dashboard**
    1.  单击左上方的**Dashboards**，在弹出的列表中选**Manage**，进入Manage页面。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155177836139940_zh-CN.png)

    2.  单击**+Dashboard**创建Dashboard。您可以选择创建一个**Folder**后，再创建**Dashboard**，您也可以导入其他Dashboard。
4.  **配置Graph图表**
    1.  创建Dashboard后，在**New Panel**的**Add**下选择**Graph**图表，单击**Pannel Title**，在弹出的窗口中单击**Edit**。
    2.  在**Metrics**配置中，选择**datasource**为**cms-grafana**，输入Project、Metric、period、Y轴和X轴等。如下图所示：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155177836139962_zh-CN.png)

    3.  Project、Metric、Period等参数详情，请参见[QueryMetricList](../../../../../intl.zh-CN/API参考/查询云产品监控数据/QueryMetricList.md#)；

         Group：云账户所在云监控的应用分组；

        Dimensions：Project与Metric所在监控项最新监控数据的实例集合，若选Group，则为该Group下的实例；

        Y轴：可支持多选；

        X轴：timestamp；

         Y-column describe：对Y-column的区分描述。

        如需了解更多Graph信息，[请单击此处](http://docs.grafana.org/features/panels/graph/)。

        **说明：** 

        -   所有参数均可按[QueryMetricList](../../../../../intl.zh-CN/API参考/查询云产品监控数据/QueryMetricList.md#)要求手动输入；
        -   所有已选择\(已输入\)参数均可输入null取消；
        -   若对应场景下Dimensions提示的实例信息不全，可刷新或按样例手动输入InstanceId的值即可。
        自定义监控：

        自定义监控的部分参数信息需手动输入，参数说明：

        -   Project：acs\_customMetric\_+ 云账号ID；
        -   Metric：上报监控数据的metricName；
        -   Period：上报监控数据时的Period；
        -   Group：上报监控数据时的Metric对应的分组ID；
        -   Dimensions：上报监控数据时的Dimension，暂不支持下拉选择，只支持输入单个Dimension，若输入多个，默认选第一个；

            **说明：** 若在云监控控制台的dimensions格式为env: public, step: 5-ReadFromAlertOnline样例，请用'&'替换示例中的','后拼接输入。

        -   Y-column：上报监控数据时的Average、Maximum、Minimum、Sum、SampleCount、P10、P20、P99等；
        -   X-column：Timestamp。
        示例如下图所示：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155177836239967_zh-CN.png)

5.  **配置Singlestat面板**
    1.  在**New Panel**的**Add**下选择**Singlestat**，单击**Pannel Title**，在弹出的窗口中单击**Edit**；
    2.  **Metric**配置可参考前面的配置Graph图表。

        示例如下图所示：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155177836239968_zh-CN.png)

        如您需了解更多[Singlestat](http://docs.grafana.org/features/panels/singlestat/)信息，[请单击此处](http://docs.grafana.org/features/panels/graph/)。

6.  **查看结果**

    完成以上步骤的配置后，即可通过Grafana创建阿里云监控Dashboard并查看监控结果。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155177836239971_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155177836239973_zh-CN.png)


