# Event monitoring overview {#concept_idt_k3b_wdb .concept}

Event monitoring provides reporting, querying, and alarm monitoring features for event-related data so that you can quickly and easily monitor and report various exceptions and important changes in your business operations. Event monitoring also ensures that you will receive alarm notifications as soon as an event-related exception occurs.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6162/15483224694804_en-US.png)

The difference between event monitoring and custom monitoring is as follows:

-   Event monitoring reports and queries discontinuous event monitoring data and generates alarms if the conditions specified in your alarm rules are met.
-   Custom monitoring reports and queries time-series monitoring data collected periodically and generates alarms if the conditions specified in your alarm rules are met.

## Event monitoring processes {#section_lhh_p2j_zdb .section}

-   Report event data

    For more information, see [Report event data](reseller.en-US/User Guide/Event monitoring/Report event data.md#).


-   Query event data

    In the CloudMonitor console, you can query any reported event data. You can choose to view all the events on the **Event Monitoring** page, or enter a specific application group to view the events in that group.

    To view all the reported events, follow these steps:

    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, click **Event Monitoring**.
    3.  On the Event Monitoring page, you can view all the events under **System Event** or **Custom Event**, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6162/15483224694816_en-US.png)

    4.  To view the details of a specific event, click **View the Detail** on the right of the target event.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6162/15483224704819_en-US.png)

        To query events of a specific group, go to the specific Event Monitoring page of the group.

-   Set an alarm rule

    Event monitoring provides an alarm reporting feature. When setting an alarm rule, you need to select a corresponding application group. After an alarm is generated, a notification is sent to the alarm contact group. To set alarm rules for an event, use either of the following two methods:

    -   Method 1:
        1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Event Monitoring**.
        3.  Click **Create Alarm Rule** on the right of the target event.
        4.  In the displayed Create/modify event alerts dialog box, enter a name for the alarm rule, set the corresponding rules and notification method, and click **OK**.
    -   Method 2:

        1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
        2.  In the left-side navigation pane, click **Application Groups**.
        3.  Click the target group name.
        4.  In the left-side navigation pane, click **Event Monitoring**.
        5.  Click **Create Alarm Rule** on the right of the target event.
        6.  In the displayed Create/modify event alerts dialog box, enter a name for the alarm rule, set the corresponding rules and notification method, and click **OK**.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6162/15483224704823_en-US.png)


