# ModifyMonitorGroupInstances {#doc_api_Cms_ModifyMonitorGroupInstances .reference}

修改应用分组中的资源。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=ModifyMonitorGroupInstances&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyMonitorGroupInstances|系统规定参数。取值：ModifyMonitorGroupInstances。

 |
|GroupId|Long|是|12345|应用分组ID。

 |
|Instances.N.Category|String|否|ECS|资源实例所属的云产品名或者产品的规格，目前支持的产品有：

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
-   KVSTORE\_SHARDING（Redis集群版）,
-   KVSTORE\_SPLITRW（Redis读写分离版），
-   KVSTORE\_STANDARD（Redis标准版），
-   MEMCACHE，
-   MNS（消息服务），
-   MONGODB（MongoDB 副本实例），
-   MONGODB\_CLUSTER（MongoDB集群版本），
-   MONGODB\_SHARDING（mongodb 分片集群），
-   MQ\_TOPIC（消息服务TOPIC），
-   OCS，
-   OPENSEARCH，
-   OSS（对象存储OSS），
-   POLARDB，
-   PETADATA，
-   SCDN（安全加速），
-   SHAREBANDWIDTHPACKAGES（共享带宽包），
-   SLS（日志服务），
-   VPN（VPN网关\)。

 N 的取值范围为 1~2000。

 |
|Instances.N.InstanceId|String|否|i-a2d5q7pm12\*\*\*\*|资源实例ID。N 的取值范围为 1~2000。

 |
|Instances.N.InstanceName|String|否|hoeName|实例名称。N 的取值范围为 1~2000。

 |
|Instances.N.RegionId|String|否|cn-hangzhou|地域ID（RegionId）。N 的取值范围为 1~2000。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|FEC7EDB3-9B08-4AC0-A42A-329F5D14B95A|请求ID，用于排查问题

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyMonitorGroupInstances
&GroupId=12345
&Instances.1.Category=ECS
&Instances.1.InstanceId=i-a2d5q7pm12****
&Instances.1.InstanceName=hoeName
&Instances.1.RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyMonitorGroupInstancesResponse>
      <RequestId>02977C39-9E74-430A-B35B-04CFBF0E7F64</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</ModifyMonitorGroupInstancesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"02977C39-9E74-430A-B35B-04CFBF0E7F64",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

