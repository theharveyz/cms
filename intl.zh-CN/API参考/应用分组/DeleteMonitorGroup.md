# DeleteMonitorGroup {#doc_api_Cms_DeleteMonitorGroup .reference}

删除指定的应用分组。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMonitorGroup)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteMonitorGroup|系统规定参数。取值：DeleteMonitorGroup。

 |
|GroupId|Long|否|12345|应用分组ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Group| | |返回受影响的报警联系组。

 |
|└ContactGroups| | |报警联系组。

 |
|└Name|String|我的组名|报警联系组名。

 |
|└GroupName|String|我的组|报警联系组名称。

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

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

