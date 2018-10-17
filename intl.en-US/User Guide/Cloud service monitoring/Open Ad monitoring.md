# Open Ad monitoring {#concept_tyx_psf_zdb .concept}

CloudMonitor provides 13 monitoring metrics for Open Ad, including RTB PV, RTB QPS, and ad click PV,    to help you monitor the service status of Open Ad in real time and set alarm rules for the monitoring metrics. After you purchase and use the Open Ad service, CloudMonitor automatically collects data on the preceding metrics.

## Monitoring service {#section_xkm_rsf_zdb .section}

-   Metrics

    |Metric|Dimension|Unit|Minimum monitor Granularity|
    |:-----|:--------|:---|:--------------------------|
    |RTB PV|User |Count|1 minute|
    |RTB QPS|User |Times/second|1 minute|
    |Ad click PV|User|Count|1 minute|
    |Ad click QPS|User |Times/second|1 minute|
    |Ad click Delay|User |Millisecond|1 minute|
    |Ad exposure PV|User |Count|1 minute|
    |Ad exposure QPS|User |Times/second|1 minute|
    |Ad exposure Delay|User |Milliseconds|1 minute|
    |DMP active crowd count|User |Days/day|1 hour|
    |DMP valid crowd requests|User |Next/day|1 hour|
    |Storage space utilized by DMP|User |Byte/day|1 hour|
    |League + dip effective crowd count|User |Days/day|1 hour|
    |Valid audience number in Umeng + DIP|User |Next/day|1 hour|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.
    -   Users can view monitoring data for up to 14 days in a row.

-   Viewing monitoring data
    1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **Open Ad monitoring page**under **Cloud Service Monitoring,**and view the overall monitoring data of the Open Ad service.

## Alarm service {#section_z3g_dtf_zdb .section}

CloudMonitor provides alarm functions for Open Ad monitoring metrics, so that you are notified immediately in case of any metric exceptions.

**Set alarm rules**

-   Method 1
    1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **Open Ad monitoring page**under **Cloud Service Monitoring**.
    3.  Click the bell icon in the upper-right corner of the monitoring chart or New Alarm Rule in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.
-   Method 2
    1.  Log on to the[CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  Go to the **Open Ad monitoring page**under **Cloud Service Monitoring**.
    3.  Click **Alarm Rules** to go to the Alarm Rules list page. Click **Create Alarm Rules** in the upper-right corner to create alarm rules.

