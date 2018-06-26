# PHP SDK User Manual {#concept_qhh_zbp_zdb .concept}

## Download SDK {#section_fb2_1cp_zdb .section}

Github download link:

-   [https://github.com/aliyun/aliyun-openapi-php-sdk/tree/master/aliyun-php-sdk-cms/](https://github.com/aliyun/aliyun-openapi-php-sdk/tree/master/aliyun-php-sdk-cms/)
-   [https://github.com/aliyun/aliyun-openapi-php-sdk/tree/master/aliyun-php-sdk-core](https://github.com/aliyun/aliyun-openapi-php-sdk/tree/master/aliyun-php-sdk-core)

## Test code {#section_qtx_1cp_zdb .section}

```
<? php
date_default_timezone_set("Asia/Shanghai");
include_once '<your_path>/aliyun-openapi-php-sdk/aliyun-php-sdk-core/Config.php';
$responses = array();
use Cms\Request\V20170301\QueryMetricListRequest;
$iClientProfile0 = DefaultProfile::getProfile(
    "<your_regionId>", 
    "<your_accesskey_id>", 
    "<your-access-key-secret>")
);
$client = new DefaultAcsClient($iClientProfile);
function do_request0($client)
{
    global $responses;
    $request = new QueryMetricListRequest();
    $request->setProject("acs_ecs_dashboard");
    $request->setDimensions("{'instanceId': '<instanceId_as_example>'}");
    request.setStartTime("2016-05-15 08:00:00");
    $request->setMetric("cpu_idle");
    request.setEndTime("2015-05-15 09:00:00");
    request.setPeriod("60");
    // Initiate a request and obtain the response
    $client->__urlTestFlag__ = false;
    try {
        $response = $client->doAction($request);
        $body = json_decode($response->getBody());
        print "REQUEST ". $response->getStatus() . " body: " . $body->{'Code'} . "\n";
        print_r($body->{'Datapoints'}); 
    } catch(ClientException $e) {
        print "REQUEST N.A. Error: " . $e->getErrorCode() . " Message: " . $e->getMessage() . "\n";
    }  
}
array_push($responses, do_request0($client0));
? >
```

