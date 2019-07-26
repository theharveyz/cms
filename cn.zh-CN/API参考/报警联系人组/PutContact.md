# PutContact {#doc_api_Cms_PutContact .reference}

创建或者修改报警联系人信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=PutContact&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|PutContact|系统规定参数。取值：PutContact。

 |
|ContactName|String|是|报警联系人名|报警联系人姓名。

 |
|Describe|String|是|报警描述|描述详情。

 |
|Channels.SMS|String|否|1333333\*\*\*\*|手机号码、短信或者电话联系方式。添加或者修改的手机号码会收到一个激活链接， 激活之后才会被加到联系人中。

 手机号码、邮箱、钉钉机器人、旺旺必须最少添加一种联系方式。

 |
|Channels.Mail|String|否|test@aliyun.com|Email地址。添加或者修改Email会收到一个激活链接， 激活之后对应的Email才会被加到联系人中。

 手机号码、邮箱、钉钉机器人、旺旺必须最少添加一种联系方式。

 |
|Channels.DingWebHook|String|否|https://oapi.dingtalk.com/robot/send?access\_token=7d49515e8ebf21106a80a9cc4bb3d247771305d52fb15d6201234565\*\*\*\*|钉钉机器人Webhook。手机号码、邮箱、钉钉机器人、旺旺必须最少添加一种联系方式。

 |
|Channels.AliIM|String|否|旺旺|旺旺联系方式。手机号码、邮箱、钉钉机器人、旺旺必须最少添加一种联系方式。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|181C406E-9DE4-484C-9C61-37AE9A1A12EE|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=PutContact
&ContactName=报警联系人名
&Describe=报警描述
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PutContactResponse>
      <Code>200</Code>
      <RequestId>181C406E-9DE4-484C-9C61-37AE9A1A12EE</RequestId>
      <Success>true</Success>
</PutContactResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"F7FA82F0-8627-441B-9B2B-8663617F36B9",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

