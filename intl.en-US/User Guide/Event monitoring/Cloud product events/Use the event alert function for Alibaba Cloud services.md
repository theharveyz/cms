# Use the event alert function for Alibaba Cloud services {#concept_dpn_bkd_v2b .concept}

This topic describes how to use the event alert function for Alibaba Cloud services to enable alerts when a system exception occurs.

## Background information {#section_sfc_gkd_v2b .section}

When an Alibaba Cloud service encounters a system exception, event monitoring can provide two types of notification. You can trace the event and automate the handling process.

-   Event alert notification can be sent to you through , emails, and DingTalk Chatbot.
-   The event is distributed to your MNS queue, Function Compute, Log Service, and URL callback. Then, you can automate the handling process based on your scenario.

## Preparations {#section_n4x_4vr_pgb .section}

If you want system events to be distributed to your MNS queue, Function Compute, Log Service, and URL callback, you must enable the corresponding services.

## Procedure {#section_jry_jkd_v2b .section}

You can create an event alert rule. Then, you can use system event testing to check whether the configured MNS queue of the alert rule can receive event alerts in a timely manner, and whether Function Compute can be triggered.

-   **Create an event alert rule** 
    1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
    2.  In the left-side navigation pane, click **Event Monitoring**.
    3.  On the **Alarm Rules** tab, click **Create Event Alarms**. The **Create/Modify Event Alarms** dialog box is displayed.
    4.  In the **Basic Information** section, set Alarm Rule Name.
    5.  In the **Event Alarm** section, set the following parameters:
        1.  Event Type: Select **System Event**.
        2.  Product Type, Event Level, and Event Name: Set the parameters based on the actual situation.
        3.  Resource Range: If you select **All Resources**, alerts are sent when any resource-related events occur. If you select **Application Groups**, alerts are sent only when events that are related to the resources in the specified group occur.
    6.  Select the **Alarm Type**. CloudMonitor supports four alert types: alert notification, MNS queue, function service, and URL callback.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17722/15565276809712_en-US.png)

-   **Test an alert rule** 
    1.  Access the Alarm Rules tab for event monitoring.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17722/15565276809690_en-US.png)
    2.  Click **Test** in the Actions column corresponding to the RAM user.
    3.  On the test page that appears, select the event to be tested. The corresponding event content will be displayed. You can change content fields such as the instance ID as needed.
    4.  Click **OK**. The system will send an event based on the content, triggering alert notification, MNS queue, Function Compute, and URL callback that are configured in the alert rule.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17722/15565276809691_en-US.png)

