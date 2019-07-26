# DeleteEventRules {#doc_api_Cms_DeleteEventRules .reference}

删除事件报警规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DeleteEventRules&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RuleNames.N|RepeatList|是|rule1|报警规则名称。N 的取值范围为 1~20。

 |
|Action|String|否|DeleteEventRules|系统规定参数。取值：DeleteEventRules。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|返回信息。

 |
|RequestId|String|E5A72B5B-4F44-438C-B68A-147FD5DC53A8|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteEventRules
&RuleNames.1=rule1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteEventRulesResponse>
      <RequestId>E5A72B5B-4F44-438C-B68A-147FD5DC53A8</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</DeleteEventRulesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"E5A72B5B-4F44-438C-B68A-147FD5DC53A8",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

