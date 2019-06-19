# DisableMetricRules {#doc_api_Cms_DisableMetricRules .reference}

You can call this operation to disable one or more alert rules.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DisableMetricRules) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DisableMetricRules|The operation that you want to perform. Set the value to DisableMetricRules.

 |
|RuleId.N|RepeatList|Yes|ab05733c97b7ce239fb1b53393dc1697c7e012\*\*\*\*|The ID of the alert rule. Valid values of N: 1 to 20.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|FF38D33A-67C1-40EB-AB65-FAEE51EDB644|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DisableMetricRules
&RuleId. 1=ab05733c97b7ce239fb1b53393dc1697c7e012****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DisableMetricRulesResponse>
  <Code>200</Code>
  <Message>success</Message>
  <RequestId>FF38D33A-67C1-40EB-AB65-FAEE51EDB644</RequestId>
  <Success>true</Success> 
</DisableMetricRulesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"FF38D33A-67C1-40EB-AB65-FAEE51EDB644",
	"Success":true,
	"Code":"200"
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

