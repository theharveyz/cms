# UninstallMonitoringAgent {#doc_api_Cms_UninstallMonitoringAgent .reference}

You can call this operation to uninstall the CloudMonitor agent.

This operation is not applicable to Alibaba Cloud ECS servers.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=UninstallMonitoringAgent) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|InstanceId|String|Yes|i-xx12\*\*\*\*| The ID of the ECS instance.

 |
|Action|String|No|UninstallMonitoringAgent| The operation that you want to perform. Set the value to UninstallMonitoringAgent.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200| The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|Successfully| The error message.

 |
|RequestId|String|466902B9-2842-40B0-B796-00FE772B6EF3| The request ID for troubleshooting.

 |
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=UninstallMonitoringAgent
&InstanceId=i-xx12****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<UninstallMonitoringAgentResponse>
  <RequestId>466902B9-2842-40B0-B796-00FE772B6EF3</RequestId>
  <Code>200</Code>
  <Message>Successfully</Message>
</UninstallMonitoringAgentResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"Successfully",
	"RequestId":"466902B9-2842-40B0-B796-00FE772B6EF3",
	"Code":"200"
}
```

## Error code {#section_mmi_ub7_e6k .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

