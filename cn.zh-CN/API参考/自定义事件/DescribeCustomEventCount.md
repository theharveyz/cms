# DescribeCustomEventCount {#doc_api_Cms_DescribeCustomEventCount .reference}

查询自定义事件的统计结果。

按照产品统计每个产品自定义事件数量。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeCustomEventCount&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCustomEventCount|系统规定参数。取值：DescribeCustomEventCount。

 |
|EndTime|String|否|1552220485596|结束时间。

 |
|EventId|String|否|123|事件ID。

 |
|GroupId|String|否|12345|应用分组ID。

 |
|Level|String|否|CRITICAL|事件级别， CRITICAL（严重\)、WARN\(警告\)、INFO\(信息\)。

 |
|Name|String|否|BABEL\_BUY|事件名称。

 |
|SearchKeywords|String|否|cms|搜索事件内容包含的关键字，支持 and 或者 or。

 -   如果想要搜索事件内容中即包括a又包括b的结果，可以搜索 a and b。
-   如果想要搜索事件内容中包括a或者b的结果，可以搜索 a or b。

 |
|StartTime|String|否|1552209685596|开始时间。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|CustomEventCounts| | |自定义事件的详细内容。

 |
|Name|String|BABEL\_BUY|事件名称。

 |
|Num|Integer|20|事件数量。

 |
|Time|Long|1552267615000|事件发生时间。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|60912C8D-B340-4253-ADE7-61ACDFD25CFC|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCustomEventCount
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCustomEventCountResponse>
      <Success>true</Success>
      <Message>userId:123456|select name, count(*) as num group by name order by name limit 1000</Message>
      <RequestId>2cf3a089-a715-4bc9-9e1b-69c883edccff</RequestId>
      <Data>
            <Time>1552267615000</Time>
            <Num>2</Num>
            <Name>BABEL_BUY</Name>
      </Data>
</DescribeCustomEventCountResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":[
		{
			"Name":"BABEL_BUY",
			"Time":1552267615000,
			"Num":"2"
		}
	],
	"Message":"userId:123456|select name, count(*) as num group by name order by name limit 1000",
	"RequestId":"2cf3a089-a715-4bc9-9e1b-69c883edccff",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

