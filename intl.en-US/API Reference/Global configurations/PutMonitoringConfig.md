# PutMonitoringConfig {#doc_api_Cms_PutMonitoringConfig .reference}

You can call this operation to make global configurations for the CloudMonitor agent. For example, you can enable automatic agent installation or one-click alert.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=PutMonitoringConfig) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PutMonitoringConfig|The operation that you want to perform. Set the value to PutMonitoringConfig.

 |
|AutoInstall|Boolean|No|true|Indicates whether to automatically install the agent for existing ECS instances.

 |
|EnableInstallAgentNewECS|Boolean|No|true|Indicates whether to enable automatic agent installation for newly-purchased ECS instances.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=PutMonitoringConfig
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<PutMonitoringConfigResponse>
  <RequestId>E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</PutMonitoringConfigResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

