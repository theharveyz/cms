# PutGroupMetricRule {#doc_api_Cms_PutGroupMetricRule .reference}

创建或者修改组报警规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=PutGroupMetricRule&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Category|String|是|ecs|产品名称或者产品规格缩写，如下：

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

 |
|GroupId|String|是|123456|应用分组ID。

 |
|MetricName|String|是|cpu\_total|监控项名称。可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。

 |
|Namespace|String|是|acs\_ecs\_dashboard|产品的数据命名空间，可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。

 |
|RuleId|String|是|bfae2ca5b4e07d2c7278772eccda169808c7b\*\*\*\*|报警规则ID，调用者统一生成，保证唯一性。

 |
|Action|String|否|PutGroupMetricRule|系统规定参数。取值：PutGroupMetricRule。

 |
|Dimensions|String|否|\[\{"instanceId":"xxxxxx"\}\]|扩展资源维度。

 |
|EffectiveInterval|String|否|00:00-23:59|报警规则的生效时间范围。

 |
|EmailSubject|String|否|出现报警|报警邮件主题。

 |
|Escalations.Critical.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Critical级别阈值比较符，可以选择如下：

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
|Escalations.Critical.Statistics|String|否|Average|Critical级别报警统计方法，每种监控项对应不同的统计方法。

 |
|Escalations.Critical.Threshold|String|否|90|Critical级别报警阈值。

 |
|Escalations.Critical.Times|Integer|否|3|Critical级别报警重试次数。

 |
|Escalations.Info.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Info级别阈值比较符，可以选择如下：

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
|Escalations.Info.Statistics|String|否|Average|Info级别报警统计方法。

 |
|Escalations.Info.Threshold|String|否|90|Info级别报警阈值。

 |
|Escalations.Info.Times|Integer|否|3|Info级别报警重试次数。

 |
|Escalations.Warn.ComparisonOperator|String|否|GreaterThanOrEqualToThreshold|Warn级别阈值比较符，可以选择如下：

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
|Escalations.Warn.Statistics|String|否|Average|Warn级别报警统计方法。

 |
|Escalations.Warn.Threshold|String|否|90|Warn级别报警阈值。

 |
|Escalations.Warn.Times|Integer|否|3|Warn级别报警重试次数。

 |
|Interval|String|否|60|报警的探测周期。

 |
|NoEffectiveInterval|String|否|00:00-05:30|报警规则非生效时间范围。

 |
|Period|String|否|60|聚合周期，单位秒。

 |
|RuleName|String|否|报警规则1|报警规则名称。

 |
|SilenceTime|Integer|否|86400|一直处于报警状态的通知沉默周期，默认86400（1天），单位s，最小1小时。

 |
|Webhook|String|否|http://www.aliyun.com|出现报警时候触发回调URL地址。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示正常，否则失败。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|461CF2CD-2FC3-4B26-8645-7BD27E7D0F1D|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=PutGroupMetricRule
&Category=ecs
&GroupId=123456
&MetricName=cpu_total
&Namespace=acs_ecs_dashboard
&RuleId=bfae2ca5b4e07d2c7278772eccda169808c7b****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PutGroupMetricRuleResponse>
      <RequestId>26C766DE-E759-4B38-8B23-28589C491CEF</RequestId>
      <Code>200</Code>
      <Success>true</Success>
</PutGroupMetricRuleResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"26C766DE-E759-4B38-8B23-28589C491CEF",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

