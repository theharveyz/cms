# DeleteMetricRuleTargets {#doc_api_Cms_DeleteMetricRuleTargets .reference}

You can call this operation to delete targets of an alert rule.

Currently, this operation only supports targets of the MNS type.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides OpenAPI Explorer to simplify API usage. You can use [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMetricRuleTargets) to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteMetricRuleTargets|The operation that you want to perform. Set this parameter to DeleteMetricRuleTargets.

 |
|RuleId|String|Yes|ruleId-xxxxxx|The ID of the alert rule for which you want to delete targets.

 |
|TargetIds.N|RepeatList|No|1|The ID of the target to delete.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|FailIds| | |The list of the targets that failed to be deleted.

 |
|└TargetIds| |1|The ID of the target that failed to be deleted.

 |
|Message|String|success|The error message.

 |
|RequestId|String|786E92D2-AC66-4250-B76F-F1E2FCDDBA1C|The ID of the request.

 |
|Success|Boolean|true|Indicates whether the call was successful.

 |

## Examples {#demo .section}

Sample request

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteMetricRuleTargets
&RuleId=ruleId-xxxxxx
&<Common request parameters>

```

Sample success response

`XML` format

``` {#xml_return_success_demo}
<DeleteMetricRuleTargetsResponse>
  <Code>200</Code>
  <Message>Success</Message>
  <Success>true</Success>
  <RequestId>786E92D2-AC66-4250-B76F-F1E2FCDDBA1C</RequestId>
  <FailIds>1</FailIds>
</DeleteMetricRuleTargetsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"Success",
	"RequestId":"786E92D2-AC66-4250-B76F-F1E2FCDDBA1C",
	"Success":true,
	"Code":"200",
	"FailIds":[
		"1"
	]
}
```

## Error codes { .section}

[View error codes.](https://error-center.aliyun.com/status/product/Cms)

