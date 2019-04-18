# DeleteMonitoringAgentProcess {#doc_api_Cms_DeleteMonitoringAgentProcess .reference}

删除进程监控。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMonitoringAgentProcess)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|InstanceId|String|是|i-KpVny6l\*\*\*\*|实例ID。

 |
|Action|String|否|DeleteMonitoringAgentProcess|系统规定参数。取值：DeleteMonitoringAgentProcess。

 |
|ProcessId|String|否|12345|进程ID。ProcessId和ProcessName 参数必须至少填写其中一个参数。

 |
|ProcessName|String|否|http|进程名称。ProcessId和ProcessName 参数必须至少填写其中一个参数。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|Successfully|错误信息。

 |
|RequestId|String|971CC023-5A96-452A-BB7C-2483F948BCFD|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteMonitoringAgentProcess
&InstanceId=i-KpVny6l****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteMonitoringAgentProcessResponse>
  <Success>true</Success>
  <Code>200</Code>
</DeleteMonitoringAgentProcessResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

