# Create a threshold alarm rule {#concept_ugq_4v4_mgb .concept}

This topic describes how to create a threshold alarm rule, so you can receive an alarm when a metric value reaches the specified threshold, and perform timely troubleshooting.

## Background {#section_of3_pv4_mgb .section}

You can create threshold alarm rules to manage and monitor the usage and operation of cloud service resources. When a metric value reaches the specified threshold, you can receive an alarm. In this way, you can be informed of exceptions and handle them efficiently.

## Prerequisites {#section_l5j_pv4_mgb .section}

We recommend that you create an alarm contact and an alarm contact group before creating a threshold alarm rule. When you create an alarm rule, you can select the alarm contact group as the alarm receiver. For more information about how to create an alarm contact and an alarm contact group, see [Create an alert contact and an alert contact group](reseller.en-US/User Guide/Alarm service/Alarm contacts/Create an alert contact and an alert contact group.md#).

If you want to use alarm callbacks in alarm rules, you must prepare a callback URL that is accessible on the Internet. In addition, you must enable the URL callback as a notification method in the existing operations and maintenance \(O&M\) or message notification system.

## Procedure {#section_wfl_pv4_mgb .section}

 **Note** 

CloudMonitor can notify you of alarms by means of phone calls, SMS messages, emails, TradeManager messages, or DingTalk ChatBot. If you want to receive alarms based on multiple methods, enter correct information when you configure alarm contacts.

 **Procedure** 

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Rules**. On the Alarm Rules page that appears, the **Threshold Value Alarm** tab page is displayed by default.
3.  Click **Create Alarm Rule** to go to the Create Alarm Rule page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/111649/156160338037632_en-US.png)

4.  Select a resource range, set alarm rule parameters, select a notification method, and then click **Confirm**. For more information about alarm rule parameters, see [Alarm rule parameters](reseller.en-US/User Guide/Alarm service/Alarm rules/Alarm rule parameters.md#).

## References {#section_fqp_13p_mgb .section}

-    [Create an alarm callback](reseller.en-US/User Guide/Alarm service/Alarm rules/Create an alert callback.md#) 
-    [Use alarm templates](reseller.en-US/User Guide/Alarm service/Use alarm templates.md#) 
-    [Use the Initiative Alarm feature](reseller.en-US/User Guide/Alarm service/Use one-click alert.md#) 

