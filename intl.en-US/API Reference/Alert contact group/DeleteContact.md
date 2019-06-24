# DeleteContact {#doc_api_Cms_DeleteContact .reference}

You can call this operation to delete an alert contact.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteContact) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteContact|The operation that you want to perform. Set the value to DeleteContact.

 |
|ContactName|String|Yes|Guan|The name of the alert contact.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|50D4CFE1-01E5-4543-939C-18BC01E3EC1C|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteContact
&ContactName=Guan
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteContactResponse>
  <RequestId>50D4CFE1-01E5-4543-939C-18BC01E3EC1C</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DeleteContactResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"50D4CFE1-01E5-4543-939C-18BC01E3EC1C",
	"Success":true,
	"Code":"200"
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

