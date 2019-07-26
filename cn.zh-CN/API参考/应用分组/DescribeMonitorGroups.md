# DescribeMonitorGroups {#doc_api_Cms_DescribeMonitorGroups .reference}

查询应用分组列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroups&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMonitorGroups|系统规定参数。取值：DescribeMonitorGroups。

 |
|SelectContactGroups|Boolean|否|true|返回结果中是否需要包含报警联系人组。

 |
|PageNumber|Integer|否|1|分页页码， 默认1 。

 |
|PageSize|Integer|否|10|分页大小，默认10。

 |
|Keyword|String|否|test|应用分组名称。可根据应用分组名称模糊查询。

 |
|InstanceId|String|否|xxx-1|资源实例ID。查询指定实例所在的应用分组。

 |
|GroupName|String|否|我的组|应用分组名称。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|状态描述信息，Code为”200”时，Message一般为空。

 |
|PageNumber|Integer|1|页码。

 |
|PageSize|Integer|10|每页记录条数。

 |
|RequestId|String|3121AE7D-4AFF-4C25-8F1D-C8226EBB1F42|请求ID，用于排查问题。

 |
|Resources| | |关联资源。

 |
|BindUrl|String|http://xxx|从k8s同步过来的URL地址。

 |
|ContactGroups| | |报警联系组。

 |
|Name|String|默认报警联系组|报警联系组名。

 |
|GmtCreate|Long|1510286840000|创建时间， 范围为一个整形，距离1970年1月1日 0点的毫秒数。

 |
|GmtModified|Long|1540370711000|修改时间， 范围为一个整形，距离1970年1月1日 0点的毫秒数。

 |
|GroupId|Long|12345|组ID。

 |
|GroupName|String|应用分组1|应用组的名称。

 |
|ServiceId|String|service-1|服务ID。

 |
|Type|String|custom|组的类型， 共有三种：

 -   custom：为用户自己创建的，
-   ehpc\_cluster:为从ehpc集群同步的，
-   kubernetes：为从k8s同步的。

 |
|Success|Boolean|true|是否成功。

 |
|Total|Integer|10|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitorGroups
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

