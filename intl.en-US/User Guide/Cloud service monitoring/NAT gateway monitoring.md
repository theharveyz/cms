# NAT gateway monitoring {#concept_i53_3rf_zdb .concept}

CloudMonitor provides multiple monitoring metrics for NAT Gateway, including the SNAT connections to help you monitor network usage of the NAT Gateway service and set alarm rules for the monitoring metrics. After you purchase the NAT gateway service, CloudMonitor automatically collects data on the preceding monitoring metrics.

## Monitoring Service {#section_php_jrf_zdb .section}

-   Metrics

    |Metric|Dimension|Unit|Minimum monitor Granularity|
    |:-----|:--------|:---|:--------------------------|
    |SNAT connections| User and instance|Count/Min|1 minute|
    |Package inbound bandwidth| User and instance|Bit/s|1 minute|
    |Package outbound bandwidth| User and instance|Bit/s|1 minute|
    |Package inbound packet| User and instance|pps|1 minute|
    |Package outbound packet| User and instance|pps|1 minute|
    |Package outbound bandwidth usage| User and instance|%|1 minute|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.
    -   You can view the monitoring data for up to 14 consecutive days.

-   View monitoring data
    1.  Log on to the.[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **NAT Gateway** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions**column to access the instance monitoring details page and view various metrics.
    4.  Click **Time Range** quick selection button from the upper menu or use the specific selection function. You can view the monitoring data for up to 14 consecutive days.
    5.  Click Zoom In in the upper-right corner of the monitoring chart to enlarge the chart.

## Alarm service {#section_oyk_bsf_zdb .section}

-   Parameter descriptions
    -   Monitoring metrics: The monitoring metrics provided by the NAT Gateway service.
    -   Statistical cycle: The alarm system checks whether your monitoring data has exceeded the alarm threshold based on the cycle.  For example, if the statistical cycle of the alarm rule for memory usage is set to one minute, the system checks whether the memory usage has exceeded the threshold value every other minute.
    -   Consecutive times: An alarm is triggered when the value of the monitoring metrics continuously exceeds the threshold value for the set consecutive cycles.

-   Set an alarm rule
    1.  Log on to the.[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **NAT Gateway** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions**column to access the instance monitoring details page.
    4.  Click the bell icon in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

-   Set multiple alarm rules
    1.  Log on to the.[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **NAT Gateway** instance list under **Cloud Service Monitoring**.
    3.  Select the appropriate instances on the instance list page. Click **Set Alarm Rules** to add multiple alarm rules.

