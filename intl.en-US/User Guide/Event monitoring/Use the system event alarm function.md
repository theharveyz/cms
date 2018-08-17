# Use the system event alarm function {#concept_dpn_bkd_v2b .concept}

## **Scenario** {#section_sfc_gkd_v2b .section}

When the Alibaba Cloud product encounters a system abnormality, the alarm function of event monitoring provides you with the following two notification capabilities, so that you can know the event and automate the abnormality handling in time:

-   Provides alarms for the event by means of voice calls, text messages, emails, and DingTalk group.
-   Distributes the event to the user's MNS queue, function service, and URL callback.

## **Create an alarm rule** {#section_jry_jkd_v2b .section}

1.  Log on to the [CloudMonitor console](https://cloudmonitor.console.aliyun.com).
2.  In the left navigation pane, select **Event Monitoring**.
3.  On the **Alarm Rules** tab page, click **Create event alerts** in the upper right corner. The **Create / modify event alerts** dialog box appears.
4.  In the **Basic Information** area, fill in the alarm rule name.
5.  In the **Event alert** area, complete the following information:
    1.  Event Type: Select **System Event**.
    2.  Product Type, Event Level, Event Name: fill in according to the actual situation
    3.  Resource Range: If you select **All Resources**, notifications are sent in accordance with the configuration for any resource-related events. If you select **Application Groups**, notifications are sent only when the event occurs for the resources in the specified group.
6.  Select the **Alarm type**. CloudMonitor supports four alarm types: alarm notification, MNS queue, function service, and URL callback.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17722/15344923879712_en-US.png)

## **Test an alarm rule** {#section_i1t_qrl_v2b .section}

You can use the testing function of the system event to simulate the occurrence of system events, so as to verify whether the MNS queue set in the alarm rule can receive the time normally, and whether the function of Function Compute can be triggered normally.

1.  Go to the Alarm Rules tab page for event monitoring.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17722/15344923879690_en-US.png)
2.  Click **test** in the Actions column.
3.  Select the event to be tested. The corresponding event content will be displayed. You can change such fields as the instance ID in the content according to the actual situation.
4.  Click **OK**. The system will send an event based on the content, triggering alarm notification, MNS queue, function service, and URL callback set in the alarm rule.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17722/15344923879691_en-US.png)

