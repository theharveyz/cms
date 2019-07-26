# DescribeMonitoringAgentAccessKey {#doc_api_Cms_DescribeMonitoringAgentAccessKey .reference}

查询非阿里云ECS主机安装云监控插件时所需要的AccessKey和AccessSecret。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitoringAgentAccessKey&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeMonitoringAgentAccessKey|系统规定参数。取值：DescribeMonitoringAgentAccessKey。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|E9F4FA2A-54BE-4EF9-9D1D-1A0B1DC86B8D|请求ID，用于排查问题。

 |
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|Successfully|错误信息。

 |
|AccessKey|String|xxxxx|安装插件需要的AccessKey。

 |
|SecretKey|String|yyyyy|安装插件需要的AccessSecret。

 |
|Success|Boolean|true|请求是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitoringAgentAccessKey
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMonitoringAgentAccessKeyResponse>
      <AccessKey>xxxx</AccessKey>
      <SecretKey>yyyy</SecretKey>
      <Success>true</Success>
      <Code>200</Code>
</DescribeMonitoringAgentAccessKeyResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"AccessKey":"xxxx",
	"SecretKey":"yyyy",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

