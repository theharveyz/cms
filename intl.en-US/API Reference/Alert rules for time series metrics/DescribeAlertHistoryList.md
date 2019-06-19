# DescribeAlertHistoryList {#doc_api_Cms_DescribeAlertHistoryList .reference}

You can call this operation to obtain the alert history.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeAlertHistoryList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|DescribeAlertHistoryList|The operation that you want to perform. Set the value to DescribeAlertHistoryList.

 |
|AlertStatus|String|No|ALARM|The alert status. Valid values:

 -   ALARM: The current resource has at least one active alert.
-   OK: The current resource does not have active alerts.

 |
|Ascending|Boolean|No|true|The order of sorting. true indicates reverse chronological order and false indicates chronological order.

 |
|EndTime|String|No|1554085998000|The time when the alert is cleared.

 |
|GroupId|String|No|123456|The ID of the application group.

 |
|MetricName|String|No|cpu\_total|The name of the metric.

 |
|Namespace|String|No|acs\_ecs\_dashboard|The data namespace of the service. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~).

 |
|Page|Integer|No|1|The number of the page.

 |
|PageSize|Integer|No|10|The number of records on each page.

 |
|RuleId|String|No|aaaabbb123|The ID of the alert rule.

 |
|RuleName|String|No|My alert rule|The name of the alert rule.

 |
|StartTime|String|No|1554085998000|The time when an alert was triggered.

 |
|State|String|No|2|The status of alert notifications. Valid values:

 -   2: Alert notification is muted.
-   0: An alert is triggered or cleared.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description |
|---------|----|-------|------------|
|AlarmHistoryList| | |The list of historical alerts.

 |
|└AlertName|String|My alert rule|The name of the alert rule.

 |
|└AlertState|String|OK|The alert status. Valid values:

 -   OK: The current resource does not have active alerts.
-   ALARM: The current resource has at least one active alert.

 |
|└AlertTime|Long|1554105040000|The time when an alert was triggered.

 |
|└ContactALIIMs| |My TradeManager|The TradeManager alert notification.

 |
|└ContactGroups| |Alert contact group|The alert contact group.

 |
|└ContactMails| |xxx@aliyun.com|The email address of the alert recipient.

 |
|└ContactSmses| |1333333\*\*\*\*|The list of mobile phone numbers of text alert recipients.

 |
|└Contacts| |My alert contacts|The alert contacts.

 |
|└Dimensions|String|\{"instanceId":"i-2zebwilv3xfdg1\*\*\*\*"\}|The associated resources.

 |
|└EvaluationCount|Integer|2|The consecutive number of times for which the matric value exceeds the threshold before an alert is triggered.

 |
|└Expression|String|$Average\>=1|The metric expression, which defines when an alert is triggered.

 |
|└GroupId|String|12345|The ID of the application group.

 |
|└InstanceName|String|ali-186xxxx123456|The ID of the instance.

 |
|└LastTime|Long|347020693|The time when the status last changed.

 |
|└Level|String|P3|The alert level. Valid values:

 -   p2: DingTalk Chatbot and email
-   p3: DingTalk Chatbot and email
-   p4: DingTalk Chatbot and email

 |
|└MetricName|String|cpu\_total|The name of the metric. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~).

 |
|└Namespace|String|acs\_ecs\_dashboard|The data namespace of the service. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~).

 |
|└RuleId|String|d97a65a7-70d2-4a8a-97bf-1a9147\*\*\*\*|The ID of the alert rule.

 |
|└RuleName|String|My alerts|The name of the alert rule.

 |
|└Status|Integer|2|The status of alert notifications. Valid values:

 -   2: Alert notification is muted.
-   0: An alert is triggered or cleared.

 |
|└Value|String|5.39|The metric value when an alert was triggered or cleared.

 |
