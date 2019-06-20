# SendDryRunSystemEvent {#doc_api_Cms_SendDryRunSystemEvent .reference}

You can call this operation to trigger a system event for debugging. This event is used to test whether the trigger logic of the event meets expectations.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=SendDryRunSystemEvent) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|SendDryRunSystemEvent|The operation that you want to perform. Set the value to SendDryRunSystemEvent.

 |
|EventName|String|Yes|Agent\_Status\_Stopped|The name of the event.

 |
|Product|String|Yes|CloudMonitor|The name of the service.

 |
|EventContent|String|No|\{"product":"CloudMonitor","resourceId":"acs:ecs:cn-hongkong:1736511134389110:instance/\{instanceId\}","level":"CRITICAL","instanceName":"instanceName","regionId":"cn-hangzhou","name":"Agent\_Status\_Stopped","content":\{"ipGroup":"0.0.0.0,0.0.0.1","tianjimonVersion":"1.2.11"\},"status":"stopped"\}|The content of the event.

 |
|GroupId|String|No|12345|The ID of the application group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description |
|---------|----|-------|------------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

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

http(s)://[Endpoint]/? Action=SendDryRunSystemEvent
&EventName=Agent_Status_Stopped
&Product=CloudMonitor
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<SendDryRunSystemEventResponse>
  <Message>success</Message>
  <RequestId>590FB642-5FFE-4AE0-883B-E1323DD20541</RequestId> 
  <Code>200</Code>
  <Success>true</Success> 
</SendDryRunSystemEventResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"590FB642-5FFE-4AE0-883B-E1323DD20541",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

