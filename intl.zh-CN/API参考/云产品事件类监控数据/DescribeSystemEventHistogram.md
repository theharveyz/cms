# DescribeSystemEventHistogram {#doc_api_Cms_DescribeSystemEventHistogram .reference}

查询系统事件的时段数量分布图（柱状图）。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSystemEventHistogram)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSystemEventHistogram|系统规定参数。取值：DescribeSystemEventHistogram。

 |
|EndTime|String|否|1552220485596|结束时间。

 |
|EventType|String|否|Exception|事件类型，不同的产品事件有不同的类型。

 |
|GroupId|String|否|12345|组ID。

 |
|Level|String|否|CRITICAL|事件级别， CRITICAL（严重\), WARN\(警告\), INFO\(信息\)。

 |
|Name|String|否|BucketIngressBandwidth|事件名称。

 |
|PageNumber|Integer|否|1|页码。

 |
|PageSize|Integer|否|10|每页显示记录条数。

 |
|Product|String|否|oss|产品的名称缩写。

 |
|SearchKeywords|String|否|cms|搜索事件内容包含的关键字，支持 and 或者 or。

 如果想要搜索事件内容中即包括a也包括b的结果，可以搜索 a and b；

 如果想要搜索事件内容中包括a或者b的结果，可以搜索 a or b。

 |
|StartTime|String|否|1552209685596|开始时间。

 |
|Status|String|否|normal|状态，多个用逗号分隔。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|486029C9-53E1-44B4-85A8-16A571A043FD|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |
|SystemEventHistograms| | |事件分段统计详情。

 |
|└Count|Long|2|事件发生数量。

 |
|└EndTime|Long|1552225753000|结束时间。

 |
|└StartTime|Long|1552225770000|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSystemEventHistogram
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSystemEventHistogramResponse>
  <SystemEventHistograms>
    <SystemEventHistogram>
      <Count>0</Count>
      <EndTime>1552226750000</EndTime>
      <StartTime>1552226740000</StartTime>
    </SystemEventHistogram>
    <SystemEventHistogram>
      <Count>0</Count>
      <EndTime>1552226760000</EndTime>
      <StartTime>1552226750000</StartTime>
    </SystemEventHistogram>
    <SystemEventHistogram>
      <Count>0</Count>
      <EndTime>1552226770000</EndTime>
      <StartTime>1552226760000</StartTime>
    </SystemEventHistogram>
    <SystemEventHistogram>
      <Count>0</Count>
      <EndTime>1552226780000</EndTime>
      <StartTime>1552226770000</StartTime>
    </SystemEventHistogram>
    <SystemEventHistogram>
      <Count>0</Count>
      <EndTime>1552226790000</EndTime>
      <StartTime>1552226780000</StartTime>
    </SystemEventHistogram>
    <SystemEventHistogram>
      <Count>0</Count>
      <EndTime>1552226800000</EndTime>
      <StartTime>1552226790000</StartTime>
    </SystemEventHistogram>
    <SystemEventHistogram>
      <Count>0</Count>
      <EndTime>1552226810000</EndTime>
      <StartTime>1552226800000</StartTime>
    </SystemEventHistogram>
    <SystemEventHistogram>
      <Count>0</Count>
      <EndTime>1552226820000</EndTime>
      <StartTime>1552226810000</StartTime>
    </SystemEventHistogram>
    <SystemEventHistogram>
      <Count>0</Count>
      <EndTime>1552226827000</EndTime>
      <StartTime>1552226820000</StartTime>
    </SystemEventHistogram>
  </SystemEventHistograms>
  <Message>userId:127067667954****</Message>
  <RequestId>729FDC1A-F4ED-427E-A57D-93925F35FC49</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSystemEventHistogramResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SystemEventHistograms":{
		"SystemEventHistogram":[
			{
				"Count":0,
				"EndTime":1552226750000,
				"StartTime":1552226740000
			},
			{
				"Count":0,
				"EndTime":1552226760000,
				"StartTime":1552226750000
			},
			{
				"Count":0,
				"EndTime":1552226770000,
				"StartTime":1552226760000
			},
			{
				"Count":0,
				"EndTime":1552226780000,
				"StartTime":1552226770000
			},
			{
				"Count":0,
				"EndTime":1552226790000,
				"StartTime":1552226780000
			},
			{
				"Count":0,
				"EndTime":1552226800000,
				"StartTime":1552226790000
			},
			{
				"Count":0,
				"EndTime":1552226810000,
				"StartTime":1552226800000
			},
			{
				"Count":0,
				"EndTime":1552226820000,
				"StartTime":1552226810000
			},
			{
				"Count":0,
				"EndTime":1552226827000,
				"StartTime":1552226820000
			}
		]
	},
	"Message":"userId:127067667954****",
	"RequestId":"729FDC1A-F4ED-427E-A57D-93925F35FC49",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

