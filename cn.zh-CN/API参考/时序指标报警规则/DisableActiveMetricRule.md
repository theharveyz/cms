# DisableActiveMetricRule {#doc_api_Cms_DisableActiveMetricRule .reference}

禁用一键告警。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DisableActiveMetricRule)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DisableActiveMetricRule|系统规定参数。取值：DisableActiveMetricRule。

 |
|Product|String|是|ecs|目前支持一键告警的产品:

 -   ecs \(云服务器 ECS\)
-   rds \(云数据库RDS版\)
-   slb \(负载均衡\)
-   redis\_standard \(云数据库Redis标准版\)
-   redis\_sharding \(云数据库Redis集群版\)
-   redis\_splitrw \(云数据库Redis读写分离版\)
-   mongodb \(云数据库MongoDB版\(副本集\)\)
-   mongodb\_sharding \(云数据库MongoDB版\(分片集群\)\)
-   hbase \(云数据库HBase版\)
-   elasticsearch \(Elasticsearch\)
-   opensearch \(OpenSearch\)

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|F82E6667-7811-4BA0-842F-5B2DC42BBAAD|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DisableActiveMetricRule
&Product=ecs
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DisableActiveMetricRuleResponse>
  <Code>200</Code>
  <Success>true</Success>
  <Message>success</Message>
  <RequestId>55850888-9CCE-4FD5-B949-5F8947D63929</RequestId>
</DisableActiveMetricRuleResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"55850888-9CCE-4FD5-B949-5F8947D63929",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

