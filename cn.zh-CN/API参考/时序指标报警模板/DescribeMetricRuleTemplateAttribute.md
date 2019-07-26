# DescribeMetricRuleTemplateAttribute {#doc_api_Cms_DescribeMetricRuleTemplateAttribute .reference}

查询报警模板的详情。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleTemplateAttribute&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeMetricRuleTemplateAttribute|系统规定参数。取值：DescribeMetricRuleTemplateAttribute。

 |
|Name|String|否|我的模板|报警模板的名称。

 |
|TemplateId|String|否|123|报警模板的ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码， 200表示成功。

 |
|RequestId|String|C14F2566-B4AC-4C3E-AC7D-0A1D16CF33DE|请求ID，用于排查问题。

 |
|Message|String|success|错误信息。

 |
|Resource| | |报警模板的详情。

 |
|AlertTemplates| | |报警模板。

 |
|Category|String|ecs|云产品缩写。

 |
|Escalations| | |阈值及报警级别

 |
|Critical| | |Critical报警级别。

 |
|ComparisonOperator|String|GreaterThanOrEqualToThreshold|Critical级别阈值比较符符：

 -   GreaterThanOrEqualToThreshold:大于等于,
-   GreaterThanThreshold:大于,
-   LessThanOrEqualToThreshold:小于等于,
-   LessThanThreshold:小于,
-   NotEqualToThreshold:不等,
-   GreaterThanYesterday:同比昨天时间上涨,
-   LessThanYesterday:同比昨天时间下降,
-   GreaterThanLastWeek:同比上周同一时间上涨,
-   LessThanLastWeek:同比上周同一时间下降,
-   GreaterThanLastPeriod:环比上周期上涨,
-   LessThanLastPeriod:环比上周期下降

 |
|Statistics|String|Average|Critical级别统计方法。

 |
|Threshold|String|90|Critical级别阈值。

 |
|Times|Integer|3|Critical重试次数。

 |
|Info| | |Info报警级别。

 |
|ComparisonOperator|String|GreaterThanOrEqualToThreshold|Info级别阈值比较符符：

 -   GreaterThanOrEqualToThreshold:大于等于,
-   GreaterThanThreshold:大于,
-   LessThanOrEqualToThreshold:小于等于,
-   LessThanThreshold:小于,
-   NotEqualToThreshold:不等,
-   GreaterThanYesterday:同比昨天时间上涨,
-   LessThanYesterday:同比昨天时间下降,
-   GreaterThanLastWeek:同比上周同一时间上涨,
-   LessThanLastWeek:同比上周同一时间下降,
-   GreaterThanLastPeriod:环比上周期上涨,
-   LessThanLastPeriod:环比上周期下降

 |
|Statistics|String|Average|Info级别统计方法。

 |
|Threshold|String|90|Info级别阈值。

 |
|Times|Integer|3|Info级别重试次数。

 |
|Warn| | |Warn报警级别。

 |
|ComparisonOperator|String|GreaterThanOrEqualToThreshold|Warn级别阈值比较符符：

 -   GreaterThanOrEqualToThreshold:大于等于,
-   GreaterThanThreshold:大于,
-   LessThanOrEqualToThreshold:小于等于,
-   LessThanThreshold:小于,
-   NotEqualToThreshold:不等,
-   GreaterThanYesterday:同比昨天时间上涨,
-   LessThanYesterday:同比昨天时间下降,
-   GreaterThanLastWeek:同比上周同一时间上涨,
-   LessThanLastWeek:同比上周同一时间下降,
-   GreaterThanLastPeriod:环比上周期上涨,
-   LessThanLastPeriod:环比上周期下降

 |
|Statistics|String|Average|Warn级别统计方法。

 |
|Threshold|String|90|Warn级别阈值。

 |
|Times|Integer|3|Warn级别重试次数。

 |
|MetricName|String|cpu\_total|监控项的名称。

 |
|Namespace|String|acs\_ecs\_dashboard|产品的namespace，用于区分产品。

 |
|RuleName|String|我的报警规则|生成报警规则的名称。

 |
|Selector|String|\{"disk":"/"\}|报警维度的扩展选项。

 |
|Description|String|报警模板描述|报警模板的描述信息。

 |
|Name|String|cpu监控模板|报警模板的名称。

 |
|RestVersion|String|0|模板的版本。

 |
|TemplateId|String|123|报警模板ID。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMetricRuleTemplateAttribute
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMetricRuleTemplateAttributeResponse>
      <Resource>
            <RestVersion>0</RestVersion>
            <Name>nametest</Name>
            <Description>nametestDesc</Description>
            <AlertTemplates>
                  <AlertTemplate>
                        <Category>ecs</Category>
                        <MetricName>cpu_total</MetricName>
                        <Namespace>acs_ecs_dashboard</Namespace>
                        <RuleName>cpu_total</RuleName>
                        <Escalations>
                              <Critical></Critical>
                              <Info></Info>
                              <Warn>
                                    <Statistics>Average</Statistics>
                                    <Threshold>90.0</Threshold>
                                    <Times>1</Times>
                                    <ComparisonOperator>GreaterThanOrEqualToThreshold</ComparisonOperator>
                              </Warn>
                        </Escalations>
                  </AlertTemplate>
                  <AlertTemplate>
                        <Category>rds</Category>
                        <MetricName>AvgLogSize</MetricName>
                        <Namespace>acs_rds_dashboard</Namespace>
                        <RuleName>AvgLogSize</RuleName>
                        <Escalations>
                              <Critical></Critical>
                              <Info></Info>
                              <Warn>
                                    <Statistics>Average</Statistics>
                                    <Threshold>12.0</Threshold>
                                    <Times>1</Times>
                                    <ComparisonOperator>GreaterThanOrEqualToThreshold</ComparisonOperator>
                              </Warn>
                        </Escalations>
                  </AlertTemplate>
            </AlertTemplates>
            <TemplateId>45</TemplateId>
      </Resource>
      <RequestId>C14F2566-B4AC-4C3E-AC7D-0A1D16CF33DE</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</DescribeMetricRuleTemplateAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Resource":{
		"Name":"nametest",
		"RestVersion":0,
		"Description":"nametestDesc",
		"AlertTemplates":{
			"AlertTemplate":[
				{
					"Category":"ecs",
					"MetricName":"cpu_total",
					"Namespace":"acs_ecs_dashboard",
					"RuleName":"cpu_total",
					"Escalations":{
						"Critical":{},
						"Info":{},
						"Warn":{
							"Statistics":"Average",
							"Threshold":"90.0",
							"Times":1,
							"ComparisonOperator":"GreaterThanOrEqualToThreshold"
						}
					}
				},
				{
					"Category":"rds",
					"MetricName":"AvgLogSize",
					"Namespace":"acs_rds_dashboard",
					"RuleName":"AvgLogSize",
					"Escalations":{
						"Critical":{},
						"Info":{},
						"Warn":{
							"Statistics":"Average",
							"Threshold":"12.0",
							"Times":1,
							"ComparisonOperator":"GreaterThanOrEqualToThreshold"
						}
					}
				}
			]
		},
		"TemplateId":45
	},
	"RequestId":"C14F2566-B4AC-4C3E-AC7D-0A1D16CF33DE",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

