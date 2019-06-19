# DescribeMonitoringAgentProcesses {#doc_api_Cms_DescribeMonitoringAgentProcesses .reference}

You can call this operation to query the process monitoring list.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentProcesses) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|DescribeMonitoringAgentProcesses|The operation that you want to perform. Set the value to DescribeMonitoringAgentProcesses.

 |
|InstanceId|String|Yes|i-xx12\*\*\*\*|The ID of the instance.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|Successfully|The error message.

 |
|NodeProcesses| | |The list of processes.

 |
|└Command|String|number|The command used to obtain information about a specified process. Valid values:

 -   number: the number of processes that match the condition.
-   detail: returns the information of the processes that match the condition.

 |
|└InstanceId|String|host-12xxx|The ID of the instance.

 |
|└ProcessId|Long|123456|The ID of the process.

 |
|└ProcessName|String|http|The name of the process.

 |
|└ProcessUser|String|admin|The user who started the process.

 |
|RequestId|String|971CC023-5A96-452A-BB7C-2483F948BCFD|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitoringAgentProcesses
&InstanceId=i-xx12****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitoringAgentProcessesResponse>
  <NodeProcesses>
    <NodeProcess>
      <Command>number</Command>
      <InstanceId>host-123aaaa</InstanceId>
      <ProcessName>http</ProcessName>
      <ProcessId>123455</ProcessId>
    </NodeProcess>
    <NodeProcess>
      <Command>number</Command>
      <InstanceId>host-123aaaa</InstanceId>
      <ProcessName>nginx</ProcessName>
      <ProcessId>123456</ProcessId>
    </NodeProcess>
  </NodeProcesses>
  <Success>true</Success> 
  <Code>200</Code>
</DescribeMonitoringAgentProcessesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"NodeProcesses":{
		"NodeProcess":[
			{
				"Command":"number",
				"InstanceId":"host-123aaaa",
				"ProcessId":123455,
				"ProcessName":"http"
			},
			{
				"Command":"number",
				"InstanceId":"host-123aaaa",
				"ProcessId":123456,
				"ProcessName":"nginx"
			}
		]
	},
	"Success":true,
	"Code":200
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

