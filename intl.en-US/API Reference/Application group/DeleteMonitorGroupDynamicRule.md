# DeleteMonitorGroupDynamicRule {#doc_api_Cms_DeleteMonitorGroupDynamicRule .reference}

You can call this operation to delete the dynamic rules of an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMonitorGroupDynamicRule) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Category|String|Yes|ecs|The cloud service name corresponding to the dynamic rules. Valid values: ECS, RDS, and SLB.

 |
|GroupId|Long|Yes|12345|The ID of the application group.

 |
|Action|String|No|DeleteMonitorGroupDynamicRule|The operation that you want to perform. Set the value to DeleteMonitorGroupDynamicRule.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The returned information.

 |
|RequestId|String|56B4516A-EB44-4C66-8854-0393B35F636B|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteMonitorGroupDynamicRule
&Category=ecs
&GroupId=12345
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteMonitorGroupDynamicRuleResponse>
  <RequestId>56B4516A-EB44-4C66-8854-0393B35F636B</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DeleteMonitorGroupDynamicRuleResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"56B4516A-EB44-4C66-8854-0393B35F636B",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

