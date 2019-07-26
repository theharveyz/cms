# DescribeMonitorGroupDynamicRules {#doc_api_Cms_DescribeMonitorGroupDynamicRules .reference}

查询应用分组动态规则的列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeMonitorGroupDynamicRules&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|GroupId|Long|是|123456|应用分组ID。

 |
|Action|String|否|DescribeMonitorGroupDynamicRules|系统规定参数。取值：DescribeMonitorGroupDynamicRules。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Integer|200|状态码，200表示成功。

 |
|Message|String|success|错误信息。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页记录条数。

 |
|RequestId|String|2170B94A-1576-4D65-900E-2093037CDAF3|请求ID，用于问题排查。

 |
|Resource| | |关联资源。

 |
|Category|String|ecs|产品名称，对应过滤。

 |
|FilterRelation|String|xxx|筛选条件。

 |
|Filters| | |规则。

 |
|Function|String|contains|计算方法，可以取值为contains：包含，startWith：前缀，endWith：后缀。

 |
|Name|String|hostName|检查的字段名。

 |
|Value|String|pre|动态规则的值。

 |
|GroupId|Long|12345|组ID。

 |
|Success|Boolean|true|是否成功。

 |
|Total|Integer|22|总记录条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeMonitorGroupDynamicRules
&GroupId=123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeMonitorGroupDynamicRulesResponse>
      <Resource>
            <Resource>
                  <Filters>
                        <Filter>
                              <Name>hostName</Name>
                              <Value>aaa</Value>
                              <Function>contains</Function>
                        </Filter>
                  </Filters>
                  <Category>ecs</Category>
                  <FilterRelation>and</FilterRelation>
            </Resource>
      </Resource>
      <RequestId>2170B94A-1576-4D65-900E-2093037CDAF3</RequestId>
      <Success>true</Success>
      <Code>200</Code>
</DescribeMonitorGroupDynamicRulesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Resource":{
		"Resource":[
			{
				"Filters":{
					"Filter":[
						{
							"Name":"hostName",
							"Value":"aaa",
							"Function":"contains"
						}
					]
				},
				"Category":"ecs",
				"FilterRelation":"and"
			}
		]
	},
	"RequestId":"2170B94A-1576-4D65-900E-2093037CDAF3",
	"Success":true,
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

