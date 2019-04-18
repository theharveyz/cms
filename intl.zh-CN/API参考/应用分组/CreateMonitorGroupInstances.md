# CreateMonitorGroupInstances {#doc_api_Cms_CreateMonitorGroupInstances .reference}

添加资源到应用分组。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cms&api=CreateMonitorGroupInstances)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateMonitorGroupInstances|系统规定参数。取值：CreateMonitorGroupInstances。

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
|Instances.N.InstanceId|String|否|i-2ze26xj5wwy12\*\*\*\*|资源实例ID。

 |
|Instances.N.InstanceName|String|否|xxxxx|实例名称。

 |
|Instances.N.RegionId|String|否|cn-hangzhou|实例所在的RegionId，例如cn-hangzhou。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|1BC69FEB-56CD-4555-A0E2-02536A24A946|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateMonitorGroupInstances
&GroupId=12345
&Instances.1.Category=ECS
&Instances.1.InstanceId=i-2ze26xj5wwy12****
&Instances.1.InstanceName=xxxxx
&Instances.1.RegionId= cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateMonitorGroupInstancesResponse>
  <RequestId>1BC69FEB-56CD-4555-A0E2-02536A24A946</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</CreateMonitorGroupInstancesResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"1BC69FEB-56CD-4555-A0E2-02536A24A946",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cms)

