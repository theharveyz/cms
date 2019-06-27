# DeleteMetricRuleTargets {#doc_api_Cms_DeleteMetricRuleTargets .reference}

删除一个报警规则的目标。

目前仅支持MNS。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMetricRuleTargets)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteMetricRuleTargets|系统规定参数。取值：DeleteMetricRuleTargets。

 |
|RuleId|String|是|ruleId-xxxxxx|关联的报警规则ID。

 |
|TargetIds.N|RepeatList|否|1|关联的目标ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示成功。

 |
|FailIds| | |删除失败的目标ID列表。

 |
|└TargetIds| |1|删除失败的目标ID。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|786E92D2-AC66-4250-B76F-F1E2FCDDBA1C|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteMetricRuleTargets
&RuleId=ruleId-xxxxxx
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteMetricRuleTargetsResponse>
  <Code>200</Code>
  <Message>Success</Message>
  <Success>true</Success>
  <RequestId>786E92D2-AC66-4250-B76F-F1E2FCDDBA1C</RequestId>
  <FailIds>1</FailIds>
</DeleteMetricRuleTargetsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Success",
	"RequestId":"786E92D2-AC66-4250-B76F-F1E2FCDDBA1C",
	"Success":true,
	"Code":"200",
	"FailIds":[
		"1"
	]
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

