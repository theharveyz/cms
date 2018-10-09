# ListAlarm {#reference_fv1_lkv_zdb .reference}

## Description {#section_epg_mkv_zdb .section}

Query specified or all alarm rule settings.

## Request Parameters {#section_hnv_mkv_zdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Required.|The parameter specified by the system. Value:  ListAlarm|
|Namespace|String|Required|Product name. For more information, see the projects for various products, such as acs\_ecs\_dashboard and acs\_rds\_dashboard, acs\_rds\_dashboard|
|Id|String|Optional|Alarm rule ID|
|Name|String|Optional|Alarm rule name, with fuzzy search supported|
|Dimensions|String|Optional|Instance information associated with the alarm rule, which is a JSON object string. for example, \{“instance”:”name1”\}.  This field is used to query all the rules associated with the instance, and Namespace must be specified when this field is used.|
|state|String|Optional|Alarm rule status, ALARM, INSUFFICIENT\_DATA，OK.|
|IsEnable|Boolean|Optional|true indicates that the alarm rule is enabled, and false indicates that the rule is disabled.|
|PageNumber|Int|Optional|Page number, default: 1.|
|PageSize|Int|Optional|Number of records on every page. Default value: 100|

## Response parameter {#section_afv_nkv_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|NextToken|Integer|Next page. Null indicates there is only one page.|
|AlarmList|List|Alarm rule details list|
|Total|Integer|Total number of compliant data items|
|Success|Boolean|Whether the request is successful|
|RequestId|String|Requested UUID, which is used for log query|
|Code|String|Request failure status code. The value 200 indicates that the request is successful, and a non-200 value indicates that the request fails|
|Message|String|Request failure prompt message|

**Alarm parameters**

|Name|Type|Description|
|:---|:---|:----------|
|Id|String|Alarm rule ID|
|Name|String|Alarm rule name|
|namespace|String|Product corresponding to the alarm rule|
|metricName|String|Monitoring metric corresponding to the alarm rule|
|Dimensions|String|List of instances associated with the alarm rule, which is a string corresponding to the JSON array, for example, \[\{“instanceId”:”name1”\} and \{“instance”:”name2”\}\] array, for example, \[\{“instanceId”:”name1”\} and \{“instance”:”name2”\}\]|
|Period|Int|Monitoring metric query cycle, in seconds|
|Statistics|String|Statistical method, for example, Average, Maximum, or Minimum|
|ComparisonOperator|String|Comparison operator|
|Threshold|String|Threshold|
|EvaluationCount|Int|An alarm is triggered when the monitoring data has been detected to exceed the threshold for this specified consecutive times. Default value: three consecutive times|
|ContactGroups|String|The contact group of the alarm rule, which is a string corresponding to the JSON array, for example, \[“Contact Group 1” and “Contact Group 2”\]|
|StartTime|Int|Start time of the effective period|
|EndTime|Int|End time of the effective period|
|SilenceTime|Int|Silence period in the alarm state, in seconds|
|NotifyType|Int|Notification type. The value 0 indicates that a notification is sent by TradeManager+email, and the value 1 indicates TradeManager+email+SMS|
|Enable|Boolean|Whether the alarm rule is enabled. “true” indicates that it is enabled|
|State|String|Alarm rule status. ALARM indicates that an alarm is triggered for one instance, INSUFFICIENT\_DATA indicates that no data exists, and OKindicates a condition other than the preceding two|

