# DeleteMetricRuleTemplate {#doc_api_Cms_DeleteMetricRuleTemplate .reference}

You can call this operation to delete an alert rule template.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMetricRuleTemplate) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|TemplateId|String|Yes|12345|The ID of the alert template.

 |
|Action|String|No|DeleteMetricRuleTemplate|The operation that you want to perform. Set the value to DeleteMetricRuleTemplate.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|7B63F8CF-D48D-4608-A402-04FB5B2B4B6A|The request ID for troubleshooting.

 |
|Resource| | |The deleted template.

 |
|└TemplateId|String|123|The ID of the template.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteMetricRuleTemplate
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteMetricRuleTemplateResponse>
  <Resource>
    <TemplateId>123</TemplateId>
  </Resource>
  <RequestId>7B63F8CF-D48D-4608-A402-04FB5B2B4B6A</RequestId> 
  <Success>true</Success> 
  <Code>200</Code>
</DeleteMetricRuleTemplateResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Resource":{
		"TemplateId":123
	},
	"RequestId":"7B63F8CF-D48D-4608-A402-04FB5B2B4B6A",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

