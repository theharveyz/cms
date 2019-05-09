# DeleteMetricRuleTemplate {#doc_api_Cms_DeleteMetricRuleTemplate .reference}

删除报警规则模板。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMetricRuleTemplate)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|TemplateId|String|是|12345|报警模板ID。

 |
|Action|String|否|DeleteMetricRuleTemplate|系统规定参数。取值：DeleteMetricRuleTemplate。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|7B63F8CF-D48D-4608-A402-04FB5B2B4B6A|请求ID，用于排查问题。

 |
|Resource| | |删除成功返回删除的模板信息。

 |
|└TemplateId|String|123|模板ID。

 |
|Success|Boolean|true|删除是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteMetricRuleTemplate
&TemplateId=12345
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteMetricRuleTemplateResponse>
  <Resource>
    <TemplateId>123</TemplateId>
  </Resource>
  <RequestId>7B63F8CF-D48D-4608-A402-04FB5B2B4B6A</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DeleteMetricRuleTemplateResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Resource":{
		"TemplateId":123
	},
	"RequestId":"7B63F8CF-D48D-4608-A402-04FB5B2B4B6A",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

