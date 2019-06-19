# DescribeActiveMetricRuleList {#doc_api_Cms_DescribeActiveMetricRuleList .reference}

You can call this operation to query the details list of one-click alert rules.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeActiveMetricRuleList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeActiveMetricRuleList| The operation that you want to perform. Set the value to DescribeActiveMetricRuleList.

 |
|Product|String|Yes|ecs| The name abbreviation of the service that supports one-click alert. Valid values:

 -   ecs \(Elastic Compute Service\)
-   rds \(ApsaraDB for RDS\)
-   slb \(Server Load Balancer\)
-   redis\_standard \(ApsaraDB RDS for Redis standard version\)
-   redis\_sharding \(ApsaraDB RDS for Redis cluster version\)
-   redis\_splitrw \(ApsaraDB RDS for Redis read/write splitting version\)
-   mongodb \(ApsaraDB RDS for MongoDB replica set instances\)
-   mongodb\_sharding \(ApsaraDB RDS for MongoDB sharded clusters\)
-   hbase \(ApsaraDB for HBase\)
-   elasticsearch \(Elasticsearch\)
-   opensearch \(Open Search\)

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200| The status code. A value of 200 indicates that the call is successful.

 |
|Datapoints| | | The list of alert rules.

 |
|└ComparisonOperator|String|\>| The comparison operator used in the alert rule.

 |
|└ContactGroups|String|Alibaba Cloud account alert contacts| The alert contact group.

 |
|└Enable|String|true| The status of the alert rule. Valid values:

 -   true: indicates that the alert rule is enabled.
-   false: indicates that the alert rule is disabled.

 |
|└EndTime|String|24| The end time of the alert rule effective period. A value of 23 indicates 23:59:59.

 |
|└EvaluationCount|String|3| The consecutive number of times for which the metric value exceeds the threshold before an alert is triggered.

 |
|└MetricName|String|cpu\_total| The name of the metric.

 |
|└Namespace|String|acs\_ecs\_dashboard| The data namespace of the service. For more information, call DescribeMetricMetaList or see [Preset metrics reference](~~28619~~).

 |
|└Period|String|60| The aggregation period of monitoring data. Unit: second. The default value is the highest frequency at which the metric is polled. Typically, you do not need to specify the aggregation period.

 |
|└RuleId|String|a151cd6023eacee2f0978e03863cc1697c89508\*\*\*\*| The ID of the alert rule.

 |
|└RuleName|String|SystemDefault\_acs\_rds\_dashboard\_CpuUsage| The name of the alert rule.

 |
|└SilenceTime|String|86400| The duration of the mute period during which new alerts are not sent even if the trigger conditions are met. Unit: second. Default value: 86400.

 |
|└StartTime|String|00| The start time of the alert rule effective period. A value of 00 indicates 00:00:00.

 |
|└State|String|Enable| The status of the alert rule.

 |
|└Statistics|String|Average| The statistical method.

 |
|└Threshold|String|90| The alert threshold.

 |
|└Webhook|String|http://www.aliyun.com| The callback URL.

 |
|Message|String|success| The error message.

 |
