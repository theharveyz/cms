# DescribeMonitorGroupInstanceAttribute {#doc_api_Cms_DescribeMonitorGroupInstanceAttribute .reference}

You can call this operation to query the resource instance details of an application group.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupInstanceAttribute) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|GroupId|Long|Yes|12345| The ID of the application group.

 |
|Action|String|No|DescribeMonitorGroupInstanceAttribute| The operation that you want to perform. Set the value to DescribeMonitorGroupInstanceAttribute.

 |
|Category|String|No|ecs| The abbreviation of the service name. Valid values:

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
|InstanceIds|String|No|rm-bp18j902q1h12\*\*\*\*,rm-bp18j902q1h1\*\*\*\*| The IDs of instances, separated with commas \(,\). You can search for multiple instances by specifying multiple IDs. Up to 20 instances can be deleted in a single request.

 |
|Keyword|String|No|i-123| The ID of the instance. You can perform fuzzy search based on the instance ID.

 |
|PageNumber|Integer|No|1| The number of the page. Default value: 1.

 |
|PageSize|Integer|No|10| The number of records on each page.

 |
|Total|Boolean|No|true| The total number of returned records.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|Integer|200| The status code. A value of 200 indicates that the call is successful.

 |
|Message|String|success| The error message.

 |
|PageNumber|Integer|1| The number of the page.

 |
|PageSize|Integer|2| The total number of returned pages.

 |
|Total|Integer|12| The total number of returned records.

 |
|Resources| | | The description of associated resources.

 |
|└Category|String|ecs| The abbreviation of the service name. Valid values:

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
|└Desc|String|desc\_test| The description.

 |
|└Dimension|String|\{"instanceId":"xxx"\}| The associated dimension.

 |
|└InstanceId|String|rm-bp179a8xfaz4i\*\*\*\*| The ID of the instance.

 |
|└InstanceName|String|hostName| The name of the instance.

 |
|└NetworkType|String|vpc| The type of the network.

 |
|└Region| | | The region.

 |
|└AvailabilityZone|String|cn-hangzhou-f| The zone.

 |
|└RegionId|String|cn-hangzhou| The ID of the region.

 |
|└Tags| | | The details of the instance. The name field of an attribute is a key and the value field of an attribute is a value.

 |
|└Key|String|instanceNetworkType| The name of the field.

 |
|└Value|String|VPC| The value of the field.

 |
|└Vpc| | | The special description for VPC instances.

 |
|└VpcInstanceId|String|vpc-2zew7etgiceg21\*\*\*\*| The ID of the VPC instance.

 |
|└VswitchInstanceId|String|vsw-2ze36seq79n992\*\*\*\*| The ID of the VSwitch instance.

 |
|Success|Boolean|true| Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |
|RequestId|String|9FB8EA79-7279-4482-8D6D-3D28EEDD871A| The request ID for troubleshooting.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeMonitorGroupInstanceAttribute
&GroupId=12345
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeMonitorGroupInstanceAttributeResponse>
  <PageNumber>1</PageNumber> 
  <PageSize>30</PageSize>
  <RequestId>7DB8DA3D-EDA6-46F8-9222-70C52416AE7D</RequestId>
  <Success>true</Success> 
  <Code>200</Code>
  <Total>1</Total> 
  <Resources>
    <Resource>
      <Vpc> 
        <VswitchInstanceId>vsw-bp1ns8xa****</VswitchInstanceId>
        <VpcInstanceId>vpc-bp12bzgjdj33****</VpcInstanceId>
      </Vpc> 
      <Tags>
        <Tag>
          <Value>12345</Value>
          <Key>aliUid</Key>
        </Tag> 
        <Tag>
          <Value>26842</Value>
          <Key>bid</Key>
        </Tag> 
        <Tag> 
          <Value>0</Value>
          <Key>levelId</Key>
        </Tag> 
        <Tag> 
          <Value>test_name</Value>
          <Key>description</Key>
        </Tag> 
        <Tag> 
          <Value>1540195308000</Value>
          <Key>gmtModified</Key>
        </Tag> 
        <Tag> 
          <Value>1538036293000</Value>
          <Key>gmtCreated</Key>
        </Tag> 
        <Tag>
          <Value>1569572293000</Value>
          <Key>endTime</Key>
        </Tag>
        <Tag>
          <Value>1</Value>
          <Key>dbInstanceId</Key>
        </Tag>
        <Tag>
          <Value>cn-hangzhou</Value>
          <Key>region</Key>
        </Tag>
        <Tag>
          <Value>MySQL</Value>
          <Key>engine</Key>
        </Tag>
        <Tag>
          <Value>5.7</Value>
          <Key>engineVersion</Key>
        </Tag>
        <Tag>
          <Value>x</Value>
          <Key>dbInstanceType</Key>
        </Tag>
      </Tags>
      <NetworkType>VPC</NetworkType>
      <Category>RDS</Category>
      <Region> 
        <RegionId>cn-hangzhou</RegionId> 
        <AvailabilityZone>cn-hangzhou-MAZ8(f,g)</AvailabilityZone>
      </Region> 
      <AliUid>127067667954****</AliUid>
      <InstanceId>rm-bp179a8xfaz4i****</InstanceId>
      <Dimension>{"userId":"127067667954****","instanceId":"rm-bp179a8xfaz4i****"}</Dimension>
      <Desc>test_name</Desc>
      <InstanceName>test_name</InstanceName>
    </Resource>
  </Resources>
</DescribeMonitorGroupInstanceAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"PageSize":30,
	"RequestId":"7DB8DA3D-EDA6-46F8-9222-70C52416AE7D",
	"Success":true,
	"Code":200,
	"Total":1,
	"Resources":{
		"Resource":[
			{
				"Vpc":{
					"VswitchInstanceId":"vsw-bp1ns8xa****",
					"VpcInstanceId":"vpc-bp12bzgjdj33****"
				},
				"NetworkType":"VPC",
				"Tags":{
					"Tag":[
						{
							"Value":"12345",
							"Key":"aliUid"
						},
						{
							"Value":"26842",
							"Key":"bid"
						},
						{
							"Value":"0",
							"Key":"levelId"
						},
						{
							"Value":"test_name",
							"Key":"description"
						},
						{
							"Value":"1540195308000",
							"Key":"gmtModified"
						},
						{
							"Value":"1538036293000",
							"Key":"gmtCreated"
						},
						{
							"Value":"1569572293000",
							"Key":"endTime"
						},
						{
							"Value":"1",
							"Key":"dbInstanceId"
						},
						{
							"Value":"rm-bp179a8xfaz4i61hx",
							"Key":"dbInstanceName"
						},
						{
							"Value":"cn-hangzhou",
							"Key":"region"
						},
						{
							"Value":"MySQL",
							"Key":"engine"
						},
						{
							"Value":"5.7",
							"Key":"engineVersion"
						},
						{
							"Value":"x",
							"Key":"dbInstanceType"
						}
					]
				},
				"Category":"RDS",
				"Region":{
					"RegionId":"cn-hangzhou",
					"AvailabilityZone":"cn-hangzhou-MAZ8(f,g)"
				},
				"AliUid":"127067667954****",
				"InstanceId":"rm-bp179a8xfaz4i****",
				"Dimension":"{\"userId\":\"127067667954****\",\"instanceId\":\"rm-bp179a8xfaz4i****\"}",
				"InstanceName":"test_name",
				"Desc":"test_name"
			}
		]
	}
}
```

## Error codes {#section_97q_nt3_v28 .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

