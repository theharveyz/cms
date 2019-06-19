# DescribeAlertingMetricRuleResources {#doc_api_Cms_DescribeAlertingMetricRuleResources .reference}

You can call this operation to query the resources with active alerts triggered based on an alert rule.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeAlertingMetricRuleResources) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|DescribeAlertingMetricRuleResources|The operation that you want to perform. Set the value to DescribeAlertingMetricRuleResources.

 |
|GroupId|String|Yes|123456|The ID of application group.

 |
|RuleId|String|Yes|alarm-uuid1234abc\*\*\*\*|The ID of the alert rule. You must specify either the GroupId or the RuleId parameter. If both parameters are specified, records that meet both conditions are returned.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description |
|---------|----|-------|------------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|9B868619-77B4-4623-AD64-6181EA7CF8FA|The request ID for troubleshooting.

 |
|Resources| | |The list of resources to which the alert rule applies.

 |
|└Enable|String|true|The status of the alert rule.

 |
|└GroupId|String|123456|The ID of the application group with which the alert rule is associated.

 |
|└LastAlertTime|String|1554718182000|The time when the alert was last triggered.

 |
|└LastModifyTime|String|1554723762000|The time when the rule was last modified.

 |
|└MetricValues|String|\{"timestamp":1554723720000,"Value":631\}|The metric value when an alert is triggered. It is a JSON string with the value varies with metric.

 |
|└Resource|String|userId=177541323192\*\*\*\*,taskId=3\*\*\*\*,instanceId=i-bp1a0v6yzqrms01k\*\*\*\*|The resource to be associated with the alert rule.

 |
|└RetryTimes|String|3|The number of retries.

 |
|└RuleId|String|alerRule1\*\*\*\*|The ID of the alert rule.

 |
|└RuleName|String|cpuAlert|The name of the alert rule.

 |
|└StartTime|String|1545901080000|The time when the resource is associated with the alert rule.

 |
|└Threshold|String|90|The alert threshold.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Total|Integer|2|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeAlertingMetricRuleResources
&GroupId=123456
&RuleId=alarm-uuid1234abc****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeAlertingMetricRuleResourcesResponse>
  <Total>1</Total> 
  <Resources>
    <Resource>
      <Enable>true</Enable>
      <Resource>userId=12****,instanceId=i-bp1a012****</Resource>
      <RuleId>alerRuleId****</RuleId>
      <RetryTimes>3</RetryTimes>
      <LastAlertTime>1554718182000</LastAlertTime>
      <MetricValues>{"timestamp":1554723720000,"Value":631}</MetricValues>
      <LastModifyTime>1554723762000</LastModifyTime>
      <StartTime>1545901080000</StartTime>
      <RuleName>ruleId</RuleName>
      <Threshold>400</Threshold>
      <GroupId>33488</GroupId>
    </Resource>
  </Resources>
  <Success>true</Success> 
</DescribeAlertingMetricRuleResourcesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Success":true,
	"Total":1,
	"Resources":{
		"Resource":[
			{
				"LastAlertTime":1554718182000,
				"Resource":"userId=12****,instanceId=i-bp1a012****",
				"Threshold":"400",
				"Enable":true,
				"LastModifyTime":1554723762000,
				"RuleId":"alerRuleId****",
				"MetricValues":"{\"timestamp\":1554723720000,\"Value\":631}",
				"RetryTimes":3,
				"StartTime":1545901080000,
				"RuleName":"ruleId",
				"GroupId":"33488"
			}
		]
	}
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

