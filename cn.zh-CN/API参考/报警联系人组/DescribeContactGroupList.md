# DescribeContactGroupList {#doc_api_Cms_DescribeContactGroupList .reference}

查询报警联系人组列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeContactGroupList&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeContactGroupList|系统规定参数。取值：DescribeContactGroupList。

 |
|PageNumber|Integer|否|10|页码。

 |
|PageSize|Integer|否|1|每页显示记录条数。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|ContactGroups| |报警联系组人列表|报警联系组人列表。

 |
|Message|String|错误信息|错误信息。

 |
|RequestId|String|916EE694-03C2-47B6-85EE-5054E3C168D3|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |
|Total|Integer|22|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeContactGroupList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeContactGroupListResponse>  
      <Code>200</Code>
      <ContactGroups>我的联系组1</ContactGroups>
      <RequestId>916EE694-03C2-47B6-85EE-5054E3C168D3</RequestId>
      <Success>true</Success>
      <Total>22</Total>
</DescribeContactGroupListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"916EE694-03C2-47B6-85EE-5054E3C168D3",
	"ContactGroups":[
		"我的联系组1"
	],
	"Success":true,
	"Code":"200",
	"Total":22
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

