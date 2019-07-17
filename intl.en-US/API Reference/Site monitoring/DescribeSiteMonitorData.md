# DescribeSiteMonitorData {#doc_api_Cms_DescribeSiteMonitorData .reference}

You call this operation to query detailed monitoring data of a site monitoring task.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides OpenAPI Explorer to simplify API usage. You can use [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorData) to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSiteMonitorData|The operation that you want to perform. Set this parameter to DescribeSiteMonitorData.

 |
|MetricName|String|Yes|Availability|The name of the metric. Valid values:

 -   Availability
-   ResponseTime

 |
|TaskId|String|Yes|49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*|The ID of the site monitoring task.

 |
|EndTime|String|No|1551581437000|The end time of the period from which you want to query monitoring data. The value can be the number of milliseconds that have elapsed since 00:00:00, January 1, 1970, or time in the format of YYYY-MM-DD HH:MM:SS, such as 2015-10-20 00:00:00.

 |
|Length|Integer|No|1000|The number of data points to return.

 |
|NextToken|String|No|49f7b317-7645-4cc9-94fd-ea42e5220930ea42e5220930ea42e522\*\*\*\*|The pagination cursor.

 |
|Period|String|No|60|The statistical period. Unit: seconds. The value must be 60 or a multiple of 60. Data is returned based on the smallest monitoring interval by default.

 |
|StartTime|String|No|1551579637000|The start time of the period from which you want to query monitoring data. The value can be the number of milliseconds that have elapsed since 00:00:00, January 1, 1970, or time in the format of YYYY-MM-DD HH:MM:SS, such as 2015-10-20 00:00:00.

 |
|Type|String|No|metric|The type of the monitoring data.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|Data|String|\[\{"Maximum":247,"Minimum":61,"Average":154,"userId":"127067667954\*\*\*\*","taskId":"49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*","timestamp":1551581760000\}\]|The monitoring data.

 |
|Message|String|successful|The error message.

 |
|NextToken|String|ea42e5220930ea42e5220930|The pagination cursor.

 |
|RequestId|String|3febb181-0d98-4af9-8b04-7faf36b048b9|The ID of the request.

 |
|Success|String|true|Indicates whether the call was successful.

 |

## Examples {#demo .section}

Sample request

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSiteMonitorData
&MetricName=Availability
&TaskId=49f7b317-7645-4cc9-94fd-ea42e522****
&<Common request parameters>

