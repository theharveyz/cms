# DescribeSystemEventCount {#doc_api_Cms_DescribeSystemEventCount .reference}

You can call this operation to query the number of events related to a service that occurred in a specified period in time.

The number of events related to the specified service is returned.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSystemEventCount) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|DescribeSystemEventCount|The operation that you want to perform. Set the value to DescribeSystemEventCount.

 |
|EndTime|String|No|1552220485596|The end time. It is the time that has passed since 00:00:00, January 1, 1970. Unit: millisecond.

 |
|EventType|String|No|Exception|The type of the event. The available event types vary with service. Call DescribeSystemEventMetaList to obtain the available event types of each service.

 |
|GroupId|String|No|12345|The ID of the application group.

 |
|Level|String|No|warn|The level of the event. Valid values: CRITICAL, WARN, and INFO.

 |
|Name|String|No|BucketIngressBandwidth|The name of the event.

 |
|Product|String|No|oss|The abbreviation of the service name. Call DescribeSystemEventMetaList to obtain the names of services for which system event monitoring is enabled.

 |
|SearchKeywords|String|No|cms|The expression of keywords in the event content. Logical operators AND and OR are supported.

 -   a and b: searches for results that contain both a and b in the event content.
-   a or b: searches for results that contain either a or b in the event content.

 |
|StartTime|String|No|1552209685596|The start time. It is the time that has passed since 00:00:00, January 1, 1970. Unit: millisecond.

 |
|Status|String|No|normal|The status of the event. Multiple states must be separated with commas \(,\).

 |

Call DescribeSystemEventMetaList to obtain information about the services for which system event monitoring is enabled. The returned information includes the service name, event name, event level, and event status.

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description |
|---------|----|-------|------------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|60912C8D-B340-4253-ADE7-61ACDFD25CFC|The request ID for troubleshooting.

 |
|Success|String|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|SystemEventCounts| | |The details of event quantity.

 |
|└Content|String|xxxx|The content.

 |
|└GroupId|String|123456|The ID of the application group.

 |
|└InstanceName|String|instanceId1|The ID of the instance.

 |
|└Level|String|Warn|The level of the event. Valid values: CRITICAL, WARN, and INFO.

 |
|└Name|String|Agent\_Status\_Stopped|The name of the event.

 |
|└Num|Long|2|The number of events.

 |
|└Product|String|ECS|The abbreviation of the service name.

 |
|└RegionId|String|cn-hangzhou|The region.

 |
|└ResourceId|String|xxxxx-1|The ID of the resource.

 |
|└Status|String|normal|The status of the event.

 |
|└Time|Long|1552199984000|The time when the event occurred.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSystemEventCount
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeSystemEventCountResponse>
  <Message>userId:1****|select product, name, count(product) as num group by product,name order by product, name</Message>
  <RequestId>4555773F-769B-4960-87E6-16009E5A4844</RequestId>
  <Data>[{"product":"CloudMonitor","time":"1552199984000","num":"1","name":"Agent_Status_Stopped"},{"product":"OSS","time":"1552199984000","num":"4","name":"UserEgressBandwidth"}]</Data> 
  <Code>200</Code>
  <Success>true</Success> 
</DescribeSystemEventCountResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Data":"[{\"product\":\"CloudMonitor\",\"time\":\"1552199984000\",\"num\":\"1\",\"name\":\"Agent_Status_Stopped\"},{\"product\":\"OSS\",\"time\":\"1552199984000\",\"num\":\"4\",\"name\":\"UserEgressBandwidth\"}]",
	"Message":"userId:1****|select product, name, count(product) as num group by product,name order by product, name",
	"RequestId":"4555773F-769B-4960-87E6-16009E5A4844",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

