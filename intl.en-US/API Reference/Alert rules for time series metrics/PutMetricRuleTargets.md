# PutMetricRuleTargets {#doc_api_Cms_PutMetricRuleTargets .reference}

You can call this operation to add or modify targets of an alert rule.

Currently, this operation only supports targets of the MNS type.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides OpenAPI Explorer to simplify API usage. You can use [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=PutMetricRuleTargets) to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PutMetricRuleTargets|The operation that you want to perform. Set this parameter to PutMetricRuleTargets.

 |
|RuleId|String|Yes|rulexx12346|The ID of the alert rule for which you want to add or modify targets.

 |
|Targets.N.Arn|String|No|acs:mns:cn-hangzhou:111:/queues/test/message|The resource description in the format of acs:\{Service name abbreviation\}:\{regionId\}:\{userId\}:/\{Message resource type\}/\{Resource name\}/message. Example: acs:mns:cn-hangzhou:111:/queues/test/message.

 -   \{Service name abbreviation\}: Currently, only MNS is supported. Set this parameter to mns.
-   \{regionId\}: the ID of the region where the message queue or topic is located.
-   \{userId\}: the account ID of the user.
-   \{Message resource type\}: Set this parameter to queues or topics.
-   \{Resource name\}: If the message resource type is set to queues, set this parameter to the queue name. If the message resource type is set to topics, set this parameter to the topic name.

 |
|Targets.N.Id|String|No|1|The ID of the target. The ID must be unique in the alert rule.

 |
|Targets.N.Level|String|No|\["INFO", "WARN", "CRITICAL"\]|The severity of the alert rule, in the format of a JSON array. Valid values:

 -   INFO
-   WARN
-   CRITICAL

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|FailData| | |The list of the targets that failed to be added or modified.

 |
|└Targets| | |The list of the targets that failed to be added or modified.

 |
|└Arn|String|acs:mns:cn-hangzhou:111:/queues/test/message|The resource description of the target. For more information, see the description in request parameters.

 |
|└Id|String|1|The ID of the target.

 |
|└Level|String|\["INFO", "WARN", "CRITICAL"\]|The severity of the alert rule, in the format of a JSON array. Valid values:

 -   INFO
-   WARN
-   CRITICAL

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

http(s)://[Endpoint]/? Action=PutMetricRuleTargets
&RuleId=rulexx12346
&<Common request parameters>

```

Sample success response

`XML` format

``` {#xml_return_success_demo}
<PutMetricRuleTargetsResponse>
  <Message>Success</Message>
  <Success>true</Success>
  <RequestId>786E92D2-AC66-4250-B76F-F1E2FCDDBA1C</RequestId>
  <FailData>
    <Targets>
      <Arn>acs:mns:cn-hangzhou:111:/queues/test/message</Arn>
      <Id>1</Id>
      <Level>INFO</Level>
      <Level>WARN</Level>
      <Level>CRITICAL</Level>
    </Targets>
  </FailData>
</PutMetricRuleTargetsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"FailData":{
		"Targets":[
			{
				"Level":[
					"INFO",
					"WARN",
					"CRITICAL"
				],
				"Id":1,
				"Arn":"acs:mns:cn-hangzhou:111:/queues/test/message"
			}
		]
	},
	"Message":"Success",
	"RequestId":"786E92D2-AC66-4250-B76F-F1E2FCDDBA1C",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes.](https://error-center.aliyun.com/status/product/Cms)

