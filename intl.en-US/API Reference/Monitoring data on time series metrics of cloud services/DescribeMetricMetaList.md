# DescribeMetricMetaList {#doc_api_Cms_DescribeMetricMetaList .reference}

You can call this operation to query the descriptions of time series metrics available to CloudMonitor.

This operation is usually used together with DescribeMetricList and DescribeMetricLast.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricMetaList) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Namespace|String|Yes|acs\_ecs\_dashboard|The namespace of the monitored service.

 |
|Action|String|No|DescribeMetricMetaList|The operation that you want to perform. Set the value to DescribeMetricMetaList.

 |
|Labels|String|No|\[\{"name":"alertUnit","value":"%"\}\]|The tags of the metric in the following format: `[{"name":"tag name","value":"tag value"},{"name":"tag name","value":"tag value"}]`.

 Available tag names:

 -   metricCategory
-   alertEnable
-   alertUnit
-   unitFactor
-   minAlertPeriod
-   productCategory

 |
|MetricName|String|No|CPUUtilization|The name of the metric. The metric with the specified name is matched.

 |
|PageNumber|Integer|No|1|The number of the page. Default value: 1.

 |
|PageSize|Integer|No|30|The number of records on each page. Default value: 30.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Code|String|200|The status code. A value of 200 indicates that the call is successful. Any other value indicates that the call has failed.

 |
|RequestId|String|0CCE0AF0-053C-4B13-A583-DC9A85785D49|The request ID for troubleshooting.

 |
|Message|String|success|The error message.

 |
|Resources| | |The details of the metric.

 |
|└Description|String|CPUUtilization|The description of the metric.

 |
|└Dimensions|String|userId,instanceId|The dimensions of metric. Multiple dimensions must be separated with commas \(,\).

 |
|└Labels|String|\[\{\\"name\\":\\"alertUnit\\",\\"value\\":\\"%\\"\},\{\\"name\\":\\"alertDefault\\",\\"value\\":\\"80\\"\},\{\\"name\\":\\"minAlertPeriod\\",\\"value\\":\\"60\\"\},\{\\"name\\":\\"metricCategory\\",\\"value\\":\\"instanceId\\"\},\{\\"name\\":\\"is\_alarm\\",\\"value\\":\\"true\\"\}\]"|The tags of the metric. It can be a JSON string such as `[{"Name":"tag name","value":"tag value"}]`. It can also be multiple strings that include repeated tag names.

 Available tag names:

 -   metricCategory
-   alertEnable
-   alertUnit
-   unitFactor
-   minAlertPeriod
-   productCategory

 |
|└MetricName|String|CPUUtilization|The name of the metric.

 |
|└Namespace|String|acs\_ecs\_dashboard|The namespace of the monitored service. It is in the acs\_service name format.

 |
|└Periods|String|60,300|The statistical periods of the metric. Multiple periods must be separated with commas \(,\).

 |
|└Statistics|String|Average,Minimum,Maximum|The statistical methods. Multiple statistical methods must be separated by commas \(,\).

 |
|└Unit|String|%|The unit of the metric.

 |
|TotalCount|String|12|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMetricMetaList
&Namespace=acs_ecs_dashboard
&<Common request parameters>

```

Successful response examples

`XML` format

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

`JSON` format

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

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

