# DescribeCustomEventAttribute {#doc_api_Cms_DescribeCustomEventAttribute .reference}

You can call this operation to query the details of a custom event.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Cms&api=DescribeCustomEventAttribute) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can call APIs, dynamically generate SDK example code, and retrieve APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCustomEventAttribute|The operation that you want to perform. Set the value to DescribeCustomEventAttribute.

 |
|EndTime|String|No|1552227965971|The end time.

 |
|EventId|String|No|123|The ID of the event.

 |
|GroupId|String|No|12345|The ID of the application group.

 |
|Level|String|No|WARN|The level of the event. Valid values: CRITICAL, WARN, and INFO.

 |
|Name|String|No|BOSS-SYNC|The name of the event.

 |
|PageNumber|Integer|No|1|The number of the page.

 |
|PageSize|Integer|No|50|The number of records on each page.

 |
|SearchKeywords|String|No|cms|The expression of keywords in the event content. Logical operators AND and OR are supported.

 -   a and b: searches for results that contain both a and b in the event content.
-   a or b: searches for results that contain either a or b in the event content.

 |
|StartTime|String|No|1552224365971|The start time.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call is successful.

 |
|CustomEvents| | |The details of the event.

 |
|└Content|String|abc|The details of the event.

 |
|└GroupId|String|12345|The ID of the application group.

 |
|└Id|String|123|The ID of the event.

 |
|└Name|String|My custom event|The name of the event.

 |
|└Time|String|1552199984000|The time when the event occurred.

 |
|Message|String|success|The error message.

 |
|RequestId|String|60912C8D-B340-4253-ADE7-61ACDFD25CFC|The request ID for troubleshooting.

 |
|Success|String|true|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCustomEventAttribute
&<Common request parameters>

```

Successful response examples

`XML` format

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

`JSON` format

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

## Error codes { .section}

[View error codes](https://error-center.aliyun.com/status/product/Cms)

