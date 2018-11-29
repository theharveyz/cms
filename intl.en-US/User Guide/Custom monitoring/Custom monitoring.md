# Custom monitoring {#concept_oq3_h3b_wdb .concept}

## Application scenarios {#section_bdp_xmk_zdb .section}

Custom monitoring allows you to customize monitoring metrics and alarm rules. You can monitor desired business metrics and report collected monitoring data to CloudMonitor. CloudMonitor processes the data and generates alarms according to the results.

Difference between event monitoring and custom monitoring:

Event monitoring is used to report, query, and generate alarms for discontinuous event monitoring data. Custom monitoring is used to report, query, and generate alarms for time series monitoring data that is collected cyclically and continuously.

## Procedure {#section_fbb_ymk_zdb .section}

-   Report monitoring data

    For details, see [Report monitoring data](reseller.en-US/User Guide/Custom monitoring/Report monitoring data.md#).


-   Query monitoring data

    After reporting the monitoring data, you can view the reported data in the console. You can view all monitoring data on the custom monitoring page or go to a specified application group to view the relevant custom monitoring data of this group.

    -   View all custom monitoring data
        1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Custom Monitoring**. The Custom Monitoring page is displayed.
        3.  Select the corresponding application group and monitoring metrics to access the time series page.
        4.  Select the time series you want to view.
    -   View custom monitoring data under an application group
        1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Application Groups**. The Application Groups page is displayed.
        3.  Select a target application group to access the group details page.
        4.  Click **Custom Monitoring**. The Custom Monitoring page is displayed.
        5.  Select a target monitoring metric. The Time Series page is displayed.
        6.  Select the time series you want to view.
-   Set alarm rules

    Custom monitoring provides you with the alarm feature. To set an alarm rule, you need to select an appropriate application group. When the alarm is triggered, a notification is sent to the contacts in the application group. To generate an alarm for your monitoring data, configure the alarm rules as follows:

    -   Method 1:

        1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Custom Monitoring**. The Custom Monitoring page is displayed.
        3.  Select the corresponding application group and monitoring metrics. The Time Series page is displayed.
        4.  Select the time series in which you want to create an alarm. In the **Operation** column, click **Set Alarm Rules**.
        5.  On the Set Alarm Rules page, enter the alarm rule name, and set the corresponding alarm policy and notification type.
    -   Method 2:

        1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Application Groups**. The Application Groups page is displayed.
        3.  Select an appropriate application group. The **Custom Monitoring** page is displayed. Select the time series in which you want to create an alarm. In the **Operation** column, click **Set Alarm Rules**.
        4.  On the Set Alarm Rules page, enter the alarm rule name, and select the corresponding monitoring metrics, dimension, alarm policy, and notification type.

