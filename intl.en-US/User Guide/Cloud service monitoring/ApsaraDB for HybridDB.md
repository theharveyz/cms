# ApsaraDB for HybridDB {#concept_pl4_tlf_zdb .concept}

Cloud monitoring through monitoring hybriddb's CPU usage, memory usage, and so on, helps the user monitor the usage of the hybridgedb instance and enables the user to set alarm rules on the monitor item. After you purchase After hybridgedb, cloud monitoring automatically collects data for the above monitoring items.

## Monitor {#section_hrz_vlf_zdb .section}

-   Monitoring items

    |Monitoring items|Dimension|Unit|Minimum monitor Granularity|
    |:---------------|:--------|:---|:--------------------------|
    |Disk usage|User and instance|%|5 minutes|
    |Connection usage|User and instance|%|5 minutes|
    |CPU usage|User and instance|%|5 minutes|
    |Memory usage|User and instance|%|5 minutes|
    |I/O throughput usage|User and instance|%|5 minutes|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.
    -   Users can view monitoring data for up to 14 days in a row.

-   View monitored data.
    1.  Log in to the [cloud monitoring console](http://cms.console.aliyun.com/#/groups/).
    2.  Go to the HybridDB instance list under Cloud Service Monitoring.
    3.  Click an instance name or click **Monitoring Chart** in the **Actions** column to access the instance monitoring information page and view various metrics.
    4.  Click the time range quick select button or the exact select function at the top of the page, maximum monitoring data support view continuous 14 Monitoring data for days.
    5.  Click the zoom in button in the upper-right corner of the monitor MAP to view the monitor larger image.

## Alarm service {#section_v1x_hmf_zdb .section}

