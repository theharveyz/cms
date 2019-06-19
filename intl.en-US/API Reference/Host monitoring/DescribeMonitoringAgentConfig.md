# DescribeMonitoringAgentConfig {#doc_api_Cms_DescribeMonitoringAgentConfig .reference}

You can call this operation to query the configuration of the CloudMonitor agent.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentConfig) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeMonitoringAgentConfig| The operation that you want to perform. Set the value to DescribeMonitoringAgentConfig.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D| The request ID for troubleshooting.

 |
|AutoInstall|Boolean|true| Indicates whether to enable automatic installation of the CloudMonitor agent.

 |
|EnableInstallAgentNewECS|Boolean|false| Indicates whether to automatically install the CloudMonitor agent for new ECS instances.

 |
|Message|String|Successfully| The error message.

 |
|Code|String|200| The status code. A value of 200 indicates that the call is successful.

 |
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|EnableActiveAlert|String|redis,rds,ecs| The name of the service for which one-click alert is enabled.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitoringAgentConfig
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitoringAgentConfigResponse>
  <UserId>12345****</UserId>
  <EnableInstallAgentNewECS>false</EnableInstallAgentNewECS>
  <Success>true</Success> 
  <ErrorCode>200</ErrorCode> 
  <EnableActiveAlert>redisa,rds,ecs</EnableActiveAlert>
  <AutoInstall>true</AutoInstall>
</DescribeMonitoringAgentConfigResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"UserId":"12345****",
	"ErrorCode":200,
	"Success":true,
	"EnableInstallAgentNewECS":false,
	"AutoInstall":true,
	"EnableActiveAlert":"redis,rds,ecs"
}
```

## Error code {#section_hkk_jhy_2za .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

