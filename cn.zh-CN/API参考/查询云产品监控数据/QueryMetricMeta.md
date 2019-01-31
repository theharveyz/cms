# QueryMetricMeta {#doc_api_987981 .reference}

查询云监控开放的时序类监控项的监控项描述。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=QueryMetricMeta)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Project|String|是|acs\_ecs\_dashboard|指标所属的Project，按等于匹配

 |
|Action|String|否|QueryMetricMeta|系统规定参数，取值：QueryMetricMeta

 |
|Labels|String|否|\[\{\\"name\\":\\"alertUnit\\",\\"value\\":\\"%\\"\}\]|根据标签过滤，格式`[{"name":"标签名","value":"标签值"},{"name":"标签名","value":"标签值"}]`。

 已有的标签name说明：

 -   MetricCategory：监控项分类的描述
-   alertEnable：是否需要报警
-   alertUnit：建议的报警单位
-   unitFactor：单位转换系数
-   minAlertPeriod：最小报警周期
-   productCategory：产品类型分类

 |
|Metric|String|否|CPUUtilization|指标名，按等于匹配

 |
|PageNumber|Integer|否|1|分页参数，默认1

 |
|PageSize|Integer|否|30|每页最大数量，默认30

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ErrorCode|String|200|状态码，200为成功，非200为失败

 |
|ErrorMessage|String|Success|错误码消息

 |
|RequestId|String|0CCE0AF0-053C-4B13-A583-DC9A85785D49|用于跟踪

 |
|Resources| | |返回的metric meta列表

 |
|└Description|String|ECS.CPUUtilization|监控项的描述

 |
|└Dimensions|String|instanceId|监控项的Dimensions，多级用英文逗号分隔，例如：userId,instanceId

 |
|└Labels|String|\[\{\\"name\\":\\"alertUnit\\",\\"value\\":\\"%\\"\},\{\\"name\\":\\"alertDefault\\",\\"value\\":\\"80\\"\},\{\\"name\\":\\"minAlertPeriod\\",\\"value\\":\\"60\\"\},\{\\"name\\":\\"metricCategory\\",\\"value\\":\\"instanceId\\"\},\{\\"name\\":\\"is\_alarm\\",\\"value\\":\\"true\\"\}\]"|监控项的标签，是一个json的string\{"name":"标签名","value":"标签的值"\}，可以是多个，name可以重复 已有的标签name说明： metricCategory：指标分类 alertEnable：是否可以报警 alertUnit：报警单位 unitFactor：单位转换系数 minAlertPeriod：最小报警周期 productCategory：产品

 |
|└Metric|String|CPUUtilization|监控项名称

 |
|└Periods|String|60,300|监控项的所有统计周期，多个用英文逗号分隔：15,60,900

 |
|└Project|String|acs\_ecs\_dashboard|监控项的Project名称，用于查询监控数据

 |
|└Statistics|String|Average,Minimum,Maximum|统计方法，多个用英文逗号分隔，例如：Maximum,Minimum,Average

 |
|└Unit|String|%|监控项的单位

 |
|Success|Boolean|true|用于标识本次调用是否成功

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=QueryMetricMeta
&Project=acs_ecs_dashboard
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryMetricMetaResponse>
  <RequestId>60498C25-B5AE-48CD-B03D-207011F21E8A</RequestId>
  <ErrorCode>200</ErrorCode>
  <Success>true</Success>
  <Resources>
    <Resource>
      <Description/>
      <Statistics>Average</Statistics>
      <Labels>[{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"role"},{"name":"is_alarm","value":"true"}]</Labels>
      <Metric>ActiveApplications</Metric>
      <Dimensions>clusterId,role</Dimensions>
      <Project>acs_hbase</Project>
      <Periods>30,300</Periods>
    </Resource>
    <Resource>
      <Description/>
      <Statistics>Average</Statistics>
      <Labels>[{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"role"},{"name":"is_alarm","value":"true"}]</Labels>
      <Metric>ActiveApplications</Metric>
      <Dimensions>clusterId,role</Dimensions>
      <Project>acs_emr</Project>
      <Periods>30,300,3600</Periods>
    </Resource>
    <Resource>
      <Description>端口当前活跃连接数</Description>
      <Statistics>Average,Minimum,Maximum</Statistics>
      <Labels>[{"name":"alertUnit","value":"Count"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"port"},{"name":"is_alarm","value":"true"}]</Labels>
      <Metric>ActiveConnection</Metric>
      <Dimensions>instanceId,port,protocol</Dimensions>
      <Project>acs_slb_dashboard</Project>
      <Periods>60,300</Periods>
      <Unit>Count</Unit>
    </Resource>
    <Resource>
      <Description>高防IP活跃并发连接</Description>
      <Statistics>Maximum</Statistics>
      <Labels>[{"name":"alertUnit","value":"count"},{"name":"minAlertPeriod","value":"60"}]</Labels>
      <Metric>ActiveConnection</Metric>
      <Dimensions>instanceId,ip</Dimensions>
      <Project>acs_ddos</Project>
      <Periods>30,60,300</Periods>
      <Unit>count</Unit>
    </Resource>
    <Resource>
      <Description>活跃消息数</Description>
      <Statistics>Average,Minimum,Maximum</Statistics>
      <Labels>[{"name":"alertUnit","value":"Count"},{"name":"minAlertPeriod","value":"300"},{"name":"metricCategory","value":"queue"},{"name":"is_alarm","value":"true"}]</Labels>
      <Metric>ActiveMessages</Metric>
      <Dimensions>region,queue</Dimensions>
      <Project>acs_mns_new</Project>
      <Periods>300</Periods>
      <Unit>Count</Unit>
    </Resource>
  </Resources>
</QueryMetricMetaResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"60498C25-B5AE-48CD-B03D-207011F21E8A",
	"Success":true,
	"ErrorCode":200,
	"Resources":{
		"Resource":[
			{
				"Description":"",
				"Statistics":"Average",
				"Metric":"ActiveApplications",
				"Labels":"[{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"role\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"clusterId,role",
				"Project":"acs_hbase",
				"Periods":"30,300"
			},
			{
				"Description":"",
				"Statistics":"Average",
				"Metric":"ActiveApplications",
				"Labels":"[{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"role\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"clusterId,role",
				"Project":"acs_emr",
				"Periods":"30,300,3600"
			},
			{
				"Description":"端口当前活跃连接数",
				"Statistics":"Average,Minimum,Maximum",
				"Metric":"ActiveConnection",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"port\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"instanceId,port,protocol",
				"Project":"acs_slb_dashboard",
				"Periods":"60,300",
				"Unit":"Count"
			},
			{
				"Description":"高防IP活跃并发连接",
				"Statistics":"Maximum",
				"Metric":"ActiveConnection",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"}]",
				"Dimensions":"instanceId,ip",
				"Project":"acs_ddos",
				"Periods":"30,60,300",
				"Unit":"count"
			},
			{
				"Description":"活跃消息数",
				"Statistics":"Average,Minimum,Maximum",
				"Metric":"ActiveMessages",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Count\"},{\"name\":\"minAlertPeriod\",\"value\":\"300\"},{\"name\":\"metricCategory\",\"value\":\"queue\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"region,queue",
				"Project":"acs_mns_new",
				"Periods":"300",
				"Unit":"Count"
			}
		]
	}
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

