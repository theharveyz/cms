# EnableAlarm {#doc_api_987935 .reference}

启动报警规则。

当您的报警规则处于停止状态时，可以使用此接口启用报警规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=EnableAlarm)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Id|String|是|576fbae7-2fd1-411a-ae13-6f09f4fafdde|报警规则的id

 |
|Action|String|否|EnableAlarm|系统规定参数，取值：EnableAlarm

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|请求失败状态码，200为成功，非200为失败

 |
|Message|String|Success|请求失败的提示信息

 |
|RequestId|String|1C5E0E5D-76D5-469C-9FA8-D74799B24860|请求的uuid，便于查询日志

 |
|Success|Boolean|true|请求是否成功

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=EnableAlarm
&Id=576fbae7-2fd1-411a-ae13-6f09f4fafdde
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<EnableAlarmResponse>
  <RequestId>1B77FA9C-4E5A-4DF9-82CB-0E898C9FDA2F</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</EnableAlarmResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"1C5E0E5D-76D5-469C-9FA8-D74799B24860",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

