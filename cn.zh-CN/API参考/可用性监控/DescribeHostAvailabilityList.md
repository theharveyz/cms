# DescribeHostAvailabilityList {#doc_api_Cms_DescribeHostAvailabilityList .reference}

查询可用性监控任务列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeHostAvailabilityList&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeHostAvailabilityList|系统规定参数。取值：DescribeHostAvailabilityList。

 |
|GroupId|Long|否|12345|应用分组ID。

 |
|Id|Long|否|12346|任务ID。

 |
|PageNumber|Integer|否|1|页码。

 |
|PageSize|Integer|否|10|每页记录条数。

 |
|TaskName|String|否|我的探测|任务名称。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|CE26797C-1094-47E6-B651-73AA888F5873|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |
|TaskList| | |任务列表。

 |
|AlertConfig| | |报警规则配置。

 |
|EndTime|Integer|23|结束时间。

 |
|EscalationList| | |报警的触发条件。

 |
|Aggregate|String|Value|统计方法，不同的监控项有不同的统计方法：

 -   HttpStatus：Value
-   HttpLatency：Average
-   TelnetStatus：Value
-   TelnetLatency：Average
-   PingLostRate：Average

 状态码类的，统计方法是原始值（Value），延时时间或者丢包率都用平均值（Average）。

 |
|MetricName|String|HttpStatus|-   HttpStatus\(HTTP状态码\)
-   HttpLatency\(HTTP等待时间\)
-   TelnetStatus\(TELNET状态码\)
-   TelnetLatency\(TELNET等待时间\)
-   PingLostRate\(PING丢包率） \)

 |
|Operator|String|\>|比较符号，如`>、>=、<、<=、=`。

 |
|Times|String|2|连续几个周期超过阈值，这个指的是周期数。

 |
|Value|String|99|监控阈值。

 |
|NotifyType|Integer|1|通知类型：

 -   2：电话+短信+邮件+钉钉机器人
-   1：短信+邮件+钉钉机器人
-   0：邮件+钉钉机器人

 |
|SilenceTime|Integer|86400|通道沉默时间，单位是秒，默认86400（1天）。

 |
|StartTime|Integer|0|起始时间，单位是小时，0表示00:00。

 |
|WebHook|String|http://www.aliyun.com|URL回调地址。

 |
|Disabled|Boolean|false|是否禁用。

 |
|GroupId|Long|12345|应用分组ID。

 |
|GroupName|String|应用组名|应用分组名称。

 |
|Id|Long|123|任务ID。

 |
|Instances| |i-a2d5q7pm3f123y456|发起探测的ecs实例列表。

 |
|TaskName|String|我的内网探测|任务名称。

 |
|TaskOption| | |任务的参数选项。

 |
|HttpKeyword|String|ok|HTTP探测类型匹配响应内容。

 |
|HttpMethod|String|GET|HTTP探测类型的方法，目前支持GET、POST、HEAD 3种方法。

 |
|HttpNegative|Boolean|true|-   true：包含内容则报警
-   false：不包含内容则报警

 |
|HttpResponseCharset|String|UTF-8|HTTP探测类型响应字符集。

 |
|HttpURI|String|http://www.aliyun.com|HTTP探测类型的探测URI地址。

 |
|TelnetOrPingHost|String|ssh.aliyun.com|如果探测任务是PING或者TELNET，此处写入要探测的域名或者地址。

 |
|TaskScope|String|GROUP|任务的范围，目前支持的3种范围：

 -   INSTANCE：任务作用在指定\(1或多个\)实例上。
-   GROUP：任务作用在整个组上\(组内所有实例\)。
-   GROUP\_SPEC\_INSTANCEUP\_SPEC\_INSTANCE：任务作用在组内指定\(1或多个\)实例上 。

 |
|TaskType|String|HTTP|目前支持的任务类型有PING、TELNET、HTTP 3种类型。

 |
|Total|Integer|12|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeHostAvailabilityList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeHostAvailabilityListResponse>
   <TaskList>
            <NodeTaskConfig>
                  <GroupName>我的应用组</GroupName>
                  <TaskOption>
                        <HttpMethod>GET</HttpMethod>
                        <HttpURI>http://www.aliyun.com</HttpURI>
                  </TaskOption>
                  <Disabled>false</Disabled>
                  <Instances>
                        <Instance>i-a2d5q7pm3f123y***</Instance>
                        <Instance>i-a2d5q7pm3f123x***</Instance>
                  </Instances>
                  <Id>123345</Id>
                  <AlertConfig>
                        <EscalationList>
                              <escalationList>
                                    <Value>400</Value>
                                    <MetricName>HttpStatus</MetricName>
                                    <Operator>&gt;</Operator>
                                    <Times>3</Times>
                                    <Aggregate>Value</Aggregate>
                              </escalationList>
                              <escalationList>
                                    <Value>500</Value>
                                    <MetricName>HttpLatency</MetricName>
                                    <Operator>&gt;</Operator>
                                    <Times>3</Times>
                                    <Aggregate>Average</Aggregate>
                              </escalationList>
                        </EscalationList>
                        <SilenceTime>86400</SilenceTime>
                        <NotifyType>1</NotifyType>
                        <EndTime>24</EndTime>
                        <StartTime>0</StartTime>
                  </AlertConfig>
                  <TaskType>HTTP</TaskType>
                  <TaskName>我的内网探测任务</TaskName>
                  <GroupId>12345</GroupId>
                  <TaskScope>GROUP</TaskScope>
            </NodeTaskConfig>
      </TaskList>
      <RequestId>CE26797C-1094-47E6-B651-73AA888F5873</RequestId>
      <Success>true</Success>
      <Code>200</Code>
      <Total>3</Total>
</DescribeHostAvailabilityListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TaskList":{
		"NodeTaskConfig":[
			{
				"GroupName":"我的应用组",
				"Disabled":false,
				"TaskOption":{
					"HttpMethod":"GET",
					"HttpURI":"http://www.aliyun.com"
				},
				"Instances":{
					"Instance":[
						"i-a2d5q7pm3f123y***",
						"i-a2d5q7pm3f123x***"
					]
				},
				"Id":123345,
				"AlertConfig":{
					"EscalationList":{
						"escalationList":[
							{
								"Value":"400",
								"MetricName":"HttpStatus",
								"Operator":">",
								"Times":3,
								"Aggregate":"Value"
							},
							{
								"Value":"500",
								"MetricName":"HttpLatency",
								"Operator":">",
								"Times":3,
								"Aggregate":"Average"
							}
						]
					},
					"NotifyType":1,
					"SilenceTime":86400,
					"EndTime":24,
					"StartTime":0
				},
				"TaskName":"我的内网探测任务",
				"TaskType":"HTTP",
				"TaskScope":"GROUP",
				"GroupId":12345
			}
		]
	},
	"RequestId":"CE26797C-1094-47E6-B651-73AA888F5873",
	"Success":true,
	"Code":200,
	"Total":3
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

