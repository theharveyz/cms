# DescribeContactList {#doc_api_Cms_DescribeContactList .reference}

You can call this operation to query the list of alert contacts.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeContactList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeContactList|The operation that you want to perform. Set the value to DescribeContactList.

 |
|ContactName|String|No|My alert contact|The name of the alert contact. Fuzzy search is not supported.

 |
|PageSize|Integer|No|10|The number of records on each page. Default value: 100.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Message|String|success|The error message.

 |
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|RequestId|String|06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83|The request ID for troubleshooting.

 |
|Contacts| | |The alert contact information.

 |
|└Channels| | |The alert notification methods.

 |
|└AliIM|String|My TradeManager|The TradeManager ID of the contact.

 |
|└DingWebHook|String|https://oapi.dingtalk.com/robot/send?access\_token=9bf44f8189597d07dfdd7a123455ffc112\*\*\*\*|The DingTalk Chatbot address of the contact.

 |
|└Mail|String|xxxx@aliyun.com|The email address of the contact.

 |
|└SMS|String|1333333\*\*\*\*|The mobile phone number of the contact.

 |
|└CreateTime|Long|1552356159000|The time when the alert contact was created.

 |
|└Desc|String|My alert notification method|The description of the alert contact.

 |
|└Name|String|Guan|The name of the alert contact.

 |
|└UpdateTime|Long|1552356159000|The time when the alert contact information was last updated.

 |
|Total|Integer|15|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeContactList
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeContactListResponse> 
  <RequestId>06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83</RequestId> 
  <Contacts> 
    <Contact> 
      <Channels>
        <SMS>1333333****</SMS>
        <Mail>xxxxx@aliyun.com</Mail>
      </Channels>
      <Name>Guan</Name>
      <CreateTime>1553006761000</CreateTime> 
      <UpdateTime>1553084361000</UpdateTime>
    </Contact>
  </Contacts>
  <Success>true</Success>
  <Code>200</Code>
</DescribeContactListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83",
	"Contacts":{
		"Contact":[
			{
				"Name":"Guan",
				"Channels":{
					"Mail":"xxxxx@aliyun.com",
					"SMS":"1333333****"
				},
				"CreateTime":1553006761000,
				"UpdateTime":1553084361000
			}
		]
	},
	"Success":true,
	"Code":"200"
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

