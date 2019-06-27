# CreateGroupMetricRules {#doc_api_Cms_CreateGroupMetricRules .reference}

批量创建应用分组报警规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=CreateGroupMetricRules)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|GroupId|Long|是|123456|应用分组ID。

 |
|Action|String|否|CreateGroupMetricRules|系统规定参数。取值：CreateGroupMetricRules。

 |
|GroupMetricRules.N.Category|String|否|ecs|产品的缩写。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Dimensions|String|否|\[\{"instanceId":"xxxxxx"\}\]|扩展资源维度。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.EffectiveInterval|String|否|00:00-23:59|报警规则的生效时间范围。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.EmailSubject|String|否|出现报警|报警邮件主题。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Critical.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Critical级别阈值比较符，可以选择如下：

 -   GreaterThanOrEqualToThreshold:大于等于
-   GreaterThanThreshold:大于
-   LessThanOrEqualToThreshold:小于等于
-   LessThanThreshold:小于
-   NotEqualToThreshold:不等
-   GreaterThanYesterday:同比昨天时间上涨
-   LessThanYesterday:同比昨天时间下降
-   GreaterThanLastWeek:同比上周同一时间上涨
-   LessThanLastWeek:同比上周同一时间下降
-   GreaterThanLastPeriod:环比上周期上涨
-   LessThanLastPeriod:环比上周期下降

 N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Critical.Statistics|String|否|Average|Critical级别报警统计方法，每种监控项对应不同的统计方法。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Critical.Threshold|String|否|90|Critical级别报警阈值。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Critical.Times|Integer|否|3|Critical级别报警重试次数。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Info.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Info级别阈值比较符，可以选择如下：

 -   GreaterThanOrEqualToThreshold:大于等于
-   GreaterThanThreshold:大于
-   LessThanOrEqualToThreshold:小于等于
-   LessThanThreshold:小于
-   NotEqualToThreshold:不等
-   GreaterThanYesterday:同比昨天时间上涨
-   LessThanYesterday:同比昨天时间下降
-   GreaterThanLastWeek:同比上周同一时间上涨
-   LessThanLastWeek:同比上周同一时间下降
-   GreaterThanLastPeriod:环比上周期上涨
-   LessThanLastPeriod:环比上周期下降

 N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Info.Statistics|String|否|Average|Info级别报警统计方法。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Info.Threshold|String|否|90|Info级别报警阈值。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Info.Times|Integer|否|3|Info级别报警重试次数。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Warn.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Warn级别阈值比较符，可以选择如下：

 -   GreaterThanOrEqualToThreshold:大于等于
-   GreaterThanThreshold:大于
-   LessThanOrEqualToThreshold:小于等于
-   LessThanThreshold:小于
-   NotEqualToThreshold:不等
-   GreaterThanYesterday:同比昨天时间上涨
-   LessThanYesterday:同比昨天时间下降
-   GreaterThanLastWeek:同比上周同一时间上涨
-   LessThanLastWeek:同比上周同一时间下降
-   GreaterThanLastPeriod:环比上周期上涨
-   LessThanLastPeriod:环比上周期下降

 N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Warn.Statistics|String|否|Average|Warn级别报警统计方法。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Warn.Threshold|String|否|90|Warn级别报警阈值。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Escalations.Warn.Times|Integer|否|3|Warn级别报警重试次数。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Interval|String|否|60|报警的探测周期。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.MetricName|String|否|cpu\_total|监控项名称。可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Namespace|String|否|acs\_ecs\_dashboard|产品的数据命名空间，可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.NoEffectiveInterval|String|否|00:00-05:30|报警规则非生效时间范围。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Period|String|否|60|聚合周期，单位秒。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.RuleId|String|否|bfae2ca5b4e07d2c7278772eccda169808c7b\*\*\*\*|报警规则ID，调用者统一生成，保证唯一性。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.RuleName|String|否|报警规则1|报警规则名称。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.SilenceTime|Integer|否|86400|一直处于报警状态的通知沉默周期，单位秒，默认86400秒（即1天），最小3600秒（即1小时）。N 的取值范围为 1~200。

 |
|GroupMetricRules.N.Webhook|String|否|http://www.aliyun.com|出现报警时候触发回调地址。N 的取值范围为 1~200。

 |

报警的3种触发条件至少选择有一个，否则会创建不成功。

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码， 200表示正常，否则失败。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|461CF2CD-2FC3-4B26-8645-7BD27E7D0F1D|请求ID，用于排查问题。

 |
|Resources| | |创建影响的资源列表。

 |
|└Code|Integer|200|状态码， 200表示成功，否则表示失败。

 |
|└Message|String|success|错误信息。

 |
|└RuleId|String|a151cd6023eacee2f0978e03863cc1697c89508\*\*\*\*|报警规则ID。

 |
|└RuleName|String|报警规则1|报警规则名称。

 |
|└Success|Boolean|true|是否成功。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateGroupMetricRules
&GroupId=123456
&GroupMetricRules.1.Category=ecs
&GroupMetricRules.1.MetricName=cpu_total
&GroupMetricRules.1.1amespace=acs_ecs_dashboard
&GroupMetricRules.1.RuleId=bfae2ca5b4e07d2c7278772eccda169808c7b****
&GroupMetricRules.1.RuleName=报警规则1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateGroupMetricRulesResponse>
  <RequestId>65D50468-ECEF-48F1-A6E1-D952E89D9436</RequestId>
  <Success>true</Success>
  <Code>200</Code>
  <Resources>
    <AlertResult>
      <RuleId>xxxx1298766</RuleId>
      <Success>true</Success>
      <RuleName>我的规则名1</RuleName>
      <Code>200</Code>
    </AlertResult>
    <AlertResult>
      <Message>Metric not found.</Message>
      <RuleId>hyu91929****</RuleId>
      <Success>false</Success>
      <RuleName>规则Id2</RuleName>
      <Code>404</Code>
    </AlertResult>
  </Resources>
</CreateGroupMetricRulesResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"65D50468-ECEF-48F1-A6E1-D952E89D9436",
	"Success":"true",
	"Code":"200",
	"Resources":{
		"AlertResult":[
			{
				"RuleId":"xxxx1298766",
				"RuleName":"我的规则名1",
				"Success":"true",
				"Code":"200"
			},
			{
				"Message":"Metric not found.",
				"RuleId":"hyu91929****",
				"RuleName":"规则Id2",
				"Success":"false",
				"Code":"404"
			}
		]
	}
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

