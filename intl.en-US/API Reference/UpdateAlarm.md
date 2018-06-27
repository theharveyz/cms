# UpdateAlarm {#reference_j3t_2gz_zdb .reference}

## Description {#section_qrc_kgz_zdb .section}

Modify an existing alarm rule.

## Request Parameters {#section_snm_kgz_zdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Required|The parameter specified by the system. Value: UpdateAlarm|
|Id|String|Mandatory|ID of the alarm rule|
|name|String|Optional|Alarm rule name|
|Period|Integer|Optional|Index query cycle, which must be consistent with that defined for metrics; default value: 300, in seconds|
|statistics|String|Optional|Value after modification|
|ComparisonOperator|String|Required|Alarm comparison operator, which must be <=,<,\>,\>=,==,! =|
|Threshold|String|Required|Alarm threshold value, which must be a numeric value currently|
|EvaluationCount|Int|Optional|Number of consecutive times it has been detected that the values exceed the threshold; default value: three times|
|ContactGroups|String|Mandatory|The contact group of the alarm rule, which must have been created on the console as a string corresponding to the JSON array, for example,  \[“Contact Group 1” and “Contact Group 2”\]|
|StartTime|Int|Optional|Start time of the alarm effective period; default value: 0, which indicates the time 00:00|
|EndTime|Int|Optional|End time of the alarm effective period; default value: 24, which indicates the time 24:00|
|SilenceTime|Int|Optional|Notification silence period in the alarm state, in seconds; default value: 86,400; minimum value: 1 hour|
|NotifyType|Int|Optional|Notification type. The value 0 indicates TradeManager+email, and the value 1 indicates that TradeManager+email+SMS|

## Response parameters {#section_o51_lgz_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|Success|Boolean|Whether the request is successful|
|RequestId|String|Requested UUID, which is used for log query|
|Code|String|Status code|
|Message|String|Request failure prompt message|

## Example {#section_bml_lgz_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=UpdateAlarm
&ComparisonOperator=%3E
&Name=test_modify
&Id=576fbae7-2fd1-411a-ae13-6f09f4fafdde
&Threshold=40
&<Common Request Parameters>
```

**Response example**

-   XML format

    ```
    <UpdateAlarmResponse>
      <RequestId>C08FADC4-CFDB-42F7-B9B8-0ED5391CD084</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </UpdateAlarmResponse>
    ```

-   JSON format

    ```
    {
        "RequestId": "945B9183-95C0-44FF-B30C-9ED37D44F6DC", 
        "Success": true, 
        "Code": "200"
    }
    ```


