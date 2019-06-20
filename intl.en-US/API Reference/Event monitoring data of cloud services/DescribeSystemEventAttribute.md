# DescribeSystemEventAttribute {#doc_api_Cms_DescribeSystemEventAttribute .reference}

You can call this operation to query system event details.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSystemEventAttribute) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSystemEventAttribute| The operation that you want to perform. Set the value to DescribeSystemEventAttribute.

 |
|EndTime|String|No|1552221584949| The end time.

 |
|EventType|String|No|Exception| The type of the event. The available event types vary with service.

 |
|GroupId|String|No|12346| The ID of the application group.

 |
|Level|String|No|warn| The level of the event. Valid values: CRITICAL, WARN, and INFO.

 |
|Name|String|No|BucketIngressBandwidth| The name of the event.

 |
|PageNumber|Integer|No|1| The number of the page. Default value: 1.

 |
|PageSize|Integer|No|10| The number of records on each page.

 |
|Product|String|No|oss| The abbreviation of the service name.

 |
|SearchKeywords|String|No|cms| The expression of keywords in the event content. Logical operators AND and OR are supported.

 a and b: searches for results that contain both a and b in the event content.

 a or b: searches for results that contain either a or b in the event content.

 |
|StartTime|String|No|1552199984949| The start time.

 |
|Status|String|No|normal| The status of the event. Multiple states must be separated with commas \(,\).

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200| The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success| The error message.

 |
|RequestId|String|60912C8D-B340-4253-ADE7-61ACDFD25CFC| The request ID for troubleshooting.

 |
|Success|String|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|SystemEvents| | | The details of the event.

 |
|└Content|String|\[\{"product":"CloudMonitor","content":"\{\\"ipGroup\\":\\"112.126.XX.XX,10.163.XX.XX\\",\\"tianjimonVersion\\":\\"1.2.22\\"\}","groupId":"176,177,178,179,180,692,120812,1663836,96,2028302","time":"1552209568000","resourceId":"acs:ecs:cn-beijing:173651113438\*\*\*\*:instance/i-25k35\*\*\*\*","level":"CRITICAL","status":"stopped","instanceName":"cmssiteprobebj-6","name":"Agent\_Status\_Stopped","regionId":"cn-beijing"\}\]| The details of the event.

 |
|└GroupId|String|12345| The ID of the application group.

 |
|└InstanceName|String|instanceId1| The name of the instance.

 |
|└Level|String|Warn| The level of the event. Valid values: CRITICAL, WARN, and INFO.

 |
|└Name|String|Agent\_Status\_Stopped| The name of the event.

 |
|└Num|Long|2| The number of events.

 |
|└Product|String|CloudMonitor| The abbreviation of the service name.

 |
|└RegionId|String|cn-hangzhou| The ID of the region.

 |
|└ResourceId|String|xxxxx-1| The ID of the resource.

 |
|└Status|String|normal| The status of the event.

 |
|└Time|Long|1552199984000| The time when the event occurred.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSystemEventAttribute
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeSystemEventAttributeResponse>
  <Message>userId:173651113438**** and product:"CloudMonitor"</Message>
  <RequestId>10CB54BE-CA25-4B48-BCAC-C4E0AF6C4A68</RequestId>
  <Data>[{"product":"CloudMonitor","content":"{\"ipGroup\":\"112.126.XX.XX,10.163.XX.XX\",\"tianjimonVersion\":\"1.2.22\"}","groupId":"176,177,178,179,180,692,120812,1663836,96,2028302","time":"1552209568000","resourceId":"acs:ecs:cn-beijing:173651113438****:instance/i-25k35****","level":"CRITICAL","status":"stopped","instanceName":"cmssiteprobebj-6","name":"Agent_Status_Stopped","regionId":"cn-beijing"}]</Data> 
  <Code>200</Code>
  <Success>true</Success> 
</DescribeSystemEventAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Data":"[{\"product\":\"CloudMonitor\",\"content\":\"{\\\"ipGroup\\\":\\\"112.126.XX.XX,10.163.XX.XX\\\",\\\"tianjimonVersion\\\":\\\"1.2.22\\\"}\",\"groupId\":\"176,177,178,179,180,692,120812,1663836,96,2028302\",\"time\":\"1552209568000\",\"resourceId\":\"acs:ecs:cn-beijing:173651113438****:instance/i-25k35****\",\"level\":\"CRITICAL\",\"status\":\"stopped\",\"instanceName\":\"cmssiteprobebj-6\",\"name\":\"Agent_Status_Stopped\",\"regionId\":\"cn-beijing\"}]",
	"Message":"userId:173651113438**** and product:\"CloudMonitor\"",
	"RequestId":"10CB54BE-CA25-4B48-BCAC-C4E0AF6C4A68",
	"Success":true,
	"Code":"200"
}
```

## Error codes {#section_9go_6ez_hq6 .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

