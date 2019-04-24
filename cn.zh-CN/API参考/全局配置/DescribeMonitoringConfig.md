# DescribeMonitoringConfig {#doc_api_Cms_DescribeMonitoringConfig .reference}

查询云监控全局配置，例如开启自动安装云监控插件以及一键告警等。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMonitoringConfig|系统规定参数。取值：DescribeMonitoringConfig。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Success|Boolean|true|是否成功。

 |
|Code|String|200|状态码，200表示成功。

 |
|RequestId|String|F35654DB-0C9D-4FB3-903F-479BA7663061|请求ID，用于排查问题。

 |
|Message|String|success|错误信息。

 |
|EnableInstallAgentNewECS|Boolean|true|开启新购ECS自动安装云监控插件。

 |
|AutoInstall|Boolean|true|自动为现存的ECS安装云监控插件。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitoringConfig
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMonitoringConfigResponse>
  <ActiveAlertProducts>rds,opensearch,ecs</ActiveAlertProducts>
  <EnableInstallAgentNewECS>false</EnableInstallAgentNewECS>
  <Success>true</Success>
  <Code>200</Code>
  <AutoInstall>true</AutoInstall>
</DescribeMonitoringConfigResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"ActiveAlertProducts":"rds,opensearch,ecs",
	"RequestId":"",
	"Success":true,
	"EnableInstallAgentNewECS":false,
	"Code":200,
	"AutoInstall":true
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

