# DescribeCustomEventCount {#doc_api_Cms_DescribeCustomEventCount .reference}

You can call this operation to obtain the numbers of custom events by service.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeCustomEventCount) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCustomEventCount|The operation that you want to perform. Set the value to DescribeCustomEventCount.

 |
|EndTime|String|No|1552220485596|The end time.

 |
|EventId|String|No|123|The ID of the event.

 |
|GroupId|String|No|12345|The ID of the application group.

 |
|Level|String|No|CRITICAL|The level of the event. Valid values: CRITICAL, WARN, and INFO.

 |
|Name|String|No|BABEL\_BUY|The name of the event.

 |
|SearchKeywords|String|No|cms|The expression of keywords in the event content. Logical operators AND and OR are supported.

 -   a and b: searches for results that contain both a and b in the event content.
-   a or b: searches for results that contain either a or b in the event content.

 |
|StartTime|String|No|1552209685596|The start time.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|CustomEventCounts| | |The details of the custom event.

 |
|└Name|String|BABEL\_BUY|The name of the event.

 |
|└Num|Integer|20|The number of events.

 |
|└Time|Long|1552267615000|The time when the event occurred.

 |
|Message|String|success|The error message.

 |
|RequestId|String|60912C8D-B340-4253-ADE7-61ACDFD25CFC|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCustomEventCount
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeCustomEventCountResponse>
  <Success>true</Success>
  <Message>userId:123456|select name, count(*) as num group by name order by name limit 1000</Message>
  <RequestId>2cf3a089-a715-4bc9-9e1b-69c883edccff</RequestId>
  <Data>
    <Time>1552267615000</Time>
    <Num>2</Num>
    <Name>BABEL_BUY</Name>
  </Data>
</DescribeCustomEventCountResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Data":[
		{
			"Name":"BABEL_BUY",
			"Time":1552267615000,
			"Num":"2"
		}
	],
	"Message":"userId:123456|select name, count(*) as num group by name order by name limit 1000",
	"RequestId":"2cf3a089-a715-4bc9-9e1b-69c883edccff",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

