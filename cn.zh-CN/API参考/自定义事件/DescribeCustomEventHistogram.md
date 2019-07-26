# DescribeCustomEventHistogram {#doc_api_Cms_DescribeCustomEventHistogram .reference}

查询自定义上报的事件的分时段数量分布图。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeCustomEventHistogram&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCustomEventHistogram|系统规定参数。取值：DescribeCustomEventHistogram。

 |
|EndTime|String|否|1552220485596|结束时间。

 |
|EventId|String|否|123|事件ID。

 |
|GroupId|String|否|12345|应用分组ID。

 |
|Level|String|否|CRITICAL|事件的级别， CRITICAL（严重\)、 WARN\(警告\)、INFO\(信息\)。

 |
|Name|String|否|BucketIngressBandwidth|事件名称。

 |
|SearchKeywords|String|否|cms|搜索事件内容包含的关键字表达式，支持 and 或者 or。

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
|EventHistograms| | |事件统计数据列表。

 |
|Count|Long|3|事件发生的数量。

 |
|EndTime|Long|1552263113000|结束时间。

 |
|StartTime|Long|1552263120000|开始时间。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|486029C9-53E1-44B4-85A8-16A571A043FD|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCustomEventHistogram
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCustomEventHistogramResponse>
  <EventHistograms>
        <EventHistogram>
              <Count>0</Count>
              <EndTime>1552226750000</EndTime>
              <StartTime>1552226740000</StartTime>
        </EventHistogram>
        <EventHistogram>
              <Count>0</Count>
              <EndTime>1552226760000</EndTime>
              <StartTime>1552226750000</StartTime>
        </EventHistogram>
        <EventHistogram>
              <Count>0</Count>
              <EndTime>1552226770000</EndTime>
              <StartTime>1552226760000</StartTime>
        </EventHistogram>
        <EventHistogram>
              <Count>0</Count>
              <EndTime>1552226780000</EndTime>
              <StartTime>1552226770000</StartTime>
        </EventHistogram>
        <EventHistogram>
              <Count>0</Count>
              <EndTime>1552226790000</EndTime>
              <StartTime>1552226780000</StartTime>
        </EventHistogram>
        <EventHistogram>
              <Count>0</Count>
              <EndTime>1552226800000</EndTime>
              <StartTime>1552226790000</StartTime>
        </EventHistogram>
        <EventHistogram>
              <Count>0</Count>
              <EndTime>1552226810000</EndTime>
              <StartTime>1552226800000</StartTime>
        </EventHistogram>
        <EventHistogram>
              <Count>0</Count>
              <EndTime>1552226820000</EndTime>
              <StartTime>1552226810000</StartTime>
        </EventHistogram>
        <EventHistogram>
              <Count>0</Count>
              <EndTime>1552226827000</EndTime>
              <StartTime>1552226820000</StartTime>
        </EventHistogram>
  </EventHistograms>
  <Message>userId:1235</Message>
  <RequestId>729FDC1A-F4ED-427E-A57D-93925F35FC49</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DescribeCustomEventHistogramResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"EventHistograms":{
		"EventHistogram":[
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
	"Message":"userId:1235",
	"RequestId":"729FDC1A-F4ED-427E-A57D-93925F35FC49",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

