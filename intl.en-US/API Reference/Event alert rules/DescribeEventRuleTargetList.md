# DescribeEventRuleTargetList {#doc_api_Cms_DescribeEventRuleTargetList .reference}

You can call this operation to query the notification methods of an event alert rule.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeEventRuleTargetList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeEventRuleTargetList|The operation that you want to perform. Set the value to DescribeEventRuleTargetList.

 |
|RuleName|String|Yes|testRule|The name of the alert rule.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Message|String|success|The error message.

 |
|RequestId|String|87170bc7-e28a-4c93-b9bf-90a1dbe84736|The request ID for troubleshooting.

 |
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|MnsParameters| | |The MNS notification.

 |
|└Id|String|2|The unique ID of the MNS notification.

 |
|└Queue|String|testQueue|The name of the MNS queue.

 |
|└Region|String|cn-hangzhou|The region where MNS is deployed.

 |
|ContactParameters| | |The alert contact group notification.

 |
|└ContactGroupName|String|Default alert contact group|The name of the alert contact group.

 |
|└Id|String|1|The unique ID of the alert contact group notification.

 |
|└Level|String|3|The method of alert notification. Valid values: 2, 3, and 4.

 -   2: DingTalk Chatbot and email.
-   3: DingTalk Chatbot and email.
-   4: DingTalk Chatbot and email.

 |
|FcParameters| | |The Function Compute notification.

 |
|└FunctionName|String|fcTest1|The name of the function.

 |
|└Id|String|3|The unique ID of the Function Compute notification.

 |
|└Region|String|cn-qingdao|The region where Function Compute is deployed.

 |
|└ServiceName|String|service1|The name of the Function Compute service.

 |
|SlsParameters| | |The Log Service notification.

 |
|└Id|String|4|The unique ID of the Log Service notification.

 |
|└LogStore|String|logstore\_test|The name of the logstore.

 |
|└Project|String|project\_test|The name of the project.

 |
|└Region|String|cn-hangzhou|The region where the project is deployed.

 |
|WebhookParameters| | |The URL callback notification.

 |
|└Id|String|5|The unique ID of the URL callback notification.

 |
|└Method|String|GET|The request method of the HTTP callback. Valid values: GET and POST.

 |
|└Protocol|String|http|The name of the protocol.

 |
|└Url|String|http://www.aliyun.com|The callback URL.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeEventRuleTargetList
&RuleName=testRule
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeEventRuleTargetListResponse>
  <SlsParameters>
    <SlsParameter> 
      <Region>cn-hangzhou</Region>
      <Project>project-test</Project>
      <Id>4</Id>
      <LogStore>logstore-test</LogStore>
    </SlsParameter>
  </SlsParameters>
  <ContactParameters>
    <ContactParameter>
      <Id>1</Id>
      <Level>3</Level>
      <ContactGroupName>aaaaa</ContactGroupName>
    </ContactParameter>
  </ContactParameters>
  <MnsParameters>
    <MnsParameter>
      <Region>cn-hangzhou</Region>
      <Id>2</Id>
      <Queue>ECS-ops</Queue>
    </MnsParameter>
  </MnsParameters>
  <RequestId>174513e9-7da9-4f05-9cae-98f9959e9379</RequestId>
  <ParameterCount>1</ParameterCount>
  <FcParameters>
    <FCParameter>
      <Region>cn-hangzhou</Region>
      <ServiceName>MetricService-1</ServiceName>
      <FunctionName>MetricFunction-0</FunctionName>
      <Id>3</Id>
    </FCParameter>
  </FcParameters> 
  <Code>200</Code>
</DescribeEventRuleTargetListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"SlsParameters":{
		"SlsParameter":[
			{
				"Region":"cn-hangzhou",
				"Id":"4",
				"Project":"project-test",
				"LogStore":"logstore-test"
			}
		]
	},
	"ContactParameters":{
		"ContactParameter":[
			{
				"Level":"3",
				"Id":"1",
				"ContactGroupName":"aaaaa"
			}
		]
	},
	"MnsParameters":{
		"MnsParameter":[
			{
				"Region":"cn-hangzhou",
				"Queue":"ECS-ops",
				"Id":"2"
			}
		]
	},
	"RequestId":"174513e9-7da9-4f05-9cae-98f9959e9379",
	"ParameterCount":1,
	"FcParameters":{
		"FCParameter":[
			{
				"Region":"cn-hangzhou",
				"ServiceName":"MetricService-1",
				"FunctionName":"MetricFunction-0",
				"Id":"3"
			}
		]
	},
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

