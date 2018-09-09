# VPN gateway {#concept_fgw_5gw_ydb .concept}

CloudMonitor monitors multiple monitoring metrics, such as inbound and outbound network bandwidth of VPN gateway. It helps you monitor the network usage of VPN gateway and allows you to set alarm rules for the monitoring metrics. After you purchase the VPN gateway service, CloudMonitor automatically collects data on the preceding monitoring metrics.

## Monitoring service {#section_mhb_rcc_zdb .section}

-   Monitoring metrics

    CloudMonitor provides the following monitoring metrics:

    |Monitoring metrics|Dimensions|Unit|Minimum monitoring granularity|
    |:-----------------|:---------|:---|:-----------------------------|
    |Inbound network bandwidth of a bandwidth package|User and instance|Bit/s|1 minute|
    |Outbound network bandwidth of a bandwidth package|User and instance|Bit/s|1 minute|
    |Incoming packet of a bandwidth package|User and instance|PPS|1 minute|
    |Outgoing packet of a bandwidth package|User and instance|PPS|1 minute|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.

    -   You can view the monitoring data for up to 7 consecutive days.


-   View monitoring data
    1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
    2.  Go to the **VPN Gateway** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions** column to access the instance monitoring details page and view various metrics.
    4.  Click the **Time Range** quick selection button at the top of the page or use the specific selection function. You can view the monitoring data for up to 7 consecutive days.
    5.  Click the **Zoom In** button in the upper-right corner of the monitoring chart to enlarge the chart.

## Alarm service {#section_eyf_12c_zdb .section}

-   Parameter description
    -   Monitoring metrics: the monitoring metrics provided by the VPN gateway service.

    -   Statistical cycle: the alarm system checks whether your monitoring data has exceeded the alarm threshold based on the cycle. For example, if the statistical cycle of the alarm rule for memory usage is set to one minute, the system checks whether the memory usage has exceeded the threshold value every other minute.

    -   Consecutive times: an alarm is triggered when the value of the monitoring metrics continuously exceeds the threshold value for the set consecutive cycles.


-   Set an alarm rule
    1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
    2.  Go to the **VPN Gateway** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions**column to access the instance monitoring details page.
    4.  Click the bell icon in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

-   Set alarm rules in batches
    1.  Log on to the [CloudMonitor console](https://cms-intl.console.aliyun.com).
    2.  Go to the **VPN Gateway** instance list under **Cloud Service Monitoring**.
    3.  Select the appropriate instance on the instance list page. Click **Set Alarm Rules** at the bottom of the page to add alarm rules in batches.

