# DescribeProjectMeta {#doc_api_Cms_DescribeProjectMeta .reference}

查询云监控支持的时序类监控项产品列表。

获取接入的云产品信息，包括产品的描述信息、 Namespace和标签。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeProjectMeta&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeProjectMeta|系统规定参数。取值：DescribeProjectMeta。

 |
|Labels|String|否|\[\{"groupFlag":true\}\]|根据标签过滤，格式为`[{"name":"标签名","value":"标签值"},{"name":"标签名","value":"标签值"}]​`。

 支持的标签名包括product、groupFlag。

 product 标签值为产品英文名称。

 groupFlag含义为该产品是否支持应用分组，标签值为true或false​ 。

 |
|PageNumber|Integer|否|1|分页参数，默认1。

 |
|PageSize|Integer|否|30|分页大小，默认30

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|PageNumber|String|1|页码。

 |
|PageSize|String|10|每页显示记录条数。

 |
|RequestId|String|4C2061B2-3B1B-43BF-A4A4-C53426F479C0|请求ID，用于排查问题。

 |
|Resources| | |具体的配置信息。

 |
|Description|String|CDN|描述信息。

 |
|Labels|String|\[\{"groupFlag":true\}\]|标签。

 |
|Namespace|String|acs\_cdn|命名空间，用于区分产品，通常为acs\_产品缩写。

 |
|Success|Boolean|true|是否成功。

 |
|Total|String|12|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeProjectMeta
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeProjectMetaResponse>
   <PageNumber>1</PageNumber>
      <PageSize>5</PageSize>
      <RequestId>4C2061B2-3B1B-43BF-A4A4-C53426F479C0</RequestId>
      <Success>true</Success>
      <Code>200</Code>
      <Total>62</Total>
      <Resources>
            <Resource>
                  <Description>分析型数据库</Description>
                  <Labels>[{"name":"product","value":"ADS"},{"name":"productCategory","value":"ads"},{"name":"groupFlag","value":"true"}]</Labels>
                  <Namespace>acs_ads</Namespace>
            </Resource>
            <Resource>
                  <Description>智能推荐</Description>
                  <Labels>[{"name":"product","value":"AIRec"},{"name":"productCategory","value":"airec"},{"name":"groupFlag","value":"true"}]</Labels>
                  <Namespace>acs_airec</Namespace>
            </Resource>
            <Resource>
                  <Description>API网关</Description>
                  <Labels>[{"name":"product","value":"APIGateway"},{"name":"productCategory","value":"apigateway"},{"name":"groupFlag","value":"true"}]</Labels>
                  <Namespace>acs_apigateway_dashboard</Namespace>
            </Resource>
            <Resource>
                  <Description>CDN</Description>
                  <Labels>[{"name":"product","value":"CDN"},{"name":"productCategory","value":"cdn"},{"name":"groupFlag","value":"true"}]</Labels>
                  <Namespace>acs_cdn</Namespace>
            </Resource>
            <Resource>
                  <Description>云企业网</Description>
                  <Labels>[{"name":"product","value":"CEN"},{"name":"productCategory","value":"cen,cen_flow,cen_vbr"},{"name":"groupFlag","value":"true"}]</Labels>
                  <Namespace>acs_cen</Namespace>
            </Resource>
      </Resources>

</DescribeProjectMetaResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"PageSize":5,
	"RequestId":"4C2061B2-3B1B-43BF-A4A4-C53426F479C0",
	"Success":true,
	"Code":200,
	"Total":62,
	"Resources":{
		"Resource":[
			{
				"Description":"分析型数据库",
				"Labels":"[{\"name\":\"product\",\"value\":\"ADS\"},{\"name\":\"productCategory\",\"value\":\"ads\"},{\"name\":\"groupFlag\",\"value\":\"true\"}]",
				"Namespace":"acs_ads"
			},
			{
				"Description":"智能推荐",
				"Labels":"[{\"name\":\"product\",\"value\":\"AIRec\"},{\"name\":\"productCategory\",\"value\":\"airec\"},{\"name\":\"groupFlag\",\"value\":\"true\"}]",
				"Namespace":"acs_airec"
			},
			{
				"Description":"API网关",
				"Labels":"[{\"name\":\"product\",\"value\":\"APIGateway\"},{\"name\":\"productCategory\",\"value\":\"apigateway\"},{\"name\":\"groupFlag\",\"value\":\"true\"}]",
				"Namespace":"acs_apigateway_dashboard"
			},
			{
				"Description":"CDN",
				"Labels":"[{\"name\":\"product\",\"value\":\"CDN\"},{\"name\":\"productCategory\",\"value\":\"cdn\"},{\"name\":\"groupFlag\",\"value\":\"true\"}]",
				"Namespace":"acs_cdn"
			},
			{
				"Description":"云企业网",
				"Labels":"[{\"name\":\"product\",\"value\":\"CEN\"},{\"name\":\"productCategory\",\"value\":\"cen,cen_flow,cen_vbr\"},{\"name\":\"groupFlag\",\"value\":\"true\"}]",
				"Namespace":"acs_cen"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

