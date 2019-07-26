# DescribeEventRuleAttribute {#doc_api_Cms_DescribeEventRuleAttribute .reference}

查询指定规则的详情。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeEventRuleAttribute&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEventRuleAttribute|系统规定参数。取值：DescribeEventRuleAttribute。

 |
|RuleName|String|是|testRule|报警规则的名称。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|9AA3F210-C03D-4C86-8DB6-21C84FF692A1|请求ID，用于排查问题。

 |
|Result| | |报警规则的详情。

 |
|Description|String|这是一个事件监控|规则的描述信息。

 |
|EventPattern| | |事件模式，用于描述这个事件的触发条件。

 |
|LevelList| |\["CRITICAL","WARN","INFO"\]|报警规则的级别， CRITICAL（严重\)、WARN\(警告\)、INFO\(信息\)。

 |
|NameList| |\*|事件名称。

 |
|Product|String|CloudMonitor|产品名称。

 |
|StatusList| |XX|事件的状态。

 |
|EventType|String|SYSTEM|事件的类型，SYSTEM：系统事件， CUSTOM：自定义事件。

 |
|GroupId|String|123456|应用分组ID。

 |
|Name|String|eventName1|报警规则的名称。

 |
|State|String|ENABLED|报警规则状态，ENABLED：启用状态 ， DISABLED：禁用状态。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeEventRuleAttribute
&RuleName=testRule
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeEventRuleAttributeResponse>
      <Result>
            <Name>newXXX</Name>
            <State>ENABLED</State>
            <EventPattern>
                  <Product>CloudMonitor</Product>
                  <LevelList>
                        <LevelList>CRITICAL</LevelList>
                        <LevelList>WARN</LevelList>
                        <LevelList>INFO</LevelList>
                  </LevelList>
                  <NameList>
                        <NameList>Group_AddResourcesFailed_QuotaReached</NameList>
                        <NameList>Agent_Status_Stopped</NameList>
                        <NameList>Agent_Status_Running</NameList>
                  </NameList>
            </EventPattern>
            <EventType>SYSTEM</EventType>
      </Result>
      <RequestId>E3E23D87-4AA7-4F1B-94DE-827D84661F64</RequestId>
      <Success>true</Success>
      <Code>200</Code>   
</DescribeEventRuleAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Result":{
		"Name":"newXXX",
		"State":"ENABLED",
		"EventPattern":{
			"Product":"CloudMonitor",
			"LevelList":{
				"LevelList":[
					"CRITICAL",
					"WARN",
					"INFO"
				]
			},
			"NameList":{
				"NameList":[
					"Group_AddResourcesFailed_QuotaReached",
					"Agent_Status_Stopped",
					"Agent_Status_Running"
				]
			}
		},
		"EventType":"SYSTEM"
	},
	"RequestId":"E3E23D87-4AA7-4F1B-94DE-827D84661F64",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

