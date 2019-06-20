# ModifyMetricRuleTemplate {#doc_api_Cms_ModifyMetricRuleTemplate .reference}

You can call this operation to modify an alert template.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=ModifyMetricRuleTemplate) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|TemplateId|Long|Yes|12346|The ID of the alert template.

 |
|Action|String|No|ModifyMetricRuleTemplate|The operation that you want to perform. Set the value to ModifyMetricRuleTemplate.

 |
|Name|String|No|My alert template|The name of the alert template.

 |
|Description|String|No|Alert template description|The description of the alert template.

 |
|RestVersion|Long|No|0|The version of the alert template. Call DescribeMetricRuleTemplateList or DescribeMetricRuleTemplateAttribute to obtain information about the alert templates. The combination of version and ID uniquely identifies an alert template.

 |
|AlertTemplates.N.MetricName|String|No|cpu\_total|The name of the metric.

 |
|AlertTemplates.N.RuleName|String|No|My alert rule|The name of the alert rule.

 |
|AlertTemplates.N.Category|String|No|ecs|The abbreviation of the service name such as ecs.

 |
|AlertTemplates.N.Namespace|String|No|acs\_ecs\_dashboard|The namespace of the service.

 |
|AlertTemplates.N.Period|Integer|No|60|The statistical period. We recommend that you do not use this parameter.

 |
|AlertTemplates.N.Selector|String|No|\{"disk":"/"\}|The extended field. For example, a value of \{"disk":"/"\} indicates that the template is applied to the root partition of all instances in a group.

 |
|AlertTemplates.N.Escalations.Critical.Statistics|String|No|Average|The statistical method of the threshold for critical-level alerts.

 |
|AlertTemplates.N.Escalations.Critical.ComparisonOperator|String|No|GreaterThanOrEqualToThreshold|The comparison operator of the threshold for critical-level alerts. Valid values:

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
|AlertTemplates.N.Escalations.Critical.Threshold|String|No|90|The threshold of critical-level alerts.

 |
|AlertTemplates.N.Escalations.Critical.Times|Integer|No|3|The consecutive number of times for which the metric value exceeds the threshold for critical-level alerts before an alert is triggered.

 |
|AlertTemplates.N.Escalations.Warn.Statistics|String|No|Average|The statistical method of the threshold for warn-level alerts.

 |
|AlertTemplates.N.Escalations.Warn.ComparisonOperator|String|No|GreaterThanOrEqualToThreshold|The comparison operator of the threshold for warn-level alerts. Valid values:

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
|AlertTemplates.N.Escalations.Warn.Threshold|String|No|90|The threshold of warn-level alerts.

 |
|AlertTemplates.N.Escalations.Warn.Times|Integer|No|3|The consecutive number of times for which the metric value exceeds the threshold for warn-level alerts before an alert is triggered.

 |
|AlertTemplates.N.Escalations.Info.Statistics|String|No|Average|The statistical method of the threshold for info-level alerts.

 |
|AlertTemplates.N.Escalations.Info.ComparisonOperator|String|No|GreaterThanOrEqualToThreshold|The comparison operator of the threshold for info-level alerts. Valid values:

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
|AlertTemplates.N.Escalations.Info.Threshold|String|No|90|The threshold of critical-level alerts.

 |
|AlertTemplates.N.Escalations.Info.Times|Integer|No|3|The consecutive number of times for which the metric value exceeds the threshold for info-level alerts before an alert is triggered.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|9E07117F-F6AE-4F1C-81E8-36FBB4892235|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=ModifyMetricRuleTemplate
&Name=My alert template
&TemplateId=12346
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<ModifyMetricRuleTemplateResponse>
  <Code>200</Code>
  <Template>123</Template>
  <RequestId>9E07117F-F6AE-4F1C-81E8-36FBB4892235</RequestId>
  <Success>true</Success> 
</ModifyMetricRuleTemplateResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"9E07117F-F6AE-4F1C-81E8-36FBB4892235",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

