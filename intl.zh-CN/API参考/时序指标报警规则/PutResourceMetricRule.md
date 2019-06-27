# PutResourceMetricRule {#doc_api_Cms_PutResourceMetricRule .reference}

对单个资源的性能指标设置阈值报警规则。

设置报警规则需要的各云产品的Namespace、MetricName、Dimensions等入参赋值，可通过查询DescribeMetricMetaList接口获得或参考[预设监控项参考](~~28619~~)。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=PutResourceMetricRule)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ContactGroups|String|是|默认报警联系组|报警联系人组，多个联系组之间用英文逗号分隔。

 |
|MetricName|String|是|cpu\_total|监控项名称。可通过查询DescribeMetricMetaList接口获得或参考[预设监控项参考](~~28619~~)。

 |
|Namespace|String|是|acs\_ecs\_dashboard|产品的数据命名空间，可通过查询DescribeMetricMetaList接口获得或参考[预设监控项参考](~~28619~~)。

 |
|Resources|String|是|\[\{"instanceId":"xxxxxxx"\}\]|需要报警的资源。

 |
|RuleId|String|是|a151cd6023eacee2f0978e03863cc1697c89508\*\*\*\*|报警规则ID，调用者统一生成，保证唯一性，已经存在的ID则修改，不存在则创建。

 |
|Action|String|否|PutResourceMetricRule|系统规定参数。取值：PutResourceMetricRule。

 |
|RuleName|String|否|我的报警规则|报警规则的展示名称。

 |
|Webhook|String|否|http://ww.aliyun.com|报警发生时会回调指定的URL地址。向URL发送POST请求。

 |
|EffectiveInterval|String|否|00:00-23:59|报警规则的生效时间范围。

 |
|NoEffectiveInterval|String|否|00:00-06:00|报警规则的不生效时间范围。

 |
|SilenceTime|Integer|否|86400|通道沉默周期，单位为秒。默认86400秒（即1天），最短为3600秒（即1小时）。监控数据持续超过报警规则阈值时，每个沉默周期内只发送1次报警通知。

 |
|Interval|String|否|60|报警规则的探测周期，单位为秒。默认为监控项的最小频率。

 |
|EmailSubject|String|否|出现告警了|报警邮件规则主题。

 |
|Period|String|否|60|监控数据的聚合周期，单位秒。默认取值为监控项对应的最小频率，通常不需要指定。

 |
|Escalations.Critical.Statistics|String|否|Average|Critical级别报警统计方法。

 |
|Escalations.Critical.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Critical级别阈值比较符，可以选择如下：

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

 |
|Escalations.Critical.Threshold|String|否|90|Critical级别报警阈值。

 |
|Escalations.Critical.Times|Integer|否|3|Critical级别报警重试次数。

 |
|Escalations.Warn.Statistics|String|否|Average|Warn级别报警统计方法。

 |
|Escalations.Warn.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Warn级别阈值比较符，可以选择如下：

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

 |
|Escalations.Warn.Threshold|String|否|90|Warn级别报警阈值。

 |
|Escalations.Warn.Times|Integer|否|3|Warn级别报警重试次数。

 |
|Escalations.Info.Statistics|String|否|Average|Info级别报警统计方法。

 |
|Escalations.Info.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Info级别阈值比较符，可以选择如下：

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

 |
|Escalations.Info.Threshold|String|否|90|Info级别报警阈值。

 |
|Escalations.Info.Times|Integer|否|3|Info级别报警重试次数。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|65D50468-ECEF-48F1-A6E1-D952E89D9436|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=PutResourceMetricRule
&ContactGroups=默认报警联系组
&MetricName=cpu_total
&Namespace=acs_ecs_dashboard
&Resources=[{"instanceId":"xxxxxxx"}]
&RuleId=a151cd6023eacee2f0978e03863cc1697c89508****
&RuleName=我的报警规则
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PutResourceMetricRuleResponse>
  <Code>200</Code>
  <Message>success</Message>
  <RequestId>65D50468-ECEF-48F1-A6E1-D952E89D9436</RequestId>
  <Success>true</Success>
</PutResourceMetricRuleResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"65D50468-ECEF-48F1-A6E1-D952E89D9436",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

