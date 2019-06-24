# Call CloudMonitor APIs {#concept_hzl_jz5_zdb .concept}

## Request structure {#section_abs_kz5_zdb .section}

CloudMonitor APIs are RPC APIs. You can call CloudMonitor APIs by sending HTTP requests.

The request structure is as follows:

`http://endpoint/?Action=xx&parameters`

Description:

-   `Endpoint`: the cloud service access point. The endpoint of CloudMonitor is `metrics.aliyuncs.com`. For more information about the endpoints of various regions, see [CloudMonitor endpoints](#).
-   `Action`: the operation that you want to perform. For example, you can call DescribeMetricList to query the monitoring data of an instance.
-   `Version`: the version of the APIs that you want to use. The current CloudMonitor API version is 2019-01-01.
-   `Parameters`: the request parameters separated with ampersands \(&\). Request parameters consist of common request parameters and custom API parameters. Common request parameters include the API version number, authentication information, and other information.

The following example shows how to call DescribeMetricList to query the monitoring data of an instance.

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=DescribeMetricList
&EndTime=2017-05-17+11%3A30%3A27 
&StartTime=2017-05-17+11%3A20%3A27 
&Period=60 
&Dimensions=%7B%22instanceId%22%3A%22i-abcdefgh123456%22%7D 
&Timestamp=2017-03-22T09%3A30%3A57Z 
&Namespace=acs_ecs_dashboard 
&Metric=cpu_idle 
```

## CloudMonitor endpoints {#section_xf3_lbv_zdb .section}

|Region|Endpoint|
|:-----|:-------|
|China \(Hangzhou\)|metrics.cn-hangzhou.aliyuncs.com|
|China \(Shanghai\)|metrics.cn-shanghai.aliyuncs.com|
|China \(Qingdao\)|metrics.cn-qingdao.aliyuncs.com|
|China \(Beijing\)|metrics.cn-beijing.aliyuncs.com|
|China \(Shenzhen\)|metrics.cn-shenzhen.aliyuncs.com|
|China \(Zhangjiakou-Beijing Winter Olympics\)|metrics.cn-zhangjiakou.aliyuncs.com|
|Hong Kong|metrics.cn-hongkong.aliyuncs.com|
|Singapore|metrics.ap-southeast-1.aliyuncs.com|
|US \(Silicon Valley\)|metrics.us-west-1.aliyuncs.com|
|US \(Virginia\)|metrics.us-east-1.aliyuncs.com|
|Germany \(Frankfurt\)|metrics.eu-central-1.aliyuncs.com|
|Australia \(Sydney\)|metrics.ap-southeast-2.aliyuncs.com|
|UAE \(Dubai\)|metrics.me-east-1.aliyuncs.com|
|Japan \(Tokyo\)|metrics.cn-hangzhou.aliyuncs.com|
|Malaysia \(Kuala Lumpur\)|metrics.ap-southeast-3.aliyuncs.com|
|China \(Hohhot\)|metrics.cn-huhehaote.aliyuncs.com|
|Indonesia \(Jakarta\)|metrics.ap-southeast-5.aliyuncs.com|
|India \(Mumbai\)|metrics.ap-south-1.aliyuncs.com|
|UK \(London\)|metrics.eu-west-1.aliyuncs.com|

**Note:** When you call the APIs to query the monitoring data of Japan \(Tokyo\), use the endpoint of China \(Hangzhou\).

## API authorization {#section_izn_wbv_zdb .section}

To keep your account secure, we recommend that you call CloudMonitor APIs as a RAM user. Before calling CloudMonitor APIs as a RAM user, you must create a RAM user and assign corresponding permissions to it.

## API signature {#section_jzn_wbv_zdb .section}

To ensure secure, Alibaba Cloud authenticates each API request through the signature. When you manually make an API request, you must use your AccessKey Secret to calculate the HMAC value based on the encoded and sorted request string in accordance with the definition in [RFC 2104](https://www.ietf.org/rfc/rfc2104.txt?spm=a2c4g.11186623.2.6.tstgdp&file=rfc2104.txt). The HMAC value is the signature. For more information, see [Sign RPC APIs](https://www.alibabacloud.com/help/doc-detail/66384.htm).

For an RPC API, you must add the signature to the API request in the following format:

`https://endpoint/?SignatureVersion=1.0&SignatureMethod=HMAC-SHA1&Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf`

Take DescribeMetricList as an example. The AccessKey ID is `testid` and AccessKey Secret is `testsecret`. The original request URL is as follows:

```
http://metrics.aliyuncs.com/?Action=DescribeMetricList&period=60&StartTime=2016-03-22T11:30:27Z&Dimensions={instanceId:'i-abcdefgh123456'}&Timestamp=2017-03-23T06:59:55Z&Namespace=acs_ecs_dashboard&SignatureVersion=1.0&Format=JSON&SignatureNonce=aeb03861-611f-43c6-9c07-b752fad3dc06&Version=2015-10-20&AccessKeyId=TestId&MetricName=cpu_idle&SignatureMethod=HMAC-SHA1
```

The corresponding StringToSign is as follows:

```
GET&%2F&AccessKeyId%3DTestId&Action%3DDescribeMetricList&Dimensions%3D%257B%2522instanceId%2522%253A%2522i-abcdefgh123456%2522%257D&Format%3DJSON&Metric%3Dcpu_idle&Period%3D60&Namespace%3Dacs_ecs_dashboard&SignatureMethod%3DHMAC-SHA1&SignatureNonce%3Daeb03861-611f-43c6-9c07-b752fad3dc06&SignatureVersion%3D1.0&StartTime%3D2016-03-22T11%253A30%253A27Z&Timestamp%3D2017-03-23T06%253A59%253A55Z&Version%3D2015-10-20
```

AccessKey Secret is `testsecret`, so the key used for HMAC calculation is `testsecret&` and the calculated signature value is as follows:

```
TLj49H/wqBWGJ7RK0r84SN5IDfM=
```

Add the signature value as the Signature parameter to the request URL. The final URL is as follows:

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=DescribeMetricList&StartTime=2016-03-22T11%3A30%3A27Z&Period=60&Dimensions=%7B%22instanceId%22%3A%22i-abcdefgh123456%22%7D&Timestamp=2017-03-23T06%3A59%3A55Z&Namespace=acs_ecs_dashboard&SignatureVersion=1.0&Format=JSON&SignatureNonce=aeb03861-611f-43c6-9c07-b752fad3dc06&Version=2015-10-20&AccessKeyId=TestId&Metric=cpu_idle&SignatureMethod=HMAC-SHA1&Signature=TLj49H%2FwqBWGJ7RK0r84SN5IDfM%3D
```

