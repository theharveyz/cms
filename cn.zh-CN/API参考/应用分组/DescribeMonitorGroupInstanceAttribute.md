# DescribeMonitorGroupInstanceAttribute {#doc_api_Cms_DescribeMonitorGroupInstanceAttribute .reference}

查询应用分组的资源实例详情。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupInstanceAttribute&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|GroupId|Long|是|12345|应用分组ID。

 |
|Action|String|否|DescribeMonitorGroupInstanceAttribute|系统规定参数。取值：DescribeMonitorGroupInstanceAttribute。

 |
|Category|String|否|ecs|资源实例所属的云产品名称缩写，如下：

 -   ECS（包括阿里云和非阿里云主机），
-   RDS（云数据库RDS版），
-   ADS（分析型数据库），
-   SLB（负载均衡），
-   VPC（弹性IP），
-   APIGATEWAY（API网关），
-   CDN，
-   CS（容器服务Swarm版），
-   DCDN（全站加速），
-   DDOS，
-   EIP（弹性公网IP），
-   ELASTICSEARCH，
-   EMR（E-MapReduce），
-   ESS（弹性伸缩），
-   HBASE，
-   IOT\_EDGE（iot边缘计算），
-   K8S\_POD（k8s pod），
-   KVSTORE\_SHARDING（Redis集群版），
-   KVSTORE\_SPLITRW（Redis读写分离版），
-   KVSTORE\_STANDARD（Redis标准版），
-   MEMCACHE，
-   MNS（消息服务），
-   MONGODB（MongoDB 副本实例），
-   MONGODB\_CLUSTER（MongoDB集群版本），
-   MONGODB\_SHARDING（MongoDB分片集群），
-   MQ\_TOPIC（消息服务TOPIC），
-   OCS（旧版云数据库Memcache），
-   OPENSEARCH（开放搜索），
-   OSS（对象存储OSS），
-   POLARDB，
-   PETADATA（HybridDB for MySQL），
-   SCDN（安全加速），
-   SHAREBANDWIDTHPACKAGES（共享带宽包），
-   SLS（日志服务），
-   VPN（VPN网关\)。

 |
|InstanceIds|String|否|rm-bp18j902q1h12\*\*\*\*,rm-bp18j902q1h1\*\*\*\*|按照多实例搜索，多个实例之间用逗号分隔。一次最多可以删除20个。

 |
|Keyword|String|否|i-123|按照实例ID模糊搜索

 |
|PageNumber|Integer|否|1|分页页码，默认值为1。

 |
|PageSize|Integer|否|10|每页显示记录条数。

 |
|Total|Boolean|否|true|总记录条数。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|返回错误信息。

 |
|PageNumber|Integer|1|页码。

 |
|PageSize|Integer|2|总页数。

 |
|Total|Integer|12|总记录条数。

 |
|Resources| | |关联资源描述。

 |
|Category|String|ecs|产品名称缩写，如下：

 -   ECS（包括阿里云和非阿里云主机），
-   RDS（云数据库RDS版），
-   ADS（分析型数据库），
-   SLB（负载均衡），
-   VPC（弹性IP），
-   APIGATEWAY（API网关），
-   CDN，
-   CS（容器服务Swarm版），
-   DCDN（全站加速），
-   DDOS，
-   EIP（弹性公网IP），
-   ELASTICSEARCH，
-   EMR（E-MapReduce），
-   ESS（弹性伸缩），
-   HBASE，
-   IOT\_EDGE（iot边缘计算），
-   K8S\_POD（k8s pod），
-   KVSTORE\_SHARDING（Redis集群版），
-   KVSTORE\_SPLITRW（Redis读写分离版），
-   KVSTORE\_STANDARD（Redis标准版），
-   MEMCACHE，
-   MNS（消息服务），
-   MONGODB（MongoDB 副本实例），
-   MONGODB\_CLUSTER（MongoDB集群版本），
-   MONGODB\_SHARDING（MongoDB分片集群），
-   MQ\_TOPIC（消息服务TOPIC），
-   OCS（旧版云数据库Memcache），
-   OPENSEARCH（开放搜索），
-   OSS（对象存储OSS），
-   POLARDB，
-   PETADATA（HybridDB for MySQL），
-   SCDN（安全加速），
-   SHAREBANDWIDTHPACKAGES（共享带宽包），
-   SLS（日志服务），
-   VPN（VPN网关\)。

 |
|Desc|String|desc\_test|描述信息。

 |
|Dimension|String|\{"instanceId":"xxx"\}|关联的维度信息。

 |
|InstanceId|String|rm-bp179a8xfaz4i\*\*\*\*|实例ID。

 |
|InstanceName|String|hostName|实例名称。

 |
|NetworkType|String|vpc|网络类型。

 |
|Region| | |区域。

 |
|AvailabilityZone|String|cn-hangzhou-f|可用区。

 |
|RegionId|String|cn-hangzhou|RegionId。

 |
|Tags| | |实例详细信息，每个属性字段名为key，属性值为value。

 |
|Key|String|instanceNetworkType|字段名。

 |
|Value|String|VPC|字段值。

 |
|Vpc| | |针对VPC实例增加的描述信息。

 |
|VpcInstanceId|String|vpc-2zew7etgiceg21\*\*\*\*|VPC实例ID。

 |
|VswitchInstanceId|String|vsw-2ze36seq79n992\*\*\*\*|Vswitch实例ID。

 |
|Success|Boolean|true|是否成功。

 |
|RequestId|String|9FB8EA79-7279-4482-8D6D-3D28EEDD871A|请求ID，用于排查问题。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitorGroupInstanceAttribute
&GroupId=12345
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

