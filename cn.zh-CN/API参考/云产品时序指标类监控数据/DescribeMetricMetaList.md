# DescribeMetricMetaList {#doc_api_Cms_DescribeMetricMetaList .reference}

查询云监控开放的时序类指标监控项描述。

通常配合查询监控数据接口DescribeMetricList、DescribeMetricLast 等一起使用。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMetricMetaList&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Namespace|String|是|acs\_kvstore|指标所属的Namespace，用于区分每个产品配置。

 |
|Action|String|否|DescribeMetricMetaList|系统规定参数，取值：DescribeMetricMetaList

 |
|Labels|String|否|\[\{"name":"productCategory","value":"kvstore\_old"\}\]|根据标签过滤，格式`[{"name":"标签名","value":"标签值"},{"name":"标签名","value":"标签值"}]`。

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

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Success|Boolean|true|是否成功。

 |
|Code|String|200|状态码，200表示成功。

 |
|RequestId|String|0CCE0AF0-053C-4B13-A583-DC9A85785D49|请求ID，用于排查问题

 |
|Message|String|success|错误信息。

 |
|Resources| | |具体的配置信息。

 |
|Description|String|CPUUtilization|监控项描述。

 |
|Dimensions|String|instanceId|监控项的Dimensions，多级用英文逗号分隔，例如：userId,instanceId。

 |
|Labels|String|\[\{\\"name\\":\\"alertUnit\\",\\"value\\":\\"Bytes\\"\},\{\\"name\\":\\"minAlertPeriod\\",\\"value\\":\\"60\\"\},\{\\"name\\":\\"metricCategory\\",\\"value\\":\\"instanceId\\"\},\{\\"name\\":\\"instanceType\\",\\"value\\":\\"disaster\\"\},\{\\"name\\":\\"is\_alarm\\",\\"value\\":\\"true\\"\},\{\\"name\\":\\"productCategory\\",\\"value\\":\\"kvstore\_old\\"\}\]|监控项的标签，是一个json的string`[{"name":"标签名","value":"标签的值"}]`，可以是多个，name可以重复。

 已有的标签name说明：

 -   metricCategory：指标分类
-   alertEnable：是否可以报警
-   alertUnit：报警单位
-   unitFactor：单位转换系数
-   minAlertPeriod：最小报警周期
-   productCategory：产品

 |
|MetricName|String|CPUUtilization|监控项名称。

 |
|Namespace|String|acs\_kvstore|用于区分产品类型，通常的命名方式为acs\_产品名。

 |
|Periods|String|60,300|监控项的所有统计周期，多个用英文逗号分隔：15,60,900。

 |
|Statistics|String|Average,Minimum,Maximum|统计方法，多个用英文逗号分隔，例如：Maximum,Minimum,Average。

 |
