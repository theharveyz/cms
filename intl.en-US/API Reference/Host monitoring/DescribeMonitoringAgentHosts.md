# DescribeMonitoringAgentHosts {#doc_api_Cms_DescribeMonitoringAgentHosts .reference}

You can call this operation to obtain the list of hosts where the CloudMonitor agent is installed.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentHosts) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeMonitoringAgentHosts| The operation that you want to perform. Set the value to DescribeMonitoringAgentHosts.

 |
|HostName|String|No|hostNam1| The name of the host.

 |
|InstanceIds|String|No|i-a3d1q1pm2f9yr29e\*\*\*\*| The ID of the instance.

 |
|InstanceRegionId|String|No|cn-hangzhou| The regionId of the instance.

 |
|KeyWord|String|No|host1| The keyword to be fuzzily matched.

 |
|PageNumber|Integer|No|1| The number of pages.

 |
|PageSize|Integer|No|10| The number of records on each page.

 |
|SerialNumbers|String|No|a1ab31a3-1234-40f2-9e95-c8caa8f0\*\*\*\*| The serial number of the host to be found.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200| The status code. A value of 200 indicates that the call is successful.

 |
|Hosts| | | The list of hosts.

 |
|└AgentVersion|String|2.1.55| The version of the CloudMonitor agent.

 |
|└AliUid|Long|123456| The AccessKey ID of the Alibaba Cloud account.

 |
|└EipAddress|String|22.22.XX.XX| The EIP of the host.

 |
|└EipId|String|xxx| The ID of the EIP.

 |
|└HostName|String|hostIP| The name of the host.

 |
|└InstanceId|String|i-a2d5q7pm3f9yr212\*\*\*\*| The ID of the instance.

 |
|└InstanceTypeFamily|String|ecs.n4| The type of the ECS instance.

 |
|└IpGroup|String|12.23.XX.XX| The IP address of the host. Multiple addresses must be separated with commas \(,\).

 |
|└NatIp|String|22.22.XX.XX| The NAT IP address.

 |
|└NetworkType|String|vpc| The network type.

 |
|└OperatingSystem|String|Linux| The operating system.

 |
|└Region|String|cn-hangzhou| The name of the region.

 |
|└SerialNumber|String|x12335-6cc8-4a22-9f21-1a00a719\*\*\*\*| The serial number.

 |
|└isAliyunHost|Boolean|true| Indicates whether the current host is an Alibaba Cloud host.

 |
|Message|String|Successfully| The error message.

 |
|PageTotal|Integer|50| The number of pages.

 |
|RequestId|String|63EEBB2A-9E51-41E4-9E83-5DE7F3B292E0| The ID of the request.

 |
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Total|Integer|10| The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitoringAgentHosts
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitoringAgentHostsResponse>
  <PageTotal>1</PageTotal>
  <PageNumber>1</PageNumber> 
  <PageSize>100</PageSize>
  <Hosts>
    <Host>
      <AgentVersion>2.1.55</AgentVersion>
      <SerialNumber>x12335-6cc8-4a22-9f21-1a00a719****</SerialNumber>
      <NetworkType>vpc</NetworkType> 
      <Region>ap-south-1</Region>
      <InstanceTypeFamily>ecs.n4</InstanceTypeFamily>
      <isAliyunHost>true</isAliyunHost>
      <IpGroup>12.23.XX.XX</IpGroup>
      <AliUid>127067667954****4</AliUid>
      <InstanceId>i-a2d5q7pm3f9yr29e****</InstanceId>
      <OperatingSystem>Linux</OperatingSystem>
      <HostName>sitemonitor-mengmai-1</HostName>
    </Host> 
  </Hosts>
  <Success>true</Success> 
  <Code>200</Code>
  <Total>2</Total>
</DescribeMonitoringAgentHostsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"PageTotal":1,
	"PageNumber":1,
	"PageSize":100,
	"Hosts":{
		"Host":[
			{
				"SerialNumber":"x12335-6cc8-4a22-9f21-1a00a719****",
				"AgentVersion":"2.1.55",
				"NetworkType":"vpc",
				"Region":"ap-south-1",
				"IpGroup":"12.23.XX.XX",
				"isAliyunHost":true,
				"InstanceTypeFamily":"ecs.n4",
				"AliUid":"127067667954****",
				"InstanceId":"i-a2d5q7pm3f9yr212****",
				"OperatingSystem":"Linux",
				"HostName":"sitemonitor-mengmai-1"
			}
		]
	},
	"Success":true,
	"Code":200,
	"Total":2
}
```

## Error code {#section_olt_zp2_ye2 .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

