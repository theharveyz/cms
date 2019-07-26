# DescribeEventRuleList {#doc_api_Cms_DescribeEventRuleList .reference}

查询事件报警的列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeEventRuleList&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEventRuleList|系统规定参数。取值：DescribeEventRuleList。

 |
|GroupId|String|否|12345|应用分组ID。

 |
|NamePrefix|String|否|test|报警规则名前缀，支持模糊搜索。

 |
|PageNumber|String|否|1|当前页码，默认1。

 |
|PageSize|String|否|10|每页显示记录条数。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示成功。

 |
|EventRules| | |事件规则。

 |
|Description|String|event|规则描述。

 |
|EventPattern| | |事件规则。

 |
|EventTypeList| |Exception|事件类型

 |
|LevelList| |\["CRITICAL", "WARN", "INFO"\]|事件的等级

 CRITICAL：严重，

 WARN：警告，

 INFO：信息

 |
|NameList| |\["Agent\_Status\_Stopped"\]|事件的名称列表

 |
|Product|String|CloudMonitor|产品的名称缩写

 |
|EventType|String|SYSTEM|事件的类型， SYSTEM：系统事件， CUSTOM：自定义事件。

 |
|GroupId|String|12345|应用组ID。

 |
|Name|String|evnetNamee|规则名称。

 |
|State|String|ENABLED|启用或者禁用状态， ENABLED表示启用状态， DISABLED表示禁用状态。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|D0E6D82B-16B5-422A-8136-EE5BDC01E415|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |
|Total|Integer|21|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeEventRuleList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeEventRuleListResponse>
      <Datapoints>
            <EventRule>
                  <Name>aaabbb</Name>
                  <State>ENABLED</State>
                  <EventPattern>
                        <EventTypeList>
                              <EventTypeList>Exception</EventTypeList>
                        </EventTypeList>
                        <Product>CloudMonitor</Product>
                        <LevelList>
                              <LevelList>*</LevelList>
                        </LevelList>
                        <NameList>
                              <NameList>Alert_SendShortMessageFailed_QuotaReached</NameList>
                              <NameList>Group_AddResourcesFailed_QuotaReached</NameList>
                              <NameList>Agent_Status_Stopped</NameList>
                              <NameList>Agent_Status_Running</NameList>
                        </NameList>
                  </EventPattern>
                  <EventType>SYSTEM</EventType>
            </EventRule>
            <EventRule>
                  <Name>default_group_event_rule_3384581</Name>
                  <Description>Default group event rule</Description>
                  <State>ENABLED</State>
                  <EventPattern>
                        <Product>*</Product>
                        <LevelList>
                              <LevelList>CRITICAL</LevelList>
                              <LevelList>WARN</LevelList>
                        </LevelList>
                        <NameList>
                              <NameList>*</NameList>
                        </NameList>
                  </EventPattern>
                  <EventType>SYSTEM</EventType>
                  <GroupId>338****</GroupId>
            </EventRule>
      </Datapoints>
      <RequestId>D0E6D82B-16B5-422A-8136-EE5BDC01E415</RequestId>
      <Success>true</Success>
      <Code>200</Code>
      <Total>20</Total>
</DescribeEventRuleListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Datapoints":{
		"EventRule":[
			{
				"Name":"aaabbb",
				"State":"ENABLED",
				"EventPattern":{
					"EventTypeList":{
						"EventTypeList":[
							"Exception"
						]
					},
					"Product":"CloudMonitor",
					"LevelList":{
						"LevelList":[
							"*"
						]
					},
					"NameList":{
						"NameList":[
							"Alert_SendShortMessageFailed_QuotaReached",
							"Group_AddResourcesFailed_QuotaReached",
							"Agent_Status_Stopped",
							"Agent_Status_Running"
						]
					}
				},
				"EventType":"SYSTEM"
			},
			{
				"Name":"default_group_event_rule_3384581",
				"Description":"Default group event rule",
				"State":"ENABLED",
				"EventPattern":{
					"Product":"*",
					"LevelList":{
						"LevelList":[
							"CRITICAL",
							"WARN"
						]
					},
					"NameList":{
						"NameList":[
							"*"
						]
					}
				},
				"EventType":"SYSTEM",
				"GroupId":"338****"
			}
		]
	},
	"RequestId":"D0E6D82B-16B5-422A-8136-EE5BDC01E415",
	"Success":true,
	"Code":"200",
	"Total":20
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