|Unit|String|%|监控项的单位。

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
    <TotalCount>120</TotalCount>
    <RequestId>EA94B362-973C-4D6B-BE94-6774E18915C2</RequestId>
    <Success>true</Success>
    <Code>200</Code>
    <Resources>
        <Resource>
            <Description>ECS.CPUUtilization</Description>
            <Statistics>Average,Minimum,Maximum</Statistics>
            <MetricName>CPUUtilization</MetricName>
            <Labels>[{"name":"alertUnit","value":"%"},{"name":"alertDefault","value":"80"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
            <Dimensions>userId,instanceId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>%</Unit>
        </Resource>
        <Resource>
            <Description></Description>
            <Statistics>Average,Maximum,Minimum</Statistics>
            <MetricName>DiskReadBPS</MetricName>
            <Labels>[{"name":"alertUnit","value":"Mbytes/s"},{"name":"minAlertPeriod","value":"60"},{"name":"unitFactor","value":"1048576"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
            <Dimensions>userId,instanceId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>bytes/s</Unit>
        </Resource>
        <Resource>
            <Description>系统磁盘读IOPS</Description>
            <Statistics>Average,Minimum,Maximum</Statistics>
            <MetricName>DiskReadIOPS</MetricName>
            <Labels>[{"name":"alertUnit","value":"Count/Second"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
            <Dimensions>userId,instanceId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>Count/Second</Unit>
        </Resource>
        <Resource>
            <Description></Description>
            <Statistics>Average,Maximum,Minimum</Statistics>
            <MetricName>DiskWriteBPS</MetricName>
            <Labels>[{"name":"alertUnit","value":"Mbytes/s"},{"name":"minAlertPeriod","value":"60"},{"name":"unitFactor","value":"1048576"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
            <Dimensions>userId,instanceId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>bytes/s</Unit>
        </Resource>
        <Resource>
            <Description>系统磁盘写IOPS</Description>
            <Statistics>Average,Minimum,Maximum</Statistics>
            <MetricName>DiskWriteIOPS</MetricName>
            <Labels>[{"name":"alertUnit","value":"Count/Second"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"instanceId"},{"name":"is_alarm","value":"true"}]</Labels>
            <Dimensions>userId,instanceId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>Count/Second</Unit>
        </Resource>
        <Resource>
            <Description></Description>
            <Statistics>Average,Minimum,Maximum</Statistics>
            <MetricName>GroupCPUUtilization</MetricName>
            <Labels>[{"name":"alertUnit","value":"%"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"groupId"}]</Labels>
            <Dimensions>groupId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>%</Unit>
        </Resource>
        <Resource>
            <Description></Description>
            <Statistics>Average,Minimum,Maximum</Statistics>
            <MetricName>GroupDiskReadBPS</MetricName>
            <Labels>[{"name":"alertUnit","value":"Mbytes/s"},{"name":"minAlertPeriod","value":"60"},{"name":"unitFactor","value":"1048576"},{"name":"metricCategory","value":"groupId"}]</Labels>
            <Dimensions>groupId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>bytes/s</Unit>
        </Resource>
        <Resource>
            <Description></Description>
            <Statistics>Average,Minimum,Maximum</Statistics>
            <MetricName>GroupDiskReadIOPS</MetricName>
            <Labels>[{"name":"alertUnit","value":"Count/Second"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"groupId"}]</Labels>
            <Dimensions>groupId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>Count/Second</Unit>
        </Resource>
        <Resource>
            <Description></Description>
            <Statistics>Average,Minimum,Maximum</Statistics>
            <MetricName>GroupDiskWriteBPS</MetricName>
            <Labels>[{"name":"alertUnit","value":"Mbytes/s"},{"name":"minAlertPeriod","value":"60"},{"name":"unitFactor","value":"1048576"},{"name":"metricCategory","value":"groupId"}]</Labels>
            <Dimensions>groupId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>bytes/s</Unit>
        </Resource>
        <Resource>
            <Description></Description>
            <Statistics>Average,Minimum,Maximum</Statistics>
            <MetricName>GroupDiskWriteIOPS</MetricName>
            <Labels>[{"name":"alertUnit","value":"Count/Second"},{"name":"minAlertPeriod","value":"60"},{"name":"metricCategory","value":"groupId"}]</Labels>
            <Dimensions>groupId</Dimensions>
            <Namespace>acs_ecs_dashboard</Namespace>
            <Periods>60,300</Periods>
            <Unit>Count/Second</Unit>
        </Resource>
    </Resources>
</DescribeMetricMetaListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TotalCount":1853,
	"RequestId":"CDE9EAFF-D54E-4024-BBFC-B0AAC883143B",
	"Success":true,
	"Code":200,
	"Resources":{
		"Resource":[
			{
				"Description":"磁盘额定容量",
				"MetricName":"ads.diskSize",
				"Statistics":"Average,Minimum,Maximum",
				"Labels":"[{\"name\":\"minAlertPeriod\",\"value\":\"300\"},{\"name\":\"alertDefault\",\"value\":\"\"},{\"name\":\"unitFactor\",\"value\":\"1\"},{\"name\":\"alertUnit\",\"value\":\"Mbytes\"},{\"name\":\"productCategory\",\"value\":\"ads\"},{\"name\":\"is_alarm\",\"value\":\"true\"},{\"name\":\"metricCategory\",\"value\":\"workerId\"}]",
				"Dimensions":"userId,instanceId,tableSchema,workerId",
				"Namespace":"acs_ads",
				"Periods":"300",
				"Unit":"Mbytes"
			},
			{
				"Description":"磁盘已用容量",
				"MetricName":"ads.diskUsed",
				"Statistics":"Average,Minimum,Maximum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Mbytes\"},{\"name\":\"minAlertPeriod\",\"value\":\"300\"},{\"name\":\"metricCategory\",\"value\":\"workerId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId,tableSchema,workerId",
				"Namespace":"acs_ads",
				"Periods":"300",
				"Unit":"Mbytes"
			},
			{
				"Description":"磁盘使用率",
				"MetricName":"ads.diskUsedPercent",
				"Statistics":"Average,Minimum,Maximum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"%\"},{\"name\":\"minAlertPeriod\",\"value\":\"300\"},{\"name\":\"metricCategory\",\"value\":\"workerId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId,tableSchema,workerId",
				"Namespace":"acs_ads",
				"Periods":"300",
				"Unit":"%"
			},
			{
				"Description":"queue的未消费的消息数目",
				"MetricName":"QueueMessageAccumulation",
				"Statistics":"Maximum",
				"Labels":"[{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"alertDefault\",\"value\":\"\"},{\"name\":\"unitFactor\",\"value\":\"1\"},{\"name\":\"alertUnit\",\"value\":\"count/min\"},{\"name\":\"productCategory\",\"value\":\"amqp\"},{\"name\":\"is_alarm\",\"value\":\"true\"},{\"name\":\"metricCategory\",\"value\":\"queue\"}]",
				"Dimensions":"userId,regionId,vhostName,queueName",
				"Namespace":"acs_amqp",
				"Periods":"60,300",
				"Unit":"count/min"
			},
			{
				"Description":"queue每分钟消息生产量",
				"MetricName":"QueueMessageInput",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"alertDefault\",\"value\":\"\"},{\"n ame\":\"unitFactor\",\"value\":\"1\"},{\"name\":\"alertUnit\",\"value\":\"count/min\"},{\"name\":\"productCategory\",\"value\":\"amqp\"},{\"name\":\"is_alarm\",\"value\":\"true\"},{\"name\":\"metricCategory\",\"value\":\"queue\"}]",
				"Dimensions":"userId,regionId,vhostName,queueName",
				"Namespace":"acs_amqp",
				"Periods":"60,300",
				"Unit":"count/min"
			},
			{
				"Description":"queue的未消费的消息数目",
				"MetricName":"QueueMessageOutput",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"alertDefault\",\"value\":\"\"},{\"name\":\"unitFactor\",\"value\":\"1\"},{\"name\":\"alertUnit\",\"value\":\"count/min\"},{\"name\":\"productCategory\",\"value\":\"amqp\"},{\"name\":\"is_alarm\",\"value\":\"true\"},{\"name\":\"metricCategory\",\"value\":\"queue\"}]",
				"Dimensions":"userId,regionId,vhostName,queueName",
				"Namespace":"acs_amqp",
				"Periods":"60,300",
				"Unit":"count/min"
			},
			{
				"Description":"实例每分钟产生的消息数量",
				"MetricName":"VhostMessageInput",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"alertDefault\",\"value\":\"\"},{\"name\":\"unitFactor\",\"value\":\"1\"},{\"name\":\"alertUnit\",\"value\":\"count/min\"},{\"name\":\"productCategory\",\"value\":\"amqp\"},{\"name\":\"is_alarm\",\"value\":\"true\"},{\"name\":\"metricCategory\",\"value\":\"vhost\"}]",
				"Dimensions":"userId,regionId,vhostName",
				"Namespace":"acs_amqp",
				"Periods":"60,300",
				"Unit":"count/min"
			},
			{
				"Description":"实例每分钟消费的消息数量",
				"MetricName":"VhostMessageOutput",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"alertDefault\",\"value\":\"\"},{\"name\":\"unitFactor\",\"value\":\"1\"},{\"name\":\"alertUnit\",\"value\":\"count/min\"},{\"name\":\"productCategory\",\"value\":\"amqp\"},{\"name\":\"is_alarm\",\"value\":\"true\"},{\"name\":\"metricCategory\",\"value\":\"vhost\"}]",
				"Dimensions":"userId,regionId,vhostName",
				"Namespace":"acs_amqp",
				"Periods":"60,300",
				"Unit":"count/min"
			},
			{
				"Description":"",
				"MetricName":"Latency",
				"Statistics":"Average",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"ms\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,region,apiUid",
				"Namespace":"acs_apigateway_dashboard",
				"Periods":"60,300,900",
				"Unit":"ms"
			},
			{
				"Description":"",
				"MetricName":"SumQPS",
				"Statistics":"Count",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,region,apiUid",
				"Namespace":"acs_apigateway_dashboard",
				"Periods":"60,300,900",
				"Unit":"Count"
			},
			{
				"Description":"",
				"MetricName":"TrafficRX",
				"Statistics":"Sum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"KBytes\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,region,apiUid",
				"Namespace":"acs_apigateway_dashboard",
				"Periods":"60,300,900",
				"Unit":"KBytes"
			},
			{
				"Description":"",
				"MetricName":"TrafficTX",
				"Statistics":"Sum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"KBytes\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,region,apiUid",
				"Namespace":"acs_apigateway_dashboard",
				"Periods":"60,300,900",
				"Unit":"KBytes"
			},
			{
				"Description":"",
				"MetricName":"code2XX",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,region,apiUid",
				"Namespace":"acs_apigateway_dashboard",
				"Periods":"60,300",
				"Unit":"count"
			},
			{
				"Description":"",
				"MetricName":"code4XX",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"tru\"}]",
				"Dimensions":"userId,region,apiUid",
				"Namespace":"acs_apigateway_dashboard",
				"Periods":"60,300",
				"Unit":"count"
			},
			{
				"Description":"",
				"MetricName":"code5XX",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,region,apiUid",
				"Namespace":"acs_apigateway_dashboard",
				"Periods":"60,300",
				"Unit":"count"
			},
			{
				"Description":"",
				"MetricName":"net_rx.Pkgs",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"pps\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId",
				"Namespace":"acs_bandwidth_package",
				"Periods":"60,300,600",
				"Unit":"pps"
			},
			{
				"Description":"",
				"MetricName":"net_rx.rate",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Mbits/s\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"unitFactor\",\"value\":\"1048576\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId",
				"Namespace":"acs_bandwidth_package",
				"Periods":"60,300,600",
				"Unit":"bits/s"
			},
			{
				"Description":"",
				"MetricName":"net_tx.Pkgs",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"pps\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId",
				"Namespace":"acs_bandwidth_package",
				"Periods":"60,300,600",
				"Unit":"pps"
			},
			{
				"Description":"",
				"MetricName":"net_tx.rate",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Mbits/s\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"unitFactor\",\"value\":\"1048576\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId",
				"Namespace":"acs_bandwidth_package",
				"Periods":"60,300,600",
				"Unit":"bits/s"
			},
			{
				"Description":"",
				"MetricName":"net_tx.ratePercent",
				"Statistics":"Value",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"%\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId",
				"Namespace":"acs_bandwidth_package",
				"Periods":"60,300,600",
				"Unit":"%"
			},
			{
				"Description":"单位时间内网络流量的最大值",
				"MetricName":"BPS",
				"Statistics":"Average,Minimum,Maximum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Mbits/s\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"unitFactor\",\"value\":\"1000000\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"unitFactor\",\"value\":\"1000\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId",
				"Namespace":"acs_cdn",
				"Periods":"60,300",
				"Unit":"bits/s"
			},
			{
				"Description":"",
				"MetricName":"GroupBPS",
				"Statistics":"Sum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Mbits/s\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"unitFactor\",\"value\":\"1000000\"},{\"name\":\"metricCategory\",\"value\":\"groupId\"},{\"name\":\"unitFactor\",\"value\":\"1000\"}]",
				"Dimensions":"userId,groupId",
				"Namespace":"acs_cdn",
				"Periods":"60,300",
				"Unit":"bits/s"
			},
			{
				"Description":"",
				"MetricName":"GroupInternetOut",
				"Statistics":"Sum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Mbytes\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"unitFactor\",\"value\":\"1000000\"},{\"name\":\"metricCategory\",\"value\":\"groupId\"},{\"name\":\"unitFactor\",\"value\":\"1000\"}]",
				"Dimensions":"userId,groupId",
				"Namespace":"acs_cdn",
				"Periods":"60,300",
				"Unit":"bytes"
			},
			{
				"Description":"下行流量",
				"MetricName":"InternetOut",
				"Statistics":"Sum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Mbytes\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"unitFactor\",\"value\":\"1000000\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"unitFactor\",\"value\":\"1000\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId",
				"Namespace":"acs_cdn",
				"Periods":"60,300",
				"Unit":"bytes"
			},
			{
				"Description":"时间粒度内的总访问次数/时间粒度",
				"MetricName":"QPS",
				"Statistics":"Average,Minimum,Maximum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId",
				"Namespace":"acs_cdn",
				"Periods":"60,300",
				"Unit":"Count"
			},
			{
				"Description":"",
				"MetricName":"UserQPS",
				"Statistics":"Average",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Count\"},{\"name\":\"alertDefault\",\"value\":\"Count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"userId\"}]",
				"Dimensions":"userId",
				"Namespace":"acs_cdn",
				"Periods":"60,300",
				"Unit":""
			},
			{
				"Description":"",
				"MetricName":"Usercode4xx",
				"Statistics":"Average",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"userId\"}]",
				"Dimensions":"userId",
				"Namespace":"acs_cdn",
				"Periods":"60",
				"Unit":"Count"
			},
			{
				"Description":"",
				"MetricName":"Usercode5xx",
				"Statistics":"Average",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"Count\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"userId\"}]",
				"Dimensions":"userId",
				"Namespace":"acs_cdn",
				"Periods":"60",
				"Unit":"Count"
			},
			{
				"Description":"",
				"MetricName":"UserhitRate",
				"Statistics":"Average",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"%\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"userId\"}]",
				"Dimensions":"userId",
				"Namespace":"acs_cdn",
				"Periods":"60",
				"Unit":"%"
			},
			{
				"Description":"时间粒度内http返回码4XX占全部返回码的百分比",
				"MetricName":"code4xx",
				"Statistics":"Average,Minimum,Maximum",
				"Labels":"[{\"name\":\"alertUnit\",\"value\":\"%\"},{\"name\":\"minAlertPeriod\",\"value\":\"60\"},{\"name\":\"metricCategory\",\"value\":\"instanceId\"},{\"name\":\"is_alarm\",\"value\":\"true\"}]",
				"Dimensions":"userId,instanceId",
				"Namespace":"acs_cdn",
				"Periods":"60,300",
				"Unit":"%"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cms)查看更多错误码。

