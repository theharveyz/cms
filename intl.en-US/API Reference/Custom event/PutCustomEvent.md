# PutCustomEvent {#doc_api_Cms_PutCustomEvent .reference}

You can call this operation to report the monitoring data for one or more custom events.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=PutCustomEvent) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PutCustomEvent|The operation that you want to perform. Set the value to PutCustomEvent.

 |
|EventInfo.N.Content|String|No|IOException|The content of the event. Valid values of N: 1 to 50.

 |
|EventInfo.N.EventName|String|No|myEvent|The name of the event. Valid values of N: 1 to 50.

 |
|EventInfo.N.GroupId|String|No|0|The ID of the application group. The value of 0 indicates that the monitoring data for a random application group is reported. Valid values of N: 1 to 50.

 |
|EventInfo.N.Time|String|No|20171013T170923.456+0800|The time when the event occurred. Valid values of N: 1 to 50.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|131DD9C8-9A32-4428-AD2E-4E3013B6E3A7|The request ID for troubleshooting.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=PutCustomEvent
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<PutCustomEventResponse>
  <Message>success</Message>
  <RequestId>131DD9C8-9A32-4428-AD2E-4E3013B6E3A7</RequestId>
  <Code>200</Code>
</PutCustomEventResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"131DD9C8-9A32-4428-AD2E-4E3013B6E3A7",
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

