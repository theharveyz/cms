# OSS monitoring {#concept_oyz_25t_xdb .concept}

OSS The Object Service Storage \(OSS\) monitoring service provides you the metric data which describes basic system operation status, performance, and metering. It also provides a custom alarm service to help you track requests, analyze usage, collect statistics on business trends, and promptly discover and diagnose system problems.

## Monitoring service {#section_syy_q5t_xdb .section}

-   Metric description

    OSS metric indicators are classified into groups such as basic service indicators, performance indicators, and metering indicators. For details, refer to [OSS metric indicator reference manual](https://www.alibabacloud.com/help/doc-detail/31880.htm).

    **Note:** To maintain consistency with the billing policies, the collection and presentation of metering indicators have the following special features:

    -   Metering indicator data displays output per hour. This means that resource metering information for each hour is combined into a single value that represents the overall metering condition for that hour.

    -   Metering indicator data has an output delay of nearly 30 minutes.

    -   The data time of metering indicator data refers to the start time of the relevant statistical period.

    -   The cutoff time of metering data acquisition is the end time of the last metering data statistical period of the current month. If no metering data is produced in the current month, the metering data acquisition cutoff is 00:00 on the first day of the current month.

    -   A maximum amount of metering indicator data is pushed for presentation. For precise metering data, refer to [Consumption records](https://expense.console.aliyun.com/?spm=a2c4g.11186623.2.5.wl5kOv).

        For example, assume that you only use PutObject requests to upload data and perform this operation at an average of 10 times per minute.  Then, in the hour between 2016-05-10 08:00:00 and 2016-05-10 09:00:00, the metering data value for your PUT requests will be 600 times \(10\*60 minutes\), the data time will be 2016-05-10  08:00:00, this part of data will be output at around 2016-05-10 09:30:00. If this part of data is the last one since 2016-05-01 00:00:00, the metering data acquisition cutoff for the current month is 2016-05-10  09:00:00. If in May 2016, you have not produced any metering data, the metering data acquisition cutoff will be 2016-05-01  00:00:00.


## Alarm service {#section_hdz_fvt_xdb .section}

**Note:** OSS buckets must be globally unique. After deleting a bucket, if you create another bucket with the same name, the monitoring and alarm rules set for the deleted bucket will be applied to the new bucket with the same name.  

Besides metering indicators and statistical indicators, alarm rules can be configured for other metric indicators and be added to alarm monitoring. Moreover, multiple alarm rules may be configured for a single metric indicator.

## User guide {#section_x5t_3vt_xdb .section}

-   For information about the alarm rules service, see [Alarm service overview](reseller.en-US/User Guide/Alarm Service/Alarm service overview.md#).

-   For instructions on how to use the OSS alarm rules service, see [OSS Alarm rules service user guide](https://www.alibabacloud.com/help/doc-detail/31878.htm).


