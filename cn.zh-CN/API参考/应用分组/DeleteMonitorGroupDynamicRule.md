# DeleteMonitorGroupDynamicRule {#doc_api_Cms_DeleteMonitorGroupDynamicRule .reference}

删除指定应用分组的动态规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DeleteMonitorGroupDynamicRule&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Category|String|是|ecs|动态规则对应的云产品类型，目前动态组支持的产品有ECS、RDS、SLB。

 |
|GroupId|Long|是|12345|应用分组ID。

 |
|Action|String|否|DeleteMonitorGroupDynamicRule|系统规定参数。取值：DeleteMonitorGroupDynamicRule。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|返回信息。

 |
|RequestId|String|56B4516A-EB44-4C66-8854-0393B35F636B|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteMonitorGroupDynamicRule
&Category=ecs
&GroupId=12345
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteMonitorGroupDynamicRuleResponse>
      <RequestId>56B4516A-EB44-4C66-8854-0393B35F636B</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</DeleteMonitorGroupDynamicRuleResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"56B4516A-EB44-4C66-8854-0393B35F636B",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

