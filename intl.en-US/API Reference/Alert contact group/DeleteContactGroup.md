# DeleteContactGroup {#doc_api_Cms_DeleteContactGroup .reference}

You can call this operation to delete an alert contact group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteContactGroup) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteContactGroup|The operation that you want to perform. Set the value to DeleteContactGroup.

 |
|ContactGroupName|String|Yes|My alert contact group|The name of the alert contact group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|F722BE59-2400-4A64-9C1A-AD886AED9A69|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteContactGroup
&ContactGroupName=My alert contact group
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteContactGroupResponse>
  <RequestId>F722BE59-2400-4A64-9C1A-AD886AED9A69</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DeleteContactGroupResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"F722BE59-2400-4A64-9C1A-AD886AED9A69",
	"Success":true,
	"Code":"200"
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

