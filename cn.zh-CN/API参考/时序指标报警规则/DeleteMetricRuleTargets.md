# DeleteMetricRuleTargets {#doc_api_Cms_DeleteMetricRuleTargets .reference}

删除一个报警规则的目标。

目前仅支持MNS。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DeleteMetricRuleTargets&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteMetricRuleTargets|系统规定参数。取值：DeleteMetricRuleTargets。

 |
|RuleId|String|是|ruleId-xxxxxx|关联的报警规则ID。

 |
|TargetIds.N|RepeatList|否|1|关联的目标ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示成功。

 |
|FailIds| | |删除失败的目标ID列表。

 |
|TargetIds| |1|删除失败的目标ID。

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

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

