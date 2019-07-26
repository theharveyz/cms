# DescribeCustomMetricList {#doc_api_Cms_DescribeCustomMetricList .reference}

查询上报的自定义监控数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeCustomMetricList&type=RPC&version=2019-01-01)

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

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|1C225028-B13B-4EFE-AE34-75C5F7412FB2|请求ID，用于排查问题。

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

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

