# DescribeCustomMetricList {#doc_api_Cms_DescribeCustomMetricList .reference}

查询上报的自定义监控数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeCustomMetricList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCustomMetricList|系统规定参数。取值：DescribeCustomMetricList。

 |
|GroupId|String|是|12345|应用分组ID。

 |
|Dimension|String|否|xx|维度map，key-value都为字符串, 支持字母、数字、连接符“\_-./\\”，键值对数量最大为10，key长度最大64字节，value长度最大64字节，超过64字节时截取前64字节。

 |
|Md5|String|否|97c25982d9745a231276bff27469fbc8|Md5校验码。

 |
|MetricName|String|否|cpu|监控项名称。

 |
|PageNumber|String|否|1|当前页码。

 |
|PageSize|String|否|10|每页显示记录条数。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|1C225028-B13B-4EFE-AE34-75C5F7412FB2|返回查询参数以及对应的查询结果，返回的结果为一个大的json字符串。

 |
|Result|String|\{\\"param\\":\{\\"metric\\":\\"\{\\\\\\"project\\\\\\":\\\\\\"acs\_customMetric\_12345\\\\\\",\\\\\\"status\\\\\\":1\}\\",\\"service\\":\\"metrics.xxxxx.com\\"\},\\"data\\":\[\{\\"groupId\\":\\"111\\",\\"count\\":1\},\{\\"groupId\\":\\"111\\",\\"count\\":2\}\]\}|监控数据结果集。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCustomMetricList
&GroupId=12345
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCustomMetricListResponse>
  <Code>200</Code>
  <Data>{"param":{"metric":"{\"project\":\"acs_customMetric_12345\",\"status\":1}","service":"metrics.xxxxx.com"},"data":[{"groupId":"111","count":1},{"groupId":"111","count":2}]}</Data>
  <Message>success</Message>
  <Success>true</Success>
</DescribeCustomMetricListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"{\"param\":{\"metric\":\"{\\\"project\\\":\\\"acs_customMetric_12345\\\",\\\"status\\\":1}\",\"service\":\"metrics.xxxxx.com\"},\"data\":[{\"groupId\":\"111\",\"count\":1},{\"groupId\":\"111\",\"count\":2}]}",
	"Message":"success",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

