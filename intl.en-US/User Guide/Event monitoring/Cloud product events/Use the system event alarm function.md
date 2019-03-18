# Use the system event alarm function {#concept_dpn_bkd_v2b .concept}

## Scenario {#section_sfc_gkd_v2b .section}

To help you to quickly learn of system event exceptions and automate the handling of these event-related exceptions when a system event occurs for one or more of your Alibaba Cloud products, the alarm function of event monitoring provides the following notification methods:

-   Alarm notifications for system events are sent as voice, text, or email messages.
-   System events are distributed to your MNS queue, function service, and URL callback.

## **Create an alarm rule** {#section_jry_jkd_v2b .section}

1.  Log on to the [CloudMonitor Console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left navigation pane, select **Event Monitoring**.
3.  On the **Alarm Rules** tab page, click **Create event alerts** in the upper-right corner. The **Create / modify event alerts** dialog box is displayed.
4.  In the **Basic Information** area, fill in the alarm rule name.
5.  In the **Event alert** area, complete the following information:
    1.  **Event Type**: Select **System Event**.
    2.  **Product Type**, **Event Level**, **Event Name**: Enter information based on your requirements.
    3.  **Resource Range**: Select **All Resources** or **Application Groups**. If you select **All Resources**, notifications are sent for any resource-related exceptions. If you select **Application Groups**, notifications are sent only when an exception occurs for resources in the application group or groups you specified.
6.  Select the **Alarm type**. CloudMonitor supports four alarm types: alarm notification, MNS queue, function service, and URL callback.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17722/15529028909712_en-US.png)


## **Test an alarm rule** {#section_i1t_qrl_v2b .section}

To verify that the MNS queues and function service set in your alarm rules function properly, you can use the system event alarm testing function to simulate the occurrence of system events.

1.  Go to the Alarm Rules tab page for event monitoring.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17722/15529028909690_en-US.png)

2.  Click **test** in the Actions column.
3.  Select an event to be tested. Content corresponding to the event you select will be displayed. You can modify displayed fields, such as Instance ID, so on, based on your requirements.
4.  Click **OK**, and the system will send an event based on the content, triggering the alarm notification, MNS queue, function service, and URL callback settings that you specified in your alarm rule.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17722/15529028909691_en-US.png)


