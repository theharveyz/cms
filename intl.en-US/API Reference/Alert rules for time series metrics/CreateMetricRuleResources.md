# CreateMetricRuleResources {#doc_api_Cms_CreateMetricRuleResources .reference}

You can call this operation to create a resource associated with an alert rule.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=CreateMetricRuleResources) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|CreateMetricRuleResources|The operation that you want to perform. Set the value to CreateMetricRuleResources.

 |
|Overwrite|String|Yes|false|Specifies whether to overwrite previously associated resources. Default value: false.

 -   true: overwrites previously associated resources.
-   false: does not overwrite previously associated resources.

 |
|Resources|String|Yes|\[\{"instanceId":"i-a2d5q7pm3f9yr29eaqzm"\}\]|The resources to associate with the alert rule. Specify the value as a JSON array, such as

 ```

[{"instanceId":"*****ixxxId1"}]

```

 You can add up to 100 resources each time. Up to 3,000 resources can be associated with an alert rule.

 |
|RuleId|String|Yes|i-2ze3w55tr2rcpejpcfap\_59c96b85-0339-4f35-ba66-ae4e34d34347|The ID of the alert rule.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the operation is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|0671A721-0D7A-4F11-BB77-2416325D65AB|The ID of the request, which can be used for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the operation is successful.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateMetricRuleResources
&Overwrite=false
&Resources=[{"instanceId":"i-a2d5q7pm3f9yr29eaqzm"}]
&RuleId=i-2ze3w55tr2rcpejpcfap_59c96b85-0339-4f35-ba66-ae4e34d34347
&<Common request parameters>

```

Sample successful responses

`XML` format

``` {#xml_return_success_demo}
<CreateMetricRuleResourcesResponse>
  <RequestId>0671A721-0D7A-4F11-BB77-2416325D65AB</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</CreateMetricRuleResourcesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"0671A721-0D7A-4F11-BB77-2416325D65AB",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

