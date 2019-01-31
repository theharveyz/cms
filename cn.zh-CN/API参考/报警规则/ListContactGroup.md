# ListContactGroup {#doc_api_987937 .reference}

查询云账号下对应的报警规则联系人组。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=ListContactGroup)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ListContactGroup|系统规定参数，取值：ListContactGroup

 |
|PageNumber|Integer|否|1|页数，默认值为第1页

 |
|PageSize|Integer|否|100|页大小，默认值为100

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|请求失败状态码，200为成功，非200为失败

 |
|ContactGroups| |"test4nudou","xzytestgroup", "云账号报警联系人"|通知的联系组，为json array对应的string，如`[“联系组1”,”联系组2”]`

 |
|Message|String|Success|请求失败的提示信息

 |
|NextToken|Integer|2|下一页，为空代表没有下一页

 |
|RequestId|String|D3D03B0A-CF1A-4DAB-BF0D-D4B6ACD5677A|请求的uuid，便于查询日志

 |
|Success|Boolean|true|请求是否成功

 |
|Total|Integer|3|符合条件数据总数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ListContactGroup
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ListContactGroupResponse>
  <RequestId>DCE1419F-D60C-441C-81C3-7425B9211AC5</RequestId>
  <ContactGroups>
    <ContactGroup>test4nudou</ContactGroup>
    <ContactGroup>xzytestgroup</ContactGroup>
    <ContactGroup>云账号报警联系人</ContactGroup>
  </ContactGroups>
  <Success>true</Success>
  <Code>200</Code>
  <Total>3</Total>
</ListContactGroupResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"D3D03B0A-CF1A-4DAB-BF0D-D4B6ACD5677A",
	"ContactGroups":{
		"ContactGroup":[
			"test4nudou",
			"xzytestgroup",
			"云账号报警联系人"
		]
	},
	"Success":true,
	"Code":"200",
	"Total":3
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

