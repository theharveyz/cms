# NodeStatus {#doc_api_988430 .reference}

查询指定实例的云监控插件运行状态。

## 插件运行状态 {#description .section}

|名称

|描述

|
|----|----|
|running

|正在运行中

|
|stopped

|已停止

|
|not\_installed

|未安装

|
|installing

|安装中

|
|install\_faild

|安装失败

|
|need\_to\_upgrade

|需要升级

|
|uninstalled

|已卸载

|

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=NodeStatus)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|InstanceId|String|是|i-abcdefgh123456|实例id，例如i-22jja5c2l。

 |
|Action|String|否|NodeStatus|系统规定参数。取值：NodeStatus

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AutoInstall|Boolean|true|是否可以使用NodeInstall自动安装

 |
|ErrorCode|Integer|200|错误码，200为成功，其他失败

 |
|ErrorMessage|String|The specified resource is not found.|错误提示

 |
|InstanceId|String|i-abcdefgh123456|实例id

 |
|RequestId|String|9E14096E-68A1-4908-92D0-E5FC6408623A|请求的唯一ID用于定位错误

 |
|Status|String|running|插件运行状态

 |
|Success|Boolean|true|本次操是否成功，等价于errorCode200

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=NodeStatus
&InstanceId=i-abcdefgh123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<NodeStatusResponse>
  <Status>running</Status>
  <InstanceId> i-abcdefgh123456</InstanceId>
  <ErrorCode>200</ErrorCode>
  <Success>true</Success>
  <AutoInstall>true</AutoInstall>
</NodeStatusResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Status":"running",
	"InstanceId":" i-abcdefgh123456",
	"ErrorCode":200,
	"Success":true,
	"AutoInstall":true
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

