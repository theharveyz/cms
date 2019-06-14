# DescribeMetricRuleTargets {#doc_api_Cms_DescribeMetricRuleTargets .reference}

查询报警规则关联目标。

目前仅支持MNS。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleTargets)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMetricRuleTargets|系统规定参数。取值：DescribeMetricRuleTargets。

 |
|RuleId|String|是|rulIdxxxxx1|报警规则ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|786E92D2-AC66-4250-B76F-F1E2FCDDBA1C|请求ID， 用于排查问题。

 |
|Targets| | |目标。

 |
|└Arn|String|acs:mns:cn-hangzhou:111:/queues/test/message|资源描述，规则为acs:\{产品缩写\}:\{regionId\}:\{userId\}:/\{消息资源类型\}/\{资源名称\}/message。例如：acs:mns:cn-hangzhou:111:/queues/test/message。

 -   \{产品资源缩写：目前仅支持mns，取值为mns
-   \{userId\}：用户账号ID
-   \{regionId\}：消息队列或者topic所在的regionId
-   \{消息资源类型\}：可选择为： queues（队列）和topics\(主题\)
-   \{资源名称\}：如果类型位queues则为队列的名称，如果topics则为主题的名称

 |
|└Id|String|1|目标ID。

 |
|└Level|String|\["INFO", "WARN", "CRITICAL"\]|报警规则的级别，为一个json数组，可以取值为

 -   INFO\(信息\)
-   WARN\(警告\)
-   CRITICAL\(紧急\)

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMetricRuleTargets
&RuleId=rulIdxxxxx1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMetricRuleTargetsResponse>
  <Code>200</Code>
  <Message>Success</Message>
  <Success>true</Success>
  <RequestId>786E92D2-AC66-4250-B76F-F1E2FCDDBA1C</RequestId>
  <FailData>
    <Targets>
      <Arn>acs:mns:cn-hangzhou:111:/queues/test/message</Arn>
      <Id>1</Id>
      <Level>INFO</Level>
      <Level>WARN</Level>
      <Level>CRITICAL</Level>
    </Targets>
  </FailData>
</DescribeMetricRuleTargetsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Success",
	"RequestId":"786E92D2-AC66-4250-B76F-F1E2FCDDBA1C",
	"Success":true,
	"Code":"200",
	"Targets":[
		{
			"Level":[
				"INFO",
				"WARN",
				"CRITICAL"
			],
			"Id":1,
			"Arn":"acs:mns:cn-hangzhou:111:/queues/test/message"
		}
	]
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

