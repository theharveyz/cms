# PutCustomMetric {#doc_api_Cms_PutCustomMetric .reference}

上报自定义监控数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=PutCustomMetric&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|PutCustomMetric|系统规定参数。取值：PutCustomMetric。

 |
|MetricList.N.Dimensions|String|否|\{"sampleName1":"value1","sampleName2":"value2"\}|维度map，key-value都为字符串, 支持字母、数字、连接符“\_-./\\”，键值对数量最大为10，key长度最大64字节，value长度最大64字节，超过64字节时截取前64字节。

 |
|MetricList.N.GroupId|String|否|12345|应用分组的id。

 |
|MetricList.N.MetricName|String|否|cpu\_total|监控项名称，支持字母、数字、连接符“\_-./\\”，其他为非法字符，最大长度为64字节，超过64字节时截取前64字节。

 |
|MetricList.N.Period|String|否|60|聚合周期，单位为秒。

 如果 type=1则需要传此字段，取值为60、300。

 |
|MetricList.N.Time|String|否|1508136760000|指标发生时间，支持“yyyyMMdd’T’HHmmss.SSSZ”和long型时间戳2种方式，例如 “20171012T132456.888+0800”或“1508136760000”。

 |
|MetricList.N.Type|String|否|0|上报数值的类型，0为原始值，1为聚合数据。

 当上报聚合数据时，建议60s、300s 周期的数据均上报，否则会无法正常查询跨度大于7天的监控数据。

 |
|MetricList.N.Values|String|否|\{"value":10.5\}|指标值集合，当type=0时，key只能为”value”，上报的是原始值，云监控会按周期将原始值聚合为多个值，比如最大、计数、求和等。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0|请求ID，用于排查问题。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=PutCustomMetric
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PutCustomMetricResponse>
      <Message>success</Message>
      <RequestId>05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0</RequestId>
      <Code>200</Code>
</PutCustomMetricResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"05B36C2C-5F6E-48D5-8B41-CE36DD7EE8E0",
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

