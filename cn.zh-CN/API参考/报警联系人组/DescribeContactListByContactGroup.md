# DescribeContactListByContactGroup {#doc_api_Cms_DescribeContactListByContactGroup .reference}

查询一个报警联系人组下的报警联系人列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeContactListByContactGroup&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeContactListByContactGroup|系统规定参数。取值：DescribeContactListByContactGroup。

 |
|ContactGroupName|String|是|我的组名|报警联系组名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示成功。

 |
|Contacts| | |报警联系人。

 |
|Channels| | |报警通道。

 |
|AliIM|String|我的旺旺|旺旺。

 |
|DingWebHook|String|钉钉机器人地址|钉钉机器人地址。

 |
|Mail|String|test@aliyun.com|Email地址。

 |
|SMS|String|1333333\*\*\*\*|手机号码。

 |
|CreateTime|Long|1552314252000|创建时间。

 |
|Desc|String|描述|报警联系组的描述。

 |
|Name|String|关某|报警联系人姓名。

 |
|UpdateTime|Long|1552314252000|更新时间。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|06D5ECC2-B9BE-42A4-8FA3-1A610FB08B83|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeContactListByContactGroup
&ContactGroupName=我的组名
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeContactListByContactGroupResponse>
      <RequestId>81A6C995-D1A8-4627-B2E6-4B651446DDF9</RequestId>
      <Contacts>
            <Contact>
              <Channels>
                <AliIM>关某</AliIM>
                <Mail>test***@aliyun.com</Mail>
              </Channels>
              <Name>关某</Name>
              <CreateTime>1552355864000</CreateTime>
              <UpdateTime>1552356159000</UpdateTime>
              <Desc>xxxx</Desc>
            </Contact>
      </Contacts>
      <Success>true</Success>
      <Code>200</Code>
</DescribeContactListByContactGroupResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"81A6C995-D1A8-4627-B2E6-4B651446DDF9",
	"Contacts":{
		"Contact":[
			{
				"Name":"关某",
				"Channels":{
					"Mail":"test***@aliyun.com",
					"AliIM":"关某"
				},
				"CreateTime":1552355864000,
				"UpdateTime":1552356159000,
				"Desc":"xxxx"
			}
		]
	},
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

