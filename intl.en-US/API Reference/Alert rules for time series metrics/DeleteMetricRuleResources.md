# DeleteMetricRuleResources {#doc_api_Cms_DeleteMetricRuleResources .reference}

You can call this operation to delete resources associated with an alert rule.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMetricRuleResources) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteMetricRuleResources|The operation that you want to perform. Set the value to DeleteMetricRuleResources.

 |
|Resources|String|Yes|\[\{"instanceId":"\*\*\*\*\*ixxxId1"\}\]|The resources to associate with the alert rule. Specify the value as a JSON array, such as

 ```

[{"instanceId":"*****ixxxId1"}].

```

 |
|RuleId|String|Yes|i-2ze3w55tr2rcpejpcfap\_59\*\*\*\*\*\*1|The ID of the alert rule.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the operation is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|D8A35882-90C6-4F03-BBEB-153C180398EA|The ID of the request, which can be used for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the operation is successful.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteMetricRuleResources
&Resources=[{"instanceId":"*****ixxxId1"}]
&RuleId=i-2ze3w55tr2rcpejpcfap_59******1
&<Common request parameters>

```

Sample successful responses

`XML` format

``` {#xml_return_success_demo}
<CreateMetricRuleResourcesResponse>
  <RequestId>0671A721-0D7A-4F11-BB77-2416325D65AB</RequestId>
  <Success>true</Success>
  <Code>200</Code>
  <Message>success</Message>
</CreateMetricRuleResourcesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"0671A721-0D7A-4F11-BB77-2416325D65AB",
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

