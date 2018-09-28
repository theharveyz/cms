# High performance time series database hitsdb {#concept_wnp_ryv_ydb .concept}

CloudMonitor monitors multiple monitoring metrics, such as HiTSDB disk usage, the number of timelines, and the number of time points. It helps you monitor the network use of NAT Gateway and allows you to set alarm rules for the monitoring metrics. When you purchase hitsdb, cloud monitoring automatically collects data for the hitsdb monitor.

## Monitoring service {#section_zmy_w1w_ydb .section}

-   Monitoring items

    |Monitoring items|Dimensions|Unit |Minimum monitor Granularity|
    |:---------------|:---------|:----|:--------------------------|
    |Disk usage| User and instance|%|20 seconds|
    |Timeline quantity| User and instance|Count|20 seconds|
    |Point in time the growth rate| User and instance|Count/Second|20 seconds|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.
    -   You can view the monitoring data for up to 14 consecutive days.

-   View metric data
    1.  Log on to the [CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  2. Go to the HiTSDB instance list under Cloud Service Monitoring.
    3.  3. Click an instance name or click Monitoring Chart in the Action column to access the instance monitoring details page and view various metrics.
    4.  Click a "Time Range" shortcut on the top of the page or use the specific selection function. Up to 14 consecutive days of metric data can be viewed.
    5.  Click the zoom button in the upper-right corner of the monitor MAP to view the monitor larger image.

## Alarm service {#section_rtd_ybw_ydb .section}

-   Description
    -   Monitor: the monitoring indicator provided by hitsdb's service.
    -   Statistical Cycle: the alarm system checks if your monitoring data exceeds the alarm threshold for this cycle. For example, if the statistical cycle of the alarm rule for memory usage is set to one minute, the system checks whether the memory usage has exceeded the threshold value every other minute.
    -   Consecutive times: an alarm is triggered when the value of the monitoring metrics continuously exceeds the threshold value for the set consecutive cycles.

-   Set an alarm rule
    1.  Log on to the [CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  Go to the HiTSDB instance list under Cloud Service Monitoring.
    3.  Click the Instance name or the monitor chart in the operation to go To the instance monitoring details page.
    4.  Click the Bell button in the upper-right corner of the monitoring chart or New Alarm Rule in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

-   Set batch alarm rules
    1.  Log on to the [CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  Go to the HiTSDB instance list under Cloud Service Monitoring.
    3.  When the instance list page selects the desired instance, click set alarm rule below the page, you can add alarm rules in bulk.

