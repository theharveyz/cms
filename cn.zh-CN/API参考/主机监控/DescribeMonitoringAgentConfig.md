# DescribeMonitoringAgentConfig {#doc_api_Cms_DescribeMonitoringAgentConfig .reference}

查询云监控插件的配置信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMonitoringAgentConfig|系统规定参数。取值：DescribeMonitoringAgentConfig。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D|请求ID，用于排查问题。

 |
|AutoInstall|Boolean|true|开启自动安装云监控插件。

 |
|EnableInstallAgentNewECS|Boolean|false|新购ECS自动安装云监控插件。

 |
|Message|String|Successfully|错误信息。

 |
|Code|String|200|状态码，200表示成功。

 |
|Success|Boolean|true|是否成功。

 |
|EnableActiveAlert|String|redis,rds,ecs|开通一键告警的产品。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitoringAgentConfig
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMonitoringAgentConfigResponse>
  <UserId>12345****</UserId>
  <EnableInstallAgentNewECS>false</EnableInstallAgentNewECS>
  <Success>true</Success>
  <ErrorCode>200</ErrorCode>
  <EnableActiveAlert>redisa,rds,ecs</EnableActiveAlert>
  <AutoInstall>true</AutoInstall>
</DescribeMonitoringAgentConfigResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"UserId":"12345****",
	"ErrorCode":200,
	"Success":true,
	"EnableInstallAgentNewECS":false,
	"AutoInstall":true,
	"EnableActiveAlert":"redisa,rds,ecs"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

