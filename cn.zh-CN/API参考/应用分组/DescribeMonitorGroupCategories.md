# DescribeMonitorGroupCategories {#doc_api_Cms_DescribeMonitorGroupCategories .reference}

查询指定应用分组的产品资源列表和每个产品的资源数量。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupCategories&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeMonitorGroupCategories|系统规定参数。取值：DescribeMonitorGroupCategories。

 |
|GroupId|Long|是|12345|应用分组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|MonitorGroupCategories| | |组实例产品类型。

 |
|GroupId|Long|123456|组ID。

 |
|MonitorGroupCategory| | |应用组产品类型。

 |
|Category|String|ECS|产品的名称缩写。目前支持的产品有：

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
|Count|Integer|1|产品实例的数量。

 |
|RequestId|String|9E0347B0-EBC3-4769-A78D-D96F21C6BB52|请求ID，用于排查问题。

 |
|Success|Boolean|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitorGroupCategories
&GroupId=12345
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

