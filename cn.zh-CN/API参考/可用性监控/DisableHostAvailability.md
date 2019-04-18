# DisableHostAvailability {#doc_api_Cms_DisableHostAvailability .reference}

禁用一个可用性监控任务。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DisableHostAvailability)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DisableHostAvailability|系统规定参数。取值：DisableHostAvailability。

 |
|Id.N|RepeatList|是|12345|任务ID。N 的取值范围为 1~20。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|ACBDBB40-DFB6-4F4C-8957-51FFB233969C|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DisableHostAvailability
&Id.1=12345
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DisableHostAvailabilityResponse>
  <RequestId>ACBDBB40-DFB6-4F4C-8957-51FFB233969C</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DisableHostAvailabilityResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"ACBDBB40-DFB6-4F4C-8957-51FFB233969C",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

