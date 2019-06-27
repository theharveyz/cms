# DescribeSystemEventAttribute {#doc_api_Cms_DescribeSystemEventAttribute .reference}

查询系统事件详情。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSystemEventAttribute)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSystemEventAttribute|系统规定参数。取值：DescribeSystemEventAttribute。

 |
|EndTime|String|否|1552221584949|结束时间。

 |
|EventType|String|否|Exception|事件类型，不同的产品事件有不同的类型。

 |
|GroupId|String|否|12346|组ID。

 |
|Level|String|否|warn|事件的级别， CRITICAL（严重\), WARN\(警告\), INFO\(信息\)。

 |
|Name|String|否|BucketIngressBandwidth|事件的名称。

 |
|PageNumber|Integer|否|1|页码，默认为1。

 |
|PageSize|Integer|否|10|每页显示记录条数。

 |
|Product|String|否|oss|产品的名称缩写。

 |
|SearchKeywords|String|否|cms|搜索事件内容包含的关键字，支持 and 或者 or。

 如果想要搜索事件内容中即包括a也包括b的结果，可以搜索 a and b；

 如果想要搜索事件内容中包括a或者b的结果，可以搜索 a or b。

 |
|StartTime|String|否|1552199984949|开始时间。

 |
|Status|String|否|normal|状态，多个用逗号分隔。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|60912C8D-B340-4253-ADE7-61ACDFD25CFC|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |
|SystemEvents| | |详细的事件内容详情。

 |
|└Content|String|\[\{"product":"CloudMonitor","content":"\{\\"ipGroup\\":\\"112.126.XX.XX,10.163.XX.XX\\",\\"tianjimonVersion\\":\\"1.2.22\\"\}","groupId":"176,177,178,179,180,692,120812,1663836,96,2028302","time":"1552209568000","resourceId":"acs:ecs:cn-beijing:173651113438\*\*\*\*:instance/i-25k35\*\*\*\*","level":"CRITICAL","status":"stopped","instanceName":"cmssiteprobebj-6","name":"Agent\_Status\_Stopped","regionId":"cn-beijing"\}\]|事件内容详情。

 |
|└GroupId|String|12345|组ID。

 |
|└InstanceName|String|instanceId1|实例名。

 |
|└Level|String|Warn|事件的级别， CRITICAL（严重\), WARN\(警告\), INFO\(信息\)。

 |
|└Name|String|Agent\_Status\_Stopped|事件名。

 |
|└Num|Long|2|发生事件的数量。

 |
|└Product|String|CloudMonitor|产品缩写

 |
|└RegionId|String|cn-hangzhou|区域ID。

 |
|└ResourceId|String|xxxxx-1|资源ID。

 |
|└Status|String|normal|状态。

 |
|└Time|Long|1552199984000|发生事件的时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSystemEventAttribute
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSystemEventAttributeResponse>
  <Message>userId:173651113438**** and product:"CloudMonitor"</Message>
  <RequestId>10CB54BE-CA25-4B48-BCAC-C4E0AF6C4A68</RequestId>
  <Data>[{"product":"CloudMonitor","content":"{\"ipGroup\":\"112.126.XX.XX,10.163.XX.XX\",\"tianjimonVersion\":\"1.2.22\"}","groupId":"176,177,178,179,180,692,120812,1663836,96,2028302","time":"1552209568000","resourceId":"acs:ecs:cn-beijing:173651113438****:instance/i-25k35****","level":"CRITICAL","status":"stopped","instanceName":"cmssiteprobebj-6","name":"Agent_Status_Stopped","regionId":"cn-beijing"}]</Data>
  <Code>200</Code>
  <Success>true</Success>
</DescribeSystemEventAttributeResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"[{\"product\":\"CloudMonitor\",\"content\":\"{\\\"ipGroup\\\":\\\"112.126.XX.XX,10.163.XX.XX\\\",\\\"tianjimonVersion\\\":\\\"1.2.22\\\"}\",\"groupId\":\"176,177,178,179,180,692,120812,1663836,96,2028302\",\"time\":\"1552209568000\",\"resourceId\":\"acs:ecs:cn-beijing:173651113438****:instance/i-25k35****\",\"level\":\"CRITICAL\",\"status\":\"stopped\",\"instanceName\":\"cmssiteprobebj-6\",\"name\":\"Agent_Status_Stopped\",\"regionId\":\"cn-beijing\"}]",
	"Message":"userId:173651113438**** and product:\"CloudMonitor\"",
	"RequestId":"10CB54BE-CA25-4B48-BCAC-C4E0AF6C4A68",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

