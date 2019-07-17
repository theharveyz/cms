# DescribeSiteMonitorStatistics {#doc_api_Cms_DescribeSiteMonitorStatistics .reference}

You can call this operation to query the statistics of a specified site monitoring task in a specified period.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides OpenAPI Explorer to simplify API usage. You can use [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorStatistics) to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSiteMonitorStatistics|The operation that you want to perform. Set this parameter to DescribeSiteMonitorStatistics.

 |
|MetricName|String|Yes|Availability|The name of the metric. Valid values:

 -   Availability
-   ErrorRate
-   ResponseTime

 |
|TaskId|String|Yes|49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*|The ID of the site monitoring task.

 |
|TimeRange|String|No|60|The time period from which you want to collect statistics. Unit: minutes. The maximum value is 1440 minutes \(that is, one day\).

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|Data|Long|100|The statistics that were collected.

 |
|Message|String|successful|The error message.

 |
|RequestId|String|3fcd12e7-d387-42ee-b77e-661c775bb17f|The ID of the request.

 |
|Success|String|true|Indicates whether the call was successful.

 |

## Examples {#demo .section}

Sample request

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSiteMonitorStatistics
&MetricName=Availability
&TaskId=49f7b317-7645-4cc9-94fd-ea42e522****
&<Common request parameters>

```

Sample success response

`XML` format

``` {#xml_return_success_demo}
<DescribeSiteMonitorStatisticsResponse>
  <Message>successful</Message>
  <RequestId>3fcd12e7-d387-42ee-b77e-661c775bb17f</RequestId>
  <Code>200</Code>
  <Success>true</Success>
</DescribeSiteMonitorStatisticsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Data":"{\"value\":100}",
	"Message":"successful",
	"RequestId":"3fcd12e7-d387-42ee-b77e-661c775bb17f",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes.](https://error-center.aliyun.com/status/product/Cms)

