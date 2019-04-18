# DescribeEventRuleTargetList {#doc_api_Cms_DescribeEventRuleTargetList .reference}

查询指定事件报警规则的报警目标。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeEventRuleTargetList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEventRuleTargetList|系统规定参数。取值：DescribeEventRuleTargetList。

 |
|RuleName|String|是|testRule|报警规则名称。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Message|String|success|错误信息。

 |
|RequestId|String|87170bc7-e28a-4c93-b9bf-90a1dbe84736|请求ID，用于排查问题。

 |
|Code|String|200|状态码， 200表示成功。

 |
|MnsParameters| | |消息服务通知。

 |
|└Id|String|2|消息服务通知方式唯一标识。

 |
|└Queue|String|testQueue|消息队列的名称。

 |
|└Region|String|cn-hangzhou|消息服务对应的Region。

 |
|ContactParameters| | |报警联系人组通知方式。

 |
|└ContactGroupName|String|默认告警通知组|报警联系人组的名称。

 |
|└Id|String|1|报警联系人组通知方式唯一标识。

 |
|└Level|String|3|通知级别，取值为2， 3，4。国际站没有电话、短信、旺旺通知方式。

 -   2：电话、短信、钉钉、旺旺、Email
-   3：短信、钉钉、旺旺、Email
-   4：钉钉、Email

 |
|FcParameters| | |函数计算通知。

 |
|└FunctionName|String|fcTest1|函数名称。

 |
|└Id|String|3|函数服务通知方式唯一标识。

 |
|└Region|String|cn-qingdao|函数计算服务对应的region。

 |
|└ServiceName|String|service1|函数服务的名称。

 |
|SlsParameters| | |日志服务（SLS）通知方式。

 |
|└Id|String|4|日志服务通知方式唯一标识。

 |
|└LogStore|String|logstore\_test|LogStore名称。

 |
|└Project|String|project\_test|Project名称。

 |
|└Region|String|cn-hangzhou|project对应的Region。

 |
|WebhookParameters| | |URL回调通知方式。

 |
|└Id|String|5|URL回调通知方式唯一标识。

 |
|└Method|String|GET|HTTP回调的请求方法，目前支持GET/POST方法。

 |
|└Protocol|String|http|协议类型。

 |
|└Url|String|http://www.aliyun.com|回调的URL地址。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeEventRuleTargetList
&RuleName=testRule
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeEventRuleTargetListResponse>
  <SlsParameters>
    <SlsParameter>
      <Region>cn-hangzhou</Region>
      <Project>project-test</Project>
      <Id>4</Id>
      <LogStore>logstore-test</LogStore>
    </SlsParameter>
  </SlsParameters>
  <ContactParameters>
    <ContactParameter>
      <Id>1</Id>
      <Level>3</Level>
      <ContactGroupName>aaaaa</ContactGroupName>
    </ContactParameter>
  </ContactParameters>
  <MnsParameters>
    <MnsParameter>
      <Region>cn-hangzhou</Region>
      <Id>2</Id>
      <Queue>ECS-ops</Queue>
    </MnsParameter>
  </MnsParameters>
  <RequestId>174513e9-7da9-4f05-9cae-98f9959e9379</RequestId>
  <ParameterCount>1</ParameterCount>
  <FcParameters>
    <FCParameter>
      <Region>cn-hangzhou</Region>
      <ServiceName>MetricService-1</ServiceName>
      <FunctionName>MetricFunction-0</FunctionName>
      <Id>3</Id>
    </FCParameter>
  </FcParameters>
  <Code>200</Code>
</DescribeEventRuleTargetListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SlsParameters":{
		"SlsParameter":[
			{
				"Region":"cn-hangzhou",
				"Id":"4",
				"Project":"project-test",
				"LogStore":"logstore-test"
			}
		]
	},
	"ContactParameters":{
		"ContactParameter":[
			{
				"Level":"3",
				"Id":"1",
				"ContactGroupName":"aaaaa"
			}
		]
	},
	"MnsParameters":{
		"MnsParameter":[
			{
				"Region":"cn-hangzhou",
				"Queue":"ECS-ops",
				"Id":"2"
			}
		]
	},
	"RequestId":"174513e9-7da9-4f05-9cae-98f9959e9379",
	"ParameterCount":1,
	"FcParameters":{
		"FCParameter":[
			{
				"Region":"cn-hangzhou",
				"ServiceName":"MetricService-1",
				"FunctionName":"MetricFunction-0",
				"Id":"3"
			}
		]
	},
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

