# CreateMetricRuleTemplate {#doc_api_Cms_CreateMetricRuleTemplate .reference}

创建报警规则模板。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=CreateMetricRuleTemplate)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Name|String|是|我的报警模板|报警规则模板名称。

 |
|Action|String|否|CreateMetricRuleTemplate|系统规定参数。取值：CreateMetricRuleTemplate。

 |
|Description|String|否|模板描述|报警规则描述信息。

 |
|AlertTemplates.N.MetricName|String|否|cpu\_total|监控项名称。可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。N 的取值范围为 1~200。

 |
|AlertTemplates.N.RuleName|String|否|我的CPU监控|报警规则的名称。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Category|String|否|ecs|产品名称或者产品规格缩写，如下：

 -   ECS（包括阿里云和非阿里云主机），
-   RDS（云数据库RDS版），
-   ADS（分析型数据库），
-   SLB（负载均衡），
-   VPC（弹性IP），
-   APIGATEWAY（API网关），
-   CDN，
-   CS（容器服务Swarm版），
-   DCDN（全站加速），
-   DDOS，
-   EIP（弹性公网IP），
-   ELASTICSEARCH，
-   EMR（E-MapReduce），
-   ESS（弹性伸缩），
-   HBASE，
-   IOT\_EDGE（iot边缘计算），
-   K8S\_POD（k8s pod），
-   KVSTORE\_SHARDING（Redis集群版），
-   KVSTORE\_SPLITRW（Redis读写分离版），
-   KVSTORE\_STANDARD（Redis标准版），
-   MEMCACHE，
-   MNS（消息服务），
-   MONGODB（MongoDB 副本实例），
-   MONGODB\_CLUSTER（MongoDB集群版本），
-   MONGODB\_SHARDING（MongoDB分片集群），
-   MQ\_TOPIC（消息服务TOPIC），
-   OCS（旧版云数据库Memcache），
-   OPENSEARCH（开放搜索），
-   OSS（对象存储OSS），
-   POLARDB，
-   PETADATA（HybridDB for MySQL），
-   SCDN（安全加速），
-   SHAREBANDWIDTHPACKAGES（共享带宽包），
-   SLS（日志服务），
-   VPN（VPN网关\)。

 N 的取值范围为 1~200。

 |
|AlertTemplates.N.Namespace|String|否|acs\_ecs\_dashboard|产品的数据命名空间，可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Period|Integer|否|60|监控数据的聚合周期，单位秒。默认取值为监控项对应的最小频率，通常不需要指定。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Selector|String|否|\{"disk":"/"\}|扩展字段选项，例如要应用一个组下所有实例的根分区，这里可以写\{"disk":"/"\}。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Critical.Statistics|String|否|Average|Critical级别统计方法。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Critical.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Critical级别阈值比较符，可以选择如下：

 -   GreaterThanOrEqualToThreshold:大于等于
-   GreaterThanThreshold:大于
-   LessThanOrEqualToThreshold:小于等于
-   LessThanThreshold:小于
-   NotEqualToThreshold:不等
-   GreaterThanYesterday:同比昨天时间上涨
-   LessThanYesterday:同比昨天时间下降
-   GreaterThanLastWeek:同比上周同一时间上涨
-   LessThanLastWeek:同比上周同一时间下降
-   GreaterThanLastPeriod:环比上周期上涨
-   LessThanLastPeriod:环比上周期下降

 |
|AlertTemplates.N.Escalations.Critical.Threshold|String|否|90|Critical级别阈值。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Critical.Times|Integer|否|3|Critical级别连续出现次数才出触发报警。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Warn.Statistics|String|否|Average|Warn级别统计方法，不同的metric在创建的时候有不同的统计方法,详细参考MetricMeta相关接口的描述信息。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Warn.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Wran级别阈值比较符，可以选择如下：

 -   GreaterThanOrEqualToThreshold:大于等于
-   GreaterThanThreshold:大于
-   LessThanOrEqualToThreshold:小于等于
-   LessThanThreshold:小于
-   NotEqualToThreshold:不等
-   GreaterThanYesterday:同比昨天时间上涨
-   LessThanYesterday:同比昨天时间下降
-   GreaterThanLastWeek:同比上周同一时间上涨
-   LessThanLastWeek:同比上周同一时间下降
-   GreaterThanLastPeriod:环比上周期上涨
-   LessThanLastPeriod:环比上周期下降

 N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Warn.Threshold|String|否|90|Warn级别阈值。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Warn.Times|Integer|否|3|Warn级别连续出现次数才出触发报警。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Info.Statistics|String|否|Average|Info级别统计方法，不同的metric在创建的时候有不同的统计方法,详细参考MetricMeta相关接口的描述信息。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Info.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Info级别阈值比较符，可以选择如下：

 -   GreaterThanOrEqualToThreshold:大于等于
-   GreaterThanThreshold:大于
-   LessThanOrEqualToThreshold:小于等于
-   LessThanThreshold:小于
-   NotEqualToThreshold:不等
-   GreaterThanYesterday:同比昨天时间上涨
-   LessThanYesterday:同比昨天时间下降
-   GreaterThanLastWeek:同比上周同一时间上涨
-   LessThanLastWeek:同比上周同一时间下降
-   GreaterThanLastPeriod:环比上周期上涨
-   LessThanLastPeriod:环比上周期下降

 N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Info.Threshold|String|否|90|Info级别阈值。N 的取值范围为 1~200。

 |
|AlertTemplates.N.Escalations.Info.Times|Integer|否|3|Info级别连续出现次数才出触发报警。N 的取值范围为 1~200。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码， 200表示成功。

 |
|Id|Long|12345|报警模板ID。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|9763ED1A-4D09-41BF-851E-310421750204|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateMetricRuleTemplate
&Name=我的报警模板
&AlertTemplates.1.MetricName=cpu_total
&AlertTemplates.1.RuleName=我的CPU监控
&AlertTemplates.1.Category=ecs
&AlertTemplates.1.1amespace=acs_ecs_dashboard
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateMetricRuleTemplateResponse>
  <RequestId>9763ED1A-4D09-41BF-851E-310421750204</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</CreateMetricRuleTemplateResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"9763ED1A-4D09-41BF-851E-310421750204",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

