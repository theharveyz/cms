# DisableAlarm {#doc_api_988970 .reference}

禁用报警规则。

报警规则停止后，将停止探测关联实例的监控项数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DisableAlarm)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Id|String|是|576fbae7-2fd1-411a-ae13-6f09f4fafdde|报警规则的id。

 |
|Action|String|否|DisableAlarm|系统规定参数，取值：DisableAlarm

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|请求失败状态码，200为成功，非200为失败。

 |
|Message|String|Success|请求失败的提示信息。

 |
|RequestId|String|DEF01F10-E747-42FE-9152-85CB43B1B552|请求的uuid，便于查询日志。

 |
|Success|Boolean|true|请求是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DisableAlarm
&Id=576fbae7-2fd1-411a-ae13-6f09f4fafdde
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DisableAlarmResponse>
  <RequestId>CF9F20A2-D4CF-4FA0-B8A3-1F4C151B3C91</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DisableAlarmResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"DEF01F10-E747-42FE-9152-85CB43B1B552",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

