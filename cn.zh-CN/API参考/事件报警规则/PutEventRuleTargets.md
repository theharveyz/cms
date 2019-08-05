# PutEventRuleTargets {#doc_api_Cms_PutEventRuleTargets .reference}

添加或者修改规则的发送目标。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=PutEventRuleTargets&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|PutEventRuleTargets|系统规定参数。取值：PutEventRuleTargets。

 |
|RuleName|String|是|testEventRule|报警规则名称。

 |
|ContactParameters.N.ContactGroupName|String|否|默认报警联系组|报警联系人组名称。N 的取值范围为 1~5。

 |
|ContactParameters.N.Id|String|否|2|ID，TARGET的唯一标识。N 的取值范围为 1~5。

 |
|ContactParameters.N.Level|String|否|3|报警通知级别，取值为2， 3，4。国际站没有电话、短信通知方式。

 -   2：电话、短信、钉钉、Email。
-   3：短信、钉钉、Email。
-   4：钉钉、Email。

 N 的取值范围为 1~5。

 |
|FcParameters.N.FunctionName|String|否|fc-test|函数名称。N 的取值范围为 1~5。

 |
|FcParameters.N.Id|String|否|1|ID，TARGET的唯一标识。N 的取值范围为 1~5。

 |
|FcParameters.N.Region|String|否|cn-hangzhou|函数服务对应的Region。N 的取值范围为 1~5。

 |
|FcParameters.N.ServiceName|String|否|fc-test|函数服务的ServiceName。N 的取值范围为 1~5。

 |
|MnsParameters.N.Id|String|否|3|ID，TARGET的唯一标识。N 的取值范围为 1~5。

 |
|MnsParameters.N.Queue|String|否|queue1|队列名称。N 的取值范围为 1~5。

 |
|MnsParameters.N.Region|String|否|cn-hangzhou|消息服务的Region。N 的取值范围为 1~5。

 |
|SlsParameters.N.Id|String|否|5|ID，TARGET的唯一标识。N 的取值范围为 1~5。

 |
|SlsParameters.N.LogStore|String|否|testlogstore|日志服务对应的LogStore。N 的取值范围为 1~5。

 |
|SlsParameters.N.Project|String|否|testproject|日志服务对应的project。N 的取值范围为 1~5。

 |
|SlsParameters.N.Region|String|否|cn-hangzhou|日志服务对应的Region。N 的取值范围为 1~5。

 |
|WebhookParameters.N.Id|String|否|4|ID，TARGET的唯一标识。

 |
|WebhookParameters.N.Method|String|否|GET|HTTP回调的请求方法，目前支持GET/POST方法。N 的取值范围为 1~5。

 |
|WebhookParameters.N.Protocol|String|否|http|协议名。N 的取值范围为 1~5。

 |
|WebhookParameters.N.Url|String|否|http://www.aliyun.com|回调的URL。N 的取值范围为 1~5。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Success|Boolean|true|是否成功。

 |
|Code|String|200|状态码， 200表示成功。

 |
|RequestId|String|409C64DA-CF14-45DF-B463-471C790DD15A|请求ID，用于排查问题。

 |
|Message|String|success|错误信息。

 |
|FailedParameterCount|String|2|错误参数数量统计。

 |
|FailedFcParameters| | |Target中如果包含创建错误的函数服务，则返回这个字段。

 |
|FunctionName|String|functionTest1|函数名。

 |
|Id|Integer|1|TargetId，Target唯一标识。

 |
|Region|String|cn-hangzhou|RegionId。

 |
|ServiceName|String|serviceTest1|函数服务的名称。

 |
|FailedMnsParameters| | |Target中如果包含创建错误的消息服务，则返回这个字段。

 |
|Id|Integer|2|TargetId，Target唯一标识。

 |
|Queue|String|testQueue|队列名称。

 |
|Region|String|cn-hangzhou|RegionId。

 |
|FailedContactParameters| | |Target中如果包含创建错误的报警联系人组，则返回这个字段。

 |
|ContactGroupName|String|默认报警联系人组|报警联系人组。

 |
|Id|Integer|2|TargetId，Target唯一标识。

 |
|Level|String|3|报警通知级别，取值为2， 3，4。国际站没有电话、短信通知方式。

 -   2：电话、短信、钉钉、Email。
-   3：短信、钉钉、Email。
-   4：钉钉、Email。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=PutEventRuleTargets
&RuleName=testEventRule
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PutEventRuleTargetsResponse>
      <RequestId>409C64DA-CF14-45DF-B463-471C790DD15A</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</PutEventRuleTargetsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"409C64DA-CF14-45DF-B463-471C790DD15A",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

