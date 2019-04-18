# DescribeSystemEventCount {#doc_api_Cms_DescribeSystemEventCount .reference}

查询各个产品指定时间段内事件的数量。

按照产品统计，返回每个产品事件数量的统计。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSystemEventCount)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSystemEventCount|系统规定参数。取值：DescribeSystemEventCount。

 |
|EndTime|String|否|1552220485596|结束时间，距离 1970 年 1 月 1 日 0 点的毫秒数。

 |
|EventType|String|否|Exception|事件类型，不同的产品事件有不同的类型，调用：DescribeSystemEventMetaList接口获得产品以及产品的事件类型。

 |
|GroupId|String|否|12345|应用分组ID。

 |
|Level|String|否|warn|事件的级别， CRITICAL（严重\), WARN\(警告\), INFO\(信息\)。

 |
|Name|String|否|BucketIngressBandwidth|事件的名称。

 |
|Product|String|否|oss|产品的名称缩写，具体都有哪些产品接入的系统事件监控，请调用：DescribeSystemEventMetaList接口。

 |
|SearchKeywords|String|否|cms|搜索事件内容包含的关键字，支持 and 或者 or。

 -   如果想要搜索事件内容中即包括a也包括b的结果，可以搜索 a and b；
-   如果想要搜索事件内容中包括a或者b的结果，可以搜索 a or b。

 |
|StartTime|String|否|1552209685596|开始时间，距离1970 年 1 月 1 日 0 点的毫秒数。

 |
|Status|String|否|normal|状态，多个状态用英文逗号分隔。

 |

有哪些产品接入了系统事件，以及对应的事件名， 事件级别、状态等，请参考DescribeSystemEventMetaList接口。

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|60912C8D-B340-4253-ADE7-61ACDFD25CFC|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |
|SystemEventCounts| | |事件数量详情。

 |
|└Content|String|xxxx|具体的内容。

 |
|└GroupId|String|123456|组ID。

 |
|└InstanceName|String|instanceId1|实例名。

 |
|└Level|String|Warn|事件的级别， CRITICAL（严重\), WARN\(警告\), INFO\(信息\)。

 |
|└Name|String|Agent\_Status\_Stopped|事件的名称。

 |
|└Num|Long|2|发生事件的数量。

 |
|└Product|String|ECS|产品缩写。

 |
|└RegionId|String|cn-hangzhou|区域。

 |
|└ResourceId|String|xxxxx-1|资源ID。

 |
|└Status|String|normal|状态。

 |
|└Time|Long|1552199984000|发生事件的时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSystemEventCount
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSystemEventCountResponse>
  <Message>userId:1****|select product, name, count(product) as num group by product,name order by product, name</Message>
  <RequestId>4555773F-769B-4960-87E6-16009E5A4844</RequestId>
  <Data>[{"product":"CloudMonitor","time":"1552199984000","num":"1","name":"Agent_Status_Stopped"},{"product":"OSS","time":"1552199984000","num":"4","name":"UserEgressBandwidth"}]</Data>
  <Code>200</Code>
  <Success>true</Success>
</DescribeSystemEventCountResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"[{\"product\":\"CloudMonitor\",\"time\":\"1552199984000\",\"num\":\"1\",\"name\":\"Agent_Status_Stopped\"},{\"product\":\"OSS\",\"time\":\"1552199984000\",\"num\":\"4\",\"name\":\"UserEgressBandwidth\"}]",
	"Message":"userId:1****|select product, name, count(product) as num group by product,name order by product, name",
	"RequestId":"4555773F-769B-4960-87E6-16009E5A4844",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

