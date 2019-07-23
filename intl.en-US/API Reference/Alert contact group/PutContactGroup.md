# PutContactGroup {#doc_api_Cms_PutContactGroup .reference}

You can call this operation to create or modify an alert contact group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=PutContactGroup) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PutContactGroup| The operation that you want to perform. Set the value to PutContactGroup.

 |
|ContactGroupName|String|Yes|My alert contact group| The name of the alert contact group.

 |
|ContactNames.N|RepeatList|Yes|Contact 1| The name of the alert contact. Valid values of N: 1 to 100.

 |
|Describe|String|Yes|Alert contact group description| The description of the alert contact group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200| The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success| The error message.

 |
|RequestId|String|06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83| The request ID for troubleshooting.

 |
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=PutContactGroup
&ContactGroupName=My alert contact group
&ContactNames. 1=Contact 1
&Describe=Alert contact name
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<PutContactGroupResponse>
  <Code>200</Code>
  <Message>success</Message>
  <RequestId>181C406E-9DE4-484C-9C61-37AE9A1A12EE</RequestId>
  <Success>true</Success> 
</PutContactGroupResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83",
	"Success":true,
	"Code":"200"
}
```

## Error code {#section_1nh_urv_kw3 .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

