# DescribeContactList {#doc_api_Cms_DescribeContactList .reference}

查询报警联系人列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeContactList&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeContactList|系统规定参数。取值：DescribeContactList。

 |
|ContactName|String|否|我的报警联系人|报警联系人姓名。只支持精确查询，暂不支持模糊查询。

 |
|PageNumber|Integer|否|1|当前页码，默认1.

 |
|PageSize|Integer|否|10|每页显示的记录条数，默认100。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Success|Boolean|true|是否成功。

 |
|Message|String|success|错误信息。

 |
|Code|String|200|状态码，200表示成功。

 |
|RequestId|String|06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83|请求ID，用于排查问题。

 |
|Contacts| | |报警联系方式。

 |
|Channels| | |报警通知方式。

 |
|AliIM|String|我的旺旺|旺旺。

 |
|DingWebHook|String|https://oapi.dingtalk.com/robot/send?access\_token=9bf44f8189597d07dfdd7a123455ffc112\*\*\*\*|钉钉机器人地址。

 |
|Mail|String|xxxx@aliyun.com|邮件地址。

 |
|SMS|String|1333333\*\*\*\*|手机号码。

 |
|CreateTime|Long|1552356159000|创建时间。

 |
|Desc|String|我的联系方式|描述信息。

 |
|Name|String|关某|联系人姓名。

 |
|UpdateTime|Long|1552356159000|更新时间。

 |
|Total|Integer|15|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeContactList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeContactListResponse>
      <RequestId>06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83</RequestId>
      <Contacts>
            <Contact>
                  <Channels>
                        <SMS>1333333****</SMS>
                        <Mail>xxxxx@aliyun.com</Mail>
                  </Channels>
                  <Name>关某</Name>
                  <CreateTime>1553006761000</CreateTime>
                  <UpdateTime>1553084361000</UpdateTime>
            </Contact>
      </Contacts>
      <Total>1</Total>
      <Success>true</Success>
      <Code>200</Code>
</DescribeContactListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83",
	"Contacts":{
		"Contact":[
			{
				"Name":"关某",
				"Channels":{
					"Mail":"xxxxx@aliyun.com",
					"SMS":"1333333****"
				},
				"CreateTime":1553006761000,
				"UpdateTime":1553084361000
			}
		]
	},
	"Success":true,
	"Code":"200",
	"Total":1
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

