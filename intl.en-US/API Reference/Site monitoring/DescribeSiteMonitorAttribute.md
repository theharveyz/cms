# DescribeSiteMonitorAttribute {#doc_api_Cms_DescribeSiteMonitorAttribute .reference}

You can call this operation to query detailed information of a site monitoring task.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides OpenAPI Explorer to simplify API usage. You can use [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorAttribute) to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSiteMonitorAttribute|The operation that you want to perform. Set this parameter to DescribeSiteMonitorAttribute.

 |
|TaskId|String|Yes|a1ecd34a-8157-44d9-b065-14950837\*\*\*\*|The ID of the site monitoring task to query.

 |
|IncludeAlert|Boolean|No|false|Specifies whether to return alert rule information in the detailed information.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|Message|String|successful|The error message.

 |
|MetricRules| | |The alert rules associated with the site monitoring task. The alert rules are returned when the IncludeAlert parameter is set to true.

 |
|└ActionEnable|String|true|Indicates whether the alert rule is enabled.

 |
|└AlarmActions|String|\["Alert group"\]|The alert group to which a notification is sent when an alert is triggered.

 |
|└ComparisonOperator|String|\>|The comparison operator.

 |
|└Dimensions|String|\[ \{ "taskId": "49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*" \} \]|The resources monitored by the alert rule.

 |
|└EvaluationCount|String|3|The consecutive number of times for which the metric value is measured before an alert is triggered.

 |
|└Expression|String|$Availability\>90|The expression of the alert rule.

 |
|└Level|String|3|The severity of the alert rule.

 |
|└MetricName|String|Availability|The name of the metric.

 |
|└Namespace|String|acs\_networkmonitor|The namespace of site monitoring. This parameter has a fixed value of acs\_networkmonitor.

 |
|└OkActions|String|\["Alert group"\]|The alert group to which a notification is sent when an alert is cleared.

 |
|└Period|String|60|The interval at which monitoring data is queried. Unit: seconds. For example, 60, 300, or 900. The value usually is the reporting period of the metric. If a statistical period was specified for the alert rule, the statistical period was returned.

 |
|└RuleId|String|49f7b317-7645-4cc1-94fd-ea42e5220932\_Availability|The ID of the alert rule.

 |
|└RuleName|String|Availability|The name of the alert rule.

 |
|└StateValue|String|OK|The alert status. A value of OK indicates that no alert was triggered. A value of ALARM indicates that an alert was triggered.

 |
|└Statistics|String|Availability|The statistical method of the alert rule.

 |
|└Threshold|String|90|The alert threshold.

 |
|RequestId|String|9ed350c5-d579-4ba1-9c5d-dda70cd8422c|The ID of the request.

 |
|SiteMonitors| | |The detailed information of the site monitoring task.

 |
|└Address|String|http://www.aliyun.com|The URL or IP address monitored by the site monitoring task.

 |
|└Interval|String|1|The monitoring interval of the site monitoring task. Unit: minutes. Valid values: 1, 5, and 15.

 |
|└IspCities| | |The detection point information, including the carriers and cities.

 |
|└City|String|546|The ID of the city.

 |
|└CityName|String|Hangzhou|The name of the city.

 |
|└Isp|String|465|The ID of the carrier.

 |
|└IspName|String|Alibaba|The name of the carrier.

 |
|└OptionJson|JSON|\{ "http\_method": "get", "response\_content": "xxxx", "time\_out": 30000\}|The extended options of the protocol of the site monitoring task. The options vary according to the protocol. For more information, see the description of extended options in CreateSiteMonitor.

 |
|└TaskId|String|a1ecd34a-8157-44d9-b060-14950837\*\*\*\*|The ID of the site monitoring task.

 |
|└TaskName|String|Site monitoring task|The name of the site monitoring task.

 |
|└TaskState|String|OK|The status of the alert rule.

 |
|└TaskType|String|HTTP|The protocol of the site monitoring task. Currently, site monitoring supports the following protocols: HTTP, Ping, TCP, UDP, DNS, SMTP, POP3, and FTP.

 |
|Success|Boolean|true|Indicates whether the call was successful.

 |

## Examples {#demo .section}

Sample request

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSiteMonitorAttribute
&TaskId=a1ecd34a-8157-44d9-b065-14950837****
&<Common request parameters>

```

Sample success response

`XML` format

``` {#xml_return_success_demo}
<DescribeSiteMonitorAttributeResponse>
  <Message>successful</Message>
  <RequestId>baac6ca7-8152-4156-987a-653a1533f0e5</RequestId>
  <SiteMonitors>
    <OptionJson>
      <http_method>get</http_method>
      <response_content>xxxx</response_content>
      <time_out>30000</time_out>
      <header>aaaaa=dd</header>
    </OptionJson>
    <Interval>1</Interval>
    <Address>http://www.aliyun.com</Address>
    <TaskId>a1ecd34a-8157-44d9-b060-1****</TaskId>
    <TaskName>aaa-bbb-ccc</TaskName>
    <TaskState>1</TaskState>
    <TaskType>HTTP</TaskType>
    <IspCities>
      <IspCity>
        <Isp>465</Isp>
        <IspName>Alibaba</IspName>
        <CityName>Hangzhou</CityName>
        <City>546</City>
      </IspCity>
      <IspCity>
        <Isp>465</Isp>
        <IspName>Alibaba</IspName>
        <CityName>Qingdao</CityName>
        <City>572</City>
      </IspCity>
      <IspCity>
        <Isp>465</Isp>
        <IspName>Alibaba</IspName>
        <CityName>Beijing</CityName>
        <City>738</City>
      </IspCity>
    </IspCities>
  </SiteMonitors>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSiteMonitorAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"successful",
	"RequestId":"baac6ca7-8152-4156-987a-653a1533f0e5",
	"Success":true,
	"SiteMonitors":{
		"OptionJson":{
			"http_method":"get",
			"response_content":"xxxx",
			"time_out":30000
		},
		"Interval":1,
		"Address":"http://www.aliyun.com",
		"TaskId":"a1ecd34a-8157-44d9-b060-1****",
		"TaskType":"HTTP",
		"TaskState":1,
		"TaskName":"aaa-bbb-ccc",
		"IspCities":{
			"IspCity":[
				{
					"Isp":"465",
					"IspName":"Alibaba",
					"CityName":"Hangzhou",
					"City":"546"
				},
				{
					"Isp":"465",
					"IspName":"Alibaba",
					"CityName":"Qingdao",
					"City":"572"
				},
				{
					"Isp":"465",
					"IspName":"Alibaba",
					"CityName":"Beijing",
					"City":"738"
				}
			]
		}
	},
	"Code":"200"
}
```

## Error codes { .section}

[View error codes.](https://error-center.aliyun.com/status/product/Cms)

