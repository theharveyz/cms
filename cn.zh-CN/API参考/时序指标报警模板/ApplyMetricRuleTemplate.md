# ApplyMetricRuleTemplate {#doc_api_Cms_ApplyMetricRuleTemplate .reference}

将报警模板应用到分组，生成报警规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=ApplyMetricRuleTemplate&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ApplyMetricRuleTemplate|系统规定参数。取值：ApplyMetricRuleTemplate。

 |
|GroupId|Long|是|12345|应用分组ID。

 |
|TemplateIds|String|是|123|报警模板ID。

 |
|ApplyMode|String|否|GROUP\_INSTANCE\_FIRST|-   GROUP\_INSTANCE\_FIRST：实例分组优先， 即应用报警模板的时候，以分组实例优先，如果分组中不存在这种实例则忽略模板中的规则。
-   ALARM\_TEMPLATE\_FIRST：模板实例优先，即应用报警模板的时候，不管分组中是否存在这种实例，都创建出这种规则。

 |
|EnableEndTime|Long|否|23|报警生效的结束时间周期， 选值为00-23，表示00：59 到23：59。

 |
|EnableStartTime|Long|否|00|报警生效的起始时间周期， 选值为00-23，表示00：00 到23：00。

 |
|SilenceTime|Long|否|86400|通道沉默周期，单位为秒。默认86400秒（即1天）。监控数据持续超过报警规则阈值时，每个沉默周期内只发送1次报警通知。

 |
|Webhook|String|否|http://www.aliyun.com|报警发生时会回调指定的URL地址。向URL发送POST请求。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|1B25BAE2-DA60-428C-8414-37A11EEB49B5|请求ID，用于排查问题。

 |
|Resource| | |影响的资源。

 |
|AlertResults| | |生成报警规则的详细结果。

 |
|Code|String|200|状态码，200表示成功。

 |
|GroupId|Long|123456|应用分组ID。

 |
|Message|String|success|错误信息。

 |
|RuleId|String|applyTemplate44491519-xxxx-xxx|报警规则ID。

 |
|RuleName|String|ruleNamex|报警规则名称。

 |
|Success|Boolean|true|是否成功。

 |
|GroupId|Long|12345|应用分组ID。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ApplyMetricRuleTemplate
&GroupId=12345
&TemplateIds=123
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ApplyMetricRuleTemplateResponse>
          <RequestId>3F897F3C-020A-4993-95B4-63ABB84F83E6</RequestId>
      <Resource>
            <AlertResults>
                  <DisplayName>xxxx11</DisplayName>
                  <Code>200</Code>
                  <Success>true</Success>
                  <Name>applyTemplate12345-321</Name>
                  <GroupId>123456</GroupId>
            </AlertResults>
            <AlertResults>
                  <DisplayName>abb33</DisplayName>
                  <Code>200</Code>
                  <Success>true</Success>
                  <Name>applyTemplate12345-322</Name>
                  <GroupId>123457</GroupId>
            </AlertResults>
            <AlertResults>
                  <DisplayName>aaaa</DisplayName>
                  <Code>200</Code>
                  <Success>true</Success>
                  <Name>applyTemplate12345-322</Name>
                  <GroupId>123459</GroupId>
            </AlertResults>
            <GroupId>3040150</GroupId>
      </Resource>
      <ErrorCode>200</ErrorCode>
      <Success>true</Success>
</ApplyMetricRuleTemplateResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Resource":{
		"AlertResults":[
			{
				"Name":"applyTemplate12345-321",
				"Success":true,
				"DisplayName":"xxxx11",
				"GroupId":123456,
				"Code":200
			},
			{
				"Name":"applyTemplate12345-322",
				"Success":true,
				"DisplayName":"abb33",
				"GroupId":123457,
				"Code":200
			},
			{
				"Name":"applyTemplate12345-322",
				"Success":true,
				"DisplayName":"aaaa",
				"GroupId":123459,
				"Code":200
			}
		],
		"GroupId":3040150
	},
	"RequestId":"3F897F3C-020A-4993-95B4-63ABB84F83E6",
	"Success":true,
	"ErrorCode":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

