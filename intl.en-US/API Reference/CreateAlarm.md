# CreateAlarm {#reference_x3v_shv_zdb .reference}

## Description {#section_fy4_33v_zdb .section}

You can create alarm rule for one or more instances.

## Request Parameters {#section_ljd_k3v_zdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The parameter specified by the system. Value: CreateAlarm|
|Name|String|Required|Alarm rule name|
|Namespace|String|Required|Product name. For more information, see the projects for various products, such as acs\_ecs\_dashboard, acs\_rds\_dashboard|
|MetricName|String|Required|The name of the monitoring item corresponding to the corresponding product, based on the metric definition of each product|
|Dimensions|String|Required|List of instances associated with the alarm rule, which is a string corresponding to the JSON  array, for example, \[\{“instanceId”:”name1”\} and \{“iinstance”:”name2”\}\]|
|Period|Integer|Optional|Index query cycle, which must be consistent with that defined for metrics; default value: 300, in seconds|
|Statistics|String|Required|Statistical method, for example, Average, which must be consistent with that defined for metrics|
|ComparisonOperator|String|Required|Alarm comparison operator, which must be <=,<,\>,\>=,==,! =|
|Threshold|String|Required.|Alarm threshold value, which must be a numeric value currently|
|EvaluationCount|Int|Optional|Number of consecutive times it has been detected that the values exceed the threshold; default value: three times|
|ContactGroups|String|Required.|The contact group of the alarm rule, which must have been created on the console as a string corresponding to the JSON array,  for example, \[“Contact Group 1” and “Contact Group 2”\]|
|StartTime|Int|Optional|Start time of the alarm effective period; default value: 0, which indicates the time 00:00|
|EndTime|Int|Optional|End time of the alarm effective period; default value: 24, which indicates the time 24:00|
|SilenceTime|Int|Optional|Notification silence period in the alarm state, in seconds; default value: 86,400; minimum value: 1 hour|
|NotifyType|Int|Optional|Notification type. The value 0 indicates TradeManager+email, and the value 1 indicates that TradeManager+email+SMS|

## Response parameter {#section_nr5_l3v_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|Data|String|Returned alarm rule ID|
|Success|Boolean|Whether the request is successful|
|RequestId|String|Requested UUID, which is used for log query|
|Code|String|Request failure status code. The value 200 indicates that the request is successful, and a non-200 value indicates that the request is failed|
|Message|String|Request failure prompt message|

## Example {#section_vrl_s3v_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/
Data content of a POST request body:
Name: test_alarm
Namespace: acs_ecs_dashboard
MetricName: vm.MemoryUtilization
Dimensions：[{"instanceId":"<your_ instanceId >","userId":"<your_ userId >"}]
Period：900
Statistics：Average
ComparisonOperator：<=
Threshold：35
EvaluationCount：2
ContactGroups：["testgroup"]
StartTime：6
EndTime：20
NotifyType：1
```

**Response example**

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


