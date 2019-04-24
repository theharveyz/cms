# PutMonitoringConfig {#doc_api_Cms_PutMonitoringConfig .reference}

设置云监控插件全局配置，例如开始自动安装插件以及一键报警等。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=PutMonitoringConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|PutMonitoringConfig|系统规定参数。取值：PutMonitoringConfig。

 |
|AutoInstall|Boolean|否|true|自动为现有的ECS安装插件。

 |
|EnableInstallAgentNewECS|Boolean|否|true|开启新购ECS自动安装云监控插件。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=PutMonitoringConfig
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PutMonitoringConfigResponse>
  <RequestId>E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</PutMonitoringConfigResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

