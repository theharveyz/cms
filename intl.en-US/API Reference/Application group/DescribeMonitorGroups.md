# DescribeMonitorGroups {#doc_api_Cms_DescribeMonitorGroups .reference}

You can call this operation to query the list of application groups.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroups) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeMonitorGroups|The operation that you want to perform. Set the value to DescribeMonitorGroups.

 |
|SelectContactGroups|Boolean|No|true|Indicates whether to include associated alert contact groups in the returned results.

 |
|PageNumber|Integer|No|1|The number of the page. Default value: 1.

 |
|PageSize|Integer|No|10|The number of records on each page. Default value: 10.

 |
|Keyword|String|No|test|The name of the application group. You can perform fuzzy search based on the application group name.

 |
|InstanceId|String|No|xxx-1|The ID of the resource instance. You can search for the application group to which the specified instance belongs.

 |
|GroupName|String|No|My group|The name of the application group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The status description. The Message parameter is null when the Code parameter is 200.

 |
|PageNumber|Integer|1|The number of the page.

 |
|PageSize|Integer|10|The number of records on each page.

 |
|RequestId|String|3121AE7D-4AFF-4C25-8F1D-C8226EBB1F42|The request ID for troubleshooting.

 |
|Resources| | |The associated resource.

 |
|└BindUrl|String|http://xxx|The URL that is synchronized from k8s.

 |
|└ContactGroups| | |The alert contact group.

 |
|└Name|String|Default alert contact group|The name of the alert contact group.

 |
|└GmtCreate|Long|1510286840000|The creation time. It is an integer, indicating the time that has passed since 00:00:00, January 1, 1970. Unit: millisecond.

 |
|└GmtModified|Long|1540370711000|The modification time. It is an integer, indicating the time that has passed since 00:00:00, January 1, 1970. Unit: millisecond.

 |
|└GroupId|Long|12345|The ID of the group.

 |
|└GroupName|String|Application group 1|The name of the application group.

 |
|└ServiceId|String|service-1|The ID of the service.

 |
|└Type|String|custom|The type of the group. Valid values:

 -   custom: The group is created by the user.
-   ehpc\_cluster: The group is synchronized from the ehpc cluster.
-   kubernetes: The group is synchronized from k8s.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Total|Integer|10|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitorGroups
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitorGroupListResponse>
  <PageNumber>1</PageNumber> 
  <PageSize>30</PageSize>
  <RequestId>31BC7201-00F2-47B2-B7B9-6A173076ACE8</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
  <Total>1</Total> 
  <Resources>
    <Resource>
      <GroupName>demo</GroupName>
      <Type>custom</Type>
      <ContactGroups>
        <ContactGroup>
          <Name>xxx</Name>
        </ContactGroup>
      </ContactGroups>
      <ServiceId>49922</ServiceId>
      <GmtCreate>1489043796000</GmtCreate>
      <GmtModified>1525183537000</GmtModified>
      <GroupId>13263</GroupId>
    </Resource>
  </Resources> 
</DescribeMonitorGroupListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"PageSize":30,
	"RequestId":"31BC7201-00F2-47B2-B7B9-6A173076ACE8",
	"Success":true,
	"Code":200,
	"Total":1,
	"Resources":{
		"Resource":[
			{
				"GroupName":"demo",
				"Type":"custom",
				"ServiceId":49922,
				"ContactGroups":{
					"ContactGroup":[
						{
							"Name":"xxx"
						}
					]
				},
				"GmtCreate":1489043796000,
				"GroupId":13263,
				"GmtModified":1525183537000
			}
		]
	}
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

