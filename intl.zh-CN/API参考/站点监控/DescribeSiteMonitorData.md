# DescribeSiteMonitorData {#doc_api_Cms_DescribeSiteMonitorData .reference}

查询任务的细粒度监控数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorData)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSiteMonitorData|系统规定参数。取值：DescribeSiteMonitorData。

 |
|TaskId|String|是|49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*|任务ID。

 |
|metricName|String|是|Availability|监控项的名称，可选为：Availability（可用率），ResponseTime（响应时间\)。

 |
|EndTime|String|否|1551581437000|结束时间，可以传入距离1970年1月1日 0点的毫秒数，也可以传入format时间格式数据，如2015-10-20 00:00:00。

 |
|Length|Integer|否|1000|返回的数据点数量。

 |
|NextToken|String|否|49f7b317-7645-4cc9-94fd-ea42e5220930ea42e5220930ea42e522\*\*\*\*|分页游标。

 |
|Period|String|否|60|统计周期，单位是秒，取60或60的整数倍。默认根据探测频率最小周期返回数据。

 |
|StartTime|String|否|1551579637000|开始时间，可以传入距离1970年1月1日0点的毫秒数，也可以传入format时间格式数据，如2015-10-20 00:00:00。

 |
|Type|String|否|metric|监控的数据类型。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Data|String|\[\{"Maximum":247,"Mimimum":61,"Average":154,"userId":"127067667954\*\*\*\*","taskId":"49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*","timestamp":1551581760000\}\]|监控数据。

 |
|Message|String|Successful|返回的消息。

 |
|NextToken|String|ea42e5220930ea42e5220930|分页游标。

 |
|RequestId|String|3febb181-0d98-4af9-8b04-7faf36b048b9|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSiteMonitorData
&metricName=Availability
&TaskId=49f7b317-7645-4cc9-94fd-ea42e522****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSiteMonitorDataResponse>
  <Data>
    <Over5totalTime>0</Over5totalTime>
    <Error4XXRate>0</Error4XXRate>
    <UnavailableNumber>0</UnavailableNumber>
    <Over2totalTime>0</Over2totalTime>
    <timestamp>1551581040000</timestamp>
    <Over100FailureRate>0</Over100FailureRate>
    <Over10FailureRate>0</Over10FailureRate>
    <Availability>100</Availability>
    <Over80FailureRate>0</Over80FailureRate>
    <userId>12345</userId>
    <AvailableNumber>2</AvailableNumber>
    <Unavailability>0</Unavailability>
    <ErrorCodeMaximum>0</ErrorCodeMaximum>
    <Over10totalTime>0</Over10totalTime>
    <taskId>49f7b317-7645-4cc9-94fd-1****</taskId>
    <Over30FailureRate>0</Over30FailureRate>
    <Error6XXRate>0</Error6XXRate>
    <Over500NumberRate>0</Over500NumberRate>
    <Over3totalTime>0</Over3totalTime>
    <Over400NumberRate>0</Over400NumberRate>
    <Error5XXRate>0</Error5XXRate>
    <Error5XXNumber>0</Error5XXNumber>
    <Over90FailureRate>0</Over90FailureRate>
    <Error4XXNumber>0</Error4XXNumber>
    <Over50FailureRate>0</Over50FailureRate>
    <ErrorCodeMinimum>0</ErrorCodeMinimum>
    <Error6XXNumber>0</Error6XXNumber>
  </Data>
  <Data>
    <Over5totalTime>0</Over5totalTime>
    <Error4XXRate>0</Error4XXRate>
    <UnavailableNumber>0</UnavailableNumber>
    <Over2totalTime>0</Over2totalTime>
    <timestamp>1551581100000</timestamp>
    <Over100FailureRate>0</Over100FailureRate>
    <Over10FailureRate>0</Over10FailureRate>
    <Availability>100</Availability>
    <Over80FailureRate>0</Over80FailureRate>
    <userId>12345</userId>
    <AvailableNumber>2</AvailableNumber>
    <Unavailability>0</Unavailability>
    <ErrorCodeMaximum>0</ErrorCodeMaximum>
    <Over10totalTime>0</Over10totalTime>
    <taskId>49f7b317-7645-4cc9-94fd-1****</taskId>
    <Over30FailureRate>0</Over30FailureRate>
    <Error6XXRate>0</Error6XXRate>
    <Over500NumberRate>0</Over500NumberRate>
    <Over3totalTime>0</Over3totalTime>
    <Over400NumberRate>0</Over400NumberRate>
    <Error5XXRate>0</Error5XXRate>
    <Error5XXNumber>0</Error5XXNumber>
    <Over90FailureRate>0</Over90FailureRate>
    <Error4XXNumber>0</Error4XXNumber>
    <Over50FailureRate>0</Over50FailureRate>
    <ErrorCodeMinimum>0</ErrorCodeMinimum>
    <Error6XXNumber>0</Error6XXNumber>
  </Data>
  <RequestId>DBDEAC51-EA3C-4853-8F25-6B48D38A28A9</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSiteMonitorDataResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":[
		{
			"Over5totalTime":0,
			"Error4XXRate":0,
			"UnavailableNumber":0,
			"Over2totalTime":0,
			"Over100FailureRate":0,
			"timestamp":1551581040000,
			"Over10FailureRate":0,
			"Availability":100,
			"userId":"12345",
			"Over80FailureRate":0,
			"AvailableNumber":2,
			"Unavailability":0,
			"ErrorCodeMaximum":0,
			"Over10totalTime":0,
			"taskId":"49f7b317-7645-4cc9-94fd-1****",
			"Over30FailureRate":0,
			"Error6XXRate":0,
			"Over500NumberRate":0,
			"Over3totalTime":0,
			"Over400NumberRate":0,
			"Error5XXRate":0,
			"Error5XXNumber":0,
			"Over90FailureRate":0,
			"Error4XXNumber":0,
			"Over50FailureRate":0,
			"ErrorCodeMinimum":0,
			"Error6XXNumber":0
		},
		{
			"Over5totalTime":0,
			"Error4XXRate":0,
			"UnavailableNumber":0,
			"Over2totalTime":0,
			"Over100FailureRate":0,
			"timestamp":1551581100000,
			"Over10FailureRate":0,
			"Availability":100,
			"userId":"12345",
			"Over80FailureRate":0,
			"AvailableNumber":2,
			"Unavailability":0,
			"ErrorCodeMaximum":0,
			"Over10totalTime":0,
			"taskId":"49f7b317-7645-4cc9-94fd-1****",
			"Over30FailureRate":0,
			"Error6XXRate":0,
			"Over500NumberRate":0,
			"Over3totalTime":0,
			"Over400NumberRate":0,
			"Error5XXRate":0,
			"Error5XXNumber":0,
			"Over90FailureRate":0,
			"Error4XXNumber":0,
			"Over50FailureRate":0,
			"ErrorCodeMinimum":0,
			"Error6XXNumber":0
		}
	],
	"RequestId":"DBDEAC51-EA3C-4853-8F25-6B48D38A28A9",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

