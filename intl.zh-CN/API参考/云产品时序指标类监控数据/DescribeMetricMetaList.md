# DescribeMetricMetaList {#doc_api_Cms_DescribeMetricMetaList .reference}

查询云监控开放的时序类监控项的监控项描述。

通常配合查询监控数据接口DescribeMetricList、DescribeMetricLast 等一起使用。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricMetaList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Namespace|String|是|acs\_ecs\_dashboard|指标所属的Namespace，用于区分每个产品配置。

 |
|Action|String|否|DescribeMetricMetaList|系统规定参数，取值：DescribeMetricMetaList

 |
|Labels|String|否|\[\{"name":"alertUnit","value":"%"\}\]|根据标签过滤，格式`[{"name":"标签名","value":"标签值"},{"name":"标签名","value":"标签值"}]`。

 已有的标签name说明：

 -   MetricCategory：监控项分类的描述
-   alertEnable：是否需要报警
-   alertUnit：建议的报警单位
-   unitFactor：单位转换系数
-   minAlertPeriod：最小报警周期
-   productCategory：产品类型分类

 |
|MetricName|String|否|CPUUtilization|监控指标名，按等于匹配。

 |
|PageNumber|Integer|否|1|分页参数，默认1。

 |
|PageSize|Integer|否|30|每页最大数量，默认30。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Success|Boolean|true|是否成功。

 |
|Code|String|200|状态码，200表示成功，非200为失败。

 |
|RequestId|String|0CCE0AF0-053C-4B13-A583-DC9A85785D49|请求ID，用于排查问题

 |
|Message|String|success|错误信息。

 |
|Resources| | |具体的配置信息。

 |
|└Description|String|CPUUtilization|监控项描述。

 |
|└Dimensions|String|instanceId|监控项的Dimensions，多级用英文逗号分隔，例如：userId,instanceId。

 |
|└Labels|String|\[\{\\"name\\":\\"alertUnit\\",\\"value\\":\\"%\\"\},\{\\"name\\":\\"alertDefault\\",\\"value\\":\\"80\\"\},\{\\"name\\":\\"minAlertPeriod\\",\\"value\\":\\"60\\"\},\{\\"name\\":\\"metricCategory\\",\\"value\\":\\"instanceId\\"\},\{\\"name\\":\\"is\_alarm\\",\\"value\\":\\"true\\"\}\]"|监控项的标签，是一个json的string`[{"name":"标签名","value":"标签的值"}]`，可以是多个，name可以重复。

 已有的标签name说明：

 -   metricCategory：指标分类
-   alertEnable：是否可以报警
-   alertUnit：报警单位
-   unitFactor：单位转换系数
-   minAlertPeriod：最小报警周期
-   productCategory：产品

 |
|└MetricName|String|CPUUtilization|监控项名称。

 |
|└Namespace|String|acs\_ecs\_dashboard|用于区分产品类型，通常的命名方式为acs\_产品名。

 |
|└Periods|String|60,300|监控项的所有统计周期，多个用英文逗号分隔：15,60,900。

 |
|└Statistics|String|Average,Minimum,Maximum|统计方法，多个用英文逗号分隔，例如：Maximum,Minimum,Average。

 |
|└Unit|String|%|监控项的单位。

 |
|TotalCount|String|12|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMetricMetaList
&Namespace=acs_ecs_dashboard
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMetricMetaListResponse>
  <TotalCount>117</TotalCount>
  <RequestId>57E86AE5-B741-4510-9821-163CB35B7EE8</RequestId>
  <Success>true</Success>
  <Code>200</Code>
  <Resources>
    <Resource>
      <Description>ECS.CPUUtilization</Description>
      <Statistics>Average,Minimum,Maximum</Statistics>
      <MetricName>CPUUtilization</MetricName>
      <Labels>[{"name":"alertUnit","value":"%"},{"name":"alertDefault","value":"80"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
      <Dimensions>instanceId</Dimensions>
      <Namespace>acs_ecs_dashboard</Namespace>
      <Periods>60,300</Periods>
      <Unit>%</Unit>
    </Resource>
    <Resource>
      <Description/>
      <Statistics>Maximum,Minimum,Average</Statistics>
      <MetricName>cpu_idle</MetricName>
      <Labels>[{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
      <Dimensions>instanceId</Dimensions>
      <Namespace>acs_ecs_dashboard</Namespace>
      <Periods>15,60,900</Periods>
      <Unit>%</Unit>
    </Resource>
    <Resource>
      <Description/>
      <Statistics>Maximum,Minimum,Average</Statistics>
      <MetricName>cpu_other</MetricName>
      <Labels>[{"name":"alertUnit","value":"%"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
      <Dimensions>instanceId</Dimensions>
      <Namespace>acs_ecs_dashboard</Namespace>
      <Periods>15,60,900</Periods>
      <Unit>%</Unit>
    </Resource>
    <Resource>
      <Description/>
      <Statistics>Maximum,Minimum,Average</Statistics>
      <MetricName>cpu_system</MetricName>
      <Labels>[{"name":"alertUnit","value":"%"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
      <Dimensions>instanceId</Dimensions>
      <Namespace>acs_ecs_dashboard</Namespace>
      <Periods>15,60,900</Periods>
      <Unit>%</Unit>
    </Resource>
    <Resource>
      <Description/>
      <Statistics>Maximum,Minimum,Average</Statistics>
      <MetricName>cpu_total</MetricName>
      <Labels>[{"name":"alertUnit","value":"%"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
      <Dimensions>instanceId</Dimensions>
      <Namespace>acs_ecs_dashboard</Namespace>
      <Periods>15,60,900</Periods>
      <Unit>%</Unit>
    </Resource>
  </Resources>
</DescribeMetricMetaListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TotalCount":117,
	"RequestId":"57E86AE5-B741-4510-9821-163CB35B7EE8",
	"Success":true,
	"Code":200,
	"Resources":{
		"Resource":[
			{
				"Description":"ECS.CPUUtilization",
				"MetricName":"CPUUtilization",
				"Statistics":"Average,Minimum,Maximum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"%\"},{\"name\":\"alertDefault\",\"value\":\"80\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"instanceId",
				"Namespace":"acs_ecs_dashboard",
				"Periods":"60,300",
				"Unit":"%"
			},
			{
				"Description":"",
				"MetricName":"cpu_idle",
				"Statistics":"Maximum,Minimum,Average",
				"Labels":"[{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"instanceId",
				"Namespace":"acs_ecs_dashboard",
				"Periods":"15,60,900",
				"Unit":"%"
			},
			{
				"Description":"",
				"MetricName":"cpu_other",
				"Statistics":"Maximum,Minimum,Average",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"%\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"instanceId",
				"Namespace":"acs_ecs_dashboard",
				"Periods":"15,60,900",
				"Unit":"%"
			},
			{
				"Description":"",
				"MetricName":"cpu_system",
				"Statistics":"Maximum,Minimum,Average",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"%\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"instanceId",
				"Namespace":"acs_ecs_dashboard",
				"Periods":"15,60,900",
				"Unit":"%"
			},
			{
				"Description":"",
				"MetricName":"cpu_total",
				"Statistics":"Maximum,Minimum,Average",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"%\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"instanceId",
				"Namespace":"acs_ecs_dashboard",
				"Periods":"15,60,900",
				"Unit":"%"
			}
		]
	}
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

