# DeleteMonitorGroupNotifyPolicy {#doc_api_Cms_DeleteMonitorGroupNotifyPolicy .reference}

You can call this operation to delete an alert notification pause policy for an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMonitorGroupNotifyPolicy) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteMonitorGroupNotifyPolicy|The operation that you want to perform. Set the value to DeleteMonitorGroupNotifyPolicy.

 |
|PolicyType|String|Yes|PauseNotify|The type of paused notifications. Valid value: PauseNotify.

 |
|GroupId|String|No|12345|The ID of the application group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|B7AF834D-D38B-4A46-920B-FE974EB7E135|The request ID for troubleshooting.

 |
|Result|Integer|1|The number of returned results.

 |
|Success|String|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteMonitorGroupNotifyPolicy
&PolicyType=PauseNotify
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteMonitorGroupNotifyPolicyResponse>
  <Result>1</Result>
  <Success>true</Success> 
  <Code>200</Code>
</DeleteMonitorGroupNotifyPolicyResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Result":2,
	"RequestId":"5D0D3910-5B01-4868-A2F2-A5DEA7F5150E",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

