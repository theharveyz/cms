# PutEventRule {#doc_api_Cms_PutEventRule .reference}

创建或者修改事件的报警规则。

如果报警规则名称不存在则创建新的报警规则，存在则修改已有的报警规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=PutEventRule&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|PutEventRule|系统规定参数。取值：PutEventRule。

 |
|RuleName|String|是|myRuleName|报警规则名称。

 |
|Description|String|否|我的事件报警测试|报警规则描述。

 |
|EventPattern.N.EventTypeList.N|RepeatList|否|Exception|事件的类型， 不限制类型用 "\*"表示， 事件类型详情请查询DescribeSystemEventMeta接口获取。N 的取值范围为 1~50。

 |
|EventPattern.N.LevelList.N|RepeatList|否|CRITICAL|事件报警的等级， 取值可选 CRITICAL（严重）， WARN（警告），INFO（信息），”\*“ 表示所有等级。N 的取值范围为 1~50。

 |
|EventPattern.N.NameList.N|RepeatList|否|Agent\_Status\_Stopped|事件的名称，请查询DescribeSystemEventMeta接口获取。N 的取值范围为 1~50。

 |
|EventPattern.N.Product|String|否|CloudMonitor|产品类型，请查询DescribeSystemEventMeta接口获取。N 的取值范围为 1~50。

 |
|EventPattern.N.StatusList.N|RepeatList|否|xxx|事件状态的名称，请查询DescribeSystemEventMeta接口获取。N 的取值范围为 1~50。

 |
|EventType|String|否|SYSTEM|事件报警类型，可选值为：

 -   SYSTEM（系统事件），
-   CUSTOM（自定义事件）。

 |
|GroupId|String|否|12345|应用分组ID。

 |
|State|String|否|ENABLED|状态， 可选值为：

 -   ENABLED（启用），
-   DISABLED（禁用）。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码， 200表示成功。

 |
|Data|String|1|返回添加影响的行数。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|0B963550-5605-4AC6-93D9-FA7644D19FEF|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=PutEventRule
&RuleName=myRuleName
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PutEventRuleResponse>
      <Data>1</Data>
      <RequestId>0B963550-5605-4AC6-93D9-FA7644D19FEF</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</PutEventRuleResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"1",
	"RequestId":"0B963550-5605-4AC6-93D9-FA7644D19FEF",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

