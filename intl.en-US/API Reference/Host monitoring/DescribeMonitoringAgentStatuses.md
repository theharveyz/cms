# DescribeMonitoringAgentStatuses {#doc_api_Cms_DescribeMonitoringAgentStatuses .reference}

You can call this operation to query the status of the CloudMonitor agent.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentStatuses) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|InstanceIds|String|Yes|i-12345w55tr2rcpejp\*\*\*\*,i-23456w55tr2rcpejp\*\*\*\*|The ID of the instance of which the status is to be obtained. Multiple instance IDs must be separated with commas \(,\).

 |
|Action|String|No|DescribeMonitoringAgentStatuses|The operation that you want to perform. Set the value to DescribeMonitoringAgentStatuses.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description |
|---------|----|-------|------------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|Successfully|The error message.

 |
|NodeStatusList| | |The status list.

 |
|└AutoInstall|Boolean|true|Indicates whether to enable automatic installation.

 |
|└InstanceId|String|i-123456w55tr2rcpejp\*\*\*\*|The ID of the instance.

 |
|└Status|String|running|The status of the agent. Valid values: running and stopped.

 |
|RequestId|String|E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitoringAgentStatuses
&InstanceIds=i-12345w55tr2rcpejp****,i-23456w55tr2rcpejp****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitoringAgentStatusesResponse>
  <NodeStatusList>
    <NodeStatus>
      <Status>running</Status> 
      <InstanceId>i-123455cpejp****</InstanceId>
      <AutoInstall>true</AutoInstall>
    </NodeStatus>
    <NodeStatus>
      <Status>running</Status> 
      <InstanceId>i-123567kg04****</InstanceId>
      <AutoInstall>true</AutoInstall>
    </NodeStatus>
  </NodeStatusList>
  <Success>true</Success> 
  <Code>200</Code>
</DescribeMonitoringAgentStatusesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"NodeStatusList":{
		"NodeStatus":[
			{
				"Status":"running",
				"InstanceId":"i-123455cpejp****",
				"AutoInstall":true
			},
			{
				"Status":"running",
				"InstanceId":"i-123567kg04****",
				"AutoInstall":true
			}
		]
	},
	"Success":true,
	"Code":200
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

