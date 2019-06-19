# DeleteMetricRules {#doc_api_Cms_DeleteMetricRules .reference}

You can call this operation to delete one or more alert rules.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMetricRules) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Id.N|RepeatList|Yes|ab05733c97b7ce239fb1b53393dc1697c7e12\*\*\*\*|The ID of the alert rule.

 |
|Action|String|No|DeleteMetricRules|The operation that you want to perform. Set the value to DeleteMetricRules.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|E5599964-8D0D-40DC-8E90-27A619384B81|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteMetricRules
&Id. 1=ab05733c97b7ce239fb1b53393dc1697c7e12****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteMetricRulesResponse>
  <Code>200</Code>
  <Message>success</Message>
  <RequestId>FF38D33A-67C1-40EB-AB65-FAEE51EDB644</RequestId>
  <Success>true</Success> 
</DeleteMetricRulesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"E5599964-8D0D-40DC-8E90-27A619384B81",
	"Success":true,
	"Code":"200"
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

