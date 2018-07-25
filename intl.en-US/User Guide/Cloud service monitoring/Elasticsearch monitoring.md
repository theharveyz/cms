# Elasticsearch monitoring {#concept_cvv_lld_zdb .concept}

CloudMonitor enables the user to monitor the usage of Elasticsearch services by collecting monitoring metrics such as the cluster status of Elasticsearch, the cluster query QPS, and the cluster writing QPS. Users can also set alarm rules for monitoring metrics. After you purchase the Elasticsearch, CloudMonitor automatically collects data on the preceding monitoring metrics.

## Monitoring service {#section_lsc_hnd_zdb .section}

-   Monitoring metrics

    |Monitoring metrics|Dimension|Unit|Minimum monitoring granularity|
    |:-----------------|:--------|:---|:-----------------------------|
    |Cluster status|Cluster| |1 minute|
    |Cluster query QPS|Cluster|Count/Second|1 minute |
    |Cluster writing QPS|Cluster|Count/Second|1 minute|
    |Node CPU usage|Node|%|1 minute|
    |Node disk usage|Node|%|1 minute|
    |Node heapmemory usage|Node|%|1 minute|
    |Node: load\_1m|Node| |1 minute|
    |Node FullGc times|Node|Count|1 minute|
    |Node Exception times|Node|Count|1 minute|
    |Cluster snapshot status|Cluster|-1 indicates that there is no snapshot; 0 indicates success; 1 indicates in progress; 2 indicates failure|1 minute|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.
    -   You can view the monitoring data for up to 14 consecutive days.

-   View monitoring data
    1.  Log on to the [CloudMonitor console](https://cms.console.aliyun.com/#/home/ecs%22%E4%BA%91%E7%9B%91%E6%8E%A7%E6%8E%A7%E5%88%B6%E5%8F%B0%22).
    2.  Go to the **Elasticsearch** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions** column to access the instance monitoring details page and view various metrics.
    4.  Click a **Time Range** shortcut on the top of the page or use the specific selection function. Up to 14 consecutive days of metric data can be viewed.
    5.  Click Zoom In in the upper-right corner of the monitoring chart to enlarge the chart.

## Alarm service {#section_jdy_m4d_zdb .section}

-   Parameter description
    -   Monitoring metrics: the monitoring metrics provided by the Elasticsearch service.
    -   Statistical cycle: the alarm system checks whether your monitoring data has exceeded the alarm threshold based on the cycle. For example, if the statistical cycle of the alarm rule for memory usage is set to one minute, the system checks whether the memory usage has exceeded the threshold value every other minute.
    -   Consecutive times: an alarm is triggered when the value of the monitoring metrics continuously exceeds the threshold value for the set consecutive cycles.

-   Set an alarm rule
    1.  Log in to the cloud monitoring console.
    2.  Go to the **Elasticsearch** instance list under **Cloud Service Monitoring**.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions** column to access the instance monitoring details page.
    4.  Click Bell icon in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

