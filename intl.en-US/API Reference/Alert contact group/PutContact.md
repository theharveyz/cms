# PutContact {#doc_api_Cms_PutContact .reference}

You can call this operation to create or modify an alert contact.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=PutContact) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PutContact|The operation that you want to perform. Set the value to PutContact.

 |
|ContactName|String|Yes|Alert contact name|The name of the alarm contact.

 |
|Describe|String|Yes|Alert contact description|The description of the alert contact.

 |
|Channels.SMS|String|No|1333333\*\*\*\*|The mobile phone number of the contact.

 |
|Channels.Mail|String|No|test@aliyun.com|The email address of the contact.

 |
|Channels.DingWebHook|String|No|https://oapi.dingtalk.com/robot/send?access\_token=7d49515e8ebf21106a80a9cc4bb3d247771305d52fb15d6201234565\*\*\*\*|The DingTalk Chatbot address.

 |
|Channels.AliIM|String|No|TradeManager|The TradeManager ID.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|181C406E-9DE4-484C-9C61-37AE9A1A12EE|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=PutContact
&ContactName=Alert contact name
&Describe=Alert contact description
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<PutContactResponse>
  <Code>200</Code>
  <RequestId>181C406E-9DE4-484C-9C61-37AE9A1A12EE</RequestId>
  <Success>true</Success> 
</PutContactResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"F7FA82F0-8627-441B-9B2B-8663617F36B9",
	"Success":true,
	"Code":"200"
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

