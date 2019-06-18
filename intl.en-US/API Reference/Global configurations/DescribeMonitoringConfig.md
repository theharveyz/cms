# DescribeMonitoringConfig {#doc_api_Cms_DescribeMonitoringConfig .reference}

You can call this operation to query the global configurations of the CloudMonitor agent. For example, you can query whether automatic agent installation or one-click alert is enabled.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringConfig) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeMonitoringConfig| The operation that you want to perform. Set the value to DescribeMonitoringConfig.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Code|String|200| The status code. A value of 200 indicates that the call is successful.

 |
|RequestId|String|F35654DB-0C9D-4FB3-903F-479BA7663061| The request ID for troubleshooting.

 |
|Message|String|success| The error message.

 |
|EnableInstallAgentNewECS|Boolean|true| Indicates whether to enable automatic agent installation for newly-purchased ECS instances.

 |
|AutoInstall|Boolean|true| Indicates whether to automatically install the agent for existing ECS instances.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitoringConfig
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitoringConfigResponse>
  <ActiveAlertProducts>rds,opensearch,ecs</ActiveAlertProducts>
  <EnableInstallAgentNewECS>false</EnableInstallAgentNewECS>
  <Success>true</Success> 
  <Code>200</Code>
  <AutoInstall>true</AutoInstall>
</DescribeMonitoringConfigResponse> 

```

`JSON` format

``` {#json_return_success_demo}
{
	"ActiveAlertProducts":"rds,opensearch,ecs",
	"RequestId":"",
	"Success":true,
	"EnableInstallAgentNewECS":false,
	"Code":200,
	"AutoInstall":true
}
```

## Error codes {#section_s5p_59v_rlj .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

