# DeleteMonitorGroup {#doc_api_Cms_DeleteMonitorGroup .reference}

删除指定的应用分组。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DeleteMonitorGroup&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteMonitorGroup|系统规定参数。取值：DeleteMonitorGroup。

 |
|GroupId|Long|否|12345|应用分组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Group| | |返回受影响的报警联系组。

 |
|ContactGroups| | |报警联系组。

 |
|Name|String|我的组名|报警联系组名称。

 |
|GroupName|String|我的组|应用分组名称。

 |
|Message|String|success|返回信息。

 |
|RequestId|String|CA35B3AE-4FFD-4A33-AE67-67EF68711EFA|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteMonitorGroup
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

