# ModifyMetricRuleTemplate {#doc_api_Cms_ModifyMetricRuleTemplate .reference}

修改报警模板。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=ModifyMetricRuleTemplate&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyMetricRuleTemplate|系统规定参数。取值：ModifyMetricRuleTemplate。

 |
|TemplateId|Long|是|12346|报警规则模板ID。

 |
|RestVersion|Long|是|0|修改报警模板的版本，从报警模板列表或则详情中获得。没修改过一次，这个字段会被自动更新。

 |
|Name|String|否|我的报警模板|报警规则模板名称。

 |
|Description|String|否|报警模板描述|报警规则描述信息。

 |
|AlertTemplates.N.MetricName|String|否|cpu\_total|监控项。N的取值范围为 1~200。

 |
|AlertTemplates.N.RuleName|String|否|我的报警规则|报警规则的名称。N的取值范围为 1~200。

 |
|AlertTemplates.N.Category|String|否|ecs|产品名称缩写，例如ecs。N的取值范围为 1~200。

 |
|AlertTemplates.N.Namespace|String|否|acs\_ecs\_dashboard|产品的namespace，用于区分不同的产品。

 |
|AlertTemplates.N.Period|Integer|否|60|统计周期，已经不建议使用。N的取值范围为 1~200。

 |
|AlertTemplates.N.Selector|String|否|\{"disk":"/"\}|扩展字段选项，例如要应用一个组下所有实例的根分区，这里可以写\{"disk":"/"\}。

 |
|AlertTemplates.N.Escalations.Critical.Statistics|String|否|Average|Critical级别统计方法。N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Critical.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Critical级别阈值比较符符，可以选择如下：

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

 N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Critical.Threshold|String|否|90|Critical级别阈值。N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Critical.Times|Integer|否|3|Critical级别连续出现次数才出触发报警。N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Warn.Statistics|String|否|Average|Warn级别统计方法。N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Warn.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Warn级别阈值比较符符，可以选择如下：

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

 N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Warn.Threshold|String|否|90|Wran级别阈值。N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Warn.Times|Integer|否|3|Warn级别连续出现次数才出触发报警。N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Info.Statistics|String|否|Average|Infol级别统计方法。N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Info.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Info级别阈值比较符符，可以选择如下：

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

 N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Info.Threshold|String|否|90|Critical级别阈值。N的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Info.Times|Integer|否|3|Info级别连续出现次数才出触发报警。N的取值范围为 1~200。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|9E07117F-F6AE-4F1C-81E8-36FBB4892235|请求Id，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyMetricRuleTemplate
&TemplateId=12346
&RestVersion=0
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyMetricRuleTemplateResponse>
    <Code>200</Code>
    <Template>123</Template>
    <RequestId>9E07117F-F6AE-4F1C-81E8-36FBB4892235</RequestId>
    <Success>true</Success>
</ModifyMetricRuleTemplateResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"9E07117F-F6AE-4F1C-81E8-36FBB4892235",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

