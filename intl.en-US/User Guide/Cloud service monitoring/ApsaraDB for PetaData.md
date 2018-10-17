# ApsaraDB for PetaData {#concept_jfc_42w_ydb .concept}

CloudMonitor  provides multiple monitoring metrics, including the minimum and maximum numbers of ApsaraDB for PetaData instances to help you monitor the instance status in a scaling group and set alarm rules for the monitoring metrics.  After you purchase the Auto Scaling service, CloudMonitor automatically collects data on the preceding metrics.

## Monitoring service {#section_m2q_vlf_12b .section}

-   Metrics

    |Metric|Dimension|Unit|Minimum monitor Granularity|
    |:-----|:--------|:---|:--------------------------|
    |Disk usage|User and instance|Byte|5 minutes|
    |Inbound bandwidth|User and instance|Byte/Second|5 minutes|
    |Outbound bandwidth|User and instance|Byte/Second|5 minutes|
    |QPS|User and instance|Count/Second|5 minutes|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.
    -   Users can view monitoring data for up to 14 days in a row.
-   Viewing monitoring data
    1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **ApsaraDB for PetaData** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions** column to access the instance monitoring details page and view various metrics.
    4.  Click **Time Range** quick selection button from the upper menu of the page or use the specific selection function. You can view the monitoring data for up to 14 consecutive days.
    5.  Click Zoom In in the upper-right corner of the monitoring chart to enlarge the chart.

## Alarm service {#section_hnd_tmf_12b .section}

-   Parameter descriptions
    -   Monitoring metrics: The monitoring metrics provided by ApsaraDB for PetaData.
    -   Statistical cycle: The alarm system checks whether your monitoring data has exceeded the alarm threshold based on the cycle.  For example, if the statistical cycle of the alarm rule for memory usage is set to one minute, the system checks whether the memory usage has exceeded the threshold value every other minute.
    -   Statistical method: Indicates the method used to determine if the data exceeds the threshold. The average value, maximum value, minimum value, and sum value can be set as the statistical method.
        -   Average value: The average value of monitoring data within the statistical cycle. For example, when the average value of all monitoring data collected within 15 minutes is adopted as the statistical method, an average value over 80% is deemed to exceed the threshold.
        -   Maximum value: The maximum value of monitoring data within the statistical cycle.  For example, when the maximum value of all monitoring data collected within 15 minutes is adopted as the statistical method, a maximum value over 80% is deemed to exceed the threshold.
        -   Minimum value: The minimum value of monitoring data within the statistical cycle.   For example, when the minimum value of all monitoring data collected within 15 minutes is adopted as the statistical method, a minimum value over 80% is deemed to exceed the threshold.
        -   Sum value: the sum of monitoring data within the statistical cycle. For example, when the sum value of all monitoring data collected within 15 minutes is adopted as the statistical method, a sum value over 80% is deemed to exceed the threshold.   This method is required for traffic metrics.
    -   Consecutive times: An alarm is triggered when the value of the monitoring metrics continuously exceeds the threshold value for the set consecutive cycles.

        For example, you have set the alarm to go off when the CPU usage exceeds the threshold value of 80% for three  consecutive 5-minute statistical cycles. The second time in 5 minutes to detect CPU usage exceeds 80% and no alarm will be issued. The third probe still exceeds 80% Alarm notification will be issued only when. That is, from the first time the actual data exceeds the threshold to the final alarm rule, the minimum time required is statistical cycle X \(number of consecutive probes-1\) = 5 x \(3-1\) = 10 minutes.

-   Set an alarm rule
    1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **ApsaraDB for PetaData** instance list under **Cloud Service Monitoring**.  
    3.  Click an instance name or click **Monitoring Chart** in the **Actions** column to access the instance monitoring information page.
    4.  Click the bell icon or **New Alarm Rule** in the upper-right corner of the monitoring data page to set an alarm rule for corresponding monitoring metrics of this instance.
-   Set multiple alarm rules
    1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **ApsaraDB for PetaData** instance list under **Cloud Service Monitoring**.  
    3.  Select the appropriate instances on the instance list page. Click **Set Alarm Rules** to add multiple alarm rules.

