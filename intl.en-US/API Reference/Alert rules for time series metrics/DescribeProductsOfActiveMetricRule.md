# DescribeProductsOfActiveMetricRule {#doc_api_Cms_DescribeProductsOfActiveMetricRule .reference}

You can call this operation to obtain the list of services for which one-click alert is enabled.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeProductsOfActiveMetricRule) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeProductsOfActiveMetricRule|The operation that you want to perform. Set the value to DescribeProductsOfActiveMetricRule.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Datapoints|String|ecs,rds|The list of services for which one-click alert is enabled. Multiple services must be separated with commas \(,\). Valid values:

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
|Message|String|success|The error message.

 |
|RequestId|String|F82E6667-7811-4BA0-842F-5B2DC42BBAAD|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeProductsOfActiveMetricRule
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeProductsOfActiveMetricRuleResponse>
  <Code>200</Code>
  <Success>true</Success> 
  <Datapoints>rds,slb</Datapoints>
  <RequestId>F82E6667-7811-4BA0-842F-5B2DC42BBAAD</RequestId>
</DescribeProductsOfActiveMetricRuleResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Datapoints":"rds,slb",
	"RequestId":"F82E6667-7811-4BA0-842F-5B2DC42BBAAD",
	"Success":true,
	"Code":"200"
}
```

## Error code { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