|└Webhooks|String|http://www.aliyun.com/webhook.html|The callback URL.

 |
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|189B35DD-68BA-43CE-A66A-57F0BE12C885|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Total|String|2|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeAlertHistoryList
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeAlertHistoryListResponse>
  <AlarmHistoryList>
    <AlarmHistory>
      <Value>4.41</Value>
      <LastTime>881140083</LastTime>
      <Webhooks/>
      <ContactSmses/>
      <RuleName>test-auto-scaling-0001</RuleName>
      <GroupId/>
      <AlertName>putNewAlarm_xxxxxx</AlertName>
      <EvaluationCount>1</EvaluationCount>
      <Status>2</Status> 
      <AlertState>ALARM</AlertState>
      <MetricName>cpu_total#60</MetricName>
      <ContactMails/>
      <AlertTime>1554986620000</AlertTime>
      <Dimensions>{"instanceId":"i-2******3"}</Dimensions>
      <RuleId/>
      <Contacts/>
      <Namespace>acs_ecs</Namespace>
      <ContactALIIMs/>
      <ContactGroups/>
      <Expression>$Average&gt;=1</Expression>
      <Level>P3</Level>
      <InstanceName/>
    </AlarmHistory>
    <AlarmHistory>
      <Value>2.13</Value>
      <LastTime>760058</LastTime>
      <Webhooks/>
      <ContactSmses/>
      <RuleName>test-auto-scaling-0001</RuleName>
      <GroupId/>
      <AlertName>putNewAlarm_us****</AlertName> 
      <EvaluationCount>1</EvaluationCount>
      <Status>2</Status> 
      <AlertState>ALARM</AlertState>
      <MetricName>cpu_total#60</MetricName>
      <ContactMails/>
      <AlertTime>1554986620000</AlertTime>
      <Dimensions>{"instanceId":"i-2z*****"}</Dimensions>
      <RuleId/>
      <Contacts/>
      <Namespace>acs_ecs</Namespace>
      <ContactALIIMs/>
      <ContactGroups/>
      <Expression>$Average&gt;=1</Expression>
      <Level>P3</Level>
      <InstanceName/>
    </AlarmHistory>
  </AlarmHistoryList>
  <RequestId>FEBE3561-166F-4DB2-BB59-020B26F30318</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
  <Total>102390</Total>
</DescribeAlertHistoryListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"AlarmHistoryList":{
		"AlarmHistory":[
			{
				"Value":"4.41",
				"LastTime":881140083,
				"Webhooks":"",
				"ContactSmses":{
					"ContactSms":[]
				},
				"RuleName":"test-auto-scaling-0001",
				"GroupId":"",
				"AlertName":"putNewAlarm_xxxxxx",
				"EvaluationCount":1,
				"Status":2,
				"AlertState":"ALARM",
				"MetricName":"cpu_total#60",
				"ContactMails":{
					"ContactMail":[]
				},
				"AlertTime":1554986620000,
				"Dimensions":"{\"instanceId\":\"i-2******3\"}",
				"RuleId":"",
				"Namespace":"acs_ecs",
				"Contacts":{
					"Contact":[]
				},
				"Level":"P3",
				"Expression":"$Average>=1",
				"ContactGroups":{
					"ContactGroup":[]
				},
				"ContactALIIMs":{
					"ContactALIIM":[]
				},
				"InstanceName":""
			},
			{
				"Value":"2.13",
				"LastTime":760058,
				"Webhooks":"",
				"ContactSmses":{
					"ContactSms":[]
				},
				"RuleName":"test-auto-scaling-0001",
				"GroupId":"",
				"AlertName":"putNewAlarm_us****",
				"EvaluationCount":1,
				"Status":2,
				"AlertState":"ALARM",
				"MetricName":"cpu_total#60",
				"ContactMails":{
					"ContactMail":[]
				},
				"AlertTime":1554986620000,
				"Dimensions":"{\"instanceId\":\"i-2z*****\"}",
				"RuleId":"",
				"Namespace":"acs_ecs",
				"Contacts":{
					"Contact":[]
				},
				"Level":"P3",
				"Expression":"$Average>=1",
				"ContactGroups":{
					"ContactGroup":[]
				},
				"ContactALIIMs":{
					"ContactALIIM":[]
				},
				"InstanceName":""
			}
		]
	},
	"RequestId":"FEBE3561-166F-4DB2-BB59-020B26F30318",
	"Success":true,
	"Code":"200",
	"Total":102390
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

