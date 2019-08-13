# PutMetricRuleTargets {#doc_api_Cms_PutMetricRuleTargets .reference}

You can call this operation to add or modify the message resource of an alert rule.

This operation only supports Message Notification Service \(MNS\) as the message service.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=PutMetricRuleTargets) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PutMetricRuleTargets|The operation that you want to perform. Set this parameter to PutMetricRuleTargets.

 |
|RuleId|String|Yes|rulexx12346|The ID of the alert rule.

 |
|Targets.N.Arn|String|No|acs:mns:cn-hangzhou:111:/queues/test/message|The resource description in the format of acs:\{service name abbreviation\}:\{regionId\}:\{userId\}:/\{message resource type\}/\{resource name\}/message, for example, acs:mns:cn-hangzhou:111:/queues/test/message.

 -   \{service name abbreviation\}: the abbreviation of the service name. Set this value to mns.
-   \{regionId\}: the region ID of the message queue or topic.
-   \{userId\}: the account ID of the user.
-   \{message resource type\}: the type of the message resource. Valid values: queues and topics.
-   \{resource name\}: the name of a queue if the resource type is queues, or the name of a topic if the type is topics.

 |
|Targets.N.Id|String|No|1|The ID of the message resource. The ID must be unique in the alert rule.

 |
|Targets.N.Level|String|No|\["INFO", "WARN", "CRITICAL"\]|The alert level, which is a string array. Valid values:

 -   INFO
-   WARN
-   CRITICAL

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|FailData| | |The list of error data.

 |
|Targets| | |The list of message resources that failed to be added or modified.

 |
|Arn|String|acs:mns:cn-hangzhou:111:/queues/test/message|The resource description in the format of acs:\{service name abbreviation\}:\{regionId\}:\{userId\}:/\{message resource type\}/\{resource name\}/message, for example, acs:mns:cn-hangzhou:111:/queues/test/message.

 -   \{service name abbreviation\}: the abbreviation of the service name. Set this value to mns.
-   \{regionId\}: the region ID of the message queue or topic.
-   \{userId\}: the account ID of the user.
-   \{message resource type\}: the type of the message resource. Valid values: queues and topics.
-   \{resource name\}: the name of a queue if the resource type is queues, or the name of a topic if the type is topics.

 |
|Id|String|1|The ID of the message resource.

 |
|Level|String|\["INFO", "WARN", "CRITICAL"\]|The alert level, which is a string array. Valid values:

 -   INFO
-   WARN
-   CRITICAL

 |
|Message|String|success|The error message.

 |
|RequestId|String|786E92D2-AC66-4250-B76F-F1E2FCDDBA1C|The ID of the request, which can be used for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful.

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

