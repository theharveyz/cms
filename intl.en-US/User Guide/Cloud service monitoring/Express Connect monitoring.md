# Express Connect monitoring {#concept_blv_wxd_zdb .concept}

CloudMonitor monitors multiple metrics, such as the inbound and outbound network traffic of the Express Connect instance. It monitors the network usage of the instance and allows you to set alarm rules for various metrics. Once you buy the Express Connect service, CloudMonitor automatically collects the data for the following metrics.

## Monitoring services {#section_ohv_xxd_zdb .section}

-   Monitoring items

    |Monitoring item|Dimension|Unit|Minimum monitoring granularity|
    |:--------------|:--------|:---|:-----------------------------|
    |Inbound network traffic|User and instance|Bytes|1 minute|
    |Outbound network traffic|User and instance|Bytes|1 minute|
    |Inbound network bandwidth|User and instance|Bits/s|1 minute|
    |Outbound network bandwidth|User and instance|Bits/s|1 minute|
    |Latency|User and instance|ms|1 minute|
    |Packet loss rate|User and instance|%|1 minute|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.

    -   You can view the monitoring data for up to 14 consecutive days.


-   View monitoring data
    1.  Log on to the [CloudMonitor console](http://cms.console.aliyun.com/#/groups/).
    2.  Enter the instance list of **Express Connect** under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Action** column to access the instance monitoring details page and view metrics.
    4.  Click a **Time Range** shortcut on the top of the page or use the specific selection function. Up to 14 consecutive days of metric data can be viewed.
    5.  Click the zoom-in button in the upper-right corner of the monitoring chart to view a large image.

## Alarm service {#section_ihr_vyd_zdb .section}

-   Parameter description
    -   Metrics: metric items provided by the Express Connect service.
    -   Statistical Cycle: indicates how often the alarm system checks whether monitoring data exceeds the alarm threshold. For example, if the statistical cycle of the alarm rule for memory usage is set to one minute, the system checks whether the memory usage has exceeded the threshold value every other minute.
    -   Statistical Methods: determines whether the data exceeds the threshold. Average, maximum, minimum, and sum can be set in the Statistical Methods.
        -   Average value: the average value of monitoring data within the statistical cycle. For example, when the average value of all monitoring data collected within 15 minutes is used as the statistical method, an average value over 80% is deemed to exceed the threshold.
        -   Maximum value: the maximum value of monitoring data within the statistical cycle. For example, when the maximum value of all monitoring data collected within 15 minutes is used as the statistical method, a maximum value over 80% is deemed to exceed the threshold.
        -   Minimum value: the minimum value of monitoring data within the statistical cycle. For example, when the minimum value of all monitoring data collected within 15 minutes is used as the statistical method, a minimum value over 80% is deemed to exceed the threshold.
        -   Sum value: the sum of monitoring data within the statistical cycle. For example, when the sum value of all monitoring data collected within 15 minutes is used as the statistical method, a sum value over 80% is deemed to exceed the threshold. This method is required for traffic metrics.
    -   Consecutive times: An alarm is triggered when the value of the monitoring metrics continuously exceeds the threshold value for the set consecutive cycles.

        For example, you have set the alarm to go off when the CPU usage exceeds the threshold value of 80% for three consecutive 5-minute statistical cycles.  That is to say, no alarm is triggered when the CPU usage is found to exceed 80% for the first time. No alarm is triggered either when the CPU usage exceeds 80% again in the second detection five minutes later. The alarm is triggered  when the CPU usage exceeds 80% again in the third detection. Therefore, from the first time when the actual data exceeds the threshold to the time when the alarm rule is triggered, the minimum time consumed is: the statistical cycle x \(the number of consecutive detections - 1\), which is 5 x \(3 - 1\) = 10 minutes in this case.


-   Set an alarm rule
    1.  Log on to [CloudMonitor console](http://cms.console.aliyun.com/#/groups/).
    2.  Enter the instance list of **Express Connect** under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Action** column to access the instance monitoring details page and view metrics.
    4.  Click the Bell button in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

-   Set alarm rules in batches
    1.  Log on to [CloudMonitor console](http://cms.console.aliyun.com/#/groups/).
    2.  Enter the instance list of **Express Connect** under **Cloud Service Monitoring**.
    3.  Select instances on the instance list page. Click **Set Alarm Rules** to add multiple alarm rules.

