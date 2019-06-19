# CreateGroupMetricRules {#doc_api_Cms_CreateGroupMetricRules .reference}

You can call this operation to create multiple metric alert rules for an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=CreateGroupMetricRules) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|GroupId|Long|Yes|123456|The ID of application group.

 |
|Action|String|No|CreateGroupMetricRules|The operation that you want to perform. Set the value to CreateGroupMetricRules.

 |
|GroupMetricRules.N.Category|String|No|ecs|The abbreviation of the service name. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Dimensions|String|No|\[\{"instanceId":"xxxxxx"\}\]|The expended resource dimensions. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.EffectiveInterval|String|No|00:00-23:59|The period when the alert rule is effective. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.EmailSubject|String|No|An alert occurs|The subject of the alert notification email. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Critical.ComparisonOperator|String|No|GreaterThanOrEqualToThreshold|The comparison operator of the threshold for critical-level alerts. Valid values:

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

 Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Critical.Statistics|String|No|Average|The statistical method for critical-level alerts. The statistical method varies with metric. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Critical.Threshold|String|No|90|The threshold for critical-level alerts. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Critical.Times|Integer|No|3|The consecutive number of times for which the metric value exceeds the threshold for critical-level alerts before an alert is triggered. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Info.ComparisonOperator|String|No|GreaterThanOrEqualToThreshold|The comparison operator of the threshold for info-level alerts. Valid values:

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

 Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Info.Statistics|String|No|Average|The statistical method for info-level alerts. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Info.Threshold|String|No|90|The threshold for info-level alerts. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Info.Times|Integer|No|3|The consecutive number of times for which the metric value exceeds the threshold for info-level alerts before an alert is triggered. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Warn.ComparisonOperator|String|No|GreaterThanOrEqualToThreshold|The comparison operator of the threshold for warn-level alerts. Valid values:

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

 Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Warn.Statistics|String|No|Average|The statistical method for warn-level alerts. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Warn.Threshold|String|No|90|The threshold for warn-level alerts. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Escalations.Warn.Times|Integer|No|3|The consecutive number of times for which the metric value exceeds the threshold for warn-level alerts before an alert is triggered. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Interval|String|No|60|The detection period of alerts. Valid values of N: 1 to 200. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.MetricName|String|No|cpu\_total|The name of the metric. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~). Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Namespace|String|No|acs\_ecs\_dashboard|The data namespace of the service. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~). Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.NoEffectiveInterval|String|No|00:00-05:30|The period when the alert rule is ineffective. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Period|String|No|60|The aggregation period. Unit: second. Valid values of N: 1 to 200. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.RuleId|String|No|bfae2ca5b4e07d2c7278772eccda169808c7b\*\*\*\*|The ID of the alert rule. The IDs of alert rules are generated by callers to ensure uniqueness. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.RuleName|String|No|Alert rule 1|The name of the alert rule. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.SilenceTime|Integer|No|86400|The duration of the mute period during which new alerts are not sent even if the trigger conditions are met. Unit: second. Default value: 86400. Minimum value: 3600. Valid values of N: 1 to 200. Valid values of N: 1 to 200.

 |
|GroupMetricRules.N.Webhook|String|No|http://www.aliyun.com|The callback URL triggered when an alert occurs. Valid values of N: 1 to 200.

 |

You must select at least one of the three alert trigger conditions. Otherwise, the alert rule cannot be created.

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful. A value other than 200 indicates that the call has failed.

 |
|Message|String|success|The error message.

 |
|RequestId|String|461CF2CD-2FC3-4B26-8645-7BD27E7D0F1D|The request ID for troubleshooting.

 |
|Resources| | |The list of resources to which the created alert rule applies.

 |
|└Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|└Message|String|success|The error message.

 |
|└RuleId|String|a151cd6023eacee2f0978e03863cc1697c89508\*\*\*\*|The ID of the alert rule.

 |
|└RuleName|String|Alert rule 1|The name of the alert rule.

 |
|└Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateGroupMetricRules
&GroupId=123456
&GroupMetricRules. 1.Category=ecs
&GroupMetricRules. 1.MetricName=cpu_total
&GroupMetricRules. 1.1amespace=acs_ecs_dashboard
&GroupMetricRules. 1.RuleId=bfae2ca5b4e07d2c7278772eccda169808c7b****
&GroupMetricRules. 1.RuleName=Alert rule 1
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<CreateGroupMetricRulesResponse>
  <RequestId>65D50468-ECEF-48F1-A6E1-D952E89D9436</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
  <Resources>
    <AlertResult>
      <RuleId>xxxx1298766</RuleId>
      <Success>true</Success> 
      <RuleName>My rule name 1</RuleName>
      <Code>200</Code>
    </AlertResult>
    <AlertResult>
      <Message>Metric not found. </Message> 
      <RuleId>hyu91929****</RuleId>
      <Success>false</Success>
      <RuleName>RuleId 2</RuleName>
      <Code>404</Code> 
    </AlertResult>
  </Resources>
</CreateGroupMetricRulesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"65D50468-ECEF-48F1-A6E1-D952E89D9436",
	"Success":"true",
	"Code":"200",
	"Resources":{
		"AlertResult":[
			{
				"RuleId":"xxxx1298766",
				"RuleName":"My rule name 1",
				"Success":"true",
				"Code":"200"
			},
			{
				"Message":"Metric not found.",
				"RuleId":"hyu91929****",
				"RuleName":"RuleId 2",
				"Success":"false",
				"Code":"404"
			}
		]
	}
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

