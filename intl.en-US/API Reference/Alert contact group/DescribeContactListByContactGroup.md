# DescribeContactListByContactGroup {#doc_api_Cms_DescribeContactListByContactGroup .reference}

You can call this operation to query the list of alert contacts in an alert contact group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeContactListByContactGroup) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeContactListByContactGroup|The operation that you want to perform. Set the value to DescribeContactListByContactGroup.

 |
|ContactGroupName|String|Yes|My alert contact group name|The name of the alert contact group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Contacts| | |The alert contact information.

 |
|└Channels| | |The alert notification methods.

 |
|└AliIM|String|My TradeManager|The TradeManager ID of the contact.

 |
|└DingWebHook|String|DingTalk Chatbot address|The DingTalk Chatbot address of the contact.

 |
|└Mail|String|test@aliyun.com|The email address of the contact.

 |
|└SMS|String|1333333\*\*\*\*|The mobile phone number of the contact.

 |
|└CreateTime|Long|1552314252000|The time when the alert contact was created.

 |
|└Desc|String|Description|The description of the alert contact group.

 |
|└Name|String|Guan|The name of the alert contact.

 |
|└UpdateTime|Long|1552314252000|The time when the alert contact information was last updated.

 |
|Message|String|success|The error message.

 |
|RequestId|String|06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeContactListByContactGroup
&ContactGroupName=My alert contact group name
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeContactListByContactGroupResponse>
  <RequestId>81A6C995-D1A8-4627-B2E6-4B651446DDF9</RequestId>
  <Contacts>
    <Contact>
      <Channels>
        <AliIM>Guan</AliIM>
        <Mail>test***@aliyun.com</Mail>
      </Channels>
      <Name>Guan</Name>
      <CreateTime>1552355864000</CreateTime>
      <UpdateTime>1552356159000</UpdateTime>
      <Desc>xxxx</Desc>
    </Contact>
  </Contacts>
  <Success>true</Success> 
  <Code>200</Code>
</DescribeContactListByContactGroupResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"81A6C995-D1A8-4627-B2E6-4B651446DDF9",
	"Contacts":{
		"Contact":[
			{
				"Name":"Guan",
				"Channels":{
					"Mail":"test***@aliyun.com",
					"AliIM":"Guan"
				},
				"CreateTime":1552355864000,
				"UpdateTime":1552356159000,
				"Desc":"xxxx"
			}
		]
	},
	"Success":true,
	"Code":"200"
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

