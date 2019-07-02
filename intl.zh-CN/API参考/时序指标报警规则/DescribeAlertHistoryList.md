# DescribeAlertHistoryList {#doc_api_Cms_DescribeAlertHistoryList .reference}

查询报警历史详情。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeAlertHistoryList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeAlertHistoryList|系统规定参数。取值：DescribeAlertHistoryList。

 |
|AlertStatus|String|否|ALARM|报警状态：

 -   ALARM：报警状态
-   OK：恢复正常

 |
|Ascending|Boolean|否|true|排序，正序或者倒序， true表示时间倒序， false表示时间正序。

 |
|EndTime|String|否|1554085998000|结束时间。

 |
|GroupId|String|否|123456|应用组ID。

 |
|MetricName|String|否|cpu\_total|监控项名称。

 |
|Namespace|String|否|acs\_ecs\_dashboard|产品的数据命名空间，可通过DescribeMetricMetaList接口查询或参考[预设监控项参考](~~28619~~)。

 |
|Page|Integer|否|1|页码。

 |
|PageSize|Integer|否|10|页面大小。

 |
|RuleId|String|否|aaaabbb123|报警规则ID。

 |
|RuleName|String|否|我的报警规则|报警规则名称。

 |
|StartTime|String|否|1554085998000|开始时间。

 |
|State|String|否|2|通道沉默状态：

 -   2：表示通道沉默。
-   0：表示报警或者恢复。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AlarmHistoryList| | |报警历史详情。

 |
|└AlertName|String|我的报警规则|报警规则名称。

 |
|└AlertState|String|OK|报警的状态：

 -   OK：表示正常。
-   ALARM：表示报警。

 |
|└AlertTime|Long|1554105040000|发生报警的时间。

 |
|└ContactALIIMs| |我的旺旺|旺旺报警通知。

 |
|└ContactGroups| |报警通知联系组|报警联系组。

 |
|└ContactMails| |xxx@aliyun.com|邮件报警通知人。

 |
|└ContactSmses| |1333333\*\*\*\*|短信报警联系方式，手机号列表。

 |
|└Contacts| |我的报警联系人|报警联系人。

 |
|└Dimensions|String|\{"instanceId":"i-2zebwilv3xfdg1\*\*\*\*"\}|关联的资源。

 |
|└EvaluationCount|Integer|2|重试次数。

 |
|└Expression|String|$Average\>=1|报警触发表达式。

 |
|└GroupId|String|12345|应用组ID。

 |
|└InstanceName|String|ali-186xxxx123456|实例名称。

 |
|└LastTime|Long|347020693|最后一次出现状态改变的时间。

 |
|└Level|String|P3|报警级别：

 -   p2：电话、短信、邮件、旺旺、钉钉机器人
-   p3：:短信、邮件、旺旺、钉钉机器人
-   p4：:邮件、旺旺、钉钉机器人

 |
|└MetricName|String|cpu\_total|监控项名称。可通过DescribeMetricMetaList接口查询或参考[预设监控项参考](~~28619~~)。

 |
|└Namespace|String|acs\_ecs\_dashboard|产品的数据命名空间，可通过DescribeMetricMetaList接口查询或参考[预设监控项参考](~~28619~~)。

 |
|└RuleId|String|d97a65a7-70d2-4a8a-97bf-1a9147\*\*\*\*|报警规则的ID。

 |
|└RuleName|String|我的报警|报警规则名称。

 |
|└Status|Integer|2|通道沉默状态：

 -   2：表示通道沉默。
-   0：表示报警或者恢复。

 |
|└Value|String|5.39|出现报警或者恢复时候的监控值。

 |
|└Webhooks|String|http://www.aliyun.com/webhook.html|URL回调地址。

 |
