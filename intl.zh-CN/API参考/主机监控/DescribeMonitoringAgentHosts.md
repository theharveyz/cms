# DescribeMonitoringAgentHosts {#doc_api_Cms_DescribeMonitoringAgentHosts .reference}

查询所有的已安装和未安装云监控插件的主机列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentHosts&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeMonitoringAgentHosts|系统规定参数。取值：DescribeMonitoringAgentHosts。

 |
|HostName|String|否|hostNam1|主机名称。

 |
|InstanceIds|String|否|i-a3d1q1pm2f9yr29e\*\*\*\*|实例ID。

 |
|InstanceRegionId|String|否|cn-hangzhou|实例的regionId。

 |
|KeyWord|String|否|host1|模糊搜索关键字。

 |
|PageNumber|Integer|否|1|页数。

 |
|PageSize|Integer|否|10|每页显示记录条数。

 |
|SerialNumbers|String|否|a1ab31a3-1234-40f2-9e95-c8caa8f0\*\*\*\*|序列号搜索。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Hosts| | |主机列表。

 |
|AgentVersion|String|2.1.55|插件版本。

 |
|AliUid|Long|123456|阿里云云账号ID。

 |
|EipAddress|String|22.22.XX.XX|EIP地址。

 |
|EipId|String|xxx|EIP的ID。

 |
|HostName|String|hostIP|主机名称。

 |
|InstanceId|String|i-a2d5q7pm3f9yr212\*\*\*\*|实例ID。

 |
|InstanceTypeFamily|String|ecs.n4|ECS 实例规格。

 |
|IpGroup|String|12.23.XX.XX|IP地址，多个地址逗号分隔。

 |
|NatIp|String|22.22.XX.XX|NAT IP。

 |
|NetworkType|String|vpc|网络类型。

 |
|OperatingSystem|String|Linux|操作系统。

 |
|Region|String|cn-hangzhou|地域。

 |
|SerialNumber|String|x12335-6cc8-4a22-9f21-1a00a719\*\*\*\*|序列号。

 |
|isAliyunHost|Boolean|true|是否是阿里云主机 。

 |
|Message|String|Successfully|错误信息。

 |
|PageTotal|Integer|50|页数。

 |
|RequestId|String|63EEBB2A-9E51-41E4-9E83-5DE7F3B292E0|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |
|Total|Integer|10|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitoringAgentHosts
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cms)查看更多错误码。

