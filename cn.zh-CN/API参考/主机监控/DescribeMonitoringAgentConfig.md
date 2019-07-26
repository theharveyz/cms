# DescribeMonitoringAgentConfig {#doc_api_Cms_DescribeMonitoringAgentConfig .reference}

查询云监控插件的配置信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentConfig&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMonitoringAgentConfig|系统规定参数。取值：DescribeMonitoringAgentConfig。

 |

## 返回数据 {#resultMapping .section}

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

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