|RequestId|String|F82E6667-7811-4BA0-842F-5B2DC42BBAAD| The request ID for troubleshooting.

 |
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeActiveMetricRuleList
&Product=ecs
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeActiveMetricRuleListResponse>
  <Code>200</Code>
  <Success>true</Success> 
  <Datapoints> 
    <Alarm>
      <Namespace>acs_rds_dashboard</Namespace>
      <Statistics>Average</Statistics>
      <Uuid>ef983030-c143-4b1b-b6c7-d4227c99****</Uuid>
      <ContactGroups>["Alibaba Cloud account alert contacts"]</ContactGroups>
      <Webhook>null</Webhook>
      <EvaluationCount>5</EvaluationCount>
      <Period>300</Period>
      <NotifyType>0</NotifyType>
      <State>OK</State>
      <Enable>true</Enable>
      <StartTime>0</StartTime>
      <EndTime>24</EndTime>
      <RuleName>SystemDefault_acs_rds_dashboard_CpuUsage</RuleName>
      <Threshold>80</Threshold>
      <MetricName>CpuUsage#300</MetricName>
      <ComparisonOperator>&gt;</ComparisonOperator>
      <SilenceTime>86400</SilenceTime>
      <Name>SystemDefault_acs_rds_dashboard_CpuUsage</Name>
    </Alarm>
    <Alarm>
      <Namespace>acs_rds_dashboard</Namespace>
      <Statistics>Average</Statistics>
      <Uuid>30b95d23-627e-4e3f-bd8a-b41099aa****</Uuid>
      <ContactGroups>["Alibaba Cloud account alert contacts"]</ContactGroups>
      <Webhook>null</Webhook>
      <EvaluationCount>5</EvaluationCount>
      <Period>300</Period>
      <NotifyType>1</NotifyType>
      <State>OK</State>
      <Enable>true</Enable>
      <StartTime>0</StartTime>
      <EndTime>24</EndTime>
      <RuleName>SystemDefault_acs_rds_dashboard_DiskUsage</RuleName>
      <Threshold>80</Threshold>
      <MetricName>DiskUsage#300</MetricName>
      <ComparisonOperator>&gt;</ComparisonOperator>
      <SilenceTime>86400</SilenceTime>
      <Name>SystemDefault_acs_rds_dashboard_DiskUsage</Name>
    </Alarm>
    <Alarm>
      <Namespace>acs_rds_dashboard</Namespace>
      <Statistics>Average</Statistics>
      <Uuid>2a657281-ae3b-45e7-8ee6-0346bc83****</Uuid>
      <ContactGroups>["Alibaba Cloud account alert contacts"]</ContactGroups>
      <Webhook>null</Webhook>
      <EvaluationCount>5</EvaluationCount>
      <Period>300</Period>
      <NotifyType>0</NotifyType>
      <State>OK</State>
      <Enable>true</Enable>
      <StartTime>0</StartTime>
      <EndTime>24</EndTime>
      <RuleName>SystemDefault_acs_rds_dashboard_IOPSUsage</RuleName>
      <Threshold>80</Threshold>
      <MetricName>IOPSUsage#300</MetricName>
      <ComparisonOperator>&gt;</ComparisonOperator>
      <SilenceTime>86400</SilenceTime>
      <Name>SystemDefault_acs_rds_dashboard_IOPSUsage</Name>
    </Alarm>
    <Alarm>
      <Namespace>acs_rds_dashboard</Namespace>
      <Statistics>Average</Statistics>
      <Uuid>c8c0cae5-2999-4fab-8b6e-1b8581cd****</Uuid>
      <ContactGroups>["Alibaba Cloud account alert contacts"]</ContactGroups>
      <Webhook>null</Webhook>
      <EvaluationCount>5</EvaluationCount>
      <Period>300</Period>
      <NotifyType>0</NotifyType>
      <State>OK</State>
      <Enable>true</Enable>
      <StartTime>0</StartTime>
      <EndTime>24</EndTime>
      <RuleName>SystemDefault_acs_rds_dashboard_ConnectionUsage</RuleName>
      <Threshold>80</Threshold>
      <MetricName>ConnectionUsage#300</MetricName>
      <ComparisonOperator>&gt;</ComparisonOperator>
      <SilenceTime>86400</SilenceTime>
      <Name>SystemDefault_acs_rds_dashboard_ConnectionUsage</Name>
    </Alarm>
    <Alarm>
      <Namespace>acs_rds_dashboard</Namespace>
      <Statistics>Average</Statistics>
      <Uuid>22798954-b384-4b5a-b9cd-bf39bbf8ee5f</Uuid>
      <ContactGroups>["Alibaba Cloud account alert contacts"]</ContactGroups>
      <Webhook>null</Webhook>
      <EvaluationCount>5</EvaluationCount>
      <Period>300</Period>
      <NotifyType>0</NotifyType>
      <State>INSUFFICIENT_DATA</State>
      <Enable>true</Enable>
      <StartTime>0</StartTime>
      <EndTime>24</EndTime>
      <RuleName>SystemDefault_acs_rds_dashboard_DataDelay</RuleName>
      <Threshold>5</Threshold>
      <MetricName>DataDelay#300</MetricName>
      <ComparisonOperator>&gt;</ComparisonOperator>
      <SilenceTime>86400</SilenceTime>
      <Name>SystemDefault_acs_rds_dashboard_DataDelay</Name>
    </Alarm>
  </Datapoints>
</DescribeActiveMetricRuleListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Datapoints":{
		"Alarm":[
			{
				"Uuid":"ef983030-c143-4b1b-b6c7-d4227c99****",
				"Period":300,
				"Statistics":"Average",
				"Webhook":"null",
				"RuleName":"SystemDefault_acs_rds_dashboard_CpuUsage",
				"EvaluationCount":5,
				"Name":"SystemDefault_acs_rds_dashboard_CpuUsage",
				"MetricName":"CpuUsage#300",
				"Threshold":"80",
				"State":"OK",
				"Enable":true,
				"SilenceTime":86400,
				"NotifyType":0,
				"Namespace":"acs_rds_dashboard",
				"ContactGroups":"[\"Alibaba Cloud account alert contacts\"]",
				"EndTime":24,
				"StartTime":0,
				"ComparisonOperator":">"
			},
			{
				"Uuid":"30b95d23-627e-4e3f-bd8a-b41099aa****",
				"Period":300,
				"Statistics":"Average",
				"Webhook":"null",
				"RuleName":"SystemDefault_acs_rds_dashboard_DiskUsage",
				"EvaluationCount":5,
				"Name":"SystemDefault_acs_rds_dashboard_DiskUsage",
				"MetricName":"DiskUsage#300",
				"Threshold":"80",
				"State":"OK",
				"Enable":true,
				"SilenceTime":86400,
				"NotifyType":1,
				"Namespace":"acs_rds_dashboard",
				"ContactGroups":"[\"Alibaba Cloud account alert contacts\"]",
				"EndTime":24,
				"StartTime":0,
				"ComparisonOperator":">"
			},
			{
				"Uuid":"2a657281-ae3b-45e7-8ee6-0346bc83****",
				"Period":300,
				"Statistics":"Average",
				"Webhook":"null",
				"RuleName":"SystemDefault_acs_rds_dashboard_IOPSUsage",
				"EvaluationCount":5,
				"Name":"SystemDefault_acs_rds_dashboard_IOPSUsage",
				"MetricName":"IOPSUsage#300",
				"Threshold":"80",
				"State":"OK",
				"Enable":true,
				"SilenceTime":86400,
				"NotifyType":0,
				"Namespace":"acs_rds_dashboard",
				"ContactGroups":"[\"Alibaba Cloud account alert contact\"]",
				"EndTime":24,
				"StartTime":0,
				"ComparisonOperator":">"
			},
			{
				"Uuid":"c8c0cae5-2999-4fab-8b6e-1b8581cd****",
				"Period":300,
				"Statistics":"Average",
				"Webhook":"null",
				"RuleName":"SystemDefault_acs_rds_dashboard_ConnectionUsage",
				"EvaluationCount":5,
				"Name":"SystemDefault_acs_rds_dashboard_ConnectionUsage",
				"MetricName":"ConnectionUsage#300",
				"Threshold":"80",
				"State":"OK",
				"Enable":true,
				"SilenceTime":86400,
				"NotifyType":0,
				"Namespace":"acs_rds_dashboard",
				"ContactGroups":"[\"Alibaba Cloud account alert contact\"]",
				"EndTime":24,
				"StartTime":0,
				"ComparisonOperator":">"
			},
			{
				"Uuid":"22798954-b384-4b5a-b9cd-bf39bbf8****",
				"Period":300,
				"Statistics":"Average",
				"Webhook":"null",
				"RuleName":"SystemDefault_acs_rds_dashboard_DataDelay",
				"EvaluationCount":5,
				"Name":"SystemDefault_acs_rds_dashboard_DataDelay",
				"MetricName":"DataDelay#300",
				"Threshold":"5",
				"State":"INSUFFICIENT_DATA",
				"Enable":true,
				"SilenceTime":86400,
				"NotifyType":0,
				"Namespace":"acs_rds_dashboard",
				"ContactGroups":"[\"Alibaba Cloud account alert contact\"]",
				"EndTime":24,
				"StartTime":0,
				"ComparisonOperator":">"
			}
		]
	},
	"Success":true,
	"Code":"200"
}
```

## Error code {#section_4m4_b74_u8a .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

