# Global acceleration monitoring {#concept_zkm_ftv_ydb .concept}

CloudMonitor monitors multiple monitoring metrics, such as inbound and outbound network bandwidth of Global Acceleration. It helps you monitor the network usage of Global Acceleration and allows you to set alarm rules for the monitoring metrics.  After you purchase the Global Acceleration service, CloudMonitor automatically collects data on the preceding monitoring metrics.

## Monitoring service {#section_dbz_htv_ydb .section}

-   Metrics

    |metric|Dimension|Unit|Minimum monitor Granularity|
    |:-----|:--------|:---|:--------------------------|
    |Inbound bandwidth|User and instance|Bits/s|1 minute|
    |outbound bandwidth|User and instance|Bits/s|1 minute|
    |Inbound package|User and instance|pps|1 minute|
    |outbound package|User and instance|pps|1 minute|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.
    -   You can view the monitoring data for up to 7 consecutive days.
-   View monitoring data
    1.  Log on to the[CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  Go to the **Global Acceleration**instance list under **Cloud Service Monitoring** .
    3.  Click an instance name or click **Monitoring Chart**in the **Actions** column to access the instance monitoring details page and view various metrics.
    4.  Click the **Time Range** quick selection button from the upper menu of the page or use the specific selection function. You can view the monitoring data for up to 7 consecutive days.
    5.  Click Zoom In in the upper-right corner of the monitoring chart to enlarge the chart.

## Alarm service {#section_zgg_zvv_ydb .section}

-   Parameter descriptions
    -   Monitoring metrics: The monitoring metrics provided by Global Acceleration service.
    -   Statistical cycle: The alarm system checks whether your monitoring data has exceeded the alarm threshold based on the cycle. For example, if the statistical cycle of the alarm rule for memory usage is set to one minute, the system checks whether the memory usage has exceeded the threshold value every other minute.
    -   Consecutive times: An alarm is triggered when the value of the monitoring metrics continuously exceeds the threshold value for the set consecutive cycles.
-   Set an alarm rule
    1.  Log on to the[CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  Go to the **Global Acceleration**instance list under **Cloud Service Monitoring** .
    3.  Click an instance name or click **Monitoring Chart**in the **Actions** column to access the instance monitoring details page.
    4.  Click bell icon in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

-   Set multiple alarm rules
    1.  Log on to the[CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  Go to the **Global Acceleration**instance list under **Cloud Service Monitoring** .
    3.  Select the appropriate instances on the instance list page. Click **Set Alarm Rules** to add multiple alarm rules.

