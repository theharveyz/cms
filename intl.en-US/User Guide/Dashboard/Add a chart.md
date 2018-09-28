# Add a chart {#concept_lfq_rxv_tdb .concept}

CloudMonitor initializes the ECS monitor tray for your user dimension, if you need to view it, additional data can be set by adding charts.

**Note:** 

-   Cloud monitoring will initialize the ECS monitor tray for you by default. Shows CPU usage, network inflows, network inflows, system disks BPS, system Disks Iops, network in traffic, network out traffic 7 monitoring charts.

-    Limit on line chart view: 1 line chart can display up to 15 lines.

-   Area map display limit: 1 area map can show up to 10 blocks of area.

-   Tabular Data restrictions: displays the sorting results of up to 1000 pieces of data.

-   Thermal attempt display limit: A thermal attempt shows a maximum of 1000 color blocks.


## Interface parameter descriptions {#section_n5b_szy_5db .section}

-   Graph type
    -   Line diagram: displays monitoring data in a time series. Multiple metric items can be added.
    -   Area chart: It displays metric data by time sequence. Multiple metric items can be added.
    -   Topn table: real-time display of monitor data values sorted from large to small. Displays a maximum of 1000 entries in positive order or 1000 data in inverted order. For example, a table can display the CPU usage of all machines in an ECS group in a descending order. Only one monitoring item can be added.
    -   Heat map: It displays the real-time data of metric items. It is used to display distribution and comparison of real-time metric data of a specific metric item of multiple instances. For example, a heat map can display the distribution of the CPU usage of multiple instances. Only one metric item can be added.
    -   Pie chart: It displays the real-time data of metric items. Often used in the comparison of data. Only one monitoring item can be added.
-   Cloud product monitoring: the monitoring of each cloud product in ALI cloud.

-   Log monitoring: a monitor that is added by the user through log monitoring.
-   Monitoring item: the name of the monitoring metric that needs to be viewed, such as CPU usage, memory usage, and so on.
-   Statistical methods: the common statistical methods for monitoring items are maximum, minimum, and average. That is, how metric data is aggregated within the statistical period.
-   Resources: monitoring data for which resources need to be viewed by applying grouping or instance filtering.

## 操作步骤 {#section_fgw_ybz_5db .section}

1.  Log on to the[CloudMonitor console](https://cms.console.aliyun.com/#/cloud/ecs).
2.  Click **Dashboard**in the navigation pane.
3.  Click on the Add chart in the upper right corner of the monitor tray To Go To The add page.
4.  Select the display type for the chart.
5.  Select the cloud product you want to view and name the chart.
6.  Select the monitoring metrics and statistics you want to view.
    -   Select the monitoring item that you want to view.
    -   Select the way metric data is aggregated, for example, by maximum value, minimum value or average value.
7.  If you need to add a monitor item, click Add monitor item, repeat Step 6th.
8.  Click "Publish" to generate a chart in Monitor Dashboard.
9.  Drag the right border, bottom border or the bottom-right corner of the chart, to resize the chart \(if required\).

