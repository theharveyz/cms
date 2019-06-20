# PutEventRuleTargets {#doc_api_Cms_PutEventRuleTargets .reference}

You can call this operation to create or modify notification methods for an alert rule.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=PutEventRuleTargets) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PutEventRuleTargets|The operation that you want to perform. Set the value to PutEventRuleTargets.

 |
|RuleName|String|Yes|testEventRule|The name of the alert rule.

 |
|ContactParameters.N.ContactGroupName|String|No|Default alert contact group|The name of the alert contact group. Valid values of N: 1 to 5.

 |
|ContactParameters.N.Id|String|No|2|The unique ID of the alert contact group notification. Valid values of N: 1 to 5.

 |
|ContactParameters.N.Level|String|No|3|The method of alert notification. Valid values: 2, 3, and 4.

 -   2: DingTalk Chatbot and email.
-   3: DingTalk Chatbot and email.
-   4: DingTalk Chatbot and email.

 Valid values of N: 1 to 5.

 |
|FcParameters.N.FunctionName|String|No|fc-test|The name of the function. Valid values of N: 1 to 5.

 |
|FcParameters.N.Id|String|No|1|The unique ID of the Function Compute notification. Valid values of N: 1 to 5.

 |
|FcParameters.N.Region|String|No|cn-hangzhou|The region where Function Compute is deployed. Valid values of N: 1 to 5.

 |
|FcParameters.N.ServiceName|String|No|fc-test|The name of the Function Compute service. Valid values of N: 1 to 5.

 |
|MnsParameters.N.Id|String|No|3|The unique ID of the Message Service \(MNS\) notification. Valid values of N: 1 to 5.

 |
|MnsParameters.N.Queue|String|No|queue1|The name of the MNS queue. Valid values of N: 1 to 5.

 |
|MnsParameters.N.Region|String|No|cn-hangzhou|The region where MNS is deployed. Valid values of N: 1 to 5.

 |
|SlsParameters.N.Id|String|No|5|The unique ID of the Log Service notification. Valid values of N: 1 to 5.

 |
|SlsParameters.N.LogStore|String|No|testlogstore|The logstore corresponding to Log Service. Valid values of N: 1 to 5.

 |
|SlsParameters.N.Project|String|No|testproject|The project corresponding to Log Service. Valid values of N: 1 to 5.

 |
|SlsParameters.N.Region|String|No|cn-hangzhou|The region where Log Service is deployed. Valid values of N: 1 to 5.

 |
|WebhookParameters.N.Id|String|No|4|The unique ID of the HTTP callback notification.

 |
|WebhookParameters.N.Method|String|No|GET|The request method of the HTTP callback. Valid values: GET and POST. Valid values of N: 1 to 5.

 |
|WebhookParameters.N.Protocol|String|No|http|The name of the protocol. Valid values of N: 1 to 5.

 |
|WebhookParameters.N.Url|String|No|http://www.aliyun.com|The callback URL. Valid values of N: 1 to 5.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|RequestId|String|409C64DA-CF14-45DF-B463-471C790DD15A|The request ID for troubleshooting.

 |
|Message|String|success|The error message.

 |
|FailedParameterCount|String|2|The number of error parameters.

 |
|FailedFcParameters| | |This field is returned if a function failed to be created.

 |
|└FunctionName|String|functionTest1|The name of the function.

 |
|└Id|Integer|1|The unique ID of the Function Compute notification.

 |
|└Region|String|cn-hangzhou|The region where Function Compute is deployed.

 |
|└ServiceName|String|serviceTest1|The name of the Function Compute service.

 |
|FailedMnsParameters| | |This field is returned if MNS failed to be created.

 |
|└Id|Integer|2|The unique ID of the MNS notification.

 |
|└Queue|String|testQueue|The name of the MNS queue.

 |
|└Region|String|cn-hangzhou|The region where MNS is deployed.

 |
|FailedContactParameters| | |This field is returned if an alert contact group fails to be created.

 |
|└ContactGroupName|String|Default alert contact group|The name of the alert contact group.

 |
|└Id|Integer|2|The unique ID of the alert contact group notification.

 |
|└Level|String|3|The method of alert notification. Valid values: 2, 3, and 4.

 -   2: DingTalk Chatbot and email.
-   3: DingTalk Chatbot and email.
-   4: DingTalk Chatbot and email.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=PutEventRuleTargets
&RuleName=testEventRule
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<PutEventRuleTargetsResponse>
  <RequestId>409C64DA-CF14-45DF-B463-471C790DD15A</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</PutEventRuleTargetsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"409C64DA-CF14-45DF-B463-471C790DD15A",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

