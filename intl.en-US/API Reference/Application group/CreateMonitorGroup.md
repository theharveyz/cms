# CreateMonitorGroup {#doc_api_Cms_CreateMonitorGroup .reference}

You can call this operation to create an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=CreateMonitorGroup) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|CreateMonitorGroup|The operation that you want to perform. Set the value to CreateMonitorGroup.

 |
|GroupName|String|Yes|My application group 1|The name of the application group.

 |
|ContactGroups|String|No|Default alert contact group|The alert contact group. Alert notifications for the application group are sent to the specified alert contact group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|GroupId|Long|123456|The ID of the application group.

 |
|Message|String|success|The status description. The Message parameter is null when the Code parameter is 200.

 |
|RequestId|String|3121AE7D-4AFF-4C25-8F1D-C8226EBB1F42|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateMonitorGroup
&GroupName=My application group 1
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<CreateMonitorGroupResponse>
  <RequestId>69C34563-DD18-419E-A7C3-60D0913254E9</RequestId>
  <Success>true</Success> 
  <GroupId>3391309</GroupId>
  <Code>200</Code>
</CreateMonitorGroupResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"69C34563-DD18-419E-A7C3-60D0913254E9",
	"Success":true,
	"Code":200,
	"GroupId":3391309
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

