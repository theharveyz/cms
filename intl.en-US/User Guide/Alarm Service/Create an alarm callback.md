# Create an alarm callback {#concept_fw5_ptn_vdb .concept}

The alarm callback feature allows you to integrate the alarm notifications sent by CloudMonitor into the existing operation and maintenance systems or message notification systems. CloudMonitor pushes alarm notifications to a specified public URL through the POST request of the HTTP protocol. When you receive an alarm notification, you can take actions according to the notification.

**Note:** The retry policy of alarm callback is three times, and the timeout duration is five seconds.

## Create an alarm callback {#section_r1b_4ps_vdb .section}

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  Select the alarm rule that you want to add a callback to.
3.  Enter the URL address to call back in the notification method.

## Callback parameters {#section_ar4_qps_vdb .section}

When an alarm rule calls back a URL address, the pushed POST request is as follows:

|Parameter|Data type|Description|
|---------|---------|-----------|
|userId|string|User ID|
|alertName|string|Alarm name|
|timestamp|string|Time stamp when the alarm is generated|
|alertState|string|Alarm status. One of three statuses is returned accordingly, namely, OK, ALERT, and INSUFFICIENT\_DATA.|
|dimensions|string|The object that has triggered an alarm. For example: \[\{“userId”:”12345”,”instanceId”:”i-12345”\}\]|
|expression|string|Alarm conditions. For example: \[\{“expression”:”$value\>12”,”level”:4,”times”:2\}\] which indicates that an alarm is triggered when the threshold value is greater than 12 for 2 times in a row. Level=4 means that the alarms are sent to you through email, and level=3 means that the alarms are sent to you through SMS and email. The times field indicates the number of consecutive times of reaching the alarm threshold that you selected when you set alarm rules.|
|curValue|string|The current value of the monitoring metrics when an alarm is triggered or cleared.|
|metricName|string|metricName|
|metricProject|string|Product name. For more information about metric items and product name, see [Preset metric item reference](../../../../reseller.en-US/API Reference/Preset metric item reference.md#).|

The following is an example of a POST request.

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
    "Curvalue": "95 ",
    "metricName":"CPUUtilization",
    "metricProject":"acs_ecs_dashboard"
}
```

