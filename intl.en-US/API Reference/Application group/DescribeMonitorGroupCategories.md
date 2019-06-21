# DescribeMonitorGroupCategories {#doc_api_Cms_DescribeMonitorGroupCategories .reference}

You can call this operation to query the list of service resources in an application group, and the number of instances that belong to each service in the application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupCategories) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeMonitorGroupCategories|The operation that you want to perform. Set the value to DescribeMonitorGroupCategories.

 |
|GroupId|Long|Yes|12345|The ID of the application group.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|MonitorGroupCategories| | |The service name of the instances in the application group.

 |
|└GroupId|Long|123456|The ID of the group.

 |
|└MonitorGroupCategory| | |The service name of the instances in the application group.

 |
|└Category|String|ECS|The abbreviation of the service name. Valid values:

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
-   EMR \(E-MapReduce \)
-   ESS \(Auto Scaling \)
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
-   VPN \(VPN Gateway\)

 |
|└Count|Integer|1|The number of instances for the service.

 |
|RequestId|String|9E0347B0-EBC3-4769-A78D-D96F21C6BB52|The request ID for troubleshooting.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitorGroupCategories
&GroupId=12345
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitorGroupCategoriesResponse>
  <MonitorGroupCategories>
    <MonitorGroupCategory>
      <Category>ECS</Category>
      <Count>1</Count>
    </MonitorGroupCategory>
  </MonitorGroupCategories>
  <RequestId>9E0347B0-EBC3-4769-A78D-D96F21C6BB52</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
</DescribeMonitorGroupCategoriesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"MonitorGroupCategories":{
		"MonitorGroupCategory":[
			{
				"Category":"ECS",
				"Count":1
			}
		]
	},
	"RequestId":"9E0347B0-EBC3-4769-A78D-D96F21C6BB52",
	"Success":true,
	"Code":200
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

