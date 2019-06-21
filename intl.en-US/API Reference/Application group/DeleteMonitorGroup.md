# DeleteMonitorGroup {#doc_api_Cms_DeleteMonitorGroup .reference}

You can call this operation to delete a specified application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMonitorGroup) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteMonitorGroup|The operation that you want to perform. Set the value to DeleteMonitorGroup.

 |
|GroupId|Long|No|12345|The ID of the application group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Group| | |The affected alert contact group.

 |
|└ContactGroups| | |The alert contact group.

 |
|└Name|String|My group name|The name of the alert contact group.

 |
|└GroupName|String|My group|The name of the application group.

 |
|Message|String|success|The returned information.

 |
|RequestId|String|CA35B3AE-4FFD-4A33-AE67-67EF68711EFA|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteMonitorGroup
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<div>
  <RequestId>C85A2870-5DF4-4269-BC50-ECB5E4591A80</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
  <Group>
    <GroupName>xxxxx</GroupName>
    <ContactGroups>
      <ContactGroup>
        <Name>default Contact</Name>
      </ContactGroup>
    </ContactGroups>
    <GroupId>3391309</GroupId>
  </Group>
</div>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"C85A2870-5DF4-4269-BC50-ECB5E4591A80",
	"Success":true,
	"Code":200,
	"Group":{
		"GroupName":"xxxxx",
		"ContactGroups":{
			"ContactGroup":[
				{
					"Name":"default Contact"
				}
			]
		},
		"GroupId":3391309
	}
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

