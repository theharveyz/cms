# CreateMonitorAgentProcess {#doc_api_Cms_CreateMonitorAgentProcess .reference}

You can call this operation to enable monitoring on a process.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=CreateMonitorAgentProcess) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|CreateMonitorAgentProcess|The operation that you want to perform. Set the value to CreateMonitorAgentProcess.

 |
|InstanceId|String|Yes|i-123\*\*\*\*|The ID of the instance.

 |
|ProcessName|String|Yes|java|The name of the process.

 |
|ProcessUser|String|No|admin|The user who started the process.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description |
|---------|----|-------|------------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Id|Long|123456|The ID of the process.

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

http(s)://[Endpoint]/? Action=CreateMonitorAgentProcess
&InstanceId=i-123****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<CreateMonitorAgentProcessResponse>
  <RequestId>971CC023-5A96-452A-BB7C-2483F948BCFD</RequestId>
  <Id>17****</Id>
  <Success>true</Success> 
  <Code>200</Code>
</CreateMonitorAgentProcessResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"971CC023-5A96-452A-BB7C-2483F948BCFD",
	"Id":"17****",
	"Success":true,
	"Code":200
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

