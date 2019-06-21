# CreateMonitorGroupNotifyPolicy {#doc_api_Cms_CreateMonitorGroupNotifyPolicy .reference}

You can call this operation to create an alert notification pause policy for an application group.

The application group will not trigger alert notifications during the effective period of the policy.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=CreateMonitorGroupNotifyPolicy) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|CreateMonitorGroupNotifyPolicy|The operation that you want to perform. Set the value to CreateMonitorGroupNotifyPolicy.

 |
|GroupId|String|Yes|12345|The ID of the application group.

 |
|PolicyType|String|Yes|PauseNotify|The type of paused notifications. Valid value: PauseNotify.

 |
|StartTime|Long|Yes|1551756547863|The start time of the period when notifications are paused. It is the time that has passed since 00:00:00, January 1, 1970. Unit: millisecond.

 |
|EndTime|Long|Yes|1551757147863|The end time of the period when notifications are paused. It is the time that has passed since 00:00:00, January 1, 1970. Unit: millisecond.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|13356BCA-3EC3-4748-A771-2064DA69AEF1|The request ID for troubleshooting.

 |
|Result|Integer|1|The number of returned results.

 |
|Success|String|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateMonitorGroupNotifyPolicy
&GroupId=12345
&PolicyType=PauseNotify 
&StartTime=1551756547863
&EndTime=1551757147863
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<CreateMonitorGroupNotifyPolicyResponse>
  <Result>1</Result>
  <Success>true</Success> 
  <Code>200</Code>
</CreateMonitorGroupNotifyPolicyResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Result":1,
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

