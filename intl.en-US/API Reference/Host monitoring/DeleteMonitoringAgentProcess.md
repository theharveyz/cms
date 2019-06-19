# DeleteMonitoringAgentProcess {#doc_api_Cms_DeleteMonitoringAgentProcess .reference}

You can call this operation to disable monitoring on a process.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMonitoringAgentProcess) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|InstanceId|String|Yes|i-KpVny6l\*\*\*\*|The ID of the instance.

 |
|Action|String|No|DeleteMonitoringAgentProcess|The operation that you want to perform. Set the value to DeleteMonitoringAgentProcess.

 |
|ProcessId|String|No|12345|The ID of the process. You must specify either the ProcessId or the ProcessName parameter.

 |
|ProcessName|String|No|http|The name of the process. You must specify either the ProcessId or the ProcessName parameter.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|Successfully|The error message.

 |
|RequestId|String|971CC023-5A96-452A-BB7C-2483F948BCFD|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteMonitoringAgentProcess
&InstanceId=i-KpVny6l****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteMonitoringAgentProcessResponse>
  <Success>true</Success> 
  <Code>200</Code>
</DeleteMonitoringAgentProcessResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Success":true,
	"Code":200
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