```

Sample success response

`XML` format

``` {#xml_return_success_demo}
<DescribeSiteMonitorDataResponse>
  <Data>
    <Over5totalTime>0</Over5totalTime>
    <Error4XXRate>0</Error4XXRate>
    <UnavailableNumber>0</UnavailableNumber>
    <Over2totalTime>0</Over2totalTime>
    <timestamp>1551581040000</timestamp>
    <Over100FailureRate>0</Over100FailureRate>
    <Over10FailureRate>0</Over10FailureRate>
    <Availability>100</Availability>
    <Over80FailureRate>0</Over80FailureRate>
    <userId>12345</userId>
    <AvailableNumber>2</AvailableNumber>
    <Unavailability>0</Unavailability>
    <ErrorCodeMaximum>0</ErrorCodeMaximum>
    <Over10totalTime>0</Over10totalTime>
    <taskId>49f7b317-7645-4cc9-94fd-1****</taskId>
    <Over30FailureRate>0</Over30FailureRate>
    <Error6XXRate>0</Error6XXRate>
    <Over500NumberRate>0</Over500NumberRate>
    <Over3totalTime>0</Over3totalTime>
    <Over400NumberRate>0</Over400NumberRate>
    <Error5XXRate>0</Error5XXRate>
    <Error5XXNumber>0</Error5XXNumber>
    <Over90FailureRate>0</Over90FailureRate>
    <Error4XXNumber>0</Error4XXNumber>
    <Over50FailureRate>0</Over50FailureRate>
    <ErrorCodeMinimum>0</ErrorCodeMinimum>
    <Error6XXNumber>0</Error6XXNumber>
  </Data>
  <Data>
    <Over5totalTime>0</Over5totalTime>
    <Error4XXRate>0</Error4XXRate>
    <UnavailableNumber>0</UnavailableNumber>
    <Over2totalTime>0</Over2totalTime>
    <timestamp>1551581100000</timestamp>
    <Over100FailureRate>0</Over100FailureRate>
    <Over10FailureRate>0</Over10FailureRate>
    <Availability>100</Availability>
    <Over80FailureRate>0</Over80FailureRate>
    <userId>12345</userId>
    <AvailableNumber>2</AvailableNumber>
    <Unavailability>0</Unavailability>
    <ErrorCodeMaximum>0</ErrorCodeMaximum>
    <Over10totalTime>0</Over10totalTime>
    <taskId>49f7b317-7645-4cc9-94fd-1****</taskId>
    <Over30FailureRate>0</Over30FailureRate>
    <Error6XXRate>0</Error6XXRate>
    <Over500NumberRate>0</Over500NumberRate>
    <Over3totalTime>0</Over3totalTime>
    <Over400NumberRate>0</Over400NumberRate>
    <Error5XXRate>0</Error5XXRate>
    <Error5XXNumber>0</Error5XXNumber>
    <Over90FailureRate>0</Over90FailureRate>
    <Error4XXNumber>0</Error4XXNumber>
    <Over50FailureRate>0</Over50FailureRate>
    <ErrorCodeMinimum>0</ErrorCodeMinimum>
    <Error6XXNumber>0</Error6XXNumber>
  </Data>
  <RequestId>DBDEAC51-EA3C-4853-8F25-6B48D38A28A9</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSiteMonitorDataResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Data":[
		{
			"Over5totalTime":0,
			"Error4XXRate":0,
			"UnavailableNumber":0,
			"Over2totalTime":0,
			"Over100FailureRate":0,
			"timestamp":1551581040000,
			"Over10FailureRate":0,
			"Availability":100,
			"userId":"12345",
			"Over80FailureRate":0,
			"AvailableNumber":2,
			"Unavailability":0,
			"ErrorCodeMaximum":0,
			"Over10totalTime":0,
			"taskId":"49f7b317-7645-4cc9-94fd-1****",
			"Over30FailureRate":0,
			"Error6XXRate":0,
			"Over500NumberRate":0,
			"Over3totalTime":0,
			"Over400NumberRate":0,
			"Error5XXRate":0,
			"Error5XXNumber":0,
			"Over90FailureRate":0,
			"Error4XXNumber":0,
			"Over50FailureRate":0,
			"ErrorCodeMinimum":0,
			"Error6XXNumber":0
		},
		{
			"Over5totalTime":0,
			"Error4XXRate":0,
			"UnavailableNumber":0,
			"Over2totalTime":0,
			"Over100FailureRate":0,
			"timestamp":1551581100000,
			"Over10FailureRate":0,
			"Availability":100,
			"userId":"12345",
			"Over80FailureRate":0,
			"AvailableNumber":2,
			"Unavailability":0,
			"ErrorCodeMaximum":0,
			"Over10totalTime":0,
			"taskId":"49f7b317-7645-4cc9-94fd-1****",
			"Over30FailureRate":0,
			"Error6XXRate":0,
			"Over500NumberRate":0,
			"Over3totalTime":0,
			"Over400NumberRate":0,
			"Error5XXRate":0,
			"Error5XXNumber":0,
			"Over90FailureRate":0,
			"Error4XXNumber":0,
			"Over50FailureRate":0,
			"ErrorCodeMinimum":0,
			"Error6XXNumber":0
		}
	],
	"RequestId":"DBDEAC51-EA3C-4853-8F25-6B48D38A28A9",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes.](https://error-center.aliyun.com/status/product/Cms)

