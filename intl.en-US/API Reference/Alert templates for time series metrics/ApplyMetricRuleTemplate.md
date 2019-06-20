# ApplyMetricRuleTemplate {#doc_api_Cms_ApplyMetricRuleTemplate .reference}

You can call this operation to apply an alert rule template to an application group to generate an alert rule.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=ApplyMetricRuleTemplate) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|ApplyMetricRuleTemplate|The operation that you want to perform. Set the value to ApplyMetricRuleTemplate.

 |
|GroupId|Long|Yes|12345|The ID of the application group.

 |
|TemplateIds|String|Yes|123|The ID of the alert rule template.

 |
|ApplyMode|String|No|GROUP\_INSTANCE\_FIRST|-   GROUP\_INSTANCE\_FIRST: The alert rule template is used to create an alert rule if the specified instances exist in the application group. No alert rule is created if the specified instances do not exist in the application group.
-   ALARM\_TEMPLATE\_FIRST: The alert rule template is used to create an alert rule no matter whether the specified instances exist in the application group.

 |
|EnableEndTime|Long|No|23|The end time of the alert period. A value of 00-23 indicates a period in time from 00:59 to 23:59.

 |
|EnableStartTime|Long|No|00|The start time of the alert period. A value of 00-23 indicates a period in time from 00:00 to 23:00.

 |
|SilenceTime|Long|No|86400|The duration of the mute period during which new alerts are not sent even if the trigger conditions are met. Unit: second. Default value: 86400 seconds \(one day\). Only one alert is sent during each mute duration even if the metric value exceeds the alert rule threshold for several consecutive times.

 |
|Webhook|String|No|http://www.aliyun.com|The callback URL triggered when an alert occurs. A POST request is sent to the specified URL.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code.

 |
|Message|String|success|The error message.

 |
|RequestId|String|1B25BAE2-DA60-428C-8414-37A11EEB49B5|The request ID for troubleshooting.

 |
|Resource| | |The affected resources.

 |
|└AlertResults| | |The details of the generated alert rule.

 |
|└Code|String|200|The status code.

 |
|└GroupId|Long|123456|The ID of the application group.

 |
|└Message|String|success|The error message.

 |
|└RuleId|String|applyTemplate44491519-xxxx-xxx|The ID of the alert rule.

 |
|└RuleName|String|ruleNamex|The name of the alert rule.

 |
|└Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|└GroupId|Long|12345|The ID of the application group.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=ApplyMetricRuleTemplate
&GroupId=12345
&TemplateIds=123
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<ApplyMetricRuleTemplateResponse>
  <RequestId>3F897F3C-020A-4993-95B4-63ABB84F83E6</RequestId>
  <Resource>
    <AlertResults>
      <DisplayName>xxxx11</DisplayName>
      <Code>200</Code>
      <Success>true</Success> 
      <Name>applyTemplate12345-321</Name>
      <GroupId>123456</GroupId>
    </AlertResults>
    <AlertResults>
      <DisplayName>abb33</DisplayName>
      <Code>200</Code>
      <Success>true</Success> 
      <Name>applyTemplate12345-322</Name>
      <GroupId>123457</GroupId>
    </AlertResults>
    <AlertResults>
      <DisplayName>aaaa</DisplayName>
      <Code>200</Code>
      <Success>true</Success> 
      <Name>applyTemplate12345-322</Name>
      <GroupId>123459</GroupId>
    </AlertResults>
    <GroupId>3040150</GroupId>
  </Resource>
  <ErrorCode>200</ErrorCode> 
  <Success>true</Success> 
</ApplyMetricRuleTemplateResponse> 

```

`JSON` format

``` {#json_return_success_demo}
{
	"Resource":{
		"AlertResults":[
			{
				"Name":"applyTemplate12345-321",
				"Success":true,
				"DisplayName":"xxxx11",
				"GroupId":123456,
				"Code":200
			},
			{
				"Name":"applyTemplate12345-322",
				"Success":true,
				"DisplayName":"abb33",
				"GroupId":123457,
				"Code":200
			},
			{
				"Name":"applyTemplate12345-322",
				"Success":true,
				"DisplayName":"aaaa",
				"GroupId":123459,
				"Code":200
			}
		],
		"GroupId":3040150
	},
	"RequestId":"3F897F3C-020A-4993-95B4-63ABB84F83E6",
	"Success":true,
	"ErrorCode":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

