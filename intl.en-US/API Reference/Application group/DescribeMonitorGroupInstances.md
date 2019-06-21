# DescribeMonitorGroupInstances {#doc_api_Cms_DescribeMonitorGroupInstances .reference}

You can call this operation to query the list of resources contained in a specified application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupInstances) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|GroupId|Long|Yes|12345|The ID of the application group.

 |
|Action|String|No|DescribeMonitorGroupInstances|The operation that you want to perform. Set the value to DescribeMonitorGroupInstances.

 |
|Category|String|No|ECS|The abbreviation of the service name. Valid values:

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
-   KVSTORE\_SHARDING \(ApsaraDB RDS for Redis cluster version\) KVSTORE\_SPLITRW \(ApsaraDB RDS for Redis read/write splitting version\)
-   KVSTORE\_STANDARD \(ApsaraDB RDS for Redis standard version\)
-   MEMCACHE \(ApsaraDB RDS for Memcache\) MNS \(Message Service\)
-   MONGODB \(ApsaraDB RDS for MongoDB replica set instances\)
-   MONGODB\_CLUSTER \(ApsaraDB RDS for MongoDB cluster version\)
-   MONGODB\_SHARDING \(ApsaraDB RDS for MongoDB sharded clusters\)
-   MQ\_TOPIC \(Message Service topic\) OCS \(original version of ApsaraDB RDS for Memcache\) OPENSEARCH \(Open Search\) OSS \(Object Storage Service\) POLARDB \(ApsaraDB for POLARDB\) PETADATA \(HybridDB for MySQL\) SCDN \(Secure Content Delivery Network\)
-   SHAREBANDWIDTHPACKAGES \(shared bandwidth package\)
-   SLS \(Log Service\)
-   VPN \(VPN Gateway\)

 |
|InstanceIds|String|No|i-x1234568|The IDs of instances, separated with commas \(,\). You can search for multiple instances by specifying multiple IDs.

 |
|Keyword|String|No|s1|The name of the instance. You can perform fuzzy search based on the instance name.

 |
|PageNumber|Integer|No|1|The number of the page. Default value: 1.

 |
|PageSize|Integer|No|10|The number of records per page. Default value: 10.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200|The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success|The error message.

 |
|PageNumber|Integer|1|The number of the page.

 |
|PageSize|Integer  |10|The number of records on each page.

 |
|RequestId|String|97F2A410-9412-499C-9AD1-76EF7EC02DF2|The request ID for troubleshooting.

 |
|Resources| | |The description of the application group resource.

 |
|└Category|String|ecs|The abbreviation of the service name. Valid values:

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
-   KVSTORE\_SHARDING \(ApsaraDB RDS for Redis cluster version\) KVSTORE\_SPLITRW \(ApsaraDB RDS for Redis read/write splitting version\)
-   KVSTORE\_STANDARD \(ApsaraDB RDS for Redis standard version\)
-   MEMCACHE \(ApsaraDB RDS for Memcache\) MNS \(Message Service\)
-   MONGODB \(ApsaraDB RDS for MongoDB replica set instances\)
-   MONGODB\_CLUSTER \(ApsaraDB RDS for MongoDB cluster version\)
-   MONGODB\_SHARDING \(ApsaraDB RDS for MongoDB sharded clusters\)
-   MQ\_TOPIC \(Message Service topic\) OCS \(original version of ApsaraDB RDS for Memcache\) OPENSEARCH \(Open Search\) OSS \(Object Storage Service\) POLARDB \(ApsaraDB for POLARDB\) PETADATA \(HybridDB for MySQL\) SCDN \(Secure Content Delivery Network\)
-   SHAREBANDWIDTHPACKAGES \(shared bandwidth package\)
-   SLS \(Log Service\)
-   VPN \(VPN Gateway\)

 |
|└Id|Long|12345|The ID of the resource.

 |
|└InstanceId|String|i-2ze3w55tr2r\*\*\*\*|The unique ID of the instance.

 |
|└InstanceName|String|hostIP|The name of the instance.

 |
|└RegionId|String|cn-hangzhou|The region where the instance is deployed.

 |
|Success|Boolean|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|Total|Integer|12|The total number of returned records.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitorGroupInstances
&GroupId=12345
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitorGroupInstancesResponse>
  <PageNumber>1</PageNumber> 
  <PageSize>30</PageSize>
  <RequestId>7670220A-0725-42EE-9252-8200C4F810D9</RequestId>
  <Success>true</Success>
  <Code>200</Code>
  <Total>1</Total> 
  <Resources>
    <Resource>
      <Category>ECS</Category>
      <InstanceId>i-2ze3w55tr2rcpejp****</InstanceId>
      <RegionId>cn-beijing</RegionId> 
      <InstanceName>dynamic_group_1</InstanceName>
    </Resource>
  </Resources>
</DescribeMonitorGroupInstancesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"PageSize":30,
	"RequestId":"7670220A-0725-42EE-9252-8200C4F810D9",
	"Success":true,
	"Code":200,
	"Total":1,
	"Resources":{
		"Resource":[
			{
				"Category":"ECS",
				"RegionId":"cn-beijing",
				"InstanceId":"i-2ze3w55tr2rcpejp****",
				"InstanceName":"dynamic_group_1"
			}
		]
	}
}
```

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

