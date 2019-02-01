# ListAlarm {#doc_api_989028 .reference}

查询指定或全部报警规则设置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=ListAlarm)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ListAlarm|系统规定参数，取值：ListAlarm

 |
|Dimension|String|否|\{"instanceId":"XXX"\}|规则关联的实例信息，为json object对应的字符串，例如\{"instanceId":"name1"\}。可以查询用于查询关联该实例的所有规则，应用该字段时必须指定Namespace。

 |
|Id|String|否|i-2ze3w55tr2rcpejpcfap\_72071739-396b-497d-849c-59a73de44bcf|报警规则的id。

 |
|IsEnable|Boolean|否|true|true为启用，false为禁用。

 |
|Name|String|否|报警测试|报警规则名称，支持模糊查询。

 |
|Namespace|String|否|acs\_ecs\_dashboard|产品名称，参考各产品对应的project，例如 acs\_ecs\_dashboard, acs\_rds\_dashboard等 。

 |
|PageNumber|Integer|否|1|页码，默认值：1。

 |
|PageSize|Integer|否|2|每页记录数，默认值：100。

 |
|State|String|否|ok|报警规则状态， ALARM, INSUFFICIENT\_DATA，OK

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AlarmList| | |报警规则详情列表。

 |
|└ComparisonOperator|String|\>|比较符

 |
|└ContactGroups|String|\["test4nudou"\]|通知的联系组，为json array对应的string，如`[“联系组1”,”联系组2”]`。

 |
|└Dimensions|String|\["\{\\"instanceId\\":\\" i-abcdefgh123456\\"\}"\]|报警规则关联的实例列表，为json array对应的字符串，例如`[{"instanceId":"name1"},{"instanceId":"name2"}]`。

 |
|└Enable|Boolean|true|该规则是否启用，true为启动。

 |
|└EndTime|Integer|24|生效时间的结束时间。

 |
|└EvaluationCount|Integer|3|连续探测几次都满足阈值条件时报警，默认3次。

 |
|└Id|String|i-2ze3w55tr2rcpejpcfap\_72071739-396b-497d-849c-59a73de44bcf|报警规则id。

 |
|└MetricName|String|CPUUtilization|报警规则对应的监控项。

 |
|└Name|String|报警测试|报警规则名称。

 |
|└Namespace|String|acs\_ecs\_dashboard|报警规则对应的产品。

 |
|└NotifyType|Integer|0|通知类型，值为0是旺旺+邮件，值为1是旺旺+邮件+短信。

 |
|└Period|Integer|300|查询指标的周期，单位为秒。

 |
|└SilenceTime|Integer|86400|一直处于报警的沉默周期，单位为秒。

 |
|└StartTime|Integer|0|生效时间的开始时间。

 |
|└State|String|ok|报警规则的状态，有一个实例报警就是ALARM，所有都没数据是INSUFFICIENT\_DATA，其它情况为OK。

 |
|└Statistics|String|Average|统计方法，例如Average、Maximum、Minimum。

 |
|└Threshold|String|90|阈值

 |
|└Webhook|String|null|回调函数，只支持公网地址，回调参数请参考[使用报警回调](~~60714~~)。

 |
|Code|String|200|请求失败状态码，200为成功，非200为失败。

 |
|Message|String|Success|请求失败的提示信息。

 |
|NextToken|Integer|2|下一页，为空代表没有下一页。

 |
|RequestId|String|EFD27F56-5799-4CE8-B625-56DF3332331C|请求的uuid，便于查询日志。

 |
|Success|Boolean|true|请求是否成功。

 |
|Total|Integer|27|符合条件数据总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ListAlarm
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ListAlarmResponse>
  <NextToken>2</NextToken>
  <RequestId>CC2CDD2B-4EA5-43CD-BEE3-758E93C36B7F</RequestId>
  <AlarmList>
    <Alarm>
      <Period>300</Period>
      <Statistics>Average</Statistics>
      <Name>ecs_cpu_total</Name>
      <MetricName>cpu_total</MetricName>
      <State>OK</State>
      <Threshold>90</Threshold>
      <Enable>true</Enable>
      <SilenceTime>86400</SilenceTime>
      <NotifyType>1</NotifyType>
      <Dimensions>["{\"instanceId\":\" i-abcdefgh123456\"}"]</Dimensions>
      <Namespace>acs_ecs_dashboard</Namespace>
      <ContactGroups>["test4nudou"]</ContactGroups>
      <Id>putNewAlarm_group_e8da18b9-bc95-4edf-a8bf-159eb6c8286b</Id>
      <EndTime>24</EndTime>
      <StartTime>0</StartTime>
      <ComparisonOperator>&gt;=</ComparisonOperator>
    </Alarm>
    <Alarm>
      <Period>300</Period>
      <Statistics>Average</Statistics>
      <Name>ecs_diskusage_utilization</Name>
      <MetricName>diskusage_utilization</MetricName>
      <State>OK</State>
      <Threshold>90</Threshold>
      <Enable>true</Enable>
      <SilenceTime>86400</SilenceTime>
      <NotifyType>1</NotifyType>
      <Dimensions>["{\"instanceId\":\" i-abcdefgh123456\"}"]</Dimensions>
      <Namespace>acs_ecs_dashboard</Namespace>
      <ContactGroups>["test4nudou"]</ContactGroups>
      <Id>putNewAlarm_group_3233eba5-0dd4-4e80-a5d5-7399dec3d7cc</Id>
      <EndTime>24</EndTime>
      <StartTime>0</StartTime>
      <ComparisonOperator>&gt;=</ComparisonOperator>
    </Alarm>
  </AlarmList>
  <Success>true</Success>
  <Code>200</Code>
  <Total>27</Total>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"NextToken":2,
	"AlarmList":{
		"Alarm":[
			{
				"Period":300,
				"Statistics":"Average",
				"Name":"ecs_cpu_total",
				"MetricName":"cpu_total",
				"State":"OK",
				"Threshold":"90",
				"Enable":true,
				"SilenceTime":86400,
				"NotifyType":1,
				"Dimensions":"[\"{\\\"instanceId\\\":\\\" i-abcdefgh123456\\\"}\"]",
				"Namespace":"acs_ecs_dashboard",
				"EndTime":24,
				"ContactGroups":"[\"test4nudou\"]",
				"Id":"putNewAlarm_group_e8da18b9-bc95-4edf-a8bf-159eb6c8286b",
				"StartTime":0,
				"ComparisonOperator":">="
			},
			{
				"Period":300,
				"Statistics":"Average",
				"Name":"ecs_diskusage_utilization",
				"MetricName":"diskusage_utilization",
				"State":"OK",
				"Threshold":"90",
				"Enable":true,
				"SilenceTime":86400,
				"NotifyType":1,
				"Dimensions":"[\"{\\\"instanceId\\\":\\\" i-abcdefgh123456\\\"}\"]",
				"Namespace":"acs_ecs_dashboard",
				"EndTime":24,
				"ContactGroups":"[\"test4nudou\"]",
				"Id":"putNewAlarm_group_3233eba5-0dd4-4e80-a5d5-7399dec3d7cc",
				"StartTime":0,
				"ComparisonOperator":">="
			}
		]
	},
	"RequestId":"EFD27F56-5799-4CE8-B625-56DF3332331C",
	"Success":true,
	"Code":"200",
	"Total":27
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

