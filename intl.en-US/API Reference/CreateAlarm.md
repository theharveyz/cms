# CreateAlarm {#reference_x3v_shv_zdb .reference}

## Description {#section_fy4_33v_zdb .section}

Create alarm rules for one or more instances.

## Request parameters {#section_ljd_k3v_zdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|A parameter specified by the system. Value: CreateAlarm.|
|Name|String|Yes|Alarm rule name|
|Namespace|String|Yes|Product name. For details, see the projects for each product, for example, acs\_ecs\_dashboard and acs\_rds\_dashboard.|
|MetricName|String|Yes|Metric name of a product. For details, see the metrics defined for each product.|
|Dimensions|String|Yes|List of instances associated with an alarm rule. The list is a string corresponding to the JSON array, for example, \[\{“instanceId”:”name1”\},\{“iinstance”:”name2”\}\].|
|Period|Integer|No|Index query period, which must be the same as that defined for metrics. Default value: 300, in seconds.|
|Statistics|String|Yes|Statistical method, for example, Average. The statistical method must be the same as that defined for metrics.|
|ComparisonOperator|String|Yes|Alarm comparison operator, which must be one of the following: <=,<,\>,\>=,==,! =|
|Threshold|String|Yes|Alarm threshold, which must be a numeric value|
|EvaluationCount|Int|No|Number of consecutive times that the threshold is exceeded. Default value: 3.|
|ContactGroups|String|Yes|The contact group of an alarm rule. The group must already exist in the console as a string corresponding to the JSON array, for example, \[Contact Group 1, Contact Group 2\].|
|StartTime|Int|No|Time when an alarm takes effect. Default value: 0, indicating that the alarm takes effect at 00:00.|
|EndTime|Int|No|Time when an alarm expires. Default value: 24, indicating that the alarm expires at 24:00.|
|SilenceTime|Int|No|Notification silence period in alarm state, in seconds. Default value: 86400. Minimum value: 3600.|
|NotifyType|Int|No|Notification type. The value 0 indicates Ali WangWang + Email ID, and the value 1 indicates Ali WangWang + Email ID + Message.|
|Webhook|String|No|A callback function that supports only Internet addresses. For details, see [Create an alarm callback](../../../../intl.en-US/User Guide/Alarm Service/Alarm callback.md#).|

## Response parameters {#section_nr5_l3v_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|Data|String|Returned alarm rule ID|
|Success|Boolean|Indicates whether a request is sent successfully.|
|RequestId|String|Request UUID, which is used for querying logs|
|Code|String|Request failure status code. The value 200 indicates that the request is sent successfully, and other values indicate that the request failed to be sent.|
|Message|String|Request failure message|

## Examples {#section_vrl_s3v_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/
Data content of a POST request body:
Name: test_alarm
Namespace: acs_ecs_dashboard
MetricName: vm.MemoryUtilization
Dimensions：[{"instanceId":"<your_ instanceId >","userId":"<your_ userId >"}]
Period: 900
Statistics: Average
ComparisonOperator: <=
Threshold: 35
EvaluationCount: 2
ContactGroups: ["testgroup"]
StartTime: 6
EndTime: 20
NotifyType: 1
```

**Response examples**

-   XML format

    ```
    <CreateAlarmResponse>
      <Data>576fbae7-2fd1-411a-ae13-6f09f4fafdde</Data>
      <RequestId>58C699ED-84BE-44D5-B55F-84AFE73932AB</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </CreateAlarmResponse>
    ```

-   JSON format

    ```
    {
        "Data": "0c4af0f1-a864-468b-bed3-15c7deff75ee", 
        "RequestId": "910ABE4E-DC9D-4231-9DC0-C96835553327", 
        "Success": true, 
        "Code": "200"
    }
    ```


