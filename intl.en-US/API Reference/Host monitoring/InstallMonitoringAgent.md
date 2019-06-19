# InstallMonitoringAgent {#doc_api_Cms_InstallMonitoringAgent .reference}

You can call this operation to install the CloudMonitor agent for the specified ECS instance. This operation is not applicable to non-Alibaba Cloud ECS servers.

For more information about the agent, see [CloudMonitor GoLang agent introduction](~~99300~~).

Ensure that the [Server Guard agent](~~28451~~) is installed on your instance before calling this operation. The Server Guard agent is integrated into security images and installed by default on purchased ECS instances. You can log on to the Server Guard console to view the status of the agent on each server.

The success rate of installing the CloudMonitor agent by calling this operation is about 95%. If the installation fails, you can log on to the host for manual installation. For more information, see [Install the CloudMonitor GoLang agent](~~97929~~).

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=InstallMonitoringAgent) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|InstanceIds.N|RepeatList|Yes|i-123\*\*\*\*|The ID of the ECS instance.

 |
|Action|String|No|InstallMonitoringAgent|The operation that you want to perform. Set the value to InstallMonitoringAgent.

 |
|Force|Boolean|No|true|Indicates whether to force install. Default value: true.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|Successfully|The installation error message.

 |
|RequestId|String|host-abc12356|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=InstallMonitoringAgent
&InstanceIds. 1=i-123****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<InstallMonitoringAgentResponse>
  <Success>true</Success> 
  <Code>200</Code>
</InstallMonitoringAgentResponse>

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

