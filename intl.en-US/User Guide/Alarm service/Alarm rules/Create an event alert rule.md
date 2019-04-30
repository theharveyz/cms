# Create an event alert rule {#concept_dpn_bkd_v2b .concept}

This topic describes how to create an event alert rule so that you can receive alert notification when system exceptions occur to an Alibaba Cloud service and handle the exceptions in a timely manner.

## Background information {#section_sfc_gkd_v2b .section}

When an exception occurs to an Alibaba Cloud service, users need to receive alert notification and handle the exception in a timely manner. The CloudMonitor alert service provides the following types of event alert notification so that you can trace exceptions as they occur and automate handling of the exceptions in a timely manner:

-   Event alerts can be sent to you through phone calls, text messages, emails, or DingTalk Chatbot.
-   Events are distributed to your MNS queue, Function Compute, and URL callback so that you can automate handling of exceptions based on your business scenario.

## Prerequisites {#section_ulh_hpk_ngb .section}

We recommend that you create an alert contact and alert contact group before creating an event alert rule. When you create an alert rule, you can select the alert contact group to receive alert notification. For more information about how to create an alert contact and an alert contact group, see [Create an alert contact and an alert contact group](reseller.en-US/User Guide/Alarm service/Alarm contacts/Create an alert contact and an alert contact group.md#).

If you want to use alert callback as an alert notification method for system events, you must prepare a callback URL that is accessible from the Internet. In addition, you must enable URL callback as a notification method in the existing O&M or message notification system.

If you want to use MNS queue or Function Compute as the notification method of a system event, create a message queue or function.

## Procedure {#section_jry_jkd_v2b .section}

 **Precautions** 

Events are classified into system events and custom events. The alert rule and notification method vary with event type.

 **Procedure** 

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Rules**. On the Alarm Rules page that appears, the **Threshold Value Alarm** tab is displayed by default.
3.  Click the **Event Alarm** tab. On the Event Alarm tab that appears, click **Create Event Alarms** in the upper-right corner. The **Create/Modify Event Alarms** dialog box is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115255/155659494037773_en-US.png)

4.  In the **Basic Information** section, enter the alert rule name.
5.  Set **Event Alarm Rule**:
    1.  If you set event type to **System Event**:
        -   Product Type, Event Level, and Event Name: Set these parameters as needed.
        -   Resource Range: If you select **All Resources**, notification is sent based on the configuration for any resource-related events. If you select **Application Group**, notification is sent only based on events related to the resources in the specified group.
    2.  If you set event type to **Custom Event**, set Application Group, Event Name, and Rule Description as needed.
6.  Set **Alarm Type**. System events can be distributed to alert notification, MNS queue, Function Compute, and URL callback. Custom events can be distributed to alert notification and alert callback.
7.  Click **OK**.

## Subsequent operations {#section_i1t_qrl_v2b .section}

After creating an event alert rule, you can use system event testing to simulate the occurrence of system events. In this way, you can verify whether the MNS queue configured in the alert rule can receive events, and whether the function of Function Compute can be triggered.

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Rules**. On the Alarm Rules page that appears, the **Threshold Value Alarm** tab is displayed by default.
3.  Click the **Event Alarm** tab. The Event Alarm tab that appears shows an alert rule list.
4.  Click **Test** in the Actions column corresponding to an alert rule. The **Create Event Test** page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/115255/155659494037781_en-US.png)

5.  Select an event that you want to test. The event content is displayed. You can modify the fields such as instance ID in the content as needed.
6.  Click **OK**. The system will send an event based on the content, triggering alert notification, MNS queue, Function Compute, or URL callback that you configure in the alert rule.

