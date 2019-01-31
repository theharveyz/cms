# NodeStatusList {#doc_api_988433 .reference}

批量查询云监控插件状态。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=NodeStatusList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|InstanceIds|String|是|i-abcdefgh123456,i-abcdefgh123457|实例id。 例如：i-22jja5c2l，多个id使用英文逗号分隔

 |
|Action|String|否|NodeStatusList|系统规定参数。取值：NodeStatusList

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ErrorCode|Integer|200|错误码，200为成功，其他为失败

 |
|ErrorMessage|String|InstanceIds is mandatory for this action.|错误提示

 |
|NodeStatusList| | |Node状态的列表

 |
|└AutoInstall|Boolean|true|是否可以使用安装接口自动安装

 |
|└InstanceId|String|i-abcdefgh123456|实例id

 |
|└Status|String|running|参考NodeStatus Agent运行状态

 |
|RequestId|String|1BB8FE8E-9BBE-490F-82EC-BF70FB849D55|请求的唯一ID用于定位错误

 |
|Success|Boolean|true|本次操是否成功，等价于errorCode200

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=NodeStatusList
&InstanceIds=i-abcdefgh123456，i-abcdefgh123457
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<NodeStatusListResponse>
  <NodeStatusList>
    <NodeStatus>
      <Status>running</Status>
      <InstanceId> i-abcdefgh123456</InstanceId>
      <AutoInstall>true</AutoInstall>
    </NodeStatus>
    <NodeStatus>
      <Status>uninstalled</Status>
      <InstanceId> i-abcdefgh123457</InstanceId>
      <AutoInstall>true</AutoInstall>
    </NodeStatus>
  </NodeStatusList>
  <Success>true</Success>
  <ErrorCode>200</ErrorCode>
</NodeStatusListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"NodeStatusList":{
		"NodeStatus":[
			{
				"Status":"running",
				"InstanceId":" i-abcdefgh123456",
				"AutoInstall":true
			},
			{
				"Status":"uninstalled",
				"InstanceId":" i-abcdefgh123457",
				"AutoInstall":true
			}
		]
	},
	"Success":true,
	"ErrorCode":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

