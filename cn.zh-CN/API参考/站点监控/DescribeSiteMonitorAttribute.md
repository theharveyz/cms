# DescribeSiteMonitorAttribute {#doc_api_Cms_DescribeSiteMonitorAttribute .reference}

查询站点监控详细信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorAttribute&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSiteMonitorAttribute|系统规定参数。取值：DescribeSiteMonitorAttribute。

 |
|TaskId|String|是|a1ecd34a-8157-44d9-b065-14950837\*\*\*\*|要查询的任务ID。

 |
|IncludeAlert|Boolean|否|false|任务详情的返回是否包含报警规则。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|Successful|错误信息。

 |
|MetricRules| | |如果请求参数中IncludeAlert=true，这里则返回对应任务的报警规则。

 |
|ActionEnable|String|true|报警规则的开启状态。

 |
|AlarmActions|String|\["通知联系人组"\]|报警规则通知报警联系组。

 |
|ComparisonOperator|String|\>|比较符。

 |
|Dimensions|String|\[ \{ "taskId": "49f7b317-7645-4cc9-94fd-ea42e522\*\*\*\*" \} \]|报警规则对应的维度。

 |
|EvaluationCount|String|3|重试次数。

 |
|Expression|String|$Availability\>90|报警规则表达式。

 |
|Level|String|3|报警规则的级别。

 |
|MetricName|String|Availability|监控项名称。

 |
|Namespace|String|acs\_networkmonitor|站点监控的namepsace为acs\_networkmonitor。

 |
|OkActions|String|\["通知联系人组"\]|发送报警。

 |
|Period|String|1m|时间间隔，统一用秒数来计算，例如 60, 300, 900。通常是监控项时申明的上报周期。如果设置报警规则的时候设置了了统计周期，则查询对应的统计数据 。

 |
|RuleId|String|49f7b317-7645-4cc1-94fd-ea42e5220932\_Availability|报警规则ID。

 |
|RuleName|String|可用性|报警规则名称。

 |
|StateValue|String|OK|报警的状态，OK：正常，ALARM：报警。

 |
|Statistics|String|Availability|报警的统计方法。

 |
|Threshold|String|90|报警阈值。

 |
|RequestId|String|9ed350c5-d579-4ba1-9c5d-dda70cd8422c|请求ID，用于排查问题。

 |
|SiteMonitors| | |站点监控任务详情。

 |
|Address|String|http://www.aliyun.com|探测地址。

 |
|Interval|String|1|监控频率， 单位为分钟， 可选值为1， 5， 15。

 |
|IspCities| | |探测点的运营商和城市。

 |
|City|String|546|城市ID。

 |
|CityName|String|杭州市|探测点城市名称。

 |
|Isp|String|465|ISP ID，用于识别ISP。

 |
|IspName|String|阿里巴巴|ISP名称。

 |
|OptionJson|Json|\{ "http\_method": "get", "response\_content": "xxxx", "time\_out": 30000\}|扩展选项， 每一种探测类型有不同的扩展类型，CreateSiteMonitor详情中扩展选项的描述。

 |
|TaskId|String|a1ecd34a-8157-44d9-b060-14950837\*\*\*\*|任务ID。

 |
|TaskName|String|探测名称|任务名称。

 |
|TaskState|String|OK|报警规则状态。

 |
|TaskType|String|HTTP|探测类型，站点监控HTTP、PING、TCP、UDP、SMTP、POP3、DNS、FTP。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSiteMonitorAttribute
&TaskId=a1ecd34a-8157-44d9-b065-14950837****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSiteMonitorAttributeResponse>
    <Message>请求成功</Message>
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
                    <IspName>阿里巴巴</IspName>
                    <CityName>杭州市</CityName>
                    <City>546</City>
              </IspCity>
              <IspCity>
                    <Isp>465</Isp>
                    <IspName>阿里巴巴</IspName>
                    <CityName>青岛市</CityName>
                    <City>572</City>
              </IspCity>
              <IspCity>
                    <Isp>465</Isp>
                    <IspName>阿里巴巴</IspName>
                    <CityName>北京市</CityName>
                    <City>738</City>
              </IspCity>
        </IspCities>
      </SiteMonitors>
      <Success>true</Success>
      <Code>200</Code>
</DescribeSiteMonitorAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"请求成功",
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
					"IspName":"阿里巴巴",
					"CityName":"杭州市",
					"City":"546"
				},
				{
					"Isp":"465",
					"IspName":"阿里巴巴",
					"CityName":"青岛市",
					"City":"572"
				},
				{
					"Isp":"465",
					"IspName":"阿里巴巴",
					"CityName":"北京市",
					"City":"738"
				}
			]
		}
	},
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

