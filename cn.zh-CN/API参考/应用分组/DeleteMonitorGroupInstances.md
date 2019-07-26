# DeleteMonitorGroupInstances {#doc_api_Cms_DeleteMonitorGroupInstances .reference}

删除应用分组内的资源实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DeleteMonitorGroupInstances&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteMonitorGroupInstances|系统规定参数。取值：DeleteMonitorGroupInstances。

 |
|Category|String|是|ecs|资源实例所属的云产品名称缩写，如下：

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
|GroupId|Long|是|123456|应用分组ID。

 |
|InstanceIdList|String|是|i-a2d5q7pm3f912\*\*\*\*,i-a2d5q7pm3f222\*\*\*\*|需要删除的实例，多个实例之间用英文逗号分隔开。一次最多能够删除20个。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|5351B0F2-26A9-4BC9-87FF-1B74034D12C3|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteMonitorGroupInstances
&Category=ecs
&GroupId=123456
&InstanceIdList=i-a2d5q7pm3f912****,i-a2d5q7pm3f222****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteMonitorGroupInstancesResponse>
      <RequestId>C5C6924C-237E-40B2-9510-41BF8F671102</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</DeleteMonitorGroupInstancesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C5C6924C-237E-40B2-9510-41BF8F671102",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

