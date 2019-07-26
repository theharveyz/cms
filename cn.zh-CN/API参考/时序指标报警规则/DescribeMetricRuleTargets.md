# DescribeMetricRuleTargets {#doc_api_Cms_DescribeMetricRuleTargets .reference}

查询报警规则关联目标。

目前仅支持MNS。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleTargets&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMetricRuleTargets|系统规定参数。取值：DescribeMetricRuleTargets。

 |
|RuleId|String|是|rulIdxxxxx1|报警规则ID。

 |

## 返回数据 {#resultMapping .section}

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
|Arn|String|acs:mns:cn-hangzhou:111:/queues/test/message|资源描述，规则为acs:\{产品缩写\}:\{regionId\}:\{userId\}:/\{消息资源类型\}/\{资源名称\}/message。例如：acs:mns:cn-hangzhou:111:/queues/test/message。

 -   \{产品资源缩写：目前仅支持mns，取值为mns。
-   \{userId\}：用户账号ID。
-   \{regionId\}：消息队列或者topic所在的regionId。
-   \{消息资源类型\}：可选择为： queues（队列）和topics（主题）。
-   \{资源名称\}：如果消息资源类型为queues，则资源名称为队列的名称，如果消息资源类型为topics，则资源名称为主题的名称。

 |
|Id|String|1|目标ID。

 |
|Level|String|\["INFO", "WARN", "CRITICAL"\]|报警级别，为一个JSON数组，可以取值为：

 -   INFO（信息）
-   WARN（警告）
-   CRITICAL（紧急）

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

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

