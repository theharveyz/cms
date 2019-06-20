# PutEventRule {#doc_api_Cms_PutEventRule .reference}

You can call this operation to create or modify an event alert rule.

If an alert rule by the specified name does not exist, a new alert rule is created. Otherwise, the specified alert rule is modified.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=PutEventRule) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PutEventRule|The operation that you want to perform. Set the value to PutEventRule.

 |
|RuleName|String|Yes|myRuleName|The name of the alarm rule.

 |
|Description|String|No|My event alert test|The description of the alert rule.

 |
|EventPattern.N.EventTypeList.N|RepeatList|No|Exception|The type of the event. A value of \* indicates any type. Call DescribeSystemEventMeta to obtain a list of event types. Valid values of N: 1 to 50.

 |
|EventPattern.N.LevelList.N|RepeatList|No|CRITICAL|The severity of the event alert. Valid values: CRITICAL, WARN, INFO, and \* \(all severity levels\). Valid values of N: 1 to 50.

 |
|EventPattern.N.NameList.N|RepeatList|No|Agent\_Status\_Stopped|The name of the event. Call DescribeSystemEventMeta to obtain a list of event names. Valid values of N: 1 to 50.

 |
|EventPattern.N.Product|String|No|CloudMonitor|The name of the service. Call DescribeSystemEventMeta to obtain a list of service names. Valid values of N: 1 to 50.

 |
|EventPattern.N.StatusList.N|RepeatList|No|xxx|The status of the event. Call DescribeSystemEventMeta to obtain a list of event states. Valid values of N: 1 to 50.

 |
|EventType|String|No|SYSTEM|The type of the event alert. Valid values:

 -   SYSTEM
-   CUSTOM

 |
|GroupId|String|No|12345|The ID of the application group.

 |
|State|String|No|ENABLED|The status of the alert rule. Valid values:

 -   ENABLED
-   DISABLED

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Data|String|1|The number of rows affected by the creation.

 |
|Message|String|success|The error message.

 |
|RequestId|String|0B963550-5605-4AC6-93D9-FA7644D19FEF|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=PutEventRule
&RuleName=myRuleName
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<PutEventRuleResponse>
  <Data>1</Data>
  <RequestId>0B963550-5605-4AC6-93D9-FA7644D19FEF</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</PutEventRuleResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Data":"1",
	"RequestId":"0B963550-5605-4AC6-93D9-FA7644D19FEF",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

