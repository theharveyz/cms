# Add charts {#concept_lfq_rxv_tdb .concept}

By default, CloudMonitor creates an initialized ECS dashboard. If you want to view additional data of your ECS instances, you can add more charts or tables to the dashboard. This topic describes several common types of charts available in a dashboard in CloudMonitor.

**Note:** 

-   The default ECS dashboard provides the following seven charts: **CPU usage**, **network inbound bandwidth**, **network outbound bandwidth**, **disk BPS**, **disk IOPS**, **network inbound traffic**, and **network outbound traffic**.
-   Each line chart can display up to 10 lines.
-   Each area chart can display up to 10 areas.
-   Each table can display up to 1,000 sorted data records.
-   A heat map can display up to 1,000 color blocks.

## Chart parameters {#section_n5b_szy_5db .section}

-   Chart types
    -   Line chart: Displays monitoring data on a basis of time series. Multiple metrics can be added.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15447532441579_en-US.png)

    -   Area chart: Displays monitoring data on a basis of time series. Multiple metrics can be added.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15447532441583_en-US.png)

    -   Table: Displays real-time metric data in descending order. Each table displays up to 1,000 data records, which are either the first 1,000 records or the last 1,000 records. Only one metric can be added.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15447532441584_en-US.png)

    -   Heat map: Displays real-time metric data. Heat maps show the distribution and comparison of real-time data of a specific metric for multiple instances. Only one metric can be added.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15447532441585_en-US.png)

    -   Pie chart: Displays real-time metric data and can be used for data comparisons. Only one metric can be added.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15447532441586_en-US.png)

-   Dashboards: Monitors Alibaba Cloud products.
-   Log monitoring: Metrics added through log monitoring.
-   Custom: Metrics added through custom monitoring.
-   Metrics: Monitoring indicators, such as CPU usage and memory usage.
-   Statistical method: Means by which metric values are aggregated during a statistical period. Some common statistical methods are maximum, minimum, and average.
-   Resource: You can use an application group or instance to filter resources and view the monitoring data of these resources.

## Procedures {#section_fgw_ybz_5db .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Dashboard** \> **Custom Dashboard**.
3.  In the upper-right corner of the displayed page, click **Add View**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6140/15447532441588_en-US.png)

4.  Select a chart type.
5.  Choose from **Dashboards**, **Log Monitoring**, and **Custom** tab pages. In this example, click the **Dashboards** tab.
6.  Select the target Alibaba Cloud product and enter a name for the chart.
7.  Select the metrics and the statistical method.
    -   Select the metrics you want to view.
    -   Select the statistical method that the metric data is aggregated, such as maximum, minimum, or average.
8.  To add a metric, click **AddMetrics** and repeat the preceding steps.
9.  Click **Save**. The chart is displayed on the dashboard.
10. If you want to resize the chart, drag the right border, lower border, or lower-right corner of the chart.

