# PHP SDK使用手册 {#concept_qhh_zbp_zdb .concept}

## SDK下载 {#section_fb2_1cp_zdb .section}

Github下载地址：

-   [https://github.com/aliyun/aliyun-openapi-php-sdk/tree/master/aliyun-php-sdk-cms/](https://github.com/aliyun/aliyun-openapi-php-sdk/tree/master/aliyun-php-sdk-cms/)
-   [https://github.com/aliyun/aliyun-openapi-php-sdk/tree/master/aliyun-php-sdk-core](https://github.com/aliyun/aliyun-openapi-php-sdk/tree/master/aliyun-php-sdk-core)

## 测试代码 {#section_qtx_1cp_zdb .section}

```
<?php
date_default_timezone_set("Asia/Shanghai");
include_once '<your_path>/aliyun-openapi-php-sdk/aliyun-php-sdk-core/Config.php';
$responses = array();
use Cms\Request\V20170301\QueryMetricListRequest;
$iClientProfile0 = DefaultProfile::getProfile(
    "<your_regionId>", 
    "<your_accesskey_id>", 
    "<your_accesskey_secret>"
);
$client0 = new DefaultAcsClient($iClientProfile0);
function do_request0($client)
{
    global $responses;
    $request = new QueryMetricListRequest();
    $request->setProject("acs_ecs_dashboard");
    $request->setDimensions("{'instanceId': '<instanceId_as_example>'}");
    $request->setStartTime("2017-03-14 14:20:27");
    $request->setMetric("cpu_idle");
    $request->setEndTime("2017-03-15 11:20:27");
    $request->setPeriod("60");
    // 发起请求，并得到response
    $client->__urlTestFlag__ = false;
    try {
        $response = $client->doAction($request);
        $body = json_decode($response->getBody());
        print "REQUEST ". $response->getStatus() . " body: " . $body->{'Code'}  . "\n";
        print_r($body->{'Datapoints'}); 
    } catch(ClientException $e) {
        print "REQUEST N.A. Error: " . $e->getErrorCode() . " Message: " . $e->getMessage() . "\n";
    }  
}
array_push($responses, do_request0($client0));
?>
```

