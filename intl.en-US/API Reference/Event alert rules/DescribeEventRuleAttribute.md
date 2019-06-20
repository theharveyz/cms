# DescribeEventRuleAttribute {#doc_api_Cms_DescribeEventRuleAttribute .reference}

You can call this operation to query the details of an alert rule.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeEventRuleAttribute) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeEventRuleAttribute|The operation that you want to perform. Set the value to DescribeEventRuleAttribute.

 |
|RuleName|String|Yes|testRule|The name of the alert rule.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|9AA3F210-C03D-4C86-8DB6-21C84FF692A1|The request ID for troubleshooting.

 |
|Result| | |The details of the alert rule.

 |
|└Description|String|This is event monitoring|The description of the alert rule.

 |
|└EventPattern| | |The mode of the event mode. It describe the trigger conditions of this event.

 |
|└LevelList| |\["CRITICAL","WARN","INFO"\]|The severity of the alert rule. Valid values: CRITICAL, WARN, and INFO.

 |
|└NameList| |\*|The name of the event.

 |
|└Product|String|CloudMonitor|The name of the service.

 |
|└StatusList| |XX|The status of the event.

 |
|└EventType|String|SYSTEM|The type of the event. Valid values: SYSTEM and CUSTOM.

 |
|└GroupId|String|123456|The ID of the application group.

 |
|└Name|String|eventName1|The name of the alert rule.

 |
|└State|String|ENABLED|The status of the alert rule. Valid values: ENABLED and DISABLED.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeEventRuleAttribute
&RuleName=testRule
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeEventRuleAttributeResponse>
  <Result>
    <Name>newXXX</Name>
    <State>ENABLED</State>
    <EventPattern>
      <Product>CloudMonitor</Product>
      <LevelList>
        <LevelList>CRITICAL</LevelList>
        <LevelList>WARN</LevelList>
        <LevelList>INFO</LevelList>
      </LevelList>
      <NameList>
        <NameList>Group_AddResourcesFailed_QuotaReached</NameList>
        <NameList>Agent_Status_Stopped</NameList>
        <NameList>Agent_Status_Running</NameList>
      </NameList>
    </EventPattern>
    <EventType>SYSTEM</EventType>
  </Result> 
  <RequestId>E3E23D87-4AA7-4F1B-94DE-827D84661F64</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DescribeEventRuleAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Result":{
		"Name":"newXXX",
		"State":"ENABLED",
		"EventPattern":{
			"Product":"CloudMonitor",
			"LevelList":{
				"LevelList":[
					"CRITICAL",
					"WARN",
					"INFO"
				]
			},
			"NameList":{
				"NameList":[
					"Group_AddResourcesFailed_QuotaReached",
					"Agent_Status_Stopped",
					"Agent_Status_Running"
				]
			}
		},
		"EventType":"SYSTEM"
	},
	"RequestId":"E3E23D87-4AA7-4F1B-94DE-827D84661F64",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

