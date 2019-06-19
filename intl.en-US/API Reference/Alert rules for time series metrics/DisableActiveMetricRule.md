# DisableActiveMetricRule {#doc_api_Cms_DisableActiveMetricRule .reference}

You can call this operation to disable one-click alert.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DisableActiveMetricRule) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DisableActiveMetricRule|The operation that you want to perform. Set the value to DisableActiveMetricRule.

 |
|Product|String|Yes|ecs|The name of the service that supports one-click alert. Valid values:

 -   ecs \(Elastic Compute Service\)
-   rds \(ApsaraDB for RDS\)
-   slb \(Server Load Balancer\)
-   redis\_standard \(ApsaraDB RDS for Redis standard version\)
-   redis\_sharding \(ApsaraDB RDS for Redis cluster version\)
-   redis\_splitrw \(ApsaraDB RDS for Redis read/write splitting version\)
-   mongodb \(ApsaraDB RDS for MongoDB replica set instances\)
-   mongodb\_sharding \(ApsaraDB RDS for MongoDB sharded clusters\)
-   hbase \(ApsaraDB for HBase\)
-   elasticsearch \(Elasticsearch\)
-   opensearch \(Open Search\)

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|F82E6667-7811-4BA0-842F-5B2DC42BBAAD|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DisableActiveMetricRule
&Product=ecs
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DisableActiveMetricRuleResponse>
  <Code>200</Code>
  <Success>true</Success> 
  <Message>success</Message>
  <RequestId>55850888-9CCE-4FD5-B949-5F8947D63929</RequestId>
</DisableActiveMetricRuleResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"success",
	"RequestId":"55850888-9CCE-4FD5-B949-5F8947D63929",
	"Success":true,
	"Code":"200"
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

