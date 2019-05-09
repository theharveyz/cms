# DescribeMetricRuleTemplateList {#doc_api_Cms_DescribeMetricRuleTemplateList .reference}

查询报警模板列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleTemplateList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMetricRuleTemplateList|系统规定参数。取值：DescribeMetricRuleTemplateList。

 |
|History|Boolean|否|false|是否显示报警模板应用到分组的历史记录。true：显示， false：不显示， 默认不显示。

 |
|Keyword|String|否|我的模板|按照模板名称模糊搜索。

 |
|Name|String|否|模板名|报警模板名称。

 |
|PageNumber|Long|否|1|页码，默认1。

 |
|PageSize|Long|否|10|每页显示模板的记录条数。

 |
|TemplateId|Long|否|12345|报警模板ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码， 200表示成功，否则为失败。

 |
|Success|Boolean|true|是否成功。

 |
|Message|String|success|错误信息。

 |
|Total|Long|11|总记录条数。

 |
|RequestId|String|1A1B405A-B877-4A27-9922-471F080E4985|请求ID，用于排查问题。

 |
|Templates| | |报警模板列表的数据。

 |
|└ApplyHistories| | |应用历史。

 |
|└ApplyTime|Long|1543459583000|应用的时间。

 |
|└GroupId|Long|12345|应用分组的ID。

 |
|└GroupName|String|我的组名|应用分组的名称。

 |
|└Description|String|cpu报警模板|报警模板的详情。

 |
|└GmtCreate|Long|1543302440000|创建报警模板的时间。

 |
|└GmtModified|Long|1543302440000|报警模板的修改时间。

 |
|└Name|String|template1|报警模板名称。

 |
|└RestVersion|Long|0|报警模板的版本，默认为0。

 |
|└TemplateId|Long|12345|报警模板的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMetricRuleTemplateList
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

