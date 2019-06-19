# DescribeMetricRuleList {#doc_api_Cms_DescribeMetricRuleList .reference}

You can call this operation to query the list of alert rules.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeMetricRuleList| The operation that you want to perform. Set the value to DescribeMetricRuleList.

 |
|Namespace|String|No|acs\_ecs\_dashboard| The data namespace of the service. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~).

 |
|MetricName|String|No|cpu\_total| The name of the metric. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~).

 |
|EnableState|Boolean|No|true| The status of the metric. true indicates that the alert rule is enabled. false indicates that the alert rule is disabled. Alert rules in all states are displayed by default.

 |
|Page|String|No|1| The number of the page. Default value: 1.

 |
|PageSize|String|No|10| The number of records on each page. Default value: 10.

 |
|AlertState|String|No|ALARM| The status of the alert rule. Valid values:

 -   OK: There are no active alerts triggered based on the alert rule.
-   ALARM: There is at least one alert triggered based on the alert rule.
-   INSUFFICIENT\_DATA: No data is available.

 |
|Dimensions|String|No|\{"instanceId":"i-xy123\*\*\*\*"\}| The instance associated with the alert rule. It is a JSON object string, such as \{"instanceId":"name1"\}. This parameter is used to query all rules associated with the instance. If you specify this parameter, you must also specify the Namespace parameter.

 |
|RuleName|String|No|ECS CPU alert rule| The name of the alert rule. Fuzzy search is supported.

 |
|GroupId|String|No|123456| The ID of the application group.

 |
|RuleIds|String|No|a151cd6023eacee2f0978e03863cc1697c8950812\*\*\*\*| The ID of the alert rule. Multiple alert IDs must be separated with commas \(,\). Up to 20 records can be queried at a time

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Code|Integer|200| The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success| The error message.

 |
|RequestId|String|0E657631-CD6C-4C24-9637-98D000B9272C| The request ID for troubleshooting.

 |
|Alarms| | | The list of alert rules.

 |
|└AlertState|String|OK| The status of the alert rule. Valid values:

 -   OK: There are no active alerts triggered based on the alert rule.
-   ALARM: There is at least one alert triggered based on the alert rule.
-   INSUFFICIENT\_DATA: No data is available.

 |
|└ContactGroups|String|Default alert contacts| The alert contacts.

 |
|└Dimensions|String|\[\{\}\]| The associated extended resources.

 |
|└EffectiveInterval|String|00:00-23:59| The period when the alert rule is effective.

 |
|└EnableState|Boolean|true| The status of the alert rule. Valid values:

 -   true: indicates that the alert rule is enabled.
-   false: indicates that the alert rule is disabled.

 |
|└Escalations| | | The trigger conditions for different levels of alerts.

 |
|└Critical| | | The trigger conditions for critical-level alerts.

 |
|└ComparisonOperator|String|GreaterThanOrEqualToThreshold| The comparison operator of the threshold for critical-level alerts. Valid values:

 -   GreaterThanOrEqualToThreshold
-   GreaterThanThreshold
-   LessThanOrEqualToThreshold
-   LessThanThreshold
-   NotEqualToThreshold
-   GreaterThanYesterday
-   LessThanYesterday
-   GreaterThanLastWeek
-   LessThanLastWeek
-   GreaterThanLastPeriod
-   LessThanLastPeriod

 |
|└Statistics|String|Average| The statistical method for critical-level alerts.

 |
|└Threshold|String|90| The threshold for critical-level alerts.

 |
|└Times|String|3| The consecutive number of times for which the metric value exceeds the threshold for critical-level alerts before an alert is triggered.

 |
|└Info| | | The trigger conditions for info-level alerts.

 |
|└ComparisonOperator|String|GreaterThanOrEqualToThreshold| The comparison operator of the threshold for info-level alerts. Valid values:

 -   GreaterThanOrEqualToThreshold
