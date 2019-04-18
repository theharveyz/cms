# DeleteHostAvailability {#doc_api_Cms_DeleteHostAvailability .reference}

删除可用性监控任务。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteHostAvailability)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteHostAvailability|系统规定参数。取值：DeleteHostAvailability。

 |
|Id.N|RepeatList|是|12345|任务ID。N 的取值范围为 1~20。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|57C782E6-B235-4842-AD2B-DB94961761EB|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteHostAvailability
&Id.1=12345
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteHostAvailabilityResponse>
  <RequestId>57C782E6-B235-4842-AD2B-DB94961761EB</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DeleteHostAvailabilityResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"57C782E6-B235-4842-AD2B-DB94961761EB",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

