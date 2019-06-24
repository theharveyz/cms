# DescribeContactGroupList {#doc_api_Cms_DescribeContactGroupList .reference}

You can call this operation to query the list of alert contact groups.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeContactGroupList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeContactGroupList|The operation that you want to perform. Set the value to DescribeContactGroupList.

 |
|PageNumber|Integer|No|10|The number of the page.

 |
|PageSize|Integer|No|1|The number of records on each page.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|ContactGroups| |Alert contact group list|The list of alert contact groups

 |
|Message|String|Error message|The error message.

 |
|RequestId|String|916EE694-03C2-47B6-85EE-5054E3C168D3|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Total|Integer|22|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeContactGroupList
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeContactGroupListResponse>
  <Code>200</Code>
  <ContactGroups>My alert contact group 1</ContactGroups>
  <RequestId>916EE694-03C2-47B6-85EE-5054E3C168D3</RequestId>
  <Success>true</Success> 
  <Total>22</Total>
</DescribeContactGroupListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"916EE694-03C2-47B6-85EE-5054E3C168D3",
	"ContactGroups":[
		"My alert contact group 1"
	],
	"Success":true,
	"Code":"200",
	"Total":22
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

