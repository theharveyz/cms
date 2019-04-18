# DescribeMetricList {#doc_api_Cms_DescribeMetricList .reference}

查询指定时间段内的云产品时序指标监控数据。

## 参数说明 {#description .section}

-   各云产品的Project、Metric、Period、Dimensions等入参如何赋值，可查询DescribeMetricMetaList接口或参考[预设监控项参考](~~28619~~)。
-   开始和结束时间执行的是左开右闭的模式，startTime不能等于或者大于endTime。
-   Cursor是分页模式下的参数，只要存在就说明还有下一页，返回为null则说明没有下一页。
-   Period一般包含60（一分钟）、300（五分钟）、900（十五分钟）。请根据文档以及查询场景的需要考虑Period。比如查询一天范围使用Period为60，则返回1000条数据（实际存在1440，因为最大返回值不超过1000，则只返回前1000条）。如果使用Period为300，则返回288条数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMetricList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMetricList|系统规定参数，取值：DescribeMetricList。

 |
|MetricName|String|是|cpu\_idle|监控项名称。

 |
|Namespace|String|是|acs\_ecs\_dashboard|命名空间，表明监控数据所属产品，如 “acs\_ecs\_dashboard”,“acs\_rds\_dashboard”。

 |
|Dimensions|String|否|\[\{"instanceId": "i-abcdefgh12\*\*\*\*"\}\]|用于查询指定资源的监控数据，是 key-value 形式的集合。常用的key-value集合为“instanceId：XXXXXX”。需要使用 JSON 字符串表示该 Map 对象，传入时请使用字符串，Dimensions字段必须按顺序传入。

 |
|EndTime|String|否|2019-01-30 00:10:00|结束时间，可以传入距离1970年1月1日 0点的毫秒数，也可以传入format时间格式数据，如2015-10-20 00:00:00。

 |
|Express|String|否|\{"groupby":\["userId","instanceId"\]\}|对查询出的现有结果进行时时计算的表达式，例如`{"groupby":["instanceId"]}`。

 |
|Length|String|否|1000|每次查询大小，用于分页查询，默认值为1000。

 |
|NextToken|String|否|xxxxxxxxxxxx|游标，用于分页使用。

 |
|Period|String|否|60|时间间隔，统一用秒数来计算，例如 60, 300, 900。 如果不填写,则按照监控项默认的最小周期来查询数据。如果填写统计周期，则查询对应的统计数据 。

 |
|StartTime|String|否|2019-01-30 00:00:00|开始时间，可以传入距离1970年1月1日0点的毫秒数，也可以传入format时间格式数据，如2015-10-20 00:00:00。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|3121AE7D-4AFF-4C25-8F1D-C8226EBB1F42|请求ID，用于排查问题。

 |
|Message|String|Success|错误信息，Code为”200”时，Message一般为空。

 |
|Datapoints|String|\[\{"timestamp":1548777660000,"userId":"123","instanceId":"i-abc","Minimum":9.92,"Average":9.92,"Maximum":9.92\}\]|监控数据列表，内容格式例如：`{ “timestamp”: 1490164200000, “Maximum”: 100, “userId”: “123456789876****”, “Minimum”: 4.55, “instanceId”: “i-bp18abl200xk9599****”, “Average”: 93.84 }`。

 |
|NextToken|String|xxxxxxxxxxxx|游标，分页标记。

 |
|Period|String|60|时间间隔，统一用秒数来计算,例如 60, 300, 900。

 |
|Code|String|200|状态码，200表示成功。

 |
|Success|String|true|是否成功，如果服务器端有异常此返回值为false，正常为true。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMetricList
&MetricName=cpu_idle
&Namespace=acs_ecs_dashboard
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryMetricListResponse>
  <Period>60</Period>
  <Datapoints>
    <Datapoints>
      <timestamp>1490152860000</timestamp>
      <Maximum>100</Maximum>
      <userId> 123456789876****</userId>
      <Minimum>93.1</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.52</Average>
    </Datapoints>
    <Datapoints>
      <timestamp>1490152920000</timestamp>
      <Maximum>100</Maximum>
      <userId> 123456789876**** </userId>
      <Minimum>92.59</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.49</Average>
    </Datapoints>
    <Datapoints>
      <timestamp>1490152980000</timestamp>
      <Maximum>100</Maximum>
      <userId>123456789876****</userId>
      <Minimum>92.86</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.44</Average>
    </Datapoints>
    <Datapoints>
      <timestamp>1490153040000</timestamp>
      <Maximum>100</Maximum>
      <userId>123456789876****</userId>
      <Minimum>91.43</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.36</Average>
    </Datapoints>
    <Datapoints>
      <timestamp>1490153100000</timestamp>
      <Maximum>100</Maximum>
      <userId>123456789876****</userId>
      <Minimum>93.55</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.51</Average>
    </Datapoints>
    <Datapoints>
      <timestamp>1490153160000</timestamp>
      <Maximum>100</Maximum>
      <userId>123456789876****</userId>
      <Minimum>93.1</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.52</Average>
    </Datapoints>
    <Datapoints>
      <timestamp>1490153220000</timestamp>
      <Maximum>100</Maximum>
      <userId>123456789876****</userId>
      <Minimum>92.59</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.42</Average>
    </Datapoints>
    <Datapoints>
      <timestamp>1490153280000</timestamp>
      <Maximum>100</Maximum>
      <userId>123456789876****</userId>
      <Minimum>91.18</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.34</Average>
    </Datapoints>
    <Datapoints>
      <timestamp>1490153340000</timestamp>
      <Maximum>100</Maximum>
      <userId>123456789876****</userId>
      <Minimum>92.86</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.46</Average>
    </Datapoints>
    <Datapoints>
      <timestamp>1490153400000</timestamp>
      <Maximum>100</Maximum>
      <userId>123456789876****</userId>
      <Minimum>91.18</Minimum>
      <instanceId>i-abcdefgh12****</instanceId>
      <Average>99.35</Average>
    </Datapoints>
  </Datapoints>
  <RequestId>6661EC50-8625-4161-B349-E0DD59002AB7</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</QueryMetricListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Period":"60",
	"Datapoints":[
		{
			"timestamp":1490152860000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":93.1,
			"Average":99.52
		},
		{
			"timestamp":1490152920000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":92.59,
			"Average":99.49
		},
		{
			"timestamp":1490152980000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":92.86,
			"Average":99.44
		},
		{
			"timestamp":1490153040000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":91.43,
			"Average":99.36
		},
		{
			"timestamp":1490153100000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":93.55,
			"Average":99.51
		},
		{
			"timestamp":1490153160000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":93.1,
			"Average":99.52
		},
		{
			"timestamp":1490153220000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":92.59,
			"Average":99.42
		},
		{
			"timestamp":1490153280000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":91.18,
			"Average":99.34
		},
		{
			"timestamp":1490153340000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":92.86,
			"Average":99.46
		},
		{
			"timestamp":1490153400000,
			"Maximum":100,
			"userId":"123456789876****",
			"instanceId":"i-abcdefgh12****",
			"Minimum":91.18,
			"Average":99.35
		}
	],
	"RequestId":"6A5F022D-AC7C-460E-94AE-B9E75083D027",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

