# EnableMetricRules {#doc_api_Cms_EnableMetricRules .reference}

You can call this operation to enable one or more alert rules.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=EnableMetricRules) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|RuleId.N|RepeatList|Yes|ab05733c97b7ce239fb1b53393dc1697c123\*\*\*\*|The ID of the alert rule.

 |
|Action|String|No|EnableMetricRules|The operation that you want to perform. Set the value to EnableMetricRules.

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

http(s)://[Endpoint]/? Action=EnableMetricRules
&RuleId. 1=ab05733c97b7ce239fb1b53393dc1697c123****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<EnableMetricRulesResponse>
  <Code>200</Code>
  <Message>success</Message>
  <RequestId>FF38D33A-67C1-40EB-AB65-FAEE51EDB644</RequestId>
  <Success>true</Success> 
</EnableMetricRulesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"FF38D33A-67C1-40EB-AB65-FAEE51EDB644",
	"Success":true,
	"Code":200
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