-   GreaterThanThreshold
-   LessThanOrEqualToThreshold
-   LessThanThreshold
-   NotEqualToThreshold
-   GreaterThanYesterday
-   LessThanYesterday
-   GreaterThanLastWeek
-   LessThanLastWeek
-   GreaterThanLastPeriod
-   LessThanLastPeriod

 |
|└Statistics|String|Average| The statistical method for info-level alerts.

 |
|└Threshold|String|90| The threshold for info-level alerts.

 |
|└Times|String|1| The consecutive number of times for which the metric value exceeds the threshold for info-level alerts before an alert is triggered.

 |
|└Warn| | | The trigger conditions for warn-level alerts.

 |
|└ComparisonOperator|String|GreaterThanOrEqualToThreshold| The comparison operator of the threshold for warn-level alerts. Valid values:

 -   GreaterThanOrEqualToThreshold
-   GreaterThanThreshold
-   LessThanOrEqualToThreshold
-   LessThanThreshold
-   NotEqualToThreshold
-   GreaterThanYesterday
-   LessThanYesterday
-   GreaterThanLastWeek
-   LessThanLastWeek
-   GreaterThanLastPeriod
-   LessThanLastPeriod

 |
|└Statistics|String|Average| The statistical method for warn-level alerts.

 |
|└Threshold|String|90| The threshold for warn-level alerts.

 |
|└Times|String|3| The consecutive number of times for which the metric value exceeds the threshold for warn-level alerts before an alert is triggered.

 |
|└GroupId|String|123456| The ID of the application group.

 |
|└GroupName|String|My application group| The name of the application group associated with the alert rule.

 |
|└MailSubject|String|An alert occurs| The subject of the alert notification email.

 |
|└MetricName|String|cpu\_total| The name of the metric.

 |
|└Namespace|String|acs\_ecs\_dashboard| The namespace of the service. It is used to differentiate different services.

 |
|└NoEffectiveInterval|String|00:00-23:59| The period when the alert rule is ineffective.

 |
|└Period|String|60| The statistical period.

 |
|└Resources|String|\[\{\\"instanceId\\":\\"i-a2d5q7pm3f9yr29e\*\*\*\*\\"\},\{\\"instanceId\\":\\"i-a2d5q7pm3f9yr29e\*\*\*\*\\"\}| The resources associated with the alert rule.

 |
|└RuleId|String|a151cd6023eacee2f0978e03863cc1697c895012\*\*\*\*| The ID of the alert rule.

 |
|└RuleName|String|My alert rule| The name of the alert rule.

 |
|└SilenceTime|String|86400| The mute duration in which no new alerts are sent even if the trigger conditions are met. Unit: second. Default value: 86400 \(one day\). Minimum value: 3600. Only one alert is sent in each mute duration.

 |
|└Webhook|String|http://www.aliyun.com| The callback URL.

 |
|Total|String|21| The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMetricRuleList
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMetricRuleListResponse>
  <Alarms>
    <Alarm>
      <Period>60</Period>
      <Statistics>Average</Statistics>
      <GroupName>Group name</GroupName>
      <Webhook/>
      <Subject>aaabbb</Subject>
      <EffectiveInterval>00:00-23:59</EffectiveInterval>
      <RuleName>My alert rule</RuleName>
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
      <ContactGroups>Test</ContactGroups>
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
      <Subject>${serviceType}-${metricName}-${levelDescription}notification(${dimensions})</Subject>
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

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"0F05309F-8863-4B2A-8F52-C6AA00E701B4",
	"Alarms":{
		"Alarm":[
			{
				"Period":60,
				"Statistics":"Average",
				"GroupName":"Group name",
				"Webhook":"",
				"Subject":"aaabbb",
				"EffectiveInterval":"00:00-23:59",
				"RuleName":"Mu alert rule",
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
				"ContactGroups":"Test",
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
				"Subject":"${serviceType}-${metricName}-${levelDescription}notification(${dimensions})",
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

## Error code {#section_t51_98z_mxs .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

