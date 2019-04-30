# Use one-click alert {#concept_egk_kbv_vdb .concept}

This topic describes how to use the one-click alert function to enable key metric alerts with a single click.

## Background information {#section_chy_w3b_3gb .section}

One-click alert allows you to enable key metric alerts with a single click. One-click alert is designed for inexperienced cloud service developers and O&M engineers. It helps them quickly establish a basic monitoring and alert system on the cloud without the need for a wide range of knowledge on cloud services and metrics. With this system, the engineers can receive alert notification on exceptions for key metrics.

## Prerequisites {#section_aw5_hkb_3gb .section}

Before using one-click alert, you must understand the services that support this function and related alert rules.

|Service name|Metric name|Rule description|
|:-----------|:----------|:---------------|
|ECS|CPUUtilization|Maximum value in 1 minute greater than 90%, five consecutive times, 1-hour mute duration, email notification|
|vm.DiskUtilization|Maximum value in 1 minute greater than 90%, five consecutive times, 1-hour mute duration, text message and email notification|
|vm.MemoryUtilization|Maximum value in 1 minute greater than 90%, five consecutive times, 1-hour mute duration, email notification|
|InternetOutRate\_Percent|Maximum value in 1 minute greater than 90%, five consecutive times, 1-hour mute duration, email notification|
|RDS|CpuUsage|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|DiskUsage|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, text message and email notification|
|IOPSUsage|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ConnectionUsage|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|DataDelay|Maximum value in 5 minutes greater than 5, five consecutive times, 1-hour mute duration, email notification|
|SLB|DropConnection|Maximum value in 1 minute greater than 0, five consecutive times, 1-hour mute duration, email notification|
|DropTrafficRX|Maximum value in 1 minute greater than 0, five consecutive times, 1-hour mute duration, email notification|
|DropTrafficTX|Maximum value in 1 minute greater than 0, five consecutive times, 1-hour mute duration, email notification|
|ApsaraDB RDS for Redis|CpuUsage|Maximum value in 1 minute greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ConnectionUsage|Maximum value in 1 minute greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|MemoryUsage|Maximum value in 1 minute greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|IntranetInRatio|Maximum value in 1 minute greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|IntranetOutRatio|Maximum value in 1 minute greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ApsaraDB RDS for MongoDB \(replica set\)|CPUUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|MemoryUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|DiskUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|IOPSUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ConnectionUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ApsaraDB RDS for MongoDB \(sharded cluster\)|ShardingCPUUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ShardingMemoryUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ShardingDiskUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ShardingIOPSUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ShardingConnectionUtilization|Maximum value in 5 minutes greater than 80%, five consecutive times, 1-hour mute duration, email notification|
|ApsaraDB RDS for HBase|LoadPerCpu|Maximum value in 5 minutes greater than 3, three consecutive times, 1-hour mute duration, email notification|
|cpu\_idle|Maximum value in 5 minutes smaller than 10, three consecutive times, 1-hour mute duration, email notification|
|compactionQueueSize|Maximum value in 5 minutes greater than 2,000, three consecutive times, 1-hour mute duration, email notification|
|rs\_handlerQueueSize|Maximum value in 5 minutes greater than 1,000, three consecutive times, 1-hour mute duration, email notification|
|CapacityUsedPercent|Maximum value in 5 minutes greater than 80%, three consecutive times, 1-hour mute duration, email notification|
|zookeeper\_tcp\_count|Maximum value in 5 minutes greater than 2,000, three consecutive times, 1-hour mute duration, email notification|
|Elasticsearch|ClusterStatus|Maximum value in 1 minute greater than 2, ten consecutive times, 1-hour mute duration, email notification|
|NodeDiskUtilization|Maximum value in 1 minute greater than 75%, ten consecutive times, 1-hour mute duration, email notification|
|NodeHeapMemoryUtilization|Maximum value in 1 minute greater than 85%, ten consecutive times, 1-hour mute duration, email notification|
|Open Search|DocSizeRatiobyApp|Maximum value in 10 minutes greater than 85%, one time, 1-hour mute duration, email notification|
|ComputeResourceRatiobyApp|Maximum value in 10 minutes greater than 85%, one time, 1-hour mute duration, email notification|

## Procedure {#section_p3z_wbv_vdb .section}

**Precautions**

-   When one-click alert is enabled, the built-in alert rules of CloudMonitor are enabled by default. An alert system is quickly established to monitor key metrics, not all metrics.
-   When one-click alert is enabled, the corresponding alert rules apply to the existing and to-be-created instances of the selected services.
-   One-click alert allows you to modify, disable, and delete built-in alert rules.

**Procedure**

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Alarms** \> **One-click Alarm**. The One-click Alarm page is displayed.
3.  Turn on **One-click Alarm** corresponding to the cloud service for which you want to enable alert notification.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6227/155660967613828_en-US.png)

4.  Click the drop-down arrow to the right of the **One-click Alarm** switch to view the alert rules that are automatically generated by CloudMonitor.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6227/155660967613830_en-US.png)

5.  \(Optional\) You can click **Disable**, **Modify**, or **Delete** in the Actions column corresponding to an alert rule to disable, modify, or delete the rule.

