# DescribeMetricRuleTemplateAttribute {#doc_api_Cms_DescribeMetricRuleTemplateAttribute .reference}

You can call this operation to query the details of an alert template.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleTemplateAttribute) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeMetricRuleTemplateAttribute|The operation that you want to perform. Set the value to DescribeMetricRuleTemplateAttribute.

 |
|Name|String|No|My template|The name of the alert template.

 |
|TemplateId|String|No|123|The ID of the alert template.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|RequestId|String|C14F2566-B4AC-4C3E-AC7D-0A1D16CF33DE|The request ID for troubleshooting.

 |
|Message|String|success|The error message.

 |
|Resource| | |The details of the alert template.

 |
|└AlertTemplates| | |The alert template.

 |
|└Category|String|ecs|The abbreviation of the service name.

 |
|└Escalations| | |The threshold and alert level.

 |
|└Critical| | |The critical-level alert.

 |
|└ComparisonOperator|String|GreaterThanOrEqualToThreshold|The comparison operator of the threshold for critical-level alerts. Valid values:

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
|└Statistics|String|Average|The statistical method of the threshold for critical-level alerts.

 |
|└Threshold|String|90|The threshold of critical-level alerts.

 |
|└Times|Integer|3|The consecutive number of times for which the metric value exceeds the threshold for critical-level alerts before an alert is triggered.

 |
|└Info| | |The info-level alert.

 |
|└ComparisonOperator|String|GreaterThanOrEqualToThreshold|The comparison operator of the threshold for info-level alerts. Valid values:

 -   GreaterThanOrEqualToThreshold
-   GreaterThanThreshold
-   LessThanOrEqualToThreshold
-   LessThanThreshold,
-   NotEqualToThreshold
-   GreaterThanYesterday
-   LessThanYesterday
-   GreaterThanLastWeek
-   LessThanLastWeek
-   GreaterThanLastPeriod
-   LessThanLastPeriod

 |
|└Statistics|String|Average|The statistical method of the threshold for info-level alerts.

 |
|└Threshold|String|90|The threshold of info-level alerts.

 |
|└Times|Integer|3|The consecutive number of times for which the metric value exceeds the threshold for warn-level alerts before an alert is triggered.

 |
|└Warn| | |The warn-level alert.

 |
|└ComparisonOperator|String|GreaterThanOrEqualToThreshold|The comparison operator of the threshold for warn-level alerts. Valid values:

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
|└Statistics|String|Average|The statistical method of the threshold for warn-level alerts.

 |
|└Threshold|String|90|The threshold of warn-level alerts.

 |
|└Times|Integer|3|The consecutive number of times for which the metric value exceeds the threshold for info-level alerts before an alert is triggered.

 |
|└MetricName|String|cpu\_total|The name of the metric.

 |
|└Namespace|String|acs\_ecs\_dashboard|The namespace of the service.

 |
|└RuleName|String|My alarm rule|The name of the alert rule.

 |
|└Selector|String|\{"disk":"/"\}|The dimension of the alert. It is an extended field.

 |
|└Description|String|Alert template description|The description of the alert template.

 |
|└Name|String|CPU monitoring template|The name of the alert template.

 |
|└RestVersion|String|0|The version of the alert rule template.

 |
|└TemplateId|String|123|The ID of the alert template.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMetricRuleTemplateAttribute
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMetricRuleTemplateAttributeResponse>
  <Resource>
    <RestVersion>0</RestVersion>
    <Name>nametest</Name>
    <Description>nametestDesc</Description>
    <AlertTemplates>
      <AlertTemplate>
        <Category>ecs</Category>
        <MetricName>cpu_total</MetricName> 
        <Namespace>acs_ecs_dashboard</Namespace>
        <RuleName>cpu_total</RuleName>
        <Escalations>
          <Critical/>
          <Info/>
          <Warn>
            <Statistics>Average</Statistics>
            <Threshold>90.0</Threshold>
            <Times>1</Times>
            <ComparisonOperator>GreaterThanOrEqualToThreshold</ComparisonOperator>
          </Warn>
        </Escalations>
      </AlertTemplate>
      <AlertTemplate>
        <Category>rds</Category>
        <MetricName>AvgLogSize</MetricName>
        <Namespace>acs_rds_dashboard</Namespace>
        <RuleName>AvgLogSize</RuleName>
        <Escalations>
          <Critical/>
          <Info/>
          <Warn>
            <Statistics>Average</Statistics>
            <Threshold>12.0</Threshold>
            <Times>1</Times>
            <ComparisonOperator>GreaterThanOrEqualToThreshold</ComparisonOperator>
          </Warn>
        </Escalations>
      </AlertTemplate>
    </AlertTemplates>
    <TemplateId>45</TemplateId>
  </Resource>
  <RequestId>C14F2566-B4AC-4C3E-AC7D-0A1D16CF33DE</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DescribeMetricRuleTemplateAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Resource":{
		"Name":"nametest",
		"RestVersion":0,
		"Description":"nametestDesc",
		"AlertTemplates":{
			"AlertTemplate":[
				{
					"Category":"ecs",
					"MetricName":"cpu_total",
					"Namespace":"acs_ecs_dashboard",
					"RuleName":"cpu_total",
					"Escalations":{
						"Critical":{},
						"Info":{},
						"Warn":{
							"Statistics":"Average",
							"Threshold":"90.0",
							"Times":1,
							"ComparisonOperator":"GreaterThanOrEqualToThreshold"
						}
					}
				},
				{
					"Category":"rds",
					"MetricName":"AvgLogSize",
					"Namespace":"acs_rds_dashboard",
					"RuleName":"AvgLogSize",
					"Escalations":{
						"Critical":{},
						"Info":{},
						"Warn":{
							"Statistics":"Average",
							"Threshold":"12.0",
							"Times":1,
							"ComparisonOperator":"GreaterThanOrEqualToThreshold"
						}
					}
				}
			]
		},
		"TemplateId":45
	},
	"RequestId":"C14F2566-B4AC-4C3E-AC7D-0A1D16CF33DE",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

