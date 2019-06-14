# UninstallMonitoringAgent {#doc_api_Cms_UninstallMonitoringAgent .reference}

卸载非阿里云主机监控插件。

不适用于阿里云ECS 插件，阿里云ECS插件卸载请参考相关文档。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=UninstallMonitoringAgent)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|InstanceId|String|是|host-\*\*\*\*|主机实例ID。

 |
|Action|String|否|UninstallMonitoringAgent|系统规定参数。取值：UninstallMonitoringAgent。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|Successfully|错误信息。

 |
|RequestId|String|466902B9-2842-40B0-B796-00FE772B6EF3|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=UninstallMonitoringAgent
&InstanceId=i-xx12****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UninstallMonitoringAgentResponse>
  <RequestId>466902B9-2842-40B0-B796-00FE772B6EF3</RequestId>
  <Code>200</Code>
  <Message>Successfully</Message>
</UninstallMonitoringAgentResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Successfully",
	"RequestId":"466902B9-2842-40B0-B796-00FE772B6EF3",
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

