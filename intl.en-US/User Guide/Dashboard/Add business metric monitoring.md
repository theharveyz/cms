# Add business metric monitoring {#concept_fdz_b1w_tdb .concept}

**Add Business Metric Monitoring** function can be used when you want to upgrade from custom monitoring to business metric monitoring.

**Note:** 

-    Limit on line chart view: 1 line chart can display up to 15 lines.
-   Limit on area chart view: 1 area chart may display up to 15 areas.
-   Table data limit: the ordered results can be displayed for a maximum of 1,000 data entries.
-   Thermal attempt display limit: A thermal attempt shows a maximum of 1000 color blocks.

## Interface parameter descriptions {#section_ud2_sn2_vdb .section}

-   Chart title: it is the title of the metric chart. It displays the name of a metric, by default.
-   Metric \(required\): the name of metric for which data is submitted via APIs/SDKs
-   Filter \(optional\): equivalent to the ‘Where’ statement in SQL. If the filtering criteria are left blank, it means all the data will be processed.
    -   Line chart: this chart displays metric data by time sequence.
    -   Area chart: this chart displays metric data by time sequence.
    -   Heat map: this map displays the real-time metric data. It is usually used to display distribution and comparison of metric data that is grouped by dimension and aggregated.
    -   Pie chart: this chart displays the real-time metric data,  Often used in the comparison of data.
    -   Topn table: displays the real-time metric data.

## 操作步骤 {#section_swn_ymf_vdb .section}

1.  Log on to the[CloudMonitor console](https://cms.console.aliyun.com/#/cloud/ecs).
2.  Click the "Dashboard" option in the left menu to access the "Dashboard" page.
3.  Click Add log monitor in the upper right corner of the monitor tray To Go To The add page.
4.  Define the Chart name, Metric name and Chart type.
5.  Define the Chart name, Metric name and Chart type.
6.  Click "Publish" to generate a chart in Monitor Dashboard.
7.  Drag the right border, bottom border or the bottom-right corner of the chart, to resize the chart \(if required\).

