# StreamCompute {#concept_g21_2bf_zdb .concept}

CloudMonitor provides service latency metrics of StreamCompute to help you monitor the performance of the StreamCompute service and set alarm rules for the monitoring metrics.  After you purchase the StreamCompute service, CloudMonitor auto collects data on the preceding metrics.

## Monitoring service {#section_fhd_sbf_zdb .section}

-   Metrics

    |Metric|Dimension|Unit|Description|Minimum monitor Granularity|
    |:-----|:--------|:---|:----------|:--------------------------|
    |Service latency|Project, job|Second| Data processing latency of the current job|1 minute|
    |Read in RPS|Project, job|RPS|Average number of data lines read per second for tasks|1 minute|
    |Write RPS|Project, job|RPS|Average number of data lines written per second for tasks|1 minute|
    |FailoverRate|Project, job|%|Measure the current job failover frequency, the lower the better.|1 minute|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.You can view the monitoring data for up to 14 consecutive days.

-   Viewing Monitoring Data
    1.  Log on to the.[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **StreamCompute** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions**column to access the instance monitoring information page and view various metrics.
    4.  Click **Time Range** quick selection button from the upper menu of the page or use the specific selection function. You can view the monitoring data for up to 14 consecutive days.
    5.  Click Zoom In in the upper-right corner of the monitoring chart to enlarge the chart.

## Alarm service {#section_nhz_ccf_zdb .section}

-   Parameter descriptions
    -   Monitoring metrics: The monitoring metrics provided by the StreamCompute service.
    -   Statistical cycle: The alarm system checks whether your monitoring data has exceeded the alarm threshold based on the cycle.   For example, if the statistical cycle of the alarm rule for memory usage is set to one  minute,  the system checks whether the memory usage has exceeded the threshold value every other minute.
    -   Statistical method: Indicates the method used to determine if the data exceeds the threshold.  The average value, maximum value, minimum value, and sum value can be set as the statistical method.
        -   Average value: The average value of monitoring data within the statistical cycle.   For example, when the average value of all monitoring data collected within 15 minutes is adopted as the statistical method, an average value over 80% is deemed to exceed the threshold.
        -   Maximum value: The maximum value of monitoring data within the statistical cycle.   For example, when the maximum value of all monitoring data collected within 15 minutes is adopted as the statistical method, a maximum value over 80% is deemed to exceed the threshold.
        -   Minimum value: The minimum value of monitoring data within the statistical cycle.   For example, when the minimum value of all monitoring data collected within 15 minutes is adopted as the statistical method, a minimum value over 80% is deemed to exceed the threshold.
        -   Sum value: The sum of monitoring data within the statistical cycle. For example, when the sum value of all monitoring data collected within 15 minutes is adopted as the statistical method, a sum value over 80% is deemed to exceed the threshold. This method is required for traffic metrics.
    -   Consecutive times: An alarm is triggered when the value of the monitoring metrics continuously exceeds the threshold value for the set consecutive cycles.

        For example, you have set the alarm to go off when the CPU usage exceeds the threshold value of 80% for three consecutive 5-minute statistical cycles.  That is to say, no alarm is triggered when the CPU usage is found to exceed 80% for the first time. No alarm is triggered either when the CPU usage exceeds 80% again in the second detection five minutes later. The alarm is triggered when the CPU usage exceeds 80% again in the third detection.   Therefore, from the first time when the actual data exceeds the threshold to the time when the alarm rule is triggered, the minimum time consumed is: the statistical cycle\(the number of consecutive detections-1\), which is 5\(3-1\) = 10 minutes in this case.


-   Set an alarm rule
    1.  Log on to the.[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **StreamCompute** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions**column.
    4.  Click the bell icon in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

-   Set multiple alarm rules
    1.  Log on to the.[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **StreamCompute** instance list under **Cloud Service Monitoring**.
    3.  Select the expected instances on the instance list page. Click **Set Alarm Rules** to add multiple alarm rules.

