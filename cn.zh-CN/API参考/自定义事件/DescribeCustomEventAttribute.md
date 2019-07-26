# DescribeCustomEventAttribute {#doc_api_Cms_DescribeCustomEventAttribute .reference}

查询自定义事件的详情。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cms&api=DescribeCustomEventAttribute&type=RPC&version=2019-01-01)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCustomEventAttribute|系统规定参数。取值：DescribeCustomEventAttribute。

 |
|EndTime|String|否|1552227965971|结束时间。

 |
|EventId|String|否|123|事件ID。

 |
|GroupId|String|否|12345|应用分组ID。

 |
|Level|String|否|WARN|事件级别， CRITICAL（严重\)、WARN\(警告\)、 INFO\(信息\)。

 |
|Name|String|否|BOSS-SYNC|事件名称。

 |
|PageNumber|Integer|否|1|页码。

 |
|PageSize|Integer|否|50|每页记录条数。

 |
|SearchKeywords|String|否|cms|搜索事件内容包含的关键字，支持 and 或者 or。

 -   如果想要搜索事件内容中即包括a又包括b的结果，可以搜索 a and b
-   如果想要搜索事件内容中包括a或者b的结果，可以搜索 a or b

 |
|StartTime|String|否|1552224365971|开始时间。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|状态码，200表示成功。

 |
|CustomEvents| | |事件详情。

 |
|Content|String|abc|上报事件的详情。

 |
|GroupId|String|12345|应用分组ID。

 |
|Id|String|123|事件ID。

 |
|Name|String|我的自定义事件|事件名称。

 |
|Time|String|1552199984000|事件发生的时间。

 |
|Message|String|success|错误信息。

 |
|RequestId|String|60912C8D-B340-4253-ADE7-61ACDFD25CFC|请求ID，用于排查问题。

 |
|Success|String|true|是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCustomEventAttribute
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCustomEventAttributeResponse>
          <Message>userId:173651113438**** and name:"BABEL_CHECK"</Message>
      <RequestId>194A3F1D-8EA6-4922-BBF2-5F213AC7B648</RequestId>
      <CustomEvents>
            <CustomEvent>
                  <Name>BABEL_CHECK</Name>
                  <Time>1553422490000</Time>
                  <Id>E4407D77-72BA-4818-8644-39D119D7****</Id>
                  <Content>requestId:BD524A26-A3DA-4133-A863-FF56B335797E, info:{"autoPay":false,"autoUseCoupon":false,"bid":"26842","buyerId":118935342242****,"commodities":[{"aliyunProduceCode":"cms","chargeType":"PREPAY","commodityCode":"cms_edition","components":[{"componentCode":"suggest_type","instanceProperty":[{"code":"suggest_type","value":"pro"}],"moduleAttrStatus":1},{"componentCode":"pay_type","instanceProperty":[{"code":"pay_type","value":"suggest"}],"moduleAttrStatus":1}],"duration":1,"free":false,"orderParams":{"aliyunProduceCode":"cms"},"orderType":"BUY","prePayPostCharge":false,"pricingCycle":"Month","quantity":1,"refundSpecCode":"","renewChange":false,"specCode":"cms_edition","specUpdate":false,"syncToSubscription":false,"upgradeInquireFinancialValue":true}],"fromApp":"commonbuy","orderParams":{"priceCheck":"true"},"payerId":118935342242****,"requestId":"57d81d14-3c60-468e-b50a-1dfdb1594673","skipChannel":false,"userId":118935342242****}</Content>
                  <GroupId>123456</GroupId>
            </CustomEvent>
            <CustomEvent>
                  <Name>BABEL_CHECK</Name>
                  <Time>1553422498000</Time>
                  <Id>D44FAC44-EB81-470A-909D-BD963FF9****</Id>
                  <Content>requestId:14CC5306-0BAB-464F-B340-CF33AD306510, info:{"autoPay":false,"autoUseCoupon":false,"bid":"26842","buyerId":118935342242****,"commodities":[{"aliyunProduceCode":"cms","chargeType":"PREPAY","commodityCode":"cms_smspackage","components":[{"componentCode":"sms_count","instanceProperty":[{"code":"sms_count","value":"1000"}],"moduleAttrStatus":1}],"duration":6,"free":false,"orderParams":{"aliyunProduceCode":"cms"},"orderType":"BUY","prePayPostCharge":false,"pricingCycle":"Month","quantity":1,"refundSpecCode":"","renewChange":false,"specCode":"cms_smspackage","specUpdate":false,"syncToSubscription":false,"upgradeInquireFinancialValue":true}],"fromApp":"commonbuy","orderParams":{"priceCheck":"true"},"payerId":118935342242****,"requestId":"64461412-31f2-4e52-a875-43bf1410bdf0","skipChannel":false,"userId":118935342242****}</Content>
                  <GroupId>36933</GroupId>
            </CustomEvent>
            <CustomEvent>
                  <Name>BABEL_CHECK</Name>
                  <Time>1553422506000</Time>
                  <Id>3AF6FE15-4F6E-459A-96F6-45C74F765209</Id>
                  <Content>requestId:4975A6F3-19AC-4C01-BAD2-034DA07FEBB5, info:{"autoPay":false,"autoUseCoupon":false,"bid":"26842","buyerId":118935342242****,"commodities":[{"aliyunProduceCode":"cms","chargeType":"PREPAY","commodityCode":"cms_call_num","components":[{"componentCode":"phone_count","instanceProperty":[{"code":"phone_count","value":"500"}],"moduleAttrStatus":1}],"duration":6,"free":false,"orderParams":{"aliyunProduceCode":"cms"},"orderType":"BUY","prePayPostCharge":false,"pricingCycle":"Month","quantity":1,"refundSpecCode":"","renewChange":false,"specCode":"cms_call_num","specUpdate":false,"syncToSubscription":false,"upgradeInquireFinancialValue":true}],"fromApp":"commonbuy","orderParams":{"priceCheck":"true"},"payerId":118935342242****,"requestId":"ade3ad32-f58b-45d7-add4-ac542be3d8ec","skipChannel":false,"userId":118935342242****}</Content>
                  <GroupId>123456</GroupId>
            </CustomEvent>
      </CustomEvents>
      <Success>true</Success>
      <Code>200</Code>
</DescribeCustomEventAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"userId:173651113438**** and name:\"BABEL_CHECK\"",
	"RequestId":"194A3F1D-8EA6-4922-BBF2-5F213AC7B648",
	"CustomEvents":{
		"CustomEvent":[
			{
				"Name":"BABEL_CHECK",
				"Time":1553422490000,
				"Id":"E4407D77-72BA-4818-8644-39D119D7****",
				"Content":"requestId:BD524A26-A3DA-4133-A863-FF56B335797E, info:{\"autoPay\":false,\"autoUseCoupon\":false,\"bid\":\"26842\",\"buyerId\":118935342242****,\"commodities\":[{\"aliyunProduceCode\":\"cms\",\"chargeType\":\"PREPAY\",\"commodityCode\":\"cms_edition\",\"components\":[{\"componentCode\":\"suggest_type\",\"instanceProperty\":[{\"code\":\"suggest_type\",\"value\":\"pro\"}],\"moduleAttrStatus\":1},{\"componentCode\":\"pay_type\",\"instanceProperty\":[{\"code\":\"pay_type\",\"value\":\"suggest\"}],\"moduleAttrStatus\":1}],\"duration\":1,\"free\":false,\"orderParams\":{\"aliyunProduceCode\":\"cms\"},\"orderType\":\"BUY\",\"prePayPostCharge\":false,\"pricingCycle\":\"Month\",\"quantity\":1,\"refundSpecCode\":\"\",\"renewChange\":false,\"specCode\":\"cms_edition\",\"specUpdate\":false,\"syncToSubscription\":false,\"upgradeInquireFinancialValue\":true}],\"fromApp\":\"commonbuy\",\"orderParams\":{\"priceCheck\":\"true\"},\"payerId\":118935342242****,\"requestId\":\"57d81d14-3c60-468e-b50a-1dfdb1594673\",\"skipChannel\":false,\"userId\":118935342242****}",
				"GroupId":"123456"
			},
			{
				"Name":"BABEL_CHECK",
				"Time":1553422498000,
				"Id":"D44FAC44-EB81-470A-909D-BD963FF9****",
				"Content":"requestId:14CC5306-0BAB-464F-B340-CF33AD306510, info:{\"autoPay\":false,\"autoUseCoupon\":false,\"bid\":\"26842\",\"buyerId\":118935342242****,\"commodities\":[{\"aliyunProduceCode\":\"cms\",\"chargeType\":\"PREPAY\",\"commodityCode\":\"cms_smspackage\",\"components\":[{\"componentCode\":\"sms_count\",\"instanceProperty\":[{\"code\":\"sms_count\",\"value\":\"1000\"}],\"moduleAttrStatus\":1}],\"duration\":6,\"free\":false,\"orderParams\":{\"aliyunProduceCode\":\"cms\"},\"orderType\":\"BUY\",\"prePayPostCharge\":false,\"pricingCycle\":\"Month\",\"quantity\":1,\"refundSpecCode\":\"\",\"renewChange\":false,\"specCode\":\"cms_smspackage\",\"specUpdate\":false,\"syncToSubscription\":false,\"upgradeInquireFinancialValue\":true}],\"fromApp\":\"commonbuy\",\"orderParams\":{\"priceCheck\":\"true\"},\"payerId\":118935342242****,\"requestId\":\"64461412-31f2-4e52-a875-43bf1410bdf0\",\"skipChannel\":false,\"userId\":118935342242****}",
				"GroupId":"36933"
			},
			{
				"Name":"BABEL_CHECK",
				"Time":1553422506000,
				"Id":"3AF6FE15-4F6E-459A-96F6-45C74F76****",
				"Content":"requestId:4975A6F3-19AC-4C01-BAD2-034DA07FEBB5, info:{\"autoPay\":false,\"autoUseCoupon\":false,\"bid\":\"26842\",\"buyerId\":118935342242****,\"commodities\":[{\"aliyunProduceCode\":\"cms\",\"chargeType\":\"PREPAY\",\"commodityCode\":\"cms_call_num\",\"components\":[{\"componentCode\":\"phone_count\",\"instanceProperty\":[{\"code\":\"phone_count\",\"value\":\"500\"}],\"moduleAttrStatus\":1}],\"duration\":6,\"free\":false,\"orderParams\":{\"aliyunProduceCode\":\"cms\"},\"orderType\":\"BUY\",\"prePayPostCharge\":false,\"pricingCycle\":\"Month\",\"quantity\":1,\"refundSpecCode\":\"\",\"renewChange\":false,\"specCode\":\"cms_call_num\",\"specUpdate\":false,\"syncToSubscription\":false,\"upgradeInquireFinancialValue\":true}],\"fromApp\":\"commonbuy\",\"orderParams\":{\"priceCheck\":\"true\"},\"payerId\":118935342242****,\"requestId\":\"ade3ad32-f58b-45d7-add4-ac542be3d8ec\",\"skipChannel\":false,\"userId\":118935342242****}",
				"GroupId":"123456"
			}
		]
	},
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cms)查看更多错误码。

