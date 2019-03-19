# ApsaraDB for HybridDB {#concept_pl4_tlf_zdb .concept}

By monitoring the CPU, disk, and memory usage, along with other metrics from ApsaraDB for HybridDB, CloudMonitor helps you quickly learn about product-wide instance usage and set alarm rules based on your specific requirements. CloudMonitor automatically collects data from ApsaraDB for HybridDB from the time when you begin to use this product.

## Monitoring service {#section_hrz_vlf_zdb .section}

-   Metrics

    |Metric|Dimensions|Unit|Minimum monitoring frequency|
    |:-----|:---------|:---|:---------------------------|
    |Disk usage|User and instance|%|5 minutes|
    |Connection usage|User and instance|%|5 minutes|
    |CPU usage|User and instance|%|5 minutes|
    |Memory usage|User and instance|%|5 minutes|
    |I/O throughput|User and instance|%|5 minutes|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.
    -   You can view up to 14 consecutive days of monitoring data.

-   View monitoring data
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the Apsara for HybridDB instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions** column to access the instance monitoring details page and view various metrics.
    4.  Click the **Time Range** toggle button from the upper menu of the page or use the precise selection function. You can view monitoring data from up to 14 consecutive days.
    5.  Click the **Zoom In** button in the upper-right corner of the monitoring chart to enlarge the chart.

## Alarm service {#section_v1x_hmf_zdb .section}

-   Parameters
    -   Metrics: The monitoring metrics taken from ApsaraDB for HybridDB.
    -   Statistical cycle: The recurring period of time in which the alarm system checks whether monitoring data has exceeded the alarm threshold.
    -   Statistical method: The calculation method and resulting value used to determine whether the data has exceeded the threshold specified in an alarm rule, which can be average, maximum, minimum, or sum.
    -   Consecutive times: An alarm is triggered after a metric value continuously exceeds the threshold specified in an alarm rule for some set of consecutive cycles. For example, if the consecutive times is set to three, then the conditions specified for an alarm rule must be met for three consecutive statistical cycles before an alarm is triggered.
-   Set an alarm rule
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the Apsara for HybridDB instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions** column to access the instance monitoring details page and view various metrics.
    4.  Click the bell icon in the upper-right corner of the monitoring chart or **Create Alarm Rules** in the upper-right corner of the page to set an alarm rule for corresponding metrics of this instance.
-   Set multiple alarm rules
    1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the ApsaraDB for HybridDB instance list under **Cloud Service Monitoring**.
    3.  Select the appropriate instances on the instance list page. Click **Set Alarm Rules** to add multiple alarm rules.

