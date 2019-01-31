# ListAlarmHistory {#doc_api_987961 .reference}

查询报警历史。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=ListAlarmHistory)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ListAlarmHistory|系统规定参数，取值：ListAlarmHistory

 |
|Cursor|String|否|1|查询数据的起始位置，为空则按时间查询前100条

 |
|EndTime|String|否|1548927491223|查询数据结束时间，默认当前时间，可以输入long型时间，也可以输入yyyy-MM-dd HH:mm:ss类型时间

 |
|Id|String|否|1a775e37-dfba-430c-ab9f-7036475c8bfb\_2dbe619b-0483-402e-9437-7c7a38fba7ed|报警规则的id。

 |
|Size|Integer|否|3|每页记录数，默认值：100。

 |
|StartTime|String|否|1548913091223|查询数据开始时间，默认24小时前，可以输入long型时间，也可以输入yyyy-MM-dd HH:mm:ss类型时间

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AlarmHistoryList| | |报警历史详情列表。

 |
|└AlarmTime|Long|1548926982000|报警发生的时间。

 |
|└ContactGroups|String|\["DB组"\]|发出的报警通知的通知对象，json array对应的字符串，例如\\“联系组1”:”联系组2”，只有通知状态为0才有该字段。

 |
|└Dimension|String|\{"instanceId":"XXX"\}|报警规则对应实例，为json object对应的字符串,例如\{“instance”:”name1”\}。

 |
|└EvaluationCount|Integer|3|连续探测几次都满足阈值条件时报警。

 |
|└Id|String|1a775e37-dfba-430c-ab9f-7036475c8bfb\_2dbe619b-0483-402e-9437-7c7a38fba7ed|报警规则的id。

 |
|└LastTime|Long|2851651669|报警持续时间，单位为毫秒。

 |
|└MetricName|String|CPUUtilization|监控项名称。

 |
|└Name|String|报警测试|报警规则的名称。

 |
|└Namespace|String|acs\_ecs\_dashboard|产品的名称。

 |
|└State|String|ALARM|报警规则状态，有OK，ALARM，INSUFFICIENT\_DATA三种状态。

 |
|└Status|Integer|2|通知发送状态，0为已通知用户，1为不在生效期未通知，2为处于报警沉默期未通知。

 |
|└Value|String|84401454|报警的当前值。

 |
|Code|String|200|请求失败状态码，200为成功，非200为失败。

 |
|Cursor|String|1|下一页数据，为空代表没有下一页。

 |
|Message|String|Success|请求失败的提示信息。

 |
|RequestId|String|1DBBCE29-0F69-435C-B65C-53D1011D1D72|请求的uuid，便于查询日志。

 |
|Success|Boolean|true|请求是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ListAlarmHistory
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ListAlarmHistoryResponse>
  <AlarmHistoryList>
    <AlarmHistory>
      <Status>2</Status>
      <Value>{"Maximum":301,"Minimum":301}</Value>
      <MetricName>http.status_groupbyinstanceid#60</MetricName>
      <State>ALARM</State>
      <LastTime>122088</LastTime>
      <AlarmTime>1489568222088</AlarmTime>
      <Namespace>acs_sitemonitor</Namespace>
      <ContactGroups>null</ContactGroups>
      <Id>1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed</Id>
      <EvaluationCount>3</EvaluationCount>
    </AlarmHistory>
    <AlarmHistory>
      <Status>0</Status>
      <Value>{"Maximum":301,"Minimum":301}</Value>
      <MetricName>http.status_groupbyinstanceid#60</MetricName>
      <State>ALARM</State>
      <LastTime>62078</LastTime>
      <AlarmTime>1489568162078</AlarmTime>
      <Namespace>acs_sitemonitor</Namespace>
      <ContactGroups>["云账号报警联系人"]</ContactGroups>
      <Id>1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed</Id>
      <EvaluationCount>3</EvaluationCount>
    </AlarmHistory>
  </AlarmHistoryList>
  <RequestId>7E7A6173-EC07-43A1-ABBF-1F05EBB4C2BB</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</ListAlarmHistoryResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"AlarmHistoryList":{
		"AlarmHistory":[
			{
				"Status":2,
				"Value":"{\"Maximum\":301,\"Minimum\":301}",
				"MetricName":"http.status_groupbyinstanceid#60",
				"State":"ALARM",
				"LastTime":122088,
				"AlarmTime":1489568222088,
				"Namespace":"acs_sitemonitor",
				"Id":"1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed",
				"ContactGroups":"null",
				"EvaluationCount":3
			},
			{
				"Status":0,
				"Value":"{\"Maximum\":301,\"Minimum\":301}",
				"MetricName":"http.status_groupbyinstanceid#60",
				"State":"ALARM",
				"LastTime":62078,
				"AlarmTime":1489568162078,
				"Namespace":"acs_sitemonitor",
				"Id":"1a775e37-dfba-430c-ab9f-7036475c8bfb_2dbe619b-0483-402e-9437-7c7a38fba7ed",
				"ContactGroups":"[\"云账号报警联系人\"]",
				"EvaluationCount":3
			}
		]
	},
	"RequestId":"1DBBCE29-0F69-435C-B65C-53D1011D1D72",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

