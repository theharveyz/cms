# ModifyHostAvailability {#doc_api_Cms_ModifyHostAvailability .reference}

You can call this operation to modify an availability monitoring task.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=ModifyHostAvailability) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|AlertConfig.NotifyType|Integer|Yes|2| The type of notifications. Valid values:

 -   2: phone call + text message + email + DingTalk Chatbot
-   1: text message + email + DingTalk Chatbot
-   0: email + DingTalk Chatbot

 |
|GroupId|Long|Yes|12345| The ID of the application group.

 |
|Id|Long|Yes|12345| The ID of the task.

 |
|TaskName|String|Yes|My test task| The name of the task.

 |
|Action|String|No|ModifyHostAvailability| The operation that you want to perform. Set the value to ModifyHostAvailability.

 |
|AlertConfig.EndTime|Integer|No|23| The end time of the alert period. Unit: hour. A value of 0 indicates 00:59.

 |
|AlertConfig.SilenceTime|Integer|No|86400| The duration of the mute period during which new alerts are not sent even if the trigger conditions are met. Unit: second. Default value: 86,400 \(one day \).

 |
|AlertConfig.StartTime|Integer|No|0| The start time of the alert period. Unit: hour. A value of 0 indicates 00:00.

 |
|AlertConfig.WebHook|String|No|http://www.aliyun.com/webhook.json| The URL callback address.

 |
|AlertConfigEscalationList.N.Aggregate|String|No|Value| The statistical method. Different statistical methods are used for different metrics:

 -   HttpStatus: Value
-   HttpLatency: Average
-   TelnetStatus: Value
-   TelnetLatency: Average
-   PingLostRate: Average

Value indicates the original value and is used for metrics such as status codes. Average indicates the average value and is used for metrics such as latency and packet loss rates.


 |
|AlertConfigEscalationList.N.MetricName|String|No|HttpStatus| The metrics for which alert is enabled. Valid values:

 -   HttpStatus \(HTTP status code\)
-   HttpLatency \(HTTP request timeout\)
-   TelnetStatus \(Telnet status code\)
-   TelnetLatency \(Telnet request timeout\)
-   PingLostRate \(Ping packet loss rate\)\)

 |
|AlertConfigEscalationList.N.Operator|String|No|\>| The comparison operator. Valid values:`>, >=, <, <=, and =.`

 |
|AlertConfigEscalationList.N.Times|Integer|No|3| The number of consecutive periods in which the metric value exceeds the threshold before an alert is triggered.

 |
|AlertConfigEscalationList.N.Value|String|No|3| The threshold of the metric value.

 |
|InstanceList.N|RepeatList|No|i-absdfkwl3212346| The list of the ECS instances used to initiate the test. A value of null indicates all the servers in the application group.

 |
|TaskOption.HttpMethod|String|No|GET| The method of HTTP tests. Valid values: GET, POST, and HEAD.

 |
|TaskOption.HttpNegative|Boolean|No|true| -   true: An alert is triggered if the specified content is included.
-   false: An alert is triggered if the specified content is excluded.

 |
|TaskOption.HttpResponseCharset|String|No|UTF-8| The response character set for HTTP tests.

 |
|TaskOption.HttpResponseMatchContent|String|No|ok| The response content to be matched.

 |
|TaskOption.HttpURI|String|No|http://www.aliyun.com| The URI used for HTTP tests.

 |
|TaskOption.TelnetOrPingHost|String|No|www.aliyun.com| The domain name or address to be tested. This parameter is required for Ping or Telnet tests.

 |
|TaskScope|String|No|GROUP| The scope of the task. Valid values:

 -   GROUP: The task is performed on all ECS instances in the group.
-   INSTANCE: The task is performed on one or more specified instances. If you select INSTANCE, you must set the InstanceList parameter.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200| The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success| The error message.

 |
|RequestId|String|ACBDBB40-DFB6-4F4C-8957-51FFB233969C| The request ID for troubleshooting.

 |
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=ModifyHostAvailability
&AlertConfig. NotifyType=2
&GroupId=12345
&Id=12345 
&TaskName=My test task
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<CreateHostAvailabilityResponse>
  <RequestId>ACBDBB40-DFB6-4F4C-8957-51FFB233969C</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</CreateHostAvailabilityResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"ACBDBB40-DFB6-4F4C-8957-51FFB233969C",
	"Success":true,
	"Code":200
}
```

## Error codes {#section_kq2_ewk_z9w .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

