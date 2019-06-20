# DeleteEventRules {#doc_api_Cms_DeleteEventRules .reference}

删除事件报警规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteEventRules)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RuleNames.N|RepeatList|是|rule1|报警规则名称。N 的取值范围为 1~20。

 |
|Action|String|否|DeleteEventRules|系统规定参数。取值：DeleteEventRules。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|返回信息。

 |
|RequestId|String|E5A72B5B-4F44-438C-B68A-147FD5DC53A8|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteEventRules
&RuleNames.1=rule1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteEventRulesResponse>
  <RequestId>E5A72B5B-4F44-438C-B68A-147FD5DC53A8</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DeleteEventRulesResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"E5A72B5B-4F44-438C-B68A-147FD5DC53A8",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

