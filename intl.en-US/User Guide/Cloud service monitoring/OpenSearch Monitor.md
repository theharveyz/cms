# OpenSearch Monitor {#concept_c3s_vbj_zdb .concept}

Cloud Monitoring monitors the storage capacity of open searches, the total number of documents, queries QPS, and other monitoring items, helps users monitor the usage of open search services and enables users to set alarm rules on monitoring items. After you buy the ExpressConnect service, CloudMonitor will automatically collect data on the metrics listed above.

## Monitoring Services {#section_lqb_ybj_zdb .section}

-   Monitoring items

    |Monitoring items|Dimensions|Unit|Minimum monitor Granularity|
    |:---------------|:---------|:---|:--------------------------|
    |Storage Capacity|APP dimension|Byte|10 minutes.|
    |Storage capacity usage|APP dimension|%|10 minutes.|
    |Total number of documents|APP dimension|Items|10 minutes.|
    |Querying QPS|APP dimension|Count/second|20 seconds|
    |Query flow limit QPS|APP dimension|Count/second|20 seconds|
    |Time-consuming Query|APP dimension|MS|20 seconds|
    |Calculate Resources|APP dimension|Lcu|20 seconds|
    |Calculate resource usage|APP dimension|%|20 seconds|
    |Calculation of consumption by single query|APP dimension|LCU|20 seconds|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.
    -   Users can view monitoring data for up to 14 days in a row.

-   Viewing Monitoring Data
    1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Enter the list of instances of the open search that the cloud service monitors.
    3.  Click the Instance name or the monitor chart in the operation to go To the instance monitoring details page to view the metrics.
    4.  Click the time range on the top of the page to quickly select a button or select an exact function, the maximum monitoring data allows you to view the monitored data for 14 consecutive days.
    5.  Click the zoom button in the upper-right corner of the monitor MAP to view the monitor larger image.

## Alarm service {#section_ihp_kcj_zdb .section}

-   Parameter descriptions
    -   Monitoring item: that is, the monitoring indicator provided by the open search service.
    -   Statistical Cycle: the alarm system checks if your monitoring data exceeds the alarm threshold for this cycle. For example, to set a memory usage alarm rule, the statistics cycle is 1 minute, an interval of 1 minute checks if memory usage exceeds the threshold.
    -   Continuous number of times: refers to the continuous number of statistical cycle monitoring items that continue to exceed the threshold value to trigger the alarm.

-   Set single alarm rule
    1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Enter the list of instances of the open search that the cloud service monitors.
    3.  Click the Instance name or the monitor chart in the operation to go To the instance monitoring details page.
    4.  Click the bell button in the upper right corner of the monitor chart or the new alarm rule in the upper right corner of the page, alarm rules can be set for monitoring items corresponding to this instance.

-   Set up bulk alarm rules
    1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Enter the list of open search instances that the cloud service monitors.
    3.  Select the appropriate instance on the instance list page. Then, click "Set Alert Policies" at the bottom of the page to add multiple alert policies.