## Example {#section_ld3_4kv_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=ListAlarm
&PageSize=2
&Dimension=%7B%22instanceId%22%3A%22 i-abcdefgh123456%22%7D
&Namespace=acs_ecs_dashboard
&PageNumber=1
&<Common Request Parameters>
```

**Response example**

-   XML format

    ```
    <ListAlarmResponse>
      <NextToken>2</NextToken>
      <RequestId>CC2CDD2B-4EA5-43CD-BEE3-758E93C36B7F</RequestId>
      <AlarmList>
        <Alarm>
          <period>1</period>
          <Statistics>Average</Statistics>
          <Name>ecs_cpu_total</Name>
          <MetricName>cpu_total</MetricName>
          <State>OK</State>
          <Threshold>90</Threshold>
          <Enable>true</Enable>
          <SilenceTime>86400</SilenceTime>
          <NotifyType>1</NotifyType>
          <Dimensions>["{\"instanceId\":\" i-abcdefgh123456\"}"]</Dimensions>
          <Namespace>acs_ecs_dashboard</Namespace>
          <ContactGroups>["test4nudou"]</ContactGroups>
          <Id>putNewAlarm_group_e8da18b9-bc95-4edf-a8bf-159eb6c8286b</Id>
          <EndTime>24</EndTime>
          <StartTime>2011-06-11Z</StartTime>
          <ComparisonOperator>&gt;=</ComparisonOperator>
        </Alarm>
        <Alarm>
          <Period>300</Period>
          <Statistics>Average</Statistics>
          <Name>ecs_diskusage_utilization</Name>
          <MetricName>diskusage_utilization</MetricName>
          <State>OK</State>
          <Threshold>90</Threshold>
          <Enable>true</Enable>
          <SilenceTime>86400</SilenceTime>
          <NotifyType>1</NotifyType>
          <Dimensions>["{\"instanceId\":\" i-abcdefgh123456\"}"]</Dimensions>
          <Namespace>acs_ecs_dashboard</Namespace>
          <ContactGroups>["test4nudou"]</ContactGroups>
          <Id>putNewAlarm_group_3233eba5-0dd4-4e80-a5d5-7399dec3d7cc</Id>
          <EndTime>24</EndTime>
          <StartTime>0</StartTime>
          <ComparisonOperator>&gt;=</ComparisonOperator>
        </Alarm>
      </AlarmList>
      <Success>true</Success>
      <Code>200</Code>
      <Total>27</Total>
    ```

-   JSON format

    ```
    {
        "NextToken": 2, 
        "RequestId": "EFD27F56-5799-4CE8-B625-56DF3332331C", 
        "AlarmList": {
            "Alarm": [
                {
                    "Period": 300, 
                    "Statistics": "Average", 
                    "Name": "ecs_cpu_total", 
                    "MetricName": "cpu_total", 
                    "State": "OK", 
                    "Threshold": "90", 
                    "Enable": true, 
                    "SilenceTime": 86400, 
                    "NotifyType": 1, 
                    "Dimensions": "[\"{\\\"instanceId\\\":\\\" i-abcdefgh123456\\\"}\"]", 
                    "Namespace": "acs_ecs_dashboard", 
                    "ContactGroups": "[\"test4nudou\"]", 
                    "Id": "putNewAlarm_group_e8da18b9-bc95-4edf-a8bf-159eb6c8286b", 
                    "EndTime": 24, 
                    "Starttime": 0, 
                    "ComparisonOperator": ">="
                }, 
                {
                    "Period": 300, 
                    "Statistics": "Average", 
                    "Name": "ecs_diskusage_utilization", 
                    "MetricName": "diskusage_utilization", 
                    "State": "OK", 
                    "Threshold": "90", 
                    "Enable": true, 
                    "SilenceTime": 86400, 
                    "NotifyType": 1, 
                    "Dimensions": "[\"{\\\"instanceId\\\":\\\" i-abcdefgh123456\\\"}\"]", 
                    "Namespace": "acs_ecs_dashboard", 
                    "ContactGroups": "[\"test4nudou\"]", 
                    "Id": "putNewAlarm_group_3233eba5-0dd4-4e80-a5d5-7399dec3d7cc", 
                    "Endtime": 24, 
                    "Starttime": 0, 
                    "ComparisonOperator": ">="
                }
            ]
        }, 
        "Success": true, 
        "code": "200", 
        "total": 2
    }
    ```


