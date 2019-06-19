# DescribeMetricRuleCount {#doc_api_Cms_DescribeMetricRuleCount .reference}

You can call this operation to obtain the numbers of alert rules by status.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleCount) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeMetricRuleCount|The operation that you want to perform. Set the value to DescribeMetricRuleCount.

 |
|MetricName|String|No|cpu\_total|The name of the metric. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~).

 |
|Namespace|String|No|acs\_ecs\_dashboard|The data namespace of the service. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~).

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|MetricRuleCount| | |The numbers of alert rules by status.

 |
|└Alarm|Integer|5|The number of alert rules based on which alerts were triggered and not cleared.

 |
|└Disable|Integer|0|The number of disabled alert rules.

 |
|└Nodata|Integer|0|The number of alert rules for which status data is unavailable.

 |
|└Ok|Integer|40|The number of alert rules that do not have active alerts triggered.

 |
|└Total|Integer|45|The total number of alert rules.

 |
|RequestId|String|FF38D33A-67C1-40EB-AB65-FAEE51EDB644|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMetricRuleCount
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMetricRuleCountResponse>
  <Success>true</Success> 
  <Code>200</Code>
  <RequestId>FF38D33A-67C1-40EB-AB65-FAEE51EDB644</RequestId>
  <MetricRuleCount>
    <Ok>40</Ok>
    <Disable>0</Disable>
    <Total>45</Total>
    <Nodata>0</Nodata>
    <Alarm>5</Alarm>
  </MetricRuleCount>
</DescribeMetricRuleCountResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"FF38D33A-67C1-40EB-AB65-FAEE51EDB644",
	"Success":true,
	"Code":"200",
	"MetricRuleCount":{
		"Ok":40,
		"Disable":0,
		"Nodata":0,
		"Total":45,
		"Alarm":5
	}
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

