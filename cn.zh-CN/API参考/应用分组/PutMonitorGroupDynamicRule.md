# PutMonitorGroupDynamicRule {#doc_api_Cms_PutMonitorGroupDynamicRule .reference}

创建或者修改一个应用分组的动态规则，满足规则描述的资源会自动添加到应用分组中。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=PutMonitorGroupDynamicRule&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|PutMonitorGroupDynamicRule|系统规定参数。取值：PutMonitorGroupDynamicRule。

 |
|GroupId|Long|是|1234|应用分组ID。

 |
|GroupRules.N.Category|String|否|ecs|动态规则的产品类型，目前支持的动态规则产品类型为ecs，rds，slb。N的取值为大于等于1的整数

 |
|GroupRules.N.FilterRelation|String|否|and|动态规则的组合条件，可选值：

 -   and 满足设置所有规则才会自动添加到分组、
-   or 表示满足任意规则的实例都会被添加到分组

N的取值为大于等于1的整数


 |
|GroupRules.N.Filters.N.Function|String|否|contains|实例过滤条件，可选值：

 -   contains：包含关系
-   startWith：前缀
-   endWith：后缀

 N的取值范围为 1~3

 |
|GroupRules.N.Filters.N.Name|String|否|hostName|实例名称，匹配的字段名称，目前仅支持主机名：hostName。N的取值范围为 1~3.

 |
|GroupRules.N.Filters.N.Value|String|否|nginx|满足的条件值。N的取值范围为 1~3.

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|3E73F1AB-D195-438A-BCA7-2F4355789C58|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=PutMonitorGroupDynamicRule
&GroupId=1234
&GroupRules.1.Category=ecs
&GroupRules.1.FilterRelation=and
&GroupRules.1.Filters.1.Function=contains
&GroupRules.1.Filters.1.1ame=hostName
&GroupRules.1.Filters.1.Value=nginx
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PutMonitorGroupDynamicRuleResponse>
      <RequestId>3E73F1AB-D195-438A-BCA7-2F4355789C58</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</PutMonitorGroupDynamicRuleResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"3E73F1AB-D195-438A-BCA7-2F4355789C58",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

