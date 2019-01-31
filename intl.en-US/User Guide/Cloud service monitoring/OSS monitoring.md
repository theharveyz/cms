# OSS monitoring {#concept_oyz_25t_xdb .concept}

By monitoring the basic service, performance, and metering data of the Object Service Storage \(OSS\) service, CloudMonitor enables you to gain insights into the overall performance of the OSS service and set alarm rules accordingly. Specifically, this can help you better track requests, analyze usage, collect statistics on business trends, and quickly discover and diagnose system issues.

## Monitoring service {#section_syy_q5t_xdb .section}

-   Metrics

    The metrics used for monitoring OSS mainly include basic service, performance, and metering indicators. For more information, see [Monitoring indicators reference](https://www.alibabacloud.com/help/doc-detail/31880.htm).

    **Note:** To maintain consistency with the billing policies, the collection and presentation of metering data have the following characteristics:

    -   Metering data is collected hourly, so that the metering data for your resources is aggregated to a single value each hour. This value represents the overall metering condition of the hour monitored.
    -   Metering data has an output delay of nearly 30 minutes.
    -   The metering data time refers to the start time of the relevant statistical period.
    -   The cutoff time of metering data is the end time of the last statistical period of the current month. If no metering data is produced in the current month, the metering data cutoff time is 00:00 on the first day of the current month.
    -   For presentation purposes, the maximum quantity of metering data is pushed. For more information about metering data, see [Usage Records](https://expense.console.aliyun.com/?spm=a2c4g.11186623.2.5.wl5kOv).

        Example

        Assuming that you only use PutObject requests to upload data and perform this operation at an average of 10 times per minute. Then, in the hour between 08:00:00 and 09:00:00 on May 10, 2016, the metering result of your PUT requests is 600 times \(10 × 60 minutes\), the time of metering data is 08:00:00 on May 10, 2016, and the result will be generated at around 09:30:00 on May 10, 2016. If the result is the last data record since 00:00:00 on May 1, 2016, the metering data cutoff time for the current month is 09:00:00 on May 10, 2016. If in May 2016, you have not produced any metering data, the metering data cutoff time will be 00:00:00 on May 1, 2016.


## Alarm service {#section_hdz_fvt_xdb .section}

**Note:** 

The names of OSS buckets are unique. Given this, after you delete a bucket, if you create another one with the same name as the deleted one, the monitoring rules and alarm rules that were previously set for the deleted bucket will also apply to the new bucket.

You can set alarm rules for several metrics in addition to the preceding metering and statistical indicators. You can also add these metrics to your monitoring list. Moreover, multiple alarm rules can be set for a single metric.

## Instructions {#section_x5t_3vt_xdb .section}

-   For more information about the alarm service, see [Alarm service overview](reseller.en-US/User Guide/Alarm service/Alarm service overview.md#).

-   For more information about the alarm service for OSS monitoring, see [OSS alarm service user guide](https://www.alibabacloud.com/help/zh/doc-detail/31878.htm).


