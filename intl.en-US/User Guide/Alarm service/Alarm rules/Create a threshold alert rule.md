# Create a threshold alert rule {#concept_ugq_4v4_mgb .concept}

This topic describes how to create a threshold alert rule so that you can receive alert notification when a metric value reaches the threshold, and handle the exception in a timely manner.

## Background information {#section_of3_pv4_mgb .section}

You can create threshold alert rules to manage and monitor the usage and operation of cloud service resources. When a metric value reaches the threshold, you will receive alert notification. This way, you can trace exceptions as they occur and automate handling of the exceptions in a timely manner.

## Prerequisites {#section_l5j_pv4_mgb .section}

We recommend that you create an alert contact and alert contact group before creating a threshold alert rule. When you create an alert rule, you can select the alert contact group as the alert notification receiver. For more information about how to create an alert contact and an alert contact group, see [Create an alert contact and an alert contact group](reseller.en-US/User Guide/Alarm service/Alarm contacts/Create an alert contact and an alert contact group.md#).

If you want to use alert callback in alert rules, you must prepare a callback URL that is accessible from the Internet. In addition, you must enable URL callback as a notification method in the existing O&M or message notification system.

## Procedure {#section_wfl_pv4_mgb .section}

 **Precautions** 

Alert notification can be sent through phone calls, text messages, emails, TradeManager messages, or DingTalk Chatbot. If you want to receive alert notification through multiple methods, be sure to enter correct information when configuring alert contacts.

 **Procedure** 

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Rules**. On the Alarm Rules page that appears, the **Threshold Value Alarm** tab is displayed by default.
3.  Click **Create Alarm Rule**. The Create Alarm Rule page is displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/111649/155659286537632_en-US.png)

4.  Select a resource range, set alert rule parameters, and select a notification method. Click **OK**.

 **Parameter description** 

-   Product: Select a cloud service, such as ECS, RDS, or OSS.
-   Resource Range: Select the resources to which the alert rule applies. You can choose from All Resources and Instance.
    -   All Resources: indicates that the alert rule applies to all your instances of the specified service. For example, you set Resource Range to All Resources and the alert threshold for MongoDB CPU utilization to 80%. The alert rule is hit when the CPU utilization of any of your MongoDB instances is greater than 80%. If you set Resource Range to All Resources, the alert rule is applied to up to 1,000 instances. If there are more than 1,000 instances, you may not receive alert notification when the specified metric reaches the threshold. We recommend that you add resources to service-specific application groups before creating alert rules.
    -   Instance: indicates that the alert rule only applies to a specific instance. For example, if you set Resource Range to Instance and the alert threshold for ECS CPU utilization to 80%. The alert rule is hit when the ECS CPU utilization of the specified instance is greater than 80%.
-   Rule Name: the name of the alert rule.
-   Rule Description: the content of the alert rule. It defines the metric data conditions in which an alert is triggered. For example, the rule description is the average CPU utilization in 5 minutes is greater than or equal to 90%. The rule is hit if the average CPU utilization in 5 minutes is greater than or equal to 90%.

    **Alert rule example**: In ECS monitoring, a data point on the metric of a single server is reported every 15 seconds. 20 data points are reported in 5 minutes.

    -   Average CPU utilization in 5 minutes greater than 90% means the average value of the 20 data points on CPU utilization that are reported in 5 minutes is greater than 90%.
    -   CPU utilization in 5 minutes always greater than 90% means the values of all the 20 data points on CPU utilization that are reported in 5 minutes are greater than 90%.
    -   CPU utilization in 5 minutes greater than 90% for once means the value of at least one of the 20 data points on CPU utilization that are reported in 5 minutes is greater than 90%.
    -   Total Internet outbound traffic in 5 minutes greater than 50 Mbit/s indicates the sum of the values of the 20 data points on Internet outbound traffic in 5 minutes is greater than 50 Mbit/s.
-   Muted For: the period when your alert rule is muted so that no new alerts for the rule are sent even if the conditions specified in the rule are met.
-   Triggered when threshold is exceeded for: the number of times a rule must be hit before an alert is sent. For example, the rule description is "average CPU utilization in 1 minute greater than 80%, three consecutive times." The rule is hit if the average CPU utilization in 1 minute is greater than 80% for three consecutive times.
-   Effective Time: the period when the alert rule is effective. The metric data is check against the alert rule only when the alert rule is effective.
-   Notification Object: the alert contact group to which alert notification is sent.
-   Alarm Level:
    -   Email + DingTalk Chatbot
-   Email Subject: the service name + metric name + instance ID by default.
-   Email Remarks: custom supplementary information of an alert email. The remarks are sent together with the alert notification email.
-   Alarm Callback: a URL that is accessible from the Internet. CloudMonitor pushes the alert notification to this address by using the POST request. Currently, only HTTP is supported.

## More information {#section_fqp_13p_mgb .section}

-   [Create an alert callback](reseller.en-US/User Guide/Alarm service/Alarm rules/Create an alert callback.md#)
-   [Create and use alert templates](reseller.en-US/User Guide/Alarm service/Use alarm templates.md#)
-   [Use one-click alert](reseller.en-US/User Guide/Alarm service/Use one-click alert.md#)

