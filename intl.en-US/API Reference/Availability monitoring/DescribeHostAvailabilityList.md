# DescribeHostAvailabilityList {#doc_api_Cms_DescribeHostAvailabilityList .reference}

You can call this operation to query the list of availability monitoring tasks.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeHostAvailabilityList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeHostAvailabilityList|The operation that you want to perform. Set the value to DescribeHostAvailabilityList.

 |
|GroupId|Long|No|12345|The ID of the application group.

 |
|Id|Long|No|12346|The ID of the task.

 |
|PageNumber|Integer|No|1|The number of the page.

 |
|PageSize|Integer|No|10|The number of records on each page.

 |
|TaskName|String|No|My test|The name of the task.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|CE26797C-1094-47E6-B651-73AA888F5873|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|TaskList| | |The list of tasks.

 |
|└AlertConfig| | |The configuration of the alert rule.

 |
|└EndTime|Integer|23|The time when the task ends.

 |
|└EscalationList| | |The trigger condition of the alert rule.

 |
|└Aggregate|String|Value|The statistical method. Different statistical methods are used for different metrics:

 -   HttpStatus: Value
-   HttpLatency: Average
-   TelnetStatus: Value
-   TelnetLatency: Average
-   PingLostRate: Average

 Value indicates the original value and is used for metrics such as status codes. Average indicates the average value and is used for metrics such as latency and packet loss rates.

 |
|└MetricName|String|HttpStatus|-   HttpStatus \(HTTP status code\)
-   HttpLatency \(HTTP request timeout\)
-   TelnetStatus \(Telnet status code\)
-   TelnetLatency \(Telnet request timeout\)
-   PingLostRate \(Ping packet loss rate\) \)

 |
|└Operator|String|\>|The comparison operator. Valid values: `>, >=, <, <=, and =`.

 |
|└Times|String|2|The number of consecutive periods in which the metric value exceeds the threshold before an alert is triggered.

 |
|└Value|String|99|The threshold of the metric.

 |
|└NotifyType|Integer|1|The type of notifications. Valid values:

 -   2: phone call + text message + email + DingTalk Chatbot
-   1: text message + email + DingTalk Chatbot
-   0: email + DingTalk Chatbot

 |
|└SilenceTime|Integer|86400|The duration of the mute period during which new alerts are not sent even if the trigger conditions are met. Unit: second. Default value: 86,400 \(one day \).

 |
|└StartTime|Integer|0|The start time. Unit: hour. A value of 0 indicates 00:00.

 |
|└WebHook|String|http://www.aliyun.com|The URL callback address.

 |
|└Disabled|Boolean|false|Indicates whether task monitoring is disabled. A value of true indicates that task monitoring is disabled. A value of false indicates that task monitoring is enabled.

 |
|└GroupId|Long|12345|The ID of the application group.

 |
|└GroupName|String|Application group name|The name of the application group.

 |
|└Id|Long|123|The ID of the task.

 |
|└Instances| |i-a2d5q7pm3f123y456|The list of ECS instances that initiate the test.

 |
|└TaskName|String|My intranet test|The name of the task.

 |
|└TaskOption| | |The parameter option of the task.

 |
|└HttpKeyword|String|ok|The response content to be matched in HTTP tests.

 |
|└HttpMethod|String|GET|The method of HTTP tests. Valid values: GET, POST, and HEAD.

 |
|└HttpNegative|Boolean|true|-   true: An alert is triggered if the specified content is included.
-   false: An alert is triggered if the specified content is excluded.

 |
|└HttpResponseCharset|String|UTF-8|The response character set for HTTP tests.

 |
|└HttpURI|String|http://www.aliyun.com|The URI used for HTTP tests.

 |
|└TelnetOrPingHost|String|ssh.aliyun.com|The domain name or address to be tested. This parameter is required for Ping or Telnet tests.

 |
|└TaskScope|String|GROUP|The scope of the task. Valid values:

 -   INSTANCE: The task is performed on one or more specified instances.
-   GROUP: The task is performed on all instances in the group.
-   GROUP\_SPEC\_INSTANCEUP\_SPEC\_INSTANCE: The task is performed on one or more specified instances in the group.

 |
|└TaskType|String|HTTP|The type of the task. Valid values: PING, TELNET, and HTTP.

 |
|Total|Integer|12|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeHostAvailabilityList
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeHostAvailabilityListResponse>
  <TaskList>
    <NodeTaskConfig>
      <GroupName>My application group</GroupName>
      <TaskOption>
        <HttpMethod>GET</HttpMethod>
        <HttpURI>http://www.aliyun.com</HttpURI>
      </TaskOption>
      <Disabled>false</Disabled>
      <Instances> 
        <Instance>i-a2d5q7pm3f123y***</Instance>
        <Instance>i-a2d5q7pm3f123x***</Instance>
      </Instances> 
      <Id>123345</Id>
      <AlertConfig>
        <EscalationList>
          <escalationList>
            <Value>400</Value>
            <MetricName>HttpStatus</MetricName>
            <Operator>&gt;</Operator>
            <Times>3</Times>
            <Aggregate>Value</Aggregate>
          </escalationList>
          <escalationList>
            <Value>500</Value>
            <MetricName>HttpLatency</MetricName>
            <Operator>&gt;</Operator>
            <Times>3</Times>
            <Aggregate>Average</Aggregate> 
          </escalationList>
        </EscalationList>
        <SilenceTime>86400</SilenceTime> 
        <NotifyType>1</NotifyType>
        <EndTime>24</EndTime>
        <StartTime>0</StartTime>
      </AlertConfig>
      <TaskType>HTTP</TaskType>
      <TaskName>My intranet test task</TaskName>
      <GroupId>12345</GroupId>
      <TaskScope>GROUP</TaskScope>
    </NodeTaskConfig>
  </TaskList>
  <RequestId>CE26797C-1094-47E6-B651-73AA888F5873</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
  <Total>3</Total>
</DescribeHostAvailabilityListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"TaskList":{
		"NodeTaskConfig":[
			{
				"GroupName":"My application group",
				"Disabled":false,
				"TaskOption":{
					"HttpMethod":"GET",
					"HttpURI":"http://www.aliyun.com"
				},
				"Instances":{
					"Instance":[
						"i-a2d5q7pm3f123y***",
						"i-a2d5q7pm3f123x***"
					]
				},
				"Id":123345,
				"AlertConfig":{
					"EscalationList":{
						"escalationList":[
							{
								"Value":"400",
								"MetricName":"HttpStatus",
								"Operator":">",
								"Times":3,
								"Aggregate":"Value"
							},
							{
								"Value":"500",
								"MetricName":"HttpLatency",
								"Operator":">",
								"Times":3,
								"Aggregate":"Average"
							}
						]
					},
					"NotifyType":1,
					"SilenceTime":86400,
					"EndTime":24,
					"StartTime":0
				},
				"TaskName":"My intranet test task",
				"TaskType":"HTTP",
				"TaskScope":"GROUP",
				"GroupId":12345
			}
		]
	},
	"RequestId":"CE26797C-1094-47E6-B651-73AA888F5873",
	"Success":true,
	"Code":200,
	"Total":3
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

