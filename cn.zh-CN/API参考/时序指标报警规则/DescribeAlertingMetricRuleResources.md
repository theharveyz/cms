# DescribeAlertingMetricRuleResources {#doc_api_Cms_DescribeAlertingMetricRuleResources .reference}

查询一个报警规则下正在报警的资源。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeAlertingMetricRuleResources&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeAlertingMetricRuleResources|系统规定参数。取值：DescribeAlertingMetricRuleResources。

 |
|GroupId|String|是|123456|应用分组ID。

 |
|RuleId|String|是|alarm-uuid1234abc\*\*\*\*|报警规则的ID。GroupId字段和RuleId字段至少需要填写1个字段，2个都填写时，查询同时满足两种查询条件。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|9B868619-77B4-4623-AD64-6181EA7CF8FA|请求ID，用于排查问题

 |
|Resources| | |报警规则的资源列表。

 |
|Enable|String|true|报警规则的启用状态。

 |
|GroupId|String|123456|如果报警规则关联到一个应用分组下，此处显示应用分组的ID。

 |
|LastAlertTime|String|1554718182000|最后一次触发报警的时间。

 |
|LastModifyTime|String|1554723762000|最后一次修改的时间。

 |
|MetricValues|String|\{"timestamp":1554723720000,"Value":631\}|触发报警时的监控值，是一个json字符串，不同的监控项，这里的监控值的描述会不同。

 |
|Resource|String|userId=177541323192\*\*\*\*,taskId=3\*\*\*\*,instanceId=i-bp1a0v6yzqrms01k\*\*\*\*|需要报警的资源。

 |
|RetryTimes|String|3|重试次数。

 |
|RuleId|String|alerRule1\*\*\*\*|报警规则ID。

 |
|RuleName|String|cpuAlert|报警规则名称。

 |
|StartTime|String|1545901080000|资源被关联到报警规则的时间。

 |
|Threshold|String|90|报警阈值。

 |
|Success|Boolean|true|是否成功。

 |
|Total|Integer|2|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeAlertingMetricRuleResources
&GroupId=123456
&RuleId=alarm-uuid1234abc****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAlertingMetricRuleResourcesResponse>
      <Total>1</Total>
      <Resources>
        <Resource>
              <Enable>true</Enable>
              <Resource>userId=12****,instanceId=i-bp1a012****</Resource>
              <RuleId>alerRuleId****</RuleId>
              <RetryTimes>3</RetryTimes>
              <LastAlertTime>1554718182000</LastAlertTime>
              <MetricValues>{"timestamp":1554723720000,"Value":631}</MetricValues>
              <LastModifyTime>1554723762000</LastModifyTime>
              <StartTime>1545901080000</StartTime>
              <RuleName>ruleId</RuleName>
              <Threshold>400</Threshold>
              <GroupId>33488</GroupId>
        </Resource>
      </Resources>
      <Success>true</Success>
</DescribeAlertingMetricRuleResourcesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Success":true,
	"Total":1,
	"Resources":{
		"Resource":[
			{
				"LastAlertTime":1554718182000,
				"Resource":"userId=12****,instanceId=i-bp1a012****",
				"Threshold":"400",
				"Enable":true,
				"LastModifyTime":1554723762000,
				"RuleId":"alerRuleId****",
				"MetricValues":"{\"timestamp\":1554723720000,\"Value\":631}",
				"RetryTimes":3,
				"StartTime":1545901080000,
				"RuleName":"ruleId",
				"GroupId":"33488"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

