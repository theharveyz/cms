# Direct Mail monitoring {#concept_pwd_g2d_zdb .concept}

CloudMonitor provides monitoring metrics for Direct Mail, including WEB/API messaging, SMTP messaging, and account exceptions,  to help you monitor the service status of Direct Mail in real time and set alarm rules for the monitoring metrics.  After you purchase and use the Direct Mail service, CloudMonitor automatically collects data on the preceding monitoring metrics.

## Monitoring service {#section_ycm_n2d_zdb .section}

-   Metrics

    |Metric|Unit|Minimum monitor Granularity|
    |:-----|:---|:--------------------------|
    |Web/API error-QPS delayed|Count/Min|1 minute|
    |Web/API error-over-quota QPS|Count/Min|1 minute|
    |Web/API error-spam QPS|Count/Min|1 minute|
    |Web/API message success QPS|Count/Min|1 minute|
    |SMTP authentication failed QPS|Count/Min|1 minute|
    |SMTP authentication is successful QPS|Count/Min|1 minute|
    |SMTP error-length exceeded QPS|Count/Min|1 minute|
    |SMTP error-over-quota QPS|Count/Min|1 minute|
    |SMTP error-spam QPS|Count/Min|1 minute|

    **Note:** 

    -   Monitor Data is saved for up to 31 days.

    -   Users can view monitoring data for up to 14 days in a row.


-   Viewing Monitoring Data
    1.  Log on to the[CloudMonitor console](http://cms.console.aliyun.com/#/groups/).
    2.  Go to the**Direct Mail monitoring**  page under **Cloud Service Monitoring**, and view the monitoring information of the Direct Mail service.

## Alarm service {#section_lvy_fgd_zdb .section}

CloudMonitor provides alarm functions for Direct Mail monitoring metrics, so that you are notified immediately in case of any metric exceptions.

**Set alarm rules**

1.  Log on to the[CloudMonitor console](http://cms.console.aliyun.com/#/groups/).
2.  Go to the**Direct Mail monitoring** page under **Cloud Service Monitoring**.
3.  Click Alarm Rules to go to the Alarm Rules list page. Click Create Alarm Rules in the upper-right corner to create alarm rules.

    Or click the bell icon in the upper-right corner of the monitoring chart or New Alarm Rule in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.


