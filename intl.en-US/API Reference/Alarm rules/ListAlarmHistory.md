# ListAlarmHistory {#reference_zpd_h2v_zdb .reference}

## Description {#section_hjn_p2v_zdb .section}

Query historical alarms.

## Request Parameters {#section_o2g_q2v_zdb .section}

|Name|Type|Required or not|Description|
|:---|:---|:--------------|:----------|
|Action|String|Yes|The parameter specified by the system. Value: ListAlarmHistory|
|Id|String|Optional|ID of the alarm rule.|
|Size|Int|Optional|Number of records on every page. Default value: 100.|
|StartTime|String|Optional|Start time of data query. The default start time is 24 hours earlier than the current time. The time can be in the long time format or yyyy-MM-dd  HH:mm:ss format|
|EndTime|String|Optional|End time of data query. The default end time is the current time. The time can be in the long time format or yyyy-MM-dd HH:mm:ss format|
|Cursor|String|Optional|Start position of data query. If it is null, the system queries the first 100 data items by time|

## Response parameter {#section_nnc_r2v_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|AlarmHistoryList|List|List of historical alarm details|
|Cursor|String|Data on the next page. If it is null, pages are unavailable|
|Success|Boolean|Whether the request is successful|
|RequestId|String|Requested UUID, which is used for log query|
|Code|String|Request failure status code. The value 200indicates that the request is successful, and a non-200value indicates that the request fails|
|Message|String|Request failure prompt message|

**History parameters**

|Name|Type|Description|
|:---|:---|:----------|
|Id|String|ID of the alarm rule.|
|Name|String|Name of the alarmt policy.|
|Namespace|String|Product name|
|MetricName|String|Metric name.|
|Dimension|String|Instance corresponding to the alarm rule, which is a JSON object string, for example, \{“instance”:”name1”\}|
|EvaluationCount|Int|An alarm is triggered when the monitoring data has been detected to exceed the threshold for this specified consecutive times|
|Value|String|Current value which triggers an alarm|
|AlarmTime|Long |Time of the alarm.|
|LastTime|Long |Alarm duration, in milliseconds|
|state|String|Alarm rule status, which can be OK, ALARM, or INSUFFICIENT\_DATA|
|Status|Integer|Notification sending status. 0 indicates that a notification has been sent to users, 1 indicates that no notification is sent because the current time is not within the effective period, and 2 indicates that no notification is sent because the current time is within the alarm silence period|
|ContactGroups|String|The contact group of the alarm rule, which is a string corresponding to the JSON  array, for example, \[“Contact Group 1” and “Contact Group 2”\]. This field is valid only when status is set to 0|

## Example {#section_nw3_s2v_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=ListAlarmHistory
&EndTime=2017-03-16+15%3A00%3A00
&Size=3
&StartTime=2017-02-20+10%3A50%3A00
&Id=1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed
&<Common Request Parameters>
```

**Response example**

-   XML format

    ```
    <ListAlarmHistoryResponse>
      <AlarmHistoryList>
        <AlarmHistory>
          <Status>2</Status>
          <Value>{"Maximum":301,"Minimum":301}</Value>
          <MetricName>http.status_groupbyinstanceid#60</MetricName>
          <State>ALARM</State>
          <LastTime>122088</LastTime>
          <AlarmTime>1489568222088</AlarmTime>
          <Namespace>acs_sitemonitor</Namespace>
          <ContactGroups>null</ContactGroups>
          <Id>1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed</Id>
          <EvaluationCount>3</EvaluationCount>
        </AlarmHistory>
        <AlarmHistory>
          <Status>0</Status>
          <Value>{"Maximum":301,"Minimum":301}</Value>
          <MetricName>http.status_groupbyinstanceid#60</MetricName>
          <State>ALARM</State>
          <LastTime>62078</LastTime>
          <AlarmTime>1489568162078</AlarmTime>
          <Namespace>acs_sitemonitor</Namespace>
          <ContactGroups>["alarm contact"]</ContactGroups>
          <Id>1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed</Id>
          <EvaluationCount>3</EvaluationCount>
        </AlarmHistory>
      </AlarmHistoryList>
      <RequestId>7E7A6173-EC07-43A1-ABBF-1F05EBB4C2BB</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </ListAlarmHistoryResponse>
    ```


-   JSON format

    ```
    {
        "AlarmHistoryList": {
            "AlarmHistory": [
                {
                    "Status": 2, 
                    "Value": "{\"Maximum\":301,\"Minimum\":301}", 
                    "MetricName": "http.status_groupbyinstanceid#60", 
                    "State": "ALARM", 
                    "LastTime": 122088, 
                    "AlarmTime": 1489568222088, 
                    "Namespace": "acs_sitemonitor", 
                    "ContactGroups": "null", 
                    "Id": "1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed", 
                    "EvaluationCount": 3
                }, 
                {
                    "Status": { 
                    "Value": "{\"Maximum\":301,\"Minimum\":301}", 
                    "MetricName": "http.status_groupbyinstanceid#60", 
                    "State": "ALARM", 
                    "LastTime": 62078, 
                    "Armtime": 1489568162078, 
                    "Namespace": "acs_sitemonitor", 
                    "ContactGroups": "[\"Alarm contact\"]", 
                    "Id": "1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed", 
                    "EvaluationCount": 3
                }
            ]
        }, 
        "RequestId": "1DBBCE29-0F69-435C-B65C-53D1011D1D72", 
        "Success": true, 
        "Code": "200"
    }
    ```


