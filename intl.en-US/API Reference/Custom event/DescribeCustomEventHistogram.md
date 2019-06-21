# DescribeCustomEventHistogram {#doc_api_Cms_DescribeCustomEventHistogram .reference}

You can call this operation to query the distribution chart of the numbers of reported custom events in different time periods.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeCustomEventHistogram) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCustomEventHistogram|The operation that you want to perform. Set the value to DescribeCustomEventHistogram.

 |
|EndTime|String|No|1552220485596|The end time.

 |
|EventId|String|No|123|The ID of the event.

 |
|GroupId|String|No|12345|The ID of the application group.

 |
|Level|String|No|CRITICAL|The level of the event. Valid values: CRITICAL, WARN, and INFO.

 |
|Name|String|No|BucketIngressBandwidth|The name of the event.

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
|EventHistograms| | |The list of event statistics.

 |
|└Count|Long|3|The number of events.

 |
|└EndTime|Long|1552263113000|The end time.

 |
|└StartTime|Long|1552263120000|The start time.

 |
|Message|String|success|The error message.

 |
|RequestId|String|486029C9-53E1-44B4-85A8-16A571A043FD|The request ID for troubleshooting.

 |
|Success|String|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCustomEventHistogram
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeCustomEventHistogramResponse>
  <EventHistograms>
    <EventHistogram>
      <Count>0</Count>
      <EndTime>1552226750000</EndTime>
      <StartTime>1552226740000</StartTime>
    </EventHistogram>
    <EventHistogram>
      <Count>0</Count>
      <EndTime>1552226760000</EndTime>
      <StartTime>1552226750000</StartTime>
    </EventHistogram>
    <EventHistogram>
      <Count>0</Count>
      <EndTime>1552226770000</EndTime>
      <StartTime>1552226760000</StartTime>
    </EventHistogram>
    <EventHistogram>
      <Count>0</Count>
      <EndTime>1552226780000</EndTime>
      <StartTime>1552226770000</StartTime>
    </EventHistogram> 
    <EventHistogram>
      <Count>0</Count>
      <EndTime>1552226790000</EndTime>
      <StartTime>1552226780000</StartTime>
    </EventHistogram>
    <EventHistogram>
      <Count>0</Count>
      <EndTime>1552226800000</EndTime>
      <StartTime>1552226790000</StartTime>
    </EventHistogram>
    <EventHistogram>
      <Count>0</Count>
      <EndTime>1552226810000</EndTime> 
      <StartTime>1552226800000</StartTime> 
    </EventHistogram>
    <EventHistogram>
      <Count>0</Count>
      <EndTime>1552226820000</EndTime>
      <StartTime>1552226810000</StartTime>
    </EventHistogram>
    <EventHistogram>
      <Count>0</Count>
      <EndTime>1552226827000</EndTime>
      <StartTime>1552226820000</StartTime>
    </EventHistogram>
  </EventHistograms>
  <Message>userId:1235</Message>
  <RequestId>729FDC1A-F4ED-427E-A57D-93925F35FC49</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DescribeCustomEventHistogramResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"EventHistograms":{
		"EventHistogram":[
			{
				"Count":0,
				"EndTime":1552226750000,
				"StartTime":1552226740000
			},
			{
				"Count":0,
				"EndTime":1552226760000,
				"StartTime":1552226750000
			},
			{
				"Count":0,
				"EndTime":1552226770000,
				"StartTime":1552226760000
			},
			{
				"Count":0,
				"EndTime":1552226780000,
				"StartTime":1552226770000
			},
			{
				"Count":0,
				"EndTime":1552226790000,
				"StartTime":1552226780000
			},
			{
				"Count":0,
				"EndTime":1552226800000,
				"StartTime":1552226790000
			},
			{
				"Count":0,
				"EndTime":1552226810000,
				"StartTime":1552226800000
			},
			{
				"Count":0,
				"EndTime":1552226820000,
				"StartTime":1552226810000
			},
			{
				"Count":0,
				"EndTime":1552226827000,
				"StartTime":1552226820000
			}
		]
	},
	"Message":"userId:1235",
	"RequestId":"729FDC1A-F4ED-427E-A57D-93925F35FC49",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

