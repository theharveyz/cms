# DescribeEventRuleList {#doc_api_Cms_DescribeEventRuleList .reference}

You can call this operation to query the list of event alerts.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeEventRuleList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeEventRuleList|The operation that you want to perform. Set the value to DescribeEventRuleList.

 |
|GroupId|String|No|12345|The ID of the application group.

 |
|NamePrefix|String|No|test|The name prefix of the alert rule. Fuzzy search is supported.

 |
|PageNumber|String|No|1|The number of the current page. Default value: 1.

 |
|PageSize|String|No|10|The number of records on each page.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|EventRules| | |The event rule.

 |
|└Description|String|event|The description of the rule.

 |
|└EventPattern| | |The event rule.

 |
|└EventTypeList| |Exception|The type of the event.

 |
|└LevelList| |\["CRITICAL", "WARN", "INFO"\]|The level of the event. Valid values:

 CRITICAL

 WARN

 INFO

 |
|└NameList| |\["Agent\_Status\_Stopped"\]|The list of event names.

 |
|└Product|String|CloudMonitor|The abbreviation of the service name.

 |
|└EventType|String|SYSTEM|The type of the event. Valid values: SYSTEM and CUSTOM.

 |
|└GroupId|String|12345|The ID of the application group.

 |
|└Name|String|evnetName|The name of the rule.

 |
|└State|String|ENABLED|The status of the rule. A value of ENABLED indicates that the rule is enabled. A value of DISABLED indicates that the rule is disabled.

 |
|Message|String|success|The error message.

 |
|RequestId|String|D0E6D82B-16B5-422A-8136-EE5BDC01E415|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Total|Integer|21|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeEventRuleList
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeEventRuleListResponse>
  <Datapoints> 
    <EventRule>
      <Name>aaabbb</Name>
      <State>ENABLED</State>
      <EventPattern>
        <EventTypeList>
          <EventTypeList>Exception</EventTypeList>
        </EventTypeList>
        <Product>CloudMonitor</Product>
        <LevelList>
          <LevelList>*</LevelList>
        </LevelList>
        <NameList>
          <NameList>Alert_SendShortMessageFailed_QuotaReached</NameList>
          <NameList>Group_AddResourcesFailed_QuotaReached</NameList>
          <NameList>Agent_Status_Stopped</NameList>
          <NameList>Agent_Status_Running</NameList>
        </NameList>
      </EventPattern>
      <EventType>SYSTEM</EventType>
    </EventRule> 
    <EventRule>
      <Name>default_group_event_rule_3384581</Name>
      <Description>Default group event rule</Description>
      <State>ENABLED</State>
      <EventPattern>
        <Product>*</Product>
        <LevelList>
          <LevelList>CRITICAL</LevelList>
          <LevelList>WARN</LevelList>
        </LevelList>
        <NameList>
          <NameList>*</NameList>
        </NameList>
      </EventPattern>
      <EventType>SYSTEM</EventType>
      <GroupId>338****</GroupId>
    </EventRule>
  </Datapoints> 
  <RequestId>D0E6D82B-16B5-422A-8136-EE5BDC01E415</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
  <Total>20</Total>
</DescribeEventRuleListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Datapoints":{
		"EventRule":[
			{
				"Name":"aaabbb",
				"State":"ENABLED",
				"EventPattern":{
					"EventTypeList":{
						"EventTypeList":[
							"Exception"
						]
					},
					"Product":"CloudMonitor",
					"LevelList":{
						"LevelList":[
							"*"
						]
					},
					"NameList":{
						"NameList":[
							"Alert_SendShortMessageFailed_QuotaReached",
							"Group_AddResourcesFailed_QuotaReached",
							"Agent_Status_Stopped",
							"Agent_Status_Running"
						]
					}
				},
				"EventType":"SYSTEM"
			},
			{
				"Name":"default_group_event_rule_3384581",
				"Description":"Default group event rule",
				"State":"ENABLED",
				"EventPattern":{
					"Product":"*",
					"LevelList":{
						"LevelList":[
							"CRITICAL",
							"WARN"
						]
					},
					"NameList":{
						"NameList":[
							"*"
						]
					}
				},
				"EventType":"SYSTEM",
				"GroupId":"338****"
			}
		]
	},
	"RequestId":"D0E6D82B-16B5-422A-8136-EE5BDC01E415",
	"Success":true,
	"Code":"200",
	"Total":20
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

