# DeleteMonitorGroupInstances {#doc_api_Cms_DeleteMonitorGroupInstances .reference}

You can call this operation to delete resource instances from an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DeleteMonitorGroupInstances) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteMonitorGroupInstances|The operation that you want to perform. Set the value to DeleteMonitorGroupInstances.

 |
|Category|String|Yes|ecs|The abbreviation of the service name. Valid values:

 -   ECS \(including Alibaba Cloud and non-Alibaba Cloud hosts\)
-   RDS \(ApsaraDB for RDS\)
-   ADS \(AnalyticDB\)
-   SLB \(Server Load Balancer\)
-   VPC \(Virtual Private Cloud\)
-   APIGATEWAY \(API Gateway\)
-   CDN
-   CS \(Container Service for Swarm\)
-   DCDN \(Dynamic Route for CDN \)
-   DDOS \(distributed denial of service\)
-   EIP \(Elastic IP\)
-   ELASTICSEARCH \(Elasticsearch\)
-   EMR \(E-MapReduce\)
-   ESS \(Auto Scaling\)
-   HBASE \(ApsaraDB for HBase\)
-   IOT\_EDGE \(IoT Edge\)
-   K8S\_POD \(k8s pod \)
-   KVSTORE\_SHARDING \(ApsaraDB RDS for Redis cluster version\)
-   KVSTORE\_SPLITRW \(ApsaraDB RDS for Redis read/write splitting version\)
-   KVSTORE\_STANDARD \(ApsaraDB RDS for Redis standard version\)
-   MEMCACHE \(ApsaraDB RDS for Memcache\)
-   MNS \(Message Service\)
-   MONGODB \(ApsaraDB RDS for MongoDB replica set instances\)
-   MONGODB\_CLUSTER \(ApsaraDB RDS for MongoDB cluster version\)
-   MONGODB\_SHARDING \(ApsaraDB RDS for MongoDB sharded clusters\)
-   MQ\_TOPIC \(Message Service topic\)
-   OCS \(old version ApsaraDB RDS for Memcache\)
-   OPENSEARCH \(Open Search\)
-   OSS \(Object Storage Service\)
-   POLARDB \(ApsaraDB for POLARDB\)
-   PETADATA \(HybridDB for MySQL\)
-   SCDN \(Secure Content Delivery Network\)
-   SHAREBANDWIDTHPACKAGES \(shared bandwidth package\)
-   SLS \(Log Service\)
-   VPN \(VPN Gateway \)

 |
|GroupId|Long|Yes|123456|The ID of the application group.

 |
|InstanceIdList|String|Yes|i-a2d5q7pm3f912\*\*\*\*,i-a2d5q7pm3f222\*\*\*\*|The instances to be deleted, separated with commas \(,\). Up to 20 instances can be deleted at a time.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|RequestId|String|5351B0F2-26A9-4BC9-87FF-1B74034D12C3|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteMonitorGroupInstances
&Category=ecs
&GroupId=123456
&InstanceIdList=i-a2d5q7pm3f912****,i-a2d5q7pm3f222****
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteMonitorGroupInstancesResponse>
  <RequestId>C5C6924C-237E-40B2-9510-41BF8F671102</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DeleteMonitorGroupInstancesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"C5C6924C-237E-40B2-9510-41BF8F671102",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

