# DescribeSiteMonitorQuota {#doc_api_Cms_DescribeSiteMonitorQuota .reference}

取得站点监控的配额以及版本。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorQuota)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSiteMonitorQuota|系统规定参数。取值：DescribeSiteMonitorQuota。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Data| | |配额。

 |
|└SiteMonitorIdcQuota|Integer|5|站点监控IDC（阿里巴巴）探点的配额，免费为为5个配额。

 |
|└SiteMonitorOperatorQuotaQuota|Integer|3|非IDC（阿里巴巴）探测点配额，默认为0。

 |
|└SiteMonitorQuotaTaskUsed|Integer|6|站点监控探测任务配额使用数。

 |
|└SiteMonitorTaskQuota|Integer|10|站点监控探测任务配额。

 |
|└SiteMonitorVersion|String|V1|站点监控的版本， V1为老版本， V2为新版。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|26860260-76C6-404E-AB7A-EB98D36A6885|请求ID，用于排查问题。

 |
|Success|String|successful|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSiteMonitorQuota
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSiteMonitorQuotaResponse>
  <Data>
    <SiteMonitorIdcQuota>20</SiteMonitorIdcQuota>
    <SiteMonitorVersion>V1</SiteMonitorVersion>
    <SiteMonitorTaskQuota>9999</SiteMonitorTaskQuota>
    <SiteMonitorQuotaTaskUsed>39</SiteMonitorQuotaTaskUsed>
    <SiteMonitorOperatorQuotaQuota>500</SiteMonitorOperatorQuotaQuota>
  </Data>
  <Message>successful</Message>
  <RequestId>26860260-76C6-404E-AB7A-EB98D36A6885</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSiteMonitorQuotaResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"SiteMonitorIdcQuota":20,
		"SiteMonitorVersion":"V1",
		"SiteMonitorTaskQuota":9999,
		"SiteMonitorOperatorQuotaQuota":500,
		"SiteMonitorQuotaTaskUsed":39
	},
	"Message":"successful",
	"RequestId":"26860260-76C6-404E-AB7A-EB98D36A6885",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

