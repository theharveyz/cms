# CreateMetricRuleTemplate {#doc_api_Cms_CreateMetricRuleTemplate .reference}

You can call this operation to create an alert rule template.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=CreateMetricRuleTemplate) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Name|String|Yes|My alert template| The name of the alert rule template.

 |
|Action|String|No|CreateMetricRuleTemplate| The operation that you want to perform. Set the value to CreateMetricRuleTemplate.

 |
|Description|String|No|Template description| The description of the alert rule template.

 |
|AlertTemplates.N.MetricName|String|No|cpu\_total| The name of the metric. Call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~) to obtain a list of metric names. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.RuleName|String|No|My CPU monitoring| The name of the alert rule. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Category|String|No|ecs| The abbreviation of the service name. Valid values:

 -   ECS \(including Alibaba Cloud and non-Alibaba Cloud hosts\)
-   RDS \(ApsaraDB for RDS\)
-   ADS \(AnalyticDB\)
-   SLB \(Server Load Balancer\)
-   VPC \(Virtual Private Cloud\)
-   APIGATEWAY \(API Gateway\)
-   CDN
-   CS \(Container Service for Swarm\)
-   DCDN \(Dynamic Route for CDN\)
-   DDOS \(distributed denial of service\)
-   EIP \(Elastic IP\)
-   ELASTICSEARCH \(Elasticsearch\)
-   EMR \(E-MapReduce\)
-   ESS \(Auto Scaling\)
-   HBASE \(ApsaraDB for HBase\)
-   IOT\_EDGE \(IoT Edge\)
-   K8S\_POD \(k8s pod\)
-   KVSTORE\_SHARDING \(ApsaraDB RDS for Redis cluster version\)
-   KVSTORE\_SPLITRW \(ApsaraDB RDS for Redis read/write splitting version\)
-   KVSTORE\_STANDARD \(ApsaraDB RDS for Redis standard version\)
-   MEMCACHE \(ApsaraDB RDS for Memcache\)
-   MNS \(Message Service\)
-   MONGODB \(ApsaraDB RDS for MongoDB replica set instances\)
-   MONGODB\_CLUSTER \(ApsaraDB RDS for MongoDB cluster version\)
-   MONGODB\_SHARDING \(ApsaraDB RDS for MongoDB sharded clusters\)
-   MQ\_TOPIC \(Message Service topic\)
-   OCS \(original version of ApsaraDB RDS for Memcache\)
-   OPENSEARCH \(Open Search\)
-   OSS \(Object Storage Service\)
-   POLARDB \(ApsaraDB for POLARDB\)
-   PETADATA \(HybridDB for MySQL\)
-   SCDN \(Secure Content Delivery Network\)
-   SHAREBANDWIDTHPACKAGES \(shared bandwidth package\)
-   SLS \(Log Service\)
-   VPN \(VPN Gateway\)

 Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Namespace|String|No|acs\_ecs\_dashboard| The data namespace of the service. Call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~) to obtain a list of namespaces. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Period|Integer|No|60| The aggregation period of monitoring data. Unit: second. The default value is the highest frequency at which the metric is polled. Typically, you do not need to specify the minimum frequency. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Selector|String|No|\{"disk":"/"\}| The extended field. For example, a value of \{"disk":"/"\} indicates that the template is applied to the root partition of all instances in a group. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Critical.Statistics|String|No|Average| The statistical method of the threshold for critical-level alerts. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Critical.ComparisonOperator|String|No|GreaterThanOrEqualToThreshold| The comparison operator of the threshold for critical-level alerts. Valid values:

 -   GreaterThanOrEqualToThreshold
-   GreaterThanThreshold
-   LessThanOrEqualToThreshold
-   LessThanThreshold
-   NotEqualToThreshold
-   GreaterThanYesterday
-   LessThanYesterday
-   GreaterThanLastWeek
-   LessThanLastWeek
-   GreaterThanLastPeriod
-   LessThanLastPeriod

 |
|AlertTemplates.N.Escalations.Critical.Threshold|String|No|90| The threshold of critical-level alerts. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Critical.Times|Integer|No|3| The consecutive number of times for which the metric value exceeds the threshold for critical-level alerts before an alert is triggered. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Warn.Statistics|String|No|Average| The statistical method of the threshold for warn-level alerts. You can configure different statistical methods when creating metrics. Call MetricMeta to obtain the related information. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Warn.ComparisonOperator|String|No|GreaterThanOrEqualToThreshold| The comparison operator of the threshold for warn-level alerts. Valid values:

 -   GreaterThanOrEqualToThreshold
-   GreaterThanThreshold
-   LessThanOrEqualToThreshold
-   LessThanThreshold
-   NotEqualToThreshold
-   GreaterThanYesterday
-   LessThanYesterday
-   GreaterThanLastWeek
-   LessThanLastWeek
-   GreaterThanLastPeriod
-   LessThanLastPeriod

 Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Warn.Threshold|String|No|90| The threshold of warn-level alerts. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Warn.Times|Integer|No|3| The consecutive number of times for which the metric value exceeds the threshold for warn-level alerts before an alert is triggered. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Info.Statistics|String|No|Average| The statistical method of the threshold for info-level alerts. You can configure different statistical methods when creating metrics. Call MetricMeta to obtain the related information. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Info.ComparisonOperator|String|No|GreaterThanOrEqualToThreshold| The comparison operator of the threshold for info-level alerts. Valid values:

 -   GreaterThanOrEqualToThreshold
-   GreaterThanThreshold
-   LessThanOrEqualToThreshold
-   LessThanThreshold
-   NotEqualToThreshold
-   GreaterThanYesterday
-   LessThanYesterday
-   GreaterThanLastWeek
-   LessThanLastWeek
-   GreaterThanLastPeriod
-   LessThanLastPeriod

 Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Info.Threshold|String|No|90| The threshold of info-level alerts. Valid values of N: 1 to 200.

 |
|AlertTemplates.N.Escalations.Info.Times|Integer|No|3| The consecutive number of times for which the metric value exceeds the threshold for info-level alerts before an alert is triggered. Valid values of N: 1 to 200.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200| The status code. A value of 200 indicates that the call is successful.

 |
|Id|Long|12345| The ID of the alert template.

 |
|Message|String|success| The error message.

 |
|RequestId|String|9763ED1A-4D09-41BF-851E-310421750204| The request ID for troubleshooting.

 |
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateMetricRuleTemplate
&Name=My alert template
&AlertTemplates. 1.MetricName=cpu_total
&AlertTemplates. 1.RuleName=My CPU monitoring
&AlertTemplates. 1.Category=ecs
&AlertTemplates. 1.1amespace=acs_ecs_dashboard
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<CreateMetricRuleTemplateResponse>
  <RequestId>9763ED1A-4D09-41BF-851E-310421750204</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</CreateMetricRuleTemplateResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"9763ED1A-4D09-41BF-851E-310421750204",
	"Success":true,
	"Code":200
}
```

## Error codes {#section_03h_afh_mmi .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

