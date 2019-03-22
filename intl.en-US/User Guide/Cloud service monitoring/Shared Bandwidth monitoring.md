# Shared Bandwidth monitoring {#concept_tr5_mq5_ydb .concept}

By monitoring multiple metrics from Shared Bandwidth, such as inbound and outbound bandwidth, CloudMonitor helps you to monitor the usage of the bandwidth. CloudMonitor automatically begins to collect data for the metrics after you create a cluster. You can also set alarm rules for clusters through CloudMonitor so that you can be notified in the case of any exceptions.

## Monitoring Services {#section_gdc_4q5_ydb .section}

-   Monitoring items

    |Monitoring items|Dimensions|Unit|Minimum monitor Granularity|
    |:---------------|:---------|:---|:--------------------------|
    |Bandwidth packet network inflows bandwidth|User dimension, instance dimension|Bits/s|1 minute|
    |Bandwidth packet network outgoing bandwidth|User dimension, instance dimension|Bits/s|1 minute|
    |Bandwidth packets network inflows packets|User dimension, instance dimension|packages/s|1 minute|
    |Bandwidth packet network flow Packet|User dimension, instance dimension|packages/s|1 minute|
    |Bandwidth packet network outgoing bandwidth usage|User dimension, instance dimension|%|1 minute|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.

    -   Users can view monitoring data for up to 7 days in a row.


-   Viewing Monitoring Data
    1.  Log on to the [CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  Enter the list of instances of shared bandwidth that the cloud service monitors.
    3.  Click the Instance name or the monitor chart in the operation to go To the instance monitoring details page to view the metrics.
    4.  Click the time range on the top of the page to quickly select a button or select an exact function, monitoring data supports viewing monitoring data for seven consecutive days.
    5.  Click the zoom button in the upper-right corner of the monitor MAP to view the monitor larger image.

## Alarm service {#section_tns_3t5_ydb .section}

-   Parameter descriptions
    -   Monitor: that is, the monitoring metrics provided by services that share bandwidth.

    -   Statistical Cycle: the alarm system checks if your monitoring data exceeds the alarm threshold for this cycle. For example, to set a memory usage alarm rule, the statistics cycle is 1 minute, an interval of 1 minute checks if memory usage exceeds the threshold.

    -   Continuous number of times: refers to the continuous number of statistical cycle monitoring items that continue to exceed the threshold value to trigger the alarm.


-   Set single alarm rule
    1.  Log on to the [CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  Enter the list of instances of shared bandwidth that the cloud service monitors.
    3.  Click the Instance name or the monitor chart in the operation to go To the instance monitoring details page.
    4.  Click the bell button in the upper right corner of the monitor chart or the new alarm rule in the upper right corner of the page, alarm rules can be set for monitoring items corresponding to this instance.

-   Set up bulk alarm rules
    1.  Log on to the [CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  Enter the list of shared bandwidth instances that the cloud service monitors.
    3.  When the instance list page selects the desired instance, click set alarm rule below the page, you can add alarm rules in bulk.