|Code|String|200|状态码， 200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|189B35DD-68BA-43CE-A66A-57F0BE12C885|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |
|Total|String|2|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeAlertHistoryList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAlertHistoryListResponse>
  <AlarmHistoryList>
    <AlarmHistory>
      <Value>4.41</Value>
      <LastTime>881140083</LastTime>
      <Webhooks/>
      <ContactSmses/>
      <RuleName>test-auto-scaling-0001</RuleName>
      <GroupId/>
      <AlertName>putNewAlarm_xxxxxx</AlertName>
      <EvaluationCount>1</EvaluationCount>
      <Status>2</Status>
      <AlertState>ALARM</AlertState>
      <MetricName>cpu_total#60</MetricName>
      <ContactMails/>
      <AlertTime>1554986620000</AlertTime>
      <Dimensions>{"instanceId":"i-2******3"}</Dimensions>
      <RuleId/>
      <Contacts/>
      <Namespace>acs_ecs</Namespace>
      <ContactALIIMs/>
      <ContactGroups/>
      <Expression>$Average&gt;=1</Expression>
      <Level>P3</Level>
      <InstanceName/>
    </AlarmHistory>
    <AlarmHistory>
      <Value>2.13</Value>
      <LastTime>760058</LastTime>
      <Webhooks/>
      <ContactSmses/>
      <RuleName>test-auto-scaling-0001</RuleName>
      <GroupId/>
      <AlertName>putNewAlarm_us****</AlertName>
      <EvaluationCount>1</EvaluationCount>
      <Status>2</Status>
      <AlertState>ALARM</AlertState>
      <MetricName>cpu_total#60</MetricName>
      <ContactMails/>
      <AlertTime>1554986620000</AlertTime>
      <Dimensions>{"instanceId":"i-2z*****"}</Dimensions>
      <RuleId/>
      <Contacts/>
      <Namespace>acs_ecs</Namespace>
      <ContactALIIMs/>
      <ContactGroups/>
      <Expression>$Average&gt;=1</Expression>
      <Level>P3</Level>
      <InstanceName/>
    </AlarmHistory>
  </AlarmHistoryList>
  <RequestId>FEBE3561-166F-4DB2-BB59-020B26F30318</RequestId>
  <Success>true</Success>
  <Code>200</Code>
  <Total>102390</Total>
</DescribeAlertHistoryListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"AlarmHistoryList":{
		"AlarmHistory":[
			{
				"Value":"4.41",
				"LastTime":881140083,
				"Webhooks":"",
				"ContactSmses":{
					"ContactSms":[]
				},
				"RuleName":"test-auto-scaling-0001",
				"GroupId":"",
				"AlertName":"putNewAlarm_xxxxxx",
				"EvaluationCount":1,
				"Status":2,
				"AlertState":"ALARM",
				"MetricName":"cpu_total#60",
				"ContactMails":{
					"ContactMail":[]
				},
				"AlertTime":1554986620000,
				"Dimensions":"{\"instanceId\":\"i-2******3\"}",
				"RuleId":"",
				"Namespace":"acs_ecs",
				"Contacts":{
					"Contact":[]
				},
				"Level":"P3",
				"Expression":"$Average>=1",
				"ContactGroups":{
					"ContactGroup":[]
				},
				"ContactALIIMs":{
					"ContactALIIM":[]
				},
				"InstanceName":""
			},
			{
				"Value":"2.13",
				"LastTime":760058,
				"Webhooks":"",
				"ContactSmses":{
					"ContactSms":[]
				},
				"RuleName":"test-auto-scaling-0001",
				"GroupId":"",
				"AlertName":"putNewAlarm_us****",
				"EvaluationCount":1,
				"Status":2,
				"AlertState":"ALARM",
				"MetricName":"cpu_total#60",
				"ContactMails":{
					"ContactMail":[]
				},
				"AlertTime":1554986620000,
				"Dimensions":"{\"instanceId\":\"i-2z*****\"}",
				"RuleId":"",
				"Namespace":"acs_ecs",
				"Contacts":{
					"Contact":[]
				},
				"Level":"P3",
				"Expression":"$Average>=1",
				"ContactGroups":{
					"ContactGroup":[]
				},
				"ContactALIIMs":{
					"ContactALIIM":[]
				},
				"InstanceName":""
			}
		]
	},
	"RequestId":"FEBE3561-166F-4DB2-BB59-020B26F30318",
	"Success":true,
	"Code":"200",
	"Total":102390
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

