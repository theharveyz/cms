# DescribeMetricRuleTargets {#doc_api_Cms_DescribeMetricRuleTargets .reference}

You can call this operation to query targets of an alert rule.

Currently, this operation only supports targets of the MNS type.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides OpenAPI Explorer to simplify API usage. You can use [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleTargets) to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeMetricRuleTargets|The operation that you want to perform. Set this parameter to DescribeMetricRuleTargets.

 |
|RuleId|String|Yes|rulIdxxxxx1|The ID of the alert rule for which you want to query targets.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|786E92D2-AC66-4250-B76F-F1E2FCDDBA1C|The ID of the request.

 |
|Targets| | |The targets that were queried.

 |
|└Arn|String|acs:mns:cn-hangzhou:111:/queues/test/message|The resource description in the format of acs:\{Service name abbreviation\}:\{regionId\}:\{userId\}:/\{Message resource type\}/\{Resource name\}/message. Example: acs:mns:cn-hangzhou:111:/queues/test/message.

 -   \{Service name abbreviation\}: Currently, only MNS is supported. This parameter has a fixed value of mns.
-   \{userId\}: the account ID of the user.
-   \{regionId\}: the ID of the region where the message queue or topic is located.
-   \{Message resource type\}: The value can be queues or topics.
-   \{Resource name\}: If the message resource type is queues, the value of this parameter is the queue name. If the message resource type is topics, the value of this parameter is the topic name.

 |
|└Id|String|1|The ID of the target.

 |
|└Level|String|\["INFO", "WARN", "CRITICAL"\]|The severity of the alert rule, in the format of a JSON array. Valid values:

 -   INFO
-   WARN
-   CRITICAL

 |

## Examples {#demo .section}

Sample request

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMetricRuleTargets
&RuleId=rulIdxxxxx1
&<Common request parameters>

```

Sample success response

`XML` format

``` {#xml_return_success_demo}
<DescribeMetricRuleTargetsResponse>
  <Code>200</Code>
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
</DescribeMetricRuleTargetsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"Success",
	"RequestId":"786E92D2-AC66-4250-B76F-F1E2FCDDBA1C",
	"Success":true,
	"Code":"200",
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
}
```

## Error codes { .section}

[View error codes.](https://error-center.aliyun.com/status/product/Cms)

