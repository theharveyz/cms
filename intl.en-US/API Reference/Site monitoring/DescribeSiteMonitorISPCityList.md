# DescribeSiteMonitorISPCityList {#doc_api_Cms_DescribeSiteMonitorISPCityList .reference}

You can call this operation to query the detection points that are available for creating site monitoring tasks.

## Debugging {#apiExplorer .section}

Alibaba Cloud provides OpenAPI Explorer to simplify API usage. You can use [OpenAPI Explorer](https://api.aliyun.com/#product=Cms&api=DescribeSiteMonitorISPCityList) to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSiteMonitorISPCityList|The operation that you want to perform. Set this parameter to DescribeSiteMonitorISPCityList.

 |
|City|String|No|Beijing|The name or ID of the city where the detection point is located. Fuzzy search is supported for city names.

 |
|Isp|String|No|Chine Mobile|The name or ID of the carrier to which the detection point belongs. Fuzzy search is supported for carrier names.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The status code. A value of 200 indicates that the call was successful.

 |
|RequestId|String|848EF34A-FD9F-48A6-879F-414279ED4F26|The ID of the request.

 |
|Message|String|success|The error message.

 |
|IspCityList| | |The list of the detection points that were queried.

 |
|└City|String|738|The ID of the city.

 |
|└CityName.zh\_CN|String|Beijing|The name of the city.

 |
|└Country.zh\_CN|String|China|The name of the country or region.

 |
|└Isp|String|232|The ID of the carrier.

 |
|└IspName.zh\_CN|String|China Unicom|The name of the carrier.

 |
|└Region.zh\_CN|String|Liaoning|The name of the province.

 |
|Success|String|true|Indicates whether the call was successful.

 |

## Examples {#demo .section}

Sample request

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSiteMonitorISPCityList
&<Common request parameters>

```

Sample success response

`XML` format

``` {#xml_return_success_demo}
<DescribeSiteMonitorISPAreaCityResponse>
  <IspCityList>
    <IspCity>
      <IspName.zh_CN>China Unicom</IspName.zh_CN>
      <Isp>232</Isp>
      <Region.zh_CN>Liaoning</Region.zh_CN>
      <Country.zh_CN>China</Country.zh_CN>
      <City>395</City>
      <CityName.zh_CN>Dalian</CityName.zh_CN>
    </IspCity>
    <IspCity>
      <IspName.zh_CN>China Unicom</IspName.zh_CN>
      <Isp>232</Isp>
      <Region.zh_CN>Heilongjiang</Region.zh_CN>
      <Country.zh_CN>China</Country.zh_CN>
      <City>392</City>
      <CityName.zh_CN>Jixi</CityName.zh_CN>
    </IspCity>
    <IspCity>
      <IspName.zh_CN>China Unicom</IspName.zh_CN>
      <Isp>232</Isp>
      <Region.zh_CN>Shaanxi</Region.zh_CN>
      <Country.zh_CN>China</Country.zh_CN>
      <City>267</City>
      <CityName.zh_CN>Hanzhong</CityName.zh_CN>
    </IspCity>
    <IspCity>
      <IspName.zh_CN>China Unicom</IspName.zh_CN>
      <Isp>232</Isp>
      <Region.zh_CN>Sichuan</Region.zh_CN>
      <Country.zh_CN>China</Country.zh_CN>
      <City>205</City>
      <CityName.zh_CN>Mianyang</CityName.zh_CN>
    </IspCity>
  </IspCityList>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSiteMonitorISPAreaCityResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"successful",
	"IspCityList":{
		"IspCity":[
			{
				"IspName.zh_CN":"China Unicom",
				"Isp":"232",
				"Region.zh_CN":"Liaoning",
				"City":"395",
				"Country.zh_CN":"China",
				"CityName.zh_CN":"Dalian"
			},
			{
				"IspName.zh_CN":"China Unicom",
				"Isp":"232",
				"Region.zh_CN":"Heilongjiang",
				"City":"392",
				"Country.zh_CN":"China",
				"CityName.zh_CN":"Jixi"
			},
			{
				"IspName.zh_CN":"China Unicom",
				"Isp":"232",
				"Region.zh_CN":"Shaanxi",
				"City":"267",
				"Country.zh_CN":"China",
				"CityName.zh_CN":"Hanzhong"
			},
			{
				"IspName.zh_CN":"China Unicom",
				"Isp":"232",
				"Region.zh_CN":"Sichuan",
				"City":"205",
				"Country.zh_CN":"China",
				"CityName.zh_CN":"Mianyang"
			}
		]
	},
	"Success":true,
	"Code":"200"
}
```

## Error codes { .section}

[View error codes.](https://error-center.aliyun.com/status/product/Cms)

