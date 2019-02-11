# Add charts {#concept_lfq_rxv_tdb .concept}

This topic describes several types of charts common in the CloudMonitor dashboard and how to add a chart.

## Scenarios {#section_n5v_5zq_pgb .section}

By default, CloudMonitor creates an initialized ECS dashboard. You can add more charts and tables to the dashboard to view even more data related to your ECS instances.

In the case that the ECS dashboard does not meet your monitoring needs, we recommend that you create an additional dashboard to which you can add charts to display custom monitoring data.

## Before you begin {#section_d4k_fbr_pgb .section}

Before you can add a chart, you need to create a dashboard.

## Chart types {#section_n5b_szy_5db .section}

-   Line chart: Displays monitoring data on a basis of time series. Multiple metrics can be added.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15498786431579_en-US.png)

-   Area chart: Displays monitoring data on a basis of time series. Multiple metrics can be added.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15498786431583_en-US.png)

-   Table: Displays real-time metric data in descending order. Each table displays up to 1,000 data records, which are either the first 1,000 records or the last 1,000 records. Only one metric can be added.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15498786441584_en-US.png)

-   Heat map: Displays real-time metric data. Heat maps show the distribution and comparison of real-time data of a specific metric for multiple instances. Only one metric can be added.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15498786441585_en-US.png)

-   Pie chart: Displays real-time metric data and can be used for data comparisons. Only one metric can be added.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15498786441586_en-US.png)


## Add a chart {#section_fgw_ybz_5db .section}

**Note:** 

-   The default ECS dashboard provides the following seven charts: **CPU Usage**, **Network Inbound Bandwidth**, **Network Outbound Bandwidth**, **Disk BPS**, **Disk IOPS**, **Network Inbound Traffic**, and **Network Outbound Traffic**.
-   Up to 20 charts can be added in a dashboard.
-   Each line chart can display up to 10 lines.
-   Each area chart can display up to 10 areas.
-   Each table can display up to 1,000 sorted data records.
-   A heat map can display up to 1,000 color blocks.

Procedure

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Dashboard** \> **Custom Dashboard**.
3.  In the upper-right corner of the displayed page, click **Add View**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15498786441588_en-US.png)

4.  Select a chart type.
5.  Choose from **Dashboards**, **Log Monitoring**, and **Custom** tab pages. In this example, click the **Dashboards** tab.
6.  Select the target Alibaba Cloud product and enter a name for the chart.
7.  Select the metric, the statistical method, and the resources.
    -   Select the metric you want to view.
    -   Select the statistical method by which the metric data is aggregated. You can choose maximum, minimum, or average.
    -   Select the resources that you want to monitor.
8.  To add a metric, click **AddMetrics** and repeat the preceding steps.
9.  Click **Save**. The chart is displayed on the dashboard.
10. If you want to resize the chart, drag the right border, lower border, or lower-right corner of the chart.

Metrics

-   **Dashboards**: Displays the monitoring data of Alibaba Cloud products.
-   **Log monitoring**: metrics added through log monitoring.
-   **Custom**: metrics added through custom monitoring.
-   **Metrics**: monitoring indicators, such as CPU usage and memory usage.
-   **Statistical method**: means by which metric values are aggregated during a statistical period. Some common statistical methods are maximum, minimum, and average.
-   **Resource**: You can use an application group or instance to filter resources and view the monitoring data of these resources.

