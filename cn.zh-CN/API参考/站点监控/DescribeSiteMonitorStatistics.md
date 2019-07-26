# DescribeSiteMonitorStatistics {#doc_api_Cms_DescribeSiteMonitorStatistics .reference}

查询指定任务一段时间内的平均统计数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorStatistics&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSiteMonitorStatistics|系统规定参数。取值：DescribeSiteMonitorStatistics。

 |
|MetricName|String|是|Availability|任务的监控项名称，可选值为：

 -   Availability ：可用率
-   ErrorRate：错误率
-   ResponseTime：响应时间

 |
|TaskId|String|是|49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*|任务ID。

 |
|TimeRange|String|否|60|统计的时间周期， 单位是分钟，最大1440分钟（1天）。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Data|Long|100|统计结果。

 |
|Message|String|Succcessful|错误信息。

 |
|RequestId|String|3fcd12e7-d387-42ee-b77e-661c775bb17f|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSiteMonitorStatistics
&MetricName=Availability
&TaskId=49f7b317-7645-4cc9-94fd-ea42e522****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSiteMonitorStatisticsResponse>
      <Message>successful</Message>
      <RequestId>3fcd12e7-d387-42ee-b77e-661c775bb17f</RequestId>
      <Code>200</Code>
      <Success>true</Success>
</DescribeSiteMonitorStatisticsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"{\"value\":100}",
	"Message":"successful",
	"RequestId":"3fcd12e7-d387-42ee-b77e-661c775bb17f",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

