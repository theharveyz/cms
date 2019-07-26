# DescribeMonitorGroupInstances {#doc_api_Cms_DescribeMonitorGroupInstances .reference}

查询指定应用分组内包含的资源列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupInstances&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|GroupId|Long|是|12345|应用分组ID。

 |
|Action|String|否|DescribeMonitorGroupInstances|系统规定参数。取值：DescribeMonitorGroupInstances。

 |
|Category|String|否|ECS|产品名称缩写，目前支持的产品有：

 -   ECS\(包括阿里云和非阿里云主机\),
-   RDS（云数据库RDS版\),
-   ADS（分析型数据库）,
-   SLB\(负载均衡\),
-   VPC（弹性IP）,
-   APIGATEWAY\(API网关\),
-   CDN,
-   CS（容器服务Swarm版）,
-   DCDN\(全站加速\),
-   DDOS,
-   EIP\(弹性公网IP\),
-   ELASTICSEARCH,
-   EMR\(E-MapReduce\),
-   ESS\(弹性伸缩\),
-   HBASE,
-   IOT\_EDGE\(iot边缘计算\),
-   K8S\_POD\(k8s pod\),
-   KVSTORE\_SHARDING\(Redis集群版）, - KVSTORE\_SPLITRW\(Redis读写分离版\),
-   KVSTORE\_STANDARD\(Redis标准版\),
-   MEMCACHE,MNS\(消息服务\),
-   MONGODB\(MongoDB 副本实例\),
-   MONGODB\_CLUSTER\(MongoDB集群版本\),
-   MONGODB\_SHARDING\(mongodb 分片集群\),
-   MQ\_TOPIC\(消息服务TOPIC）, - OCS, - OPENSEARCH,OSS\(对象存储OSS）, - POLARDB,PETADATA,SCDN\(安全加速\),
-   SHAREBANDWIDTHPACKAGES\(共享带宽包\),
-   SLS（日志服务\),
-   VPN\(VPN网关\)。

 |
|InstanceIds|String|否|i-x1234568|按照实例ID搜索。

 |
|Keyword|String|否|s1|按照实例名称模糊查询。

 |
|PageNumber|Integer|否|1|页码，默认值是1。

 |
|PageSize|Integer|否|10|每页显示记录条数，默认值是10。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|PageNumber|Integer|1|页码。

 |
|PageSize|Integer|10|每页记录条数。

 |
|RequestId|String|97F2A410-9412-499C-9AD1-76EF7EC02DF2|请求ID，用于排查问题。

 |
|Resources| | |应用分组资源的描述信息。

 |
|Category|String|ecs|产品名称缩写，目前支持的产品有：

 -   ECS\(包括阿里云和非阿里云主机\),
-   RDS（云数据库RDS版\),
-   ADS（分析型数据库）,
-   SLB\(负载均衡\),
-   VPC（弹性IP）,
-   APIGATEWAY\(API网关\),
-   CDN,
-   CS（容器服务Swarm版）,
-   DCDN\(全站加速\),
-   DDOS,
-   EIP\(弹性公网IP\),
-   ELASTICSEARCH,
-   EMR\(E-MapReduce\),
-   ESS\(弹性伸缩\),
-   HBASE,
-   IOT\_EDGE\(iot边缘计算\),
-   K8S\_POD\(k8s pod\),
-   KVSTORE\_SHARDING\(Redis集群版）, - KVSTORE\_SPLITRW\(Redis读写分离版\),
-   KVSTORE\_STANDARD\(Redis标准版\),
-   MEMCACHE,MNS\(消息服务\),
-   MONGODB\(MongoDB 副本实例\),
-   MONGODB\_CLUSTER\(MongoDB集群版本\),
-   MONGODB\_SHARDING\(mongodb 分片集群\),
-   MQ\_TOPIC\(消息服务TOPIC）, - OCS, - OPENSEARCH,OSS\(对象存储OSS）, - POLARDB,PETADATA,SCDN\(安全加速\),
-   SHAREBANDWIDTHPACKAGES\(共享带宽包\),
-   SLS（日志服务\),
-   VPN\(VPN网关\)。

 |
|Id|Long|12345|资源ID。

 |
|InstanceId|String|i-2ze3w55tr2r\*\*\*\*|实例ID，实例的唯一标识。

 |
|InstanceName|String|hostIP|实例名称。

 |
|RegionId|String|cn-hangzhou|实例对应的地域（RegionId）。

 |
|Success|Boolean|true|是否成功。

 |
|Total|Integer|12|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitorGroupInstances
&GroupId=12345
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

