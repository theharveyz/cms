# DescribeMonitoringAgentStatuses {#doc_api_Cms_DescribeMonitoringAgentStatuses .reference}

查询云监控插件运行状态。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentStatuses)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|InstanceIds|String|是|i-12345w55tr2rcpejp\*\*\*\*,i-23456w55tr2rcpejp\*\*\*\*|要获取状态的实例ID，多个实例ID直接用英文逗号分隔。

 |
|Action|String|否|DescribeMonitoringAgentStatuses|系统规定参数。取值：DescribeMonitoringAgentStatuses。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|Successfully|错误信息。

 |
|NodeStatusList| | |状态列表。

 |
|└AutoInstall|Boolean|true|是否开启自动安装。

 |
|└InstanceId|String|i-123456w55tr2rcpejp\*\*\*\*|实例ID。

 |
|└Status|String|running|运行状态，运行中：running，已停止：stoped。

 |
|RequestId|String|E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitoringAgentStatuses
&InstanceIds=i-12345w55tr2rcpejp****,i-23456w55tr2rcpejp****
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

