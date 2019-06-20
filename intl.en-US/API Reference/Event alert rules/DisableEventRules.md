# DisableEventRules {#doc_api_Cms_DisableEventRules .reference}

You can call this operation to disable one or more event alert rules.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DisableEventRules) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DisableEventRules|The operation that you want to perform. Set the value to DisableEventRules.

 |
|RuleNames.N|RepeatList|Yes|ruleName1|The name of the alert rule. Valid values of N: 1 to 20.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|3FD0E8B5-F132-4F4E-A081-2878AF378B12|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DisableEventRules
&RuleNames. 1=ruleName1
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DisableEventRulesResponse>
  <RequestId>3FD0E8B5-F132-4F4E-A081-2878AF378B12</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DisableEventRulesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"3FD0E8B5-F132-4F4E-A081-2878AF378B12",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

