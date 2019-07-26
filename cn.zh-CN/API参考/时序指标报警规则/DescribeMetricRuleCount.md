# DescribeMetricRuleCount {#doc_api_Cms_DescribeMetricRuleCount .reference}

分类取得报警规则的数量。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMetricRuleCount&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeMetricRuleCount|系统规定参数。取值：DescribeMetricRuleCount。

 |
|MetricName|String|否|cpu\_total|监控项名称。可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。

 |
|Namespace|String|否|acs\_ecs\_dashboard|产品的数据命名空间，可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示成功。

 |
|Message|String|success|错误信息。

 |
|MetricRuleCount| | |各类状态的报警规则数量统计。

 |
|Alarm|Integer|5|报警状态的规则数量。

 |
|Disable|Integer|0|禁用的数量。

 |
|Nodata|Integer|0|无数据状态的规则数量。

 |
|Ok|Integer|40|正常状态的规则数量。

 |
|Total|Integer|45|报警规则总数量。

 |
|RequestId|String|FF38D33A-67C1-40EB-AB65-FAEE51EDB644|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMetricRuleCount
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMetricRuleCountResponse>
      <Success>true</Success>
      <Code>200</Code>
      <RequestId>FF38D33A-67C1-40EB-AB65-FAEE51EDB644</RequestId>
      <MetricRuleCount>
            <Ok>40</Ok>
            <Disable>0</Disable>
            <Total>45</Total>
            <Nodata>0</Nodata>
            <Alarm>5</Alarm>
      </MetricRuleCount>
</DescribeMetricRuleCountResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"FF38D33A-67C1-40EB-AB65-FAEE51EDB644",
	"Success":true,
	"Code":"200",
	"MetricRuleCount":{
		"Ok":40,
		"Disable":0,
		"Nodata":0,
		"Total":45,
		"Alarm":5
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

