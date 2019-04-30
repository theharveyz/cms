# Create an alert callback {#concept_fw5_ptn_vdb .concept}

This topic describes how to create an alert callback to integrate CloudMonitor alerts to your existing O&M or message system.

## Background information {#section_e3m_r31_hgb .section}

CloudMonitor provides the alert callback feature for alert notification in addition to the methods such as emails, and DingTalk Chatbot. Alert callback allows O&M engineers and developers to handle alert events flexibly.

CloudMonitor pushes alerts to a specified Internet URL through HTTP POST requests. You can take actions based on received notification.

## Prerequisites {#section_n5y_ck1_hgb .section}

-   You have a callback URL that is accessible through the Internet.
-   URL callback is enabled as an alert notification method in your existing O&M or message system.

## Procedure {#section_igt_2k1_hgb .section}

**Precautions**

-   According to the retry policy of alert callback, the number of retries is 3 and the timeout period is 5 seconds.
-   Currently, only HTTP is supported.

**Procedure**

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Modify an existing alert rule by creating a callback or create an alert rule.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6225/155659569335880_en-US.png)

3.  In the notification method section, enter the URL address for alert callback and click **OK**. When an alert rule is triggered, CloudMonitor sends an alert to your specified URL.

## Callback parameters {#section_ar4_qps_vdb .section}

The following table lists the content of a POST request that is pushed when an alert rule calls back a URL.

|Parameter|Data type|Description|
|---------|---------|-----------|
|userId|String|The user ID.|
|alertName|String|The alert name.|
|timestamp|String|The time stamp when the alert is generated.|
|alertState|String|The alert state. One of the following states is returned: OK, ALERT, and INSUFFICIENT\_DATA.|
|dimensions|String|The object that has triggered the alert. For example: \[\{"userId":"12345","instanceId":"i-12345"\}\]|
|expression|String|The alert conditions. For example, \[\{"expression":"$value\>12","level":4,"times":2\}\] indicates that an alert is triggered when the threshold value is greater than 12 for two consecutive times. If the value of level is 4, an alert is sent to you through an email. If the value of level is 3, an alert is sent to you through a text message and an email. The times field indicates the number of consecutive times of reaching the alert threshold that you selected when configuring the alert rule.|
|curValue|String|The current value of the metric when an alert is triggered or cleared.|
|metricName|String|The metric name.|
|metricProject|String|The service name. For more information about the metric and service names, see [Preset metrics reference](../../../../reseller.en-US/API Reference/Preset metric reference.md#).|

An example of a POST request is as follows:

```
{
    "userId":"12345",
    "alertName":"putNewAlarm_group_a37cd898-ea6b-4b7b-a8a8-de017a8327f6",
    "timestamp":"1508136760",
    "alertState":"ALARM",
    "dimensions":[
        {
            "userId":"12345",
            "instanceId":"i-12345"
        }
    ],
   "expression":"[{\"expression\":\"$Average>90\",\"level\":4,\"times\":2}]" , 
    "curValue":"95",
    "metricName":"CPUUtilization",
    "metricProject":"acs_ecs_dashboard"
}
```

