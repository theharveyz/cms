# DeleteMetricRuleResources {#doc_api_Cms_DeleteMetricRuleResources .reference}

删除报警规则关联的资源。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMetricRuleResources)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteMetricRuleResources|系统规定参数。取值：DeleteMetricRuleResources。

 |
|Resources|String|是|\[\{"instanceId":"\*\*\*\*\*ixxxId1"\}\]|关联的资源，格式为一个json数组，如：

 ```

[{"instanceId":"*****ixxxId1"}]

```

 |
|RuleId|String|是|i-2ze3w55tr2rcpejpcfap\_59\*\*\*\*\*\*1|报警规则ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|D8A35882-90C6-4F03-BBEB-153C180398EA|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteMetricRuleResources
&Resources=[{"instanceId":"*****ixxxId1"}]
&RuleId=i-2ze3w55tr2rcpejpcfap_59******1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateMetricRuleResourcesResponse>
  <RequestId>0671A721-0D7A-4F11-BB77-2416325D65AB</RequestId>
  <Success>true</Success>
  <Code>200</Code>
  <Message>success</Message>
</CreateMetricRuleResourcesResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"0671A721-0D7A-4F11-BB77-2416325D65AB",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

