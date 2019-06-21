# PutCustomMetric {#doc_api_Cms_PutCustomMetric .reference}

You can call this operation to obtain the monitoring data of one or more custom metrics.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=PutCustomMetric) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|PutCustomMetric|The operation that you want to perform. Set the value to PutCustomMetric.

 |
|MetricList.N.Dimensions|String|No|\{"sampleName1":"value1","sampleName2":"value2"\}|The dimension map. All key-value pairs are strings. A string can contain letters, digits, and connectors such as underscores \(\_\), hyphens \(-\), periods \(.\), forward slashes \(/\), and backslashes \(\\\). The maximum number of key-value pairs is 10. The maximum length of a key is 64 bytes. The maximum length of a value is 64 bytes. Excess characters will be truncated from the string.

 |
|MetricList.N.GroupId|String|No|12345|The ID of the application group.

 |
|MetricList.N.MetricName|String|No|cpu\_total|The name of the metric. A metric name can contain letters, digits, and connectors such as underscores \(\_\), hyphens \(-\), periods \(.\), forward slashes \(/\), and backslashes \(\\\). Other characters are invalid. The maximum length is 64 bytes. Excess characters will be truncated from the string.

 |
|MetricList.N.Period|String|No|60|The aggregation period. Unit: second.

 If the preceding Type parameter is set to 1, this field is required. Valid values: 60 and 300.

 |
|MetricList.N.Time|String|No|1508136760000|The time at which the metric value is generated. The timestamp can be in the "yyyyMMdd’T’HHmmss.SSSZ" format or long format, such as 20171012T132456.888+0800 or 1508136760000.

 |
|MetricList.N.Type|String|No|0|The type of the reported value. The value of 0 indicates raw data and the value of 1 indicates aggregate data.

 We recommend that data with the aggregation period as either 60s or 300s be reported. Otherwise, you will not be able to query monitoring data that is older than seven days.

 |
|MetricList.N.Values|String|No|\{"value":10.5\}|The collection of metric values. If the preceding MetricList.N.Type parameter is set to 0, the key must be "value" and raw data is reported. CloudMonitor aggregates raw data generated over the aggregation period into several values, such as maximum, count, and sum.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0|The request ID for troubleshooting.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=PutCustomMetric
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<PutCustomMetricResponse>
  <Message>success</Message>
  <RequestId>05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0</RequestId>
  <Code>200</Code>
</PutCustomMetricResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0",
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

