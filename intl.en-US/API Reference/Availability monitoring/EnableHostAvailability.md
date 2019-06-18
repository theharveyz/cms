# EnableHostAvailability {#doc_api_Cms_EnableHostAvailability .reference}

You can call this operation to enable availability monitoring.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=EnableHostAvailability) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|EnableHostAvailability|The operation that you want to perform. Set the value to EnableHostAvailability.

 |
|Id.N|RepeatList|Yes|123456|The ID of the task. Valid values of N: 1 to 20.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|ACBDBB40-DFB6-4F4C-8957-51FFB233969C|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=EnableHostAvailability
&Id. 1=123456
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<EnableHostAvailabilityResponse>
  <RequestId>ACBDBB40-DFB6-4F4C-8957-51FFB233969C</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</EnableHostAvailabilityResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"ACBDBB40-DFB6-4F4C-8957-51FFB233969C",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

