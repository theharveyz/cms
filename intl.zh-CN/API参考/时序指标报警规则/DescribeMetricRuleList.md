# DescribeMetricRuleList {#doc_api_Cms_DescribeMetricRuleList .reference}

查询报警规则列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeMetricRuleList|系统规定参数。取值：DescribeMetricRuleList。

 |
|Namespace|String|否|acs\_ecs\_dashboard|产品的数据命名空间，可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。

 |
|MetricName|String|否|cpu\_total|监控项名称。可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。

 |
|EnableState|Boolean|否|true|启用状态， true：启用， false：禁用，默认为所有状态。

 |
|Page|String|否|1|分页码，默认1。

 |
|PageSize|String|否|10|每页显示记录条数，默认10。

 |
|AlertState|String|否|ALARM|报警规则状态， ALARM, INSUFFICIENT\_DATA，OK。

 |
|Dimensions|String|否|\{"instanceId":"i-xy123\*\*\*\*"\}|规则关联的实例信息，为json object对应的字符串，例如\{"instanceId":"name1"\}。可以查询用于查询关联该实例的所有规则，应用该字段时必须指定Namespace。

 |
|RuleName|String|否|ECSCPU报警规则|报警规则的名称，支持模糊查询。

 |
|GroupId|String|否|123456|应用分组的ID。

 |
|RuleIds|String|否|a151cd6023eacee2f0978e03863cc1697c8950812\*\*\*\*|报警规则的IID，支持一次查询多个，多个ID之间用逗号分隔。单次最多可批量查询20条

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Success|Boolean|true|是否成功。

 |
|Code|Integer|200|状态码， 200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|0E657631-CD6C-4C24-9637-98D000B9272C|请求ID，用于排查问题。

 |
|Alarms| | |报警规则列表。

 |
|└AlertState|String|OK|报警规则的状态：

 -   OK：正常
-   ALARM：报警
-   INSUFFICIENT\_DATA：无数据

 |
|└ContactGroups|String|默认报警联系人|报警联系人。

 |
|└Dimensions|String|\[\{\}\]|关联的扩展资源。

 |
|└EffectiveInterval|String|00:00-23:59|报警规则的生效时间段。

 |
|└EnableState|Boolean|true|开启状态：

 -   true表示开启 。
-   fase表示禁用。

 |
|└Escalations| | |报警分级别触发条件。

 |
|└Critical| | |Critical级别报警触发条件。

 |
|└ComparisonOperator|String|GreaterThanOrEqualToThreshold|Critical级别阈值比较符，可以选择如下：

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
|└Statistics|String|Average|Critical级别报警统计方法。

 |
|└Threshold|String|90|Critical级别阈值。

 |
|└Times|String|3|Critical级别连续出现次数，联系出现这个次数并且超过阈值才会触发报警。

 |
|└Info| | |Info级别报警触发条件。

 |
|└ComparisonOperator|String|GreaterThanOrEqualToThreshold|Infol级别阈值比较符，可以选择如下：

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
|└Statistics|String|Average|Info级别报警统计方法。

 |
|└Threshold|String|90|Info级别阈值。

 |
|└Times|String|1|Info级别连续出现次数，连续出现这个次数并且超过阈值才会触发报警。

 |
|└Warn| | |Warnl级别报警触发条件。

 |
|└ComparisonOperator|String|GreaterThanOrEqualToThreshold|Warn级别阈值比较符，可以选择如下：

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
|└Statistics|String|Average|Warn级别报警统计方法

 |
|└Threshold|String|90|Warn级别阈值

 |
|└Times|String|3|Warn级别连续出现次数，联系出现这个次数并且超过阈值才会触发报警

 |
|└GroupId|String|123456|应用分组ID。

 |
|└GroupName|String|我的应用组|如果报警规则是关联到应用组上的，则此处显示的是组名称。

 |
|└MailSubject|String|发生报警|报警邮件主题定义。

 |
|└MetricName|String|cpu\_total|监控项。

 |
|└Namespace|String|acs\_ecs\_dashboard|产品的namespace，用于区分不同的产品。

 |
|└NoEffectiveInterval|String|00:00-23:59|报警规则不生效时间段，如00:00-23:59。

 |
|└Period|String|60|统计周期。

 |
