# ListContactGroup {#doc_api_987937 .reference}

Call this API to query the alarm contact groups associated with an alarm rule under an Alibaba Cloud account.

## Debugging {#apiExplorer .section}

Perform online debugging in [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=QueryMetricLast). OpenAPI Explorer provides various functions that help simplify the usage of APIs, including online API calling, dynamic SDK example code generation, and quick retrieval.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|ListContactGroup| The name of the API specified by the system

 |
|PageNumber|Integer|No|1| The page number. Default value: page 1.

 |
|PageSize|Integer|No|100| The number of records on each page. Default value: 100 records.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|Code|String|200| The returned request status code. The status code 200 indicates that the request is successful, and other status codes indicate that the request failed.

 |
|ContactGroups| |"test4nudou","xzytestgroup", "Alarm contact under an Alibaba Cloud account"| The alarm contact group of the alarm rule, which must be a string corresponding to the JSON array, for example: `["Contact Group 1" and "Contact Group 2"]`

 |
|Message|String|Success| A message that indicates that the request failed

 |
|NextToken|Integer|2| The next page. If the value is null, this indicates there is only one page.

 |
|RequestId|String|D3D03B0A-CF1A-4DAB-BF0D-D4B6ACD5677A| The universal unique identifier \(UUID\) for the request, which is used to query logs

 |
|Success|Boolean|true| Indicates whether the request is successful.

 |
|Total|Integer|3| The total number of compliant data items

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/?Action=ListContactGroup
&<Common request parameters>

```

Normal response examples

In `XML` format

``` {#xml_return_success_demo}
<ListContactGroupResponse>
  <RequestId>DCE1419F-D60C-441C-81C3-7425B9211AC5</RequestId>
  <ContactGroups>
    <ContactGroup>test4nudou</ContactGroup>
    <ContactGroup>xzytestgroup</ContactGroup>
    <ContactGroup>Alarm contact under an Alibaba Cloud account</ContactGroup>
  </ContactGroups>
  <Success>true</Success>
  <Code>200</Code>
  <Total>3</Total>
</ListContactGroupResponse>

```

In `JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"D3D03B0A-CF1A-4DAB-BF0D-D4B6ACD5677A",
	"ContactGroups":{
		"ContactGroup":[
			"test4nudou",
			"xzytestgroup",
			"Alarm contact under an Alibaba Cloud account"
		]
	},
	"Success":true,
	"Code":"200",
	"Total":3
}
```

## Error codes {#section_qyy_t2d_5gb .section}

Click [here](https://error-center.aliyun.com/status/product/Cms) to view the error codes.

