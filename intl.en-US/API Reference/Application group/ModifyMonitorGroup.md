# ModifyMonitorGroup {#doc_api_Cms_ModifyMonitorGroup .reference}

You can call this operation to modify an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=ModifyMonitorGroup) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyMonitorGroup|The operation that you want to perform. Set the value to ModifyMonitorGroup.

 |
|GroupId|String|Yes|12346|The ID of the application group.

 |
|ContactGroups|String|No|Alert contact group|The alert contact group.

 |
|GroupName|String|No|Modify group name 1|The name of the application group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|C85A2870-5DF4-4269-BC50-ECB5E4591A80|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=ModifyMonitorGroup
&GroupId=12346
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<ModifyMonitorGroupResponse>
  <RequestId>36FE4D3A-A907-4F2A-921C-89612FFA977B</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</ModifyMonitorGroupResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"36FE4D3A-A907-4F2A-921C-89612FFA977B",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

