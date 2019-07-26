# EnableMetricRules {#doc_api_Cms_EnableMetricRules .reference}

启用一个或多个报警规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=EnableMetricRules&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RuleId.N|RepeatList|是|ab05733c97b7ce239fb1b53393dc1697c123\*\*\*\*|报警规则的ID。

 |
|Action|String|否|EnableMetricRules|系统规定参数。取值：EnableMetricRules。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|FF38D33A-67C1-40EB-AB65-FAEE51EDB644|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=EnableMetricRules
&RuleId.1=ab05733c97b7ce239fb1b53393dc1697c123****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<EnableMetricRulesResponse>
      <Code>200</Code>
      <Message>success</Message>
      <RequestId>FF38D33A-67C1-40EB-AB65-FAEE51EDB644</RequestId>
      <Success>true</Success>
</EnableMetricRulesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"FF38D33A-67C1-40EB-AB65-FAEE51EDB644",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

