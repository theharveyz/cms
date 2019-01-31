# CreateAlarm {#doc_api_988998 .reference}

创建报警规则。

可以为某一个实例创建报警规则，也可以为多个实例同时创建报警规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=CreateAlarm)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ComparisonOperator|String|是|\>|报警比较符，只能为以下几种`<=，<，>，>=，==，!=`

 |
|ContactGroups|String|是|\["cms测试组"\]|报警规则通知的联系组，必须在控制台上已创建，为json array对应的string，例如`[“联系组1”，”联系组2”]`。

 |
|Dimensions|String|是|\[\{"instanceId":"i-2zecrzcri3d6fhd2ff7j "\}\]|报警规则对应实例列表，为json array对应的string，例如`[{“instanceId”:”name1”},{“instanceId”:”name2”}]`。

 |
|MetricName|String|是|CPUUtilization|相应产品对应的监控项名称，参考各产品metric定义。

 |
|Name|String|是|abc|报警规则名称。

 |
|Namespace|String|是|acs\_ecs\_dashboard|产品名称，参考各产品对应的project，例如acs\_ecs\_dashboard， acs\_rds\_dashboard等 。

 |
|Statistics|String|是|Average|统计方法，必须与定义的metric一致，例如Average。

 |
|Threshold|String|是|90|报警阈值，目前只开放数值类型功能。

 |
|Action|String|否|CreateAlarm|系统规定参数，取值：CreateAlarm

 |
|DryRun|Boolean|否|true|是否需要检查Webhook可用。

 |
|EndTime|Integer|否|24|报警生效时间的结束时间，默认24，代表24点。

 |
|EvaluationCount|Integer|否|3|连续探测几次都满足阈值条件时报警，默认3次。

 |
|NotifyType|Integer|否|1|通知类型，为0是旺旺+邮件，为1是旺旺+邮件+短信。

 |
|Period|Integer|否|60|查询指标的周期，必须与定义的metric一致，默认300，单位为秒 。

 |
|SilenceTime|Integer|否|86400|一直处于报警状态的通知沉默周期，默认86400，单位s，最小1小时。

 |
|StartTime|Integer|否|0|报警生效时间的开始时间，默认0，代表0点。

 |
|Webhook|String|否|http://www.net.cn/example\_callback.htm|回调函数，只支持公网地址，回调参数请参考[使用报警回调](~~60714~~)。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|请求失败状态码，200为成功，非200为失败。

 |
|Data|String|0c4af0f1-a864-468b-bed3-15c7deff75ee|返回的报警规则id。

 |
|Message|String|Success|请求失败的提示信息。

 |
|RequestId|String|910ABE4E-DC9D-4231-9DC0-C96835553327|请求的uuid，便于查询日志。

 |
|Success|Boolean|true|请求是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateAlarm
&ComparisonOperator=>
&ContactGroups=["cms测试组"]
&Dimensions=[{"instanceId":"i-2zecrzcri3d6fhd2ff7j "}]
&MetricName=CPUUtilization
&Name=abc
&Namespace=acs_ecs_dashboard
&Statistics=Average
&Threshold=90
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateAlarmResponse>
  <Data>576fbae7-2fd1-411a-ae13-6f09f4fafdde</Data>
  <RequestId>58C699ED-84BE-44D5-B55F-84AFE73932AB</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</CreateAlarmResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"0c4af0f1-a864-468b-bed3-15c7deff75ee",
	"RequestId":"910ABE4E-DC9D-4231-9DC0-C96835553327",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

