# High performance time series database hitsdb {#concept_wnp_ryv_ydb .concept}

Cloud Monitoring monitors hitsdb's disk usage, timeline count, point-in-time increment, and so on, helps users monitor hitsdb usage and enables users to set alarm rules on monitoring items. When you purchase hitsdb, cloud monitoring automatically collects data for the hitsdb monitor.

## Monitoring Services {#section_zmy_w1w_ydb .section}

-   Monitoring items

    |Monitoring items|Dimensions|Unit|Minimum monitor Granularity|
    |:---------------|:---------|:---|:--------------------------|
    |Disk usage|User dimension, instance dimension|%|20 seconds|
    |Timeline quantity|User dimension, instance dimension|Count|20 seconds|
    |Point in time the growth rate|User dimension, instance dimension|Count/second|20 seconds|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.

    -   Users can view monitoring data for up to 14 days in a row.


-   Viewing Monitoring Data
    1.  Log in to the cloud monitoring console.
    2.  Enter the list of instances of hitsdb that the cloud service monitors.
    3.  Click the Instance name or the monitor chart in the operation to go To the instance monitoring details page to view the metrics.
    4.  Click the time range on the top of the page to quickly select a button or select an exact function, the maximum monitoring data allows you to view the monitored data for 14 consecutive days.
    5.  Click the zoom button in the upper-right corner of the monitor MAP to view the monitor larger image.

## Alarm service {#section_rtd_ybw_ydb .section}

-   Parameter descriptions
    -   Monitor: the monitoring indicator provided by hitsdb's service.

    -   Statistical Cycle: the alarm system checks if your monitoring data exceeds the alarm threshold for this cycle. For example, to set a memory usage alarm rule, the statistics cycle is 1 minute, an interval of 1 minute checks if memory usage exceeds the threshold.

    -   Continuous number of times: refers to the continuous number of statistical cycle monitoring items that continue to exceed the threshold value to trigger the alarm.


-   Set single alarm rule
    1.  Log in to the cloud monitoring console.
    2.  Enter the list of instances of hitsdb that the cloud service monitors.
    3.  Click the Instance name or the monitor chart in the operation to go To the instance monitoring details page.
    4.  Click the bell button in the upper right corner of the monitor chart or the new alarm rule in the upper right corner of the page, alarm rules can be set for monitoring items corresponding to this instance.

-   Set up bulk alarm rules
    1.  Log in to the cloud monitoring console.
    2.  Enter the list of hitsdb instances monitored by the cloud service.
    3.  When the instance list page selects the desired instance, click set alarm rule below the page, you can add alarm rules in bulk.

