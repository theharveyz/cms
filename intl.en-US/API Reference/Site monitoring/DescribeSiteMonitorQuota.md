# DescribeSiteMonitorQuota {#doc_api_Cms_DescribeSiteMonitorQuota .reference}

You can call this operation to query the quota and version of site monitoring.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides OpenAPI Explorer to simplify API usage. You can use [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorQuota) to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSiteMonitorQuota|The operation that you want to perform. Set this parameter to DescribeSiteMonitorQuota.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|Data| | |The quota data.

 |
|└SiteMonitorIdcQuota|Integer|5|The quota of detection points provided by Alibaba IDCs. The quota is 5 for free.

 |
|└SiteMonitorOperatorQuotaQuota|Integer|3|The quota of detection points provided by non-Alibaba IDCs. Default value: 0.

 |
|└SiteMonitorQuotaTaskUsed|Integer|6|The used quota of site monitoring tasks.

 |
|└SiteMonitorTaskQuota|Integer|10|The quota of site monitoring tasks.

 |
|└SiteMonitorVersion|String|V1|The version of site monitoring. The value can be V1 or V2.

 |
|Message|String|success|The error message.

 |
|RequestId|String|26860260-76C6-404E-AB7A-EB98D36A6885|The ID of the request.

 |
|Success|String|successful|Indicates whether the call was successful.

 |

## Examples {#demo .section}

Sample request

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSiteMonitorQuota
&<Common request parameters>

```

Sample success response

`XML` format

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

`JSON` format

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

## Error codes { .section}

[View error codes.](https://error-center.aliyun.com/status/product/Cms)

