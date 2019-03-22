# Custom monitoring overview {#concept_oq3_h3b_wdb .concept}

## Application scenarios {#section_bdp_xmk_zdb .section}

Custom monitoring allows you to customize metrics and alarm rules so that you can monitor metrics, report monitoring data, and set alarm rules with your specific requirements in mind.

Custom monitoring is different from event monitoring in that custom monitoring reports and queries time-series data that is collected periodically, whereas event monitoring only reports and queries data that is related to a singular event.

This topic discusses the procedures for operations custom monitoring including reporting, querying, and viewing monitoring data on the console, and how to set alarm rules for custom monitoring.

## Procedures {#section_fbb_ymk_zdb .section}

-   Report monitoring data.

    For more information and the specific procedure used, see [Report monitoring data](reseller.en-US/User Guide/Custom monitoring/Report monitoring data.md#).


-   Query monitoring data.

    After you have reported monitoring data, you can view the reported data in the console. You can choose to view all monitoring data on the custom monitoring page or to view custom monitoring data for one or more application group.

    -   To view all custom monitoring data, complete the following steps:
        1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Custom Monitoring**. The Custom Monitoring page is displayed.
        3.  Select the corresponding application group and metric to access the Time Series page.
        4.  Select the time series you want to view.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6218/15532454844922_en-US.png)

    -   To view the custom monitoring data in an application group, complete the following steps:
        1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Application Groups**. The Application Groups page is displayed.
        3.  Select the target application group.
        4.  Click **Custom Monitoring**. The Custom Monitoring page is displayed.
        5.  Select the target metric. The Time Series page is displayed.
        6.  Select the time series you want to view.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6218/15532454854926_en-US.png)

-   Set an alarm rule.

    Custom monitoring provides an alarm reporting feature. To set an alarm rule, you need to select an application group. When an alarm is triggered, a notification will be sent to the alarm contacts in the application group. To generate alarms for your monitoring data, set the alarm rule using either of the following two methods:

    -   Method 1:

        1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Custom Monitoring**. The Custom Monitoring page is displayed.
        3.  Select the corresponding application group and metric. The Time Series page is displayed.
        4.  Select the time series for which you want to create an alarm rule, and then click **Setup Alarm Rule** in the **Operation** column.
        5.  On the Setup Alarm Rule page, enter a name for the alarm rule and set the corresponding alarm policy and notification method.
    -   Method 2:

        1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Application Groups**. The Application Groups page is displayed.
        3.  Select the target application group. The **Custom Monitoring** page is displayed. Select the time series for which you want to create an alarm rule, and then click **Setup Alarm Rule** in the **Operation** column.
        4.  On the Setup Alarm Rule page, enter a name for the alarm rule and select the corresponding metric, dimension, alarm rule, and notification method.

