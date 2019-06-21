# DescribeCustomMetricList {#doc_api_Cms_DescribeCustomMetricList .reference}

You can call this operation to query the monitoring data of a custom metric.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeCustomMetricList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCustomMetricList|The operation that you want to perform. Set the value to DescribeCustomMetricList.

 |
|GroupId|String|Yes|12345|The ID of the application group.

 |
|Dimension|String|No|xx|The dimension map. All key-value pairs are strings. A string can contain letters, digits, and connectors such as underscores \(\_\), hyphens \(-\), periods \(.\), forward slashes \(/\), and backslashes \(\\\). The maximum number of key-value pairs is 10. The maximum length of a key is 64 bytes. The maximum length of a value is 64 bytes. Excess characters will be truncated from the string.

 |
|Md5|String|No|97c25982d9745a231276bff27469fbc8|The MD5 verification code.

 |
|MetricName|String|No|cpu|The name of the metric.

 |
|PageNumber|String|No|1|The number of the current page.

 |
|PageSize|String|No|10|The number of records on each page.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|1C225028-B13B-4EFE-AE34-75C5F7412FB2|The request ID for troubleshooting.

 |
|Result|String|\{\\"param\\":\{\\"metric\\":\\"\{\\\\\\"project\\\\\\":\\\\\\"acs\_customMetric\_12345\\\\\\",\\\\\\"status\\\\\\":1\}\\",\\"service\\":\\"metrics.xxxxx.com\\"\},\\"data\\":\[\{\\"groupId\\":\\"111\\",\\"count\\":1\},\{\\"groupId\\":\\"111\\",\\"count\\":2\}\]\}|The monitoring data set.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCustomMetricList
&GroupId=12345
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeCustomMetricListResponse>
  <Code>200</Code>
  <Data>{"param":{"metric":"{\"project\":\"acs_customMetric_12345\",\"status\":1}","service":"metrics.xxxxx.com"},"data":[{"groupId":"111","count":1},{"groupId":"111","count":2}]}</Data> 
  <Message>success</Message>
  <Success>true</Success>
</DescribeCustomMetricListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Data":"{\"param\":{\"metric\":\"{\\\"project\\\":\\\"acs_customMetric_12345\\\",\\\"status\\\":1}\",\"service\":\"metrics.xxxxx.com\"},\"data\":[{\"groupId\":\"111\",\"count\":1},{\"groupId\":\"111\",\"count\":2}]}",
	"Message":"success",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

