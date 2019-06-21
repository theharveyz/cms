# ModifyMonitorGroupInstances {#doc_api_Cms_ModifyMonitorGroupInstances .reference}

You can call this operation to modify resources in an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=ModifyMonitorGroupInstances) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyMonitorGroupInstances| The operation that you want to perform. Set the value to ModifyMonitorGroupInstances.

 |
|GroupId|Long|Yes|12345| The ID of the application group.

 |
|Instances.N.Category|String|No|ECS| The abbreviation of the service name. Valid values:

 -   ECS \(including Alibaba Cloud and non-Alibaba Cloud hosts\)
-   RDS \(ApsaraDB for RDS\)
-   ADS \(AnalyticDB\)
-   SLB \(Server Load Balancer\)
-   VPC \(Virtual Private Cloud\)
-   APIGATEWAY \(API Gateway\)
-   CDN
-   CS \(Container Service for Swarm\)
-   DCDN \(Dynamic Route for CDN\)
-   DDOS \(distributed denial of service\)
-   EIP \(Elastic IP\)
-   ELASTICSEARCH \(Elasticsearch\)
-   EMR \(E-MapReduce\)
-   ESS \(Auto Scaling\)
-   HBASE \(ApsaraDB for HBase\)
-   IOT\_EDGE \(IoT Edge\)
-   K8S\_POD \(k8s pod\)
-   KVSTORE\_SHARDING \(ApsaraDB RDS for Redis cluster version\)
-   KVSTORE\_SPLITRW \(ApsaraDB RDS for Redis read/write splitting version\)
-   KVSTORE\_STANDARD \(ApsaraDB RDS for Redis standard version\)
-   MEMCACHE \(ApsaraDB RDS for Memcache\)
-   MNS \(Message Service\)
-   MONGODB \(ApsaraDB RDS for MongoDB replica set instances\)
-   MONGODB\_CLUSTER \(ApsaraDB RDS for MongoDB cluster version\)
-   MONGODB\_SHARDING \(ApsaraDB RDS for MongoDB sharded clusters\)
-   MQ\_TOPIC \(Message Service topic\)
-   OCS \(original version of ApsaraDB RDS for Memcache\)
-   OPENSEARCH \(Open Search\)
-   OSS \(Object Storage Service\)
-   POLARDB \(ApsaraDB for POLARDB\)
-   PETADATA \(HybridDB for MySQL\)
-   SCDN \(Secure Content Delivery Network\)
-   SHAREBANDWIDTHPACKAGES \(shared bandwidth package\)
-   SLS \(Log Service\)
-   VPN \(VPN Gateway\)

 Valid values of N: 1 to 2000.

 |
|Instances.N.InstanceId|String|No|i-a2d5q7pm12\*\*\*\*| The ID of the resource instance. Valid values of N: 1 to 2000.

 |
|Instances.N.InstanceName|String|No|hoeName| The name of the instance. Valid values of N: 1 to 2000.

 |
|Instances.N.RegionId|String|No|cn-hangzhou| The ID of the region. Valid values of N: 1 to 2000.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200| The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success| The error message.

 |
|RequestId|String|FEC7EDB3-9B08-4AC0-A42A-329F5D14B95A| The request ID for troubleshooting.

 |
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=ModifyMonitorGroupInstances
&GroupId=12345
&Instances. 1.Category=ECS
&Instances. 1.InstanceId=i-a2d5q7pm12****
&Instances. 1.InstanceName=hoeName
&Instances. 1.RegionId=cn-hangzhou
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<ModifyMonitorGroupInstancesResponse>
  <RequestId>02977C39-9E74-430A-B35B-04CFBF0E7F64</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</ModifyMonitorGroupInstancesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"02977C39-9E74-430A-B35B-04CFBF0E7F64",
	"Success":true,
	"Code":200
}
```

## Error codes {#section_18n_qyl_imc .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

