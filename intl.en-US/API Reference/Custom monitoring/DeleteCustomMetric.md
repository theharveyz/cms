# DeleteCustomMetric {#doc_api_Cms_DeleteCustomMetric .reference}

You can call this operation to delete the monitoring data of a custom metric.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteCustomMetric) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteCustomMetric|The operation that you want to perform. Set the value to DeleteCustomMetric.

 |
|GroupId|String|Yes|12345|The ID of the application group.

 |
|MetricName|String|Yes|cpu|The name of the metric.

 |
|Md5|String|No|38796C8CFFEB8F89BB2A626C7BD79FD3|The MD5 verification code. It is returned when you query the monitoring list.

 |
|UUID|String|No|5497633c-66c5-4eae-abaa-89db5adb\*\*\*\*|The unique identifier of a metric. It is returned when you query a custom metric.

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

http(s)://[Endpoint]/? Action=DeleteCustomMetric
&GroupId=12345
&MetricName=cpu
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteCustomMetricResponse>
  <Message>success</Message>
  <RequestId>05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0</RequestId>
  <Code>200</Code>
</DeleteCustomMetricResponse>

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

