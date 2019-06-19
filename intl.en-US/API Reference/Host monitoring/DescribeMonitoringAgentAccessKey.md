# DescribeMonitoringAgentAccessKey {#doc_api_Cms_DescribeMonitoringAgentAccessKey .reference}

You can call this operation to query the AccessKey ID and AccessKey Secret required for installing the CloudMonitor agent on a non-Alibaba Cloud ECS server.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentAccessKey) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeMonitoringAgentAccessKey|The operation that you want to perform. Set the value to DescribeMonitoringAgentAccessKey.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D|The request ID for troubleshooting.

 |
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|Successfully|The error message.

 |
|AccessKey|String|xxxxx|The AccessKey ID required to install the agent.

 |
|SecretKey|String|yyyyy|The AccessKey Secret required to install the agent.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitoringAgentAccessKey
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitoringAgentAccessKeyResponse>
  <AccessKey>xxxx</AccessKey>
  <SecretKey>yyyy</SecretKey>
  <Success>true</Success> 
  <Code>200</Code>
</DescribeMonitoringAgentAccessKeyResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"AccessKey":"xxxx",
	"SecretKey":"yyyy",
	"Success":true,
	"Code":200
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

