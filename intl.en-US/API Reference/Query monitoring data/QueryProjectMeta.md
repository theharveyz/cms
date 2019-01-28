# QueryProjectMeta {#concept_otq_nys_zfb .concept}

You can call the QueryProjectMeta API to query the products that are supported by time-series metrics in CloudMonitor. Typically, this API is used together with the QueryMetricMeta API and the QueryMetricList/QueryMetricLast API.

## Request types {#section_xwc_qzs_zfb .section}

POST | GET

## Request parameters {#section_xnn_szs_zfb .section}

|Parameter|Type|Required?|Description|
|---------|----|---------|-----------|
|Action|String|Yes|A system required parameter. Valid value: QueryProjectMeta.|
|Labels|String|No| The query results are filtered based on labels, which are in the format of \[\{"name":"the label name","value":"the label value"\},\{"name":"the label name","value":"the label value"\}\]​.

 Supported label names include "product" and "groupFlag". The value of the label name "product" is the name of the product.

 The label name "groupFlag" indicates whether the product supports application groups. The corresponding label value is "true" or "false".

 |
|PageNumber|int|No|The page number. Default value: 1.|
|PageSize|int|No|The maximum number of entries per page. Default value: 30.|

## Response parameters { .section}

|**Parameter**|**Type**|**Description**|
|-------------|--------|---------------|
|RequestId|String|Used to track the request|
|Success|Boolean|Indicates whether the API is called successfully.|
|ErrorCode|String|The code 200 indicates a successful API call.|
|ErrorMessage|String|The error message|
|Resources|Array|The ProjectMeta list|

## ProjectMeta fields { .section}

|Field|Type|Required?|Description|
|-----|----|---------|-----------|
|Labels|String|No| \[\{"name":"label name","value":"label value"\}, \{"name":"label name","value":"label value"\}\]

 Supported label names include "product" and "groupFlag".

 The value of the label name "product" is the name of the product.

 The label name "groupFlag" indicates whether the product supports application groups. The corresponding label value is "true" or "false".

 |
|Project|String|No|The Project to which the metric belongs. It is used to query monitoring data.|
|Description|String|No|A description of the metric|

## Error codes { .section}

|HTTPStateCode|ErrorCode|ErrorMessage|
|-------------|---------|------------|
|403|AccessForbidden|User not authorized to operate on the specified resource.|
|400|ParameterInvalid|Illegal parameters.|
|404|ResourceNotFound|The specified resource is not found.|
|500|InternalError|The request processing has failed due to some unknown error.|

## Request example { .section}

```

import com.aliyuncs.DefaultAcsClient;
import com.aliyuncs.IAcsClient;
import com.aliyuncs.cms.model.v20180308. QueryProjectMetaRequest;
import com.aliyuncs.cms.model.v20180308. QueryProjectMetaResponse;
import com.aliyuncs.profile.DefaultProfile;


class Test {
public static void main(String[] args) {


//Initialization
DefaultProfile profile = DefaultProfile.getProfile("cn-hangzhou", "", "");
IAcsClient client = new DefaultAcsClient(profile);

//Set the parameter.
QueryProjectMetaRequest request = new QueryProjectMetaRequest();

//Initiate the request.
try {
QueryProjectMetaResponse response = client.getAcsResponse(request);
System.out.println("Success:" + response.getSuccess());
System.out.println("ErrorCode:" + response.getErrorCode());
System.out.println("ErrorMessage:" + response.getErrorMessage());
System.out.println("RequestId:" + response.getRequestId());
} catch (Exception e) {
e.printStackTrace();
}
}
}
```

## Response example {#section_g4d_kft_zfb .section}

```

{
"RequestId": "D3DBF9F5-7C4D-4A67-B869-097C069C481D",
"ErrorCode": 200,
"Success": true,
"Resources": {
"Resource": [
{
"Description": "AnalyticDB",
"Labels": "[{\"name\":\"product\",\"value\":\"ADS\"},{\"name\":\"groupFlag\",\"value\":\"true\"}]",
"Project": "acs_ads"
},
{
"Description": "API Gateway",
"Labels": "[{\"name\":\"product\",\"value\":\"APIGateway\"},{\"name\":\"groupFlag\",\"value\":\"true\"}]",
"Project": "acs_apigateway_dashboard"
},
{
"Description": "Internet Shared Bandwidth",
"Labels": "[{\"name\":\"product\",\"value\":\"InternetSharedBandwidth\"},{\"name\":\"groupFlag\",\"value\":\"true\"}]",
"Project": "acs_bandwidth_package"
},
{
"Description": "CDN",
"Labels": "[{\"name\":\"product\",\"value\":\"CDN\"},{\"name\":\"groupFlag\",\"value\":\"true\"}]",
"Project": "acs_cdn"
},
{
"Description": "Cloud Enterprise Network",
"Labels": "[{\"name\":\"product\",\"value\":\"CEN\"},{\"name\":\"groupFlag\",\"value\":\"false\"}]",
"Project": "acs_cen"
}
]
}
}
```

