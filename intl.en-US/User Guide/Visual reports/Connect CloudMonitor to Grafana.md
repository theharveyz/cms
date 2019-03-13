# Connect CloudMonitor to Grafana {#concept_x5d_cmk_zgb .concept}

This topic describes how to import monitoring data from CloudMonitor to Grafana for data visualization.

## Background information {#section_nyc_jmk_zgb .section}

CloudMonitor stores both custom monitoring data and the system monitoring data of the core products of Alibaba Cloud. In addition to using the built-in charts, graphs, and dashboards provided by CloudMonitor to display the data, you can also use the third-party tool Grafana for further data visualization options. To use Grafana, complete the instructions in the following sections.

## Preparations {#section_lxf_nmk_zgb .section}

1.  **Download and install Grafana.**

    You can install Grafana on CentOS by using the following two commands:

    Command 1:

    `yum install https://s3-us-west-2.amazonaws.com/grafana-releases/release/grafana-5.3.0-1.x86_64.rpm`

    Command 2:

    ```
    wget https://s3-us-west-2.amazonaws.com/grafana-releases/release/grafana-5.3.0-1.x86_64.rpm 
    sudo yum localinstall grafana-5.3.0-1.x86_64.rpm 
    ```

    For more information, see [Officially recommended installation methods](http://docs.grafana.org/installation/?spm=a2c63.p38356.a3.23.7f634246zuXN5l).

2.  **Start Grafana.**

    Run the service grafana-server start command to start Grafana.


## Procedure {#section_ozw_pll_zgb .section}

1.  **Install the CloudMonitor data source agent.**

    Confirm the directory in which the Grafana agent is to be installed, install the agent, and then restart grafana-server.

    **Note:** For example, the agent is installed in the `/var/lib/grafana/plugins/` directory on CentOS.

    On CentOS, the installation command is as follows:

    ```
    cd /var/lib/grafana/plugins/
    git clone https://github.com/aliyun/aliyun-cms-grafana.git 
    service grafana-server restart
    ```

    Alternatively, you can download `aliyun-cms-grafana.zip`, decompress it, upload it to the plugins directory of the Grafana on the server, and then restart grafana-server.

    **Note:** You cannot set alarms for monitoring data in the current version of Grafana.

2.  **Configure the CloudMonitor data source agent.**

    After Grafana is successfully installed, its default access port number is 3000. The user name and password are both set as admin.

    1.  On the Grafana homepage, choose **Configuration** \> **Data Sources**.
    2.  On the Data Sources page, click **Add data source** in the upper-right corner.
    3.  Set parameters for the data source.

        |Configuration item|Description|
        |------------------|-----------|
        |Data source|Name: Enter a name for the data source.Type: Select **CMS Grafana Service**.

|
        |HTTP|URL: `http://metrics.cn-shanghai.aliyuncs.com` is used as an example. For more information, see [Endpoints](../../../../../reseller.en-US/API Reference/Call API operations.md#section_xf3_lbv_zdb).Access: Retain the default option.

|
        |Auth|Retain the default settings.|
        |CloudMonitor service details|Enter an AccessKey \(AK\) of an account that has the appropriate read and write permissions.The AK of your RAM user account is recommended.

|

        The following figure shows the configuration items.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155244163439937_en-US.png)

    4.  Click **Save & Test**.
3.  **Create a dashboard.**
    1.  On the Grafana homepage, choose **Dashboards** \> **Manage**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155244163439940_en-US.png)

    2.  Create a dashboard by using any of the following conditions:
        -   Click **+Dashboard**.
        -   Click **+Folder** to create a folder, and then click **+Dashboard**.
        -   Click **+Import** to import a dashboard.
4.  **Configure a graph.**
    1.  Choose **New Panel** \> **Add** \> **Graph** and click **Panel Title**. In the displayed dialog box, click **Edit**.
    2.  In the **Metrics** area, set **datasource** to **cms-grafana** and set Project, Metric, Period, Y-column, and X-column, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155244163439962_en-US.png)

        For more information, see [QueryMetricList](../../../../../reseller.en-US/API Reference/Query monitoring data/QueryMetricList.md#).

        The following describes some of the other parameters in detail:

        Group: Indicates the CloudMonitor application group to which your Alibaba Cloud account belongs.

        Dimensions: Indicates the latest set of the instance monitoring data that relates to the configuration item of Project and Metric. If you set this parameter to Group, monitoring data for instances in this group will be displayed.

        Y-column: You can select more than one option.

        X-column: Set to timestamp.

        Y-column describe: Indicates what is each option displayed in Y-column.

        For more information about the graph, click [here](http://docs.grafana.org/features/panels/graph/).

        **Note:** 

        -   You can set all the parameters manually by following the instructions in [QueryMetricList](../../../../../reseller.en-US/API Reference/Query monitoring data/QueryMetricList.md#).
        -   You can enter null for a parameter to cancel it. This can be done for any of the parameters.
        -   You can refresh the page to view the full list or enter the InstanceID in the search bar in the case of incomplete information relating to the instances \(previously set as dimensions\).
        For custom monitoring data, you need to manually enter the following parameters:

        -   Project: Enter acs\_customMetric and your Alibaba Cloud account ID.
        -   Metric: Indicates the metricName for reporting monitoring data.
        -   Period: Indicates the period of time for reporting monitoring data.
        -   Group: Indicates the group ID corresponding to Metric.
        -   Dimensions: Indicates the dimension for reporting monitoring data. Currently, no drop-down list is available that can provide multiple options. Moreover, only one dimension can be selected at a time. Selecting more than one dimension is currently not supported. Therefore, if you enter multiple dimensions, only the first one will be valid by default.

            **Note:** If the dimensions provided by the CloudMonitor console are found in the following format `env: public, step: 5-ReadFromAlertOnline`, then you will need to replace the commas \(,\) with ampersands \(&\).

        -   Y-column: Includes Average, Maximum, Minimum, Sum, SampleCount, P10, P20, P99, along with other options for reporting monitoring data.
        -   X-column: Set to timestamp.
        The following figure shows an example visualization for custom monitoring data.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155244163439967_en-US.png)

5.  **Configure the Singlestat panel.**
    1.  Choose **New Panel** \> **Add** \> **Singlestat** and click **Panel Title**. In the displayed dialog box, click **Edit**.
    2.  In the **Metric** area, set parameters by following the instructions provided in step 4.

        The following figure shows an example of a configured Singlestat panel.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155244163439968_en-US.png)

        For more information, see [Singlestat](http://docs.grafana.org/features/panels/graph/).

6.  **View monitoring results.**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155244163439971_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/134811/155244163439973_en-US.png)


