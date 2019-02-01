# QueryMetricLast {#doc_api_989027 .reference}

查询指定监控对象的最新监控数据。

各云产品的Project、Metric、Period、Dimensions等入参如何赋值，请参见[预设监控项参考](~~28619~~)。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=QueryMetricLast)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Metric|String|是|CPUUtilization|监控项名称。

 |
|Project|String|是|acs\_ecs\_dashboard|名字空间，表明监控数据所属产品，如 “acs\_ecs\_dashboard”，“acs\_rds\_dashboard”等 。

 |
|Action|String|否|QueryMetricLast|系统规定参数，取值：QueryMetricLast

 |
|Cursor|String|否|1000|游标

 |
|Dimensions|String|否|\[\{"instanceId":"XXX"\}\]|用于过滤监控数据的 key-value 集合，key 可以使用注册监控项时申明的 dimensionKeys 中的一个或多个，value 为 该 key 对应的值。instanceId 是必填项 需要使用 JSON 字符串表示该 Map 对象，传入时请使用字符串，dimension要求必须按顺序传入。

 |
|EndTime|String|否|2019-01-31 10:10:00|可以传入距离 1970 年 1 月 1 日 0 点的毫秒数，也可以传入format时间格式数据，如2015-10-20 00:00:00。

 |
|Express|String|否|\{"groupby":\["userId","instanceId"\]\}|对查出的现有结果进行时时计算的表达式，例如`{"groupby":["instanceId"]}`

 |
|Length|String|否|1000|返回监控数据的每页大小，用于分页查询。默认值为1000，即每页1000条监控数据。

 |
|Period|String|否|60|时间间隔，统一用秒数来计算，例如 60, 300, 900。 如果不填写，则按照注册监控项时申明的上报周期来查询原始数据。如果填写统计周期,则查询对应的统计数据。

 |
|StartTime|String|否|2019-01-31 10:00:00|开始时间，可以传入距离 1970 年 1 月 1 日 0 点的毫秒数，也可以传入format时间格式数据，如2015-10-20 00:00:00。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，正常为”200”。

 |
|Cursor|String|10000|游标

 |
|Datapoints|String|\[\{"timestamp":1548900600000,"userId":"000","instanceId":"abc","Minimum":6.3,"Average":6.3,"Maximum":6.3\}\]|监控数据列表，内容格式例如：\{ “timestamp”: 1490164200000,”Maximum”: 100,”userId”: “1234567898765432”, “Minimum”: 4.55,”instanceId”: “i-bp18abl200xk9599ck7c”, “Average”: 93.84\}

 |
|Message|String|Success|状态描述信息，Code为“200”时，Message一般为空。

 |
|Period|String|60|时间间隔，统一用秒数来计算，例如 60, 300, 900。

 |
|RequestId|String|021472A6-25E3-4094-8D00-BA4B6A5486C3|当请求出现问题时，可以提供此字段给技术人员进行问题排查。

 |
|Success|String|true|成功返回true， 失败返回false

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=QueryMetricLast
&Metric=CPUUtilization
&Project=acs_ecs_dashboard
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryMetricLastResponse>
  <Period>60</Period>
  <Datapoints>
    <Datapoints>
      <timestamp>1490164200000</timestamp>
      <Maximum>100</Maximum>
      <userId>1234567898765432</userId>
      <Minimum>4.55</Minimum>
      <instanceId>i-bp18abl200xk9599ck7c</instanceId>
      <Average>93.84</Average>
    </Datapoints>
  </Datapoints>
  <RequestId>021472A6-25E3-4094-8D00-BA4B6A5486C3</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</QueryMetricLastResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Period":"60",
	"Datapoints":[
		{
			"timestamp":1490164200000,
			"Maximum":100,
			"userId":"1234567898765432",
			"instanceId":"i-bp18abl200xk9599ck7c",
			"Minimum":4.55,
			"Average":93.84
		}
	],
	"RequestId":"4E7664F2-9CDE-4212-9318-A0712D345A5E",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

