# EnableHostAvailability {#doc_api_Cms_EnableHostAvailability .reference}

启用可用性监控任务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=EnableHostAvailability&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|EnableHostAvailability|系统规定参数。取值：EnableHostAvailability。

 |
|Id.N|RepeatList|是|123456|任务ID。N的取值范围为 1~20。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

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

http(s)://[Endpoint]/?Action=EnableHostAvailability
&Id.1=123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<EnableHostAvailabilityResponse>
      <RequestId>ACBDBB40-DFB6-4F4C-8957-51FFB233969C</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</EnableHostAvailabilityResponse>
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

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

