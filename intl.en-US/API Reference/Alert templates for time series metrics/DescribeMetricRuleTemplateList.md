# DescribeMetricRuleTemplateList {#doc_api_Cms_DescribeMetricRuleTemplateList .reference}

You can call this operation to query the list of alert templates.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleTemplateList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeMetricRuleTemplateList|The operation that you want to perform. Set the value to DescribeMetricRuleTemplateList.

 |
|History|Boolean|No|false|Indicates whether to display the historical records of the alert templates that are applied to the application group. A value of true indicates that historical records are to be displayed. A value of false indicates that historical records are not to be displayed. Default value: false.

 |
|Keyword|String|No|My templates|The name of the template. You can perform fuzzy search based on the template name.

 |
|Name|String|No|Template name|The name of the alert template.

 |
|PageNumber|Long|No|1|The number of the page. Default value: 1.

 |
|PageSize|Long|No|10|The number of records on each page.

 |
|TemplateId|Long|No|12345|The ID of the alert template.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful. Any other value indicates that the call has failed.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Message|String|success|The error message.

 |
|Total|Long|11|The total number of returned records.

 |
|RequestId|String|1A1B405A-B877-4A27-9922-471F080E4985|The request ID for troubleshooting.

 |
|Templates| | |The historical data of alert templates.

 |
|└ApplyHistories| | |The application history.

 |
|└ApplyTime|Long|1543459583000|The time when the template was applied.

 |
|└GroupId|Long|12345|The ID of the application group.

 |
|└GroupName|String|My group name|The name of the application group.

 |
|└Description|String|CPU alert template|The details of the alert template.

 |
|└GmtCreate|Long|1543302440000|The time when the alert template was created.

 |
|└GmtModified|Long|1543302440000|The time when the alert template was modified.

 |
|└Name|String|template1|The name of the alert template.

 |
|└RestVersion|Long|0|The version of the alert template. Default value: 0.

 |
|└TemplateId|Long|12345|The ID of the alert template.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMetricRuleTemplateList
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMetricRuleTemplateListResponse>
  <RequestId>03AE5FA9-8CB2-4B5B-8306-1BBBF012A1A7</RequestId>
  <Templates>
    <Template> 
      <RestVersion>0</RestVersion>
      <Name>newtemplate_1</Name>
      <Description>description_111111</Description>
      <GmtCreate>1543302440000</GmtCreate>
      <GmtModified>1543302440000</GmtModified>
      <TemplateId>32</TemplateId>
    </Template> 
    <Template> 
      <RestVersion>0</RestVersion>
      <Name>newtemplate_2</Name>
      <Description/> 
      <GmtCreate>1543307344000</GmtCreate>
      <GmtModified>1543307344000</GmtModified>
      <TemplateId>42</TemplateId>
    </Template> 
  </Templates>
  <Success>true</Success> 
  <Code>200</Code>
  <Total>65</Total>
</DescribeMetricRuleTemplateListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"03AE5FA9-8CB2-4B5B-8306-1BBBF012A1A7",
	"Templates":{
		"Template":[
			{
				"Name":"newtemplate_1",
				"RestVersion":0,
				"Description":"description_111111",
				"GmtCreate":1543302440000,
				"GmtModified":1543302440000,
				"TemplateId":32
			},
			{
				"Name":"newtemplate_2",
				"RestVersion":0,
				"Description":"",
				"GmtCreate":1543307344000,
				"GmtModified":1543307344000,
				"TemplateId":42
			}
		]
	},
	"Success":true,
	"Code":200,
	"Total":65
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

