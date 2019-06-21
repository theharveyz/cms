# PutMonitorGroupDynamicRule {#doc_api_Cms_PutMonitorGroupDynamicRule .reference}

You can call this operation to create or modify the dynamic rules of an application group. Resources that meet the rules are automatically added to the application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=PutMonitorGroupDynamicRule) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PutMonitorGroupDynamicRule|The operation that you want to perform. Set the value to PutMonitorGroupDynamicRule.

 |
|GroupId|Long|Yes|1234|The ID of the application group.

 |
|GroupRules.N.Category|String|No|ecs|The abbreviation of the service name to which the dynamic rules apply. Valid values: ecs, rds, and slb. The value of N is an integer greater than or equal to 1.

 |
|GroupRules.N.FilterRelation|String|No|and|The logical condition between dynamic rules. Valid values:

 -   and: The instances that meet all the dynamic rules are automatically added to the application group.
-   or: The instances that meet any of the dynamic rules are automatically added to the application group.

 The value of N is an integer greater than or equal to 1.

 |
|GroupRules.N.Filters.N.Function|String|No|contains|The instance filtering condition. Valid values:

 -   contains: inclusion
-   startWith: prefix
-   endWith: suffix

 Valid values of N: 1 to 3.

 |
|GroupRules.N.Filters.N.Name|String|No|hostName|The name of the instance. It specifies the field name to be matched. Valid value: hostName. Valid values of N: 1 to 3.

 |
|GroupRules.N.Filters.N.Value|String|No|nginx|The value of the condition. Valid values of N: 1 to 3.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|3E73F1AB-D195-438A-BCA7-2F4355789C58|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=PutMonitorGroupDynamicRule
&GroupId=1234
&GroupRules. 1.Category=ecs
&GroupRules. 1.FilterRelation=and
&GroupRules. 1.Filters. 1.Function=contains
&GroupRules. 1.Filters. 1.1ame=hostName
&GroupRules. 1.Filters. 1.Value=nginx
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<PutMonitorGroupDynamicRuleResponse> 
  <RequestId>3E73F1AB-D195-438A-BCA7-2F4355789C58</RequestId> 
  <Success>true</Success> 
  <Code>200</Code>
</PutMonitorGroupDynamicRuleResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"3E73F1AB-D195-438A-BCA7-2F4355789C58",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