|└Resources|String|\[\{\\"instanceId\\":\\"i-a2d5q7pm3f9yr29e\*\*\*\*\\"\},\{\\"instanceId\\":\\"i-a2d5q7pm3f9yr29e\*\*\*\*\\"\}|报警规则关联的资源。

 |
|└RuleId|String|a151cd6023eacee2f0978e03863cc1697c895012\*\*\*\*|报警规则ID。

 |
|└RuleName|String|我的报警规则|报警规则的名称。

 |
|└SilenceTime|String|86400|通道沉默周期，单位为秒。默认86400秒（1天），最短为3600秒（1天）。监控数据持续超过报警规则阈值时，每个沉默周期内只发送1次报警通知。

 |
|└Webhook|String|http://www.aliyun.com|URL回调地址。

 |
|Total|String|21|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMetricRuleList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMetricRuleListResponse>
  <Alarms>
    <Alarm>
      <Period>60</Period>
      <Statistics>Average</Statistics>
      <GroupName>组的名称</GroupName>
      <Webhook/>
      <Subject>aaabbb</Subject>
      <EffectiveInterval>00:00-23:59</EffectiveInterval>
      <RuleName>我的报警规则</RuleName>
      <NoEffectiveInterval/>
      <GroupId>3596360</GroupId>
      <EvaluationCount>3</EvaluationCount>
      <MetricName>cpu_total</MetricName>
      <Threshold>92</Threshold>
      <State>OK</State>
      <Enable>true</Enable>
      <SilenceTime>86400</SilenceTime>
      <Dimensions>[{}]</Dimensions>
      <RuleId>a151cd6023eacee2f0978e03863cc1697c89508e2b61****</RuleId>
      <Namespace>acs_ecs_dashboard</Namespace>
      <ContactGroups>测试</ContactGroups>
      <Escalations>
        <Critical>
          <Statistics>Average</Statistics>
          <Threshold>92</Threshold>
          <Times>3</Times>
          <ComparisonOperator>GreaterThanOrEqualToThreshold</ComparisonOperator>
        </Critical>
        <Info/>
        <Warn/>
      </Escalations>
      <ComparisonOperator>&gt;=</ComparisonOperator>
      <Resources>[{"instanceId":"i-a2d5q7pm3f12****"}]</Resources>
    </Alarm>
    <Alarm>
      <Period>60</Period>
      <Statistics>Average</Statistics>
      <GroupName>demo</GroupName>
      <Webhook/>
      <Subject>${serviceType}-${metricName}-${levelDescription}通知（${dimensions}）</Subject>
      <EffectiveInterval>00:00-23:59</EffectiveInterval>
      <RuleName>xxxxxxxxxxxxxxx</RuleName>
      <NoEffectiveInterval/>
      <GroupId>12345</GroupId>
      <EvaluationCount>3</EvaluationCount>
      <MetricName>cpu_total</MetricName>
      <Threshold>90</Threshold>
      <State>OK</State>
      <Enable>true</Enable>
      <SilenceTime>86400</SilenceTime>
      <Dimensions>[{}]</Dimensions>
      <RuleId>alarmRule_uuid_adbe286748952b82c6a4ebe3a07521697bb706****</RuleId>
      <Namespace>acs_ecs_dashboard</Namespace>
      <ContactGroups>rongfei</ContactGroups>
      <Escalations>
        <Critical>
          <Statistics>Average</Statistics>
          <Threshold>6666</Threshold>
          <Times>3</Times>
          <ComparisonOperator>GreaterThanOrEqualToThreshold</ComparisonOperator>
        </Critical>
        <Info/>
        <Warn/>
      </Escalations>
      <ComparisonOperator>&gt;=</ComparisonOperator>
      <Resources>[{"instanceId":"host-fTcUci7****"}</Resources>
    </Alarm>
  </Alarms>
  <RequestId>0F05309F-8863-4B2A-8F52-C6AA00E701B4</RequestId>
  <Success>true</Success>
  <Code>200</Code>
  <Total>102</Total>
</DescribeMetricRuleListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0F05309F-8863-4B2A-8F52-C6AA00E701B4",
	"Alarms":{
		"Alarm":[
			{
				"Period":60,
				"Statistics":"Average",
				"GroupName":"组的名称",
				"Webhook":"",
				"Subject":"aaabbb",
				"EffectiveInterval":"00:00-23:59",
				"RuleName":"我的报警规则",
				"NoEffectiveInterval":"",
				"GroupId":"3596360",
				"EvaluationCount":3,
				"MetricName":"cpu_total",
				"Threshold":"92",
				"State":"OK",
				"Enable":true,
				"SilenceTime":86400,
				"Dimensions":"[{}]",
				"RuleId":"a151cd6023eacee2f0978e03863cc1697c89508e2b61****",
				"Namespace":"acs_ecs_dashboard",
				"ContactGroups":"测试",
				"ComparisonOperator":">=",
				"Escalations":{
					"Critical":{
						"Statistics":"Average",
						"Threshold":"92",
						"Times":3,
						"ComparisonOperator":"GreaterThanOrEqualToThreshold"
					},
					"Info":{},
					"Warn":{}
				},
				"Resources":"[{\"instanceId\":\"i-a2d5q7pm3f12****\"}]"
			},
			{
				"Period":60,
				"Statistics":"Average",
				"GroupName":"demo",
				"Webhook":"",
				"Subject":"${serviceType}-${metricName}-${levelDescription}通知（${dimensions}）",
				"EffectiveInterval":"00:00-23:59",
				"RuleName":"xxxxxxxxxxxxxxx",
				"NoEffectiveInterval":"",
				"GroupId":"12345",
				"EvaluationCount":3,
				"MetricName":"cpu_total",
				"Threshold":"90",
				"State":"OK",
				"Enable":true,
				"SilenceTime":86400,
				"Dimensions":"[{}]",
				"RuleId":"alarmRule_uuid_adbe286748952b82c6a4ebe3a07521697bb706****",
				"Namespace":"acs_ecs_dashboard",
				"ContactGroups":"rongfei",
				"ComparisonOperator":">=",
				"Escalations":{
					"Critical":{
						"Statistics":"Average",
						"Threshold":"6666",
						"Times":3,
						"ComparisonOperator":"GreaterThanOrEqualToThreshold"
					},
					"Info":{},
					"Warn":{}
				},
				"Resources":"[{\"instanceId\":\"host-fTcUci7****\"}"
			}
		]
	},
	"Success":true,
	"Code":"200",
	"Total":102
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

