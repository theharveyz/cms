# DescribeMonitorGroupDynamicRules {#doc_api_Cms_DescribeMonitorGroupDynamicRules .reference}

You can call this operation to query the list of dynamic rules for an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupDynamicRules) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|GroupId|Long|Yes|123456|The ID of the application group.

 |
|Action|String|No|DescribeMonitorGroupDynamicRules|The operation that you want to perform. Set the value to DescribeMonitorGroupDynamicRules.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|PageNumber|Integer|1|The number of the current page.

 |
|PageSize|Integer|10|The number of records on each page.

 |
|RequestId|String|2170B94A-1576-4D65-900E-2093037CDAF3|The request ID for troubleshooting.

 |
|Resource| | |The associated resource.

 |
|└Category|String|ecs|The name of the service.

 |
|└FilterRelation|String|xxx|The filtering condition.

 |
|└Filters| | |The rules.

 |
|└Function|String|contains|The calculation method. Valid values: contains, startWith, and endWith.

 |
|└Name|String|hostName|The name of the field.

 |
|└Value|String|pre|The value of the dynamic rule.

 |
|└GroupId|Long|12345|The ID of the group.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Total|Integer|22|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitorGroupDynamicRules
&GroupId=123456
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitorGroupDynamicRulesResponse> 
  <Resource>
    <Resource>
      <Filters>
        <Filter>
          <Name>hostName</Name>
          <Value>aaa</Value>
          <Function>contains</Function>
        </Filter>
      </Filters>
      <Category>ecs</Category>
      <FilterRelation>and</FilterRelation>
    </Resource>
  </Resource>
  <RequestId>2170B94A-1576-4D65-900E-2093037CDAF3</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DescribeMonitorGroupDynamicRulesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Resource":{
		"Resource":[
			{
				"Filters":{
					"Filter":[
						{
							"Name":"hostName",
							"Value":"aaa",
							"Function":"contains"
						}
					]
				},
				"Category":"ecs",
				"FilterRelation":"and"
			}
		]
	},
	"RequestId":"2170B94A-1576-4D65-900E-2093037CDAF3",
	"Success":true,
	"Code":200
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

