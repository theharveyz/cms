# DescribeMonitorGroupNotifyPolicyList {#doc_api_Cms_DescribeMonitorGroupNotifyPolicyList .reference}

You can call this operation to query the list of alert notification pause policies for an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupNotifyPolicyList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeMonitorGroupNotifyPolicyList|The operation that you want to perform. Set the value to DescribeMonitorGroupNotifyPolicyList.

 |
|PolicyType|String|Yes|PauseNotify|The type of paused notifications. Valid value: PauseNotify.

 |
|GroupId|string|No|12346|The ID of the application group.

 |
|PageNumber|Integer|No|1|The number of the page. Default value: 1.

 |
|PageSize|Integer|No|100|The number of records on each page. Default value: 10.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|NotifyPolicyList| | |The list of paused notifications.

 |
|└EndTime|Long|1551761781273|The end time.

 |
|└GroupId|String|12345|The ID of the group.

 |
|└Id|String|111|The ID of the paused notification.

 |
|└StartTime|Long|1551761781273|The start time.

 |
|└Type|String|PauseNotify|The type of paused notifications. Default value: PauseNotify.

 |
|RequestId|String|6072F026-C441-41A6-B114-35A1E8F8FDD3|The request ID for troubleshooting.

 |
|Success|String|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Total|Integer|11|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitorGroupNotifyPolicyList
&PolicyType=PauseNotify 
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitorGroupNotifyPolicyListResponse>
  <NotifyPolicyList>
    <NotifyPolicy>
      <Type>PauseNotify</Type>
      <EndTime>1551763581273</EndTime>
      <Id>7995</Id>
      <StartTime>1551761781273</StartTime>
      <GroupId>13263</GroupId>
    </NotifyPolicy>
  </NotifyPolicyList>
  <Success>true</Success> 
  <Code>200</Code> 
  <Total>1</Total> 
</DescribeMonitorGroupNotifyPolicyListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"NotifyPolicyList":{
		"NotifyPolicy":[
			{
				"Type":"PauseNotify",
				"Id":7995,
				"EndTime":1551763581273,
				"StartTime":1551761781273,
				"GroupId":"13263"
			}
		]
	},
	"Success":true,
	"Code":"200",
	"Total":1
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

