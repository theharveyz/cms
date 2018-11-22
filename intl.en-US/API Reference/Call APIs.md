# Call APIs {#concept_hzl_jz5_zdb .concept}

## Request structure {#section_abs_kz5_zdb .section}

CloudMonitor APIs are RPC APIs. You can call SLB APIs by sending HTTP requests.

The request structure is as follows:

`http://endpoint/?Action=xx&parameters`

where:

-   `Endpoint` is the cloud service access point. The access point of CloudMonitor is `metrics.aliyuncs.com`. For details about the endpoints of each region, see [Endpoint](#).
-   `Action` is an operation to be performed, for example, calling the QueryMetricList API to query the monitoring data of an instance.
-   `Version` is the version of the API to be used. The current version is 2017-03-01.
-   `Parameters` are the request parameters separated by ampersands \(&\). Request parameters consist of common parameters and API specific parameters. Common parameters include the API version number, authentication information, and other information.

The following example shows how to call the QueryMetricList API to query the monitoring data of an instance.

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=QueryMetricList
&EndTime=2017-05-17+11%3A30%3A27
&StartTime=2017-05-17+11%3A20%3A27
&Period=60
&Dimensions=%7B%22instanceId%22%3A%22i-abcdefgh123456%22%7D
&Timestamp=2017-03-22T09%3A30%3A57Z
&Project=acs_ecs_dashboard
&Metric=cpu_idle
```

## Endpoint {#section_xf3_lbv_zdb .section}

|Region|Endpoint|
|:-----|:-------|
|China East 1 \(Hangzhou\)|metrics.cn-hangzhou.aliyuncs.com|
|China East 2 \(Shanghai\)|metrics.cn-shanghai.aliyuncs.com|
|China North 1 \(Qingdao\)|metrics.cn-qingdao.aliyuncs.com|
|China North 2 \(Beijing\)|metrics.cn-beijing.aliyuncs.com|
|China South 1 \(Shenzhen\)|metrics.cn-shenzhen.aliyuncs.com|
|China North 3 \(Zhangjiakou\)|metrics.cn-zhangjiakou.aliyuncs.com|
|Hong Kong|metrics.cn-hongkong.aliyuncs.com|
|Asia Pacific SE 1 \(Singapore\)|metrics.ap-southeast-1.aliyuncs.com|
|US West 1 \(Silicon Valley\)|metrics.us-west-1.aliyuncs.com|
|US East 1 \(Virginia\)|metrics.us-east-1.aliyuncs.com|
|EU Central 1 \(Frankfurt\)|metrics.eu-central-1.aliyuncs.com|
|Asia Pacific SE 2 \(Sydney\)|metrics.ap-southeast-2.aliyuncs.com|
|Middle East 1 \(Dubai\)|metrics.me-east-1.aliyuncs.com|
|Asia Pacific NE 1 \(Tokyo\)|metrics.cn-hangzhou.aliyuncs.com|
|Asia Pacific SE 3 \(Kuala Lumpur\)|metrics.ap-southeast-3.aliyuncs.com|
|China North 5 \(Huhehaote\)|metrics.cn-huhehaote.aliyuncs.com|
|Asia Pacific SE 5 \(Jakarta\)|metrics.ap-southeast-5.aliyuncs.com|
|Asia Pacific SOU 1 \(Mumbai\)|metrics.ap-south-1.aliyuncs.com|
|UK \(London\)|metrics.eu-west-1.aliyuncs.com|

**Note:** When you call the APIs to query the monitoring data in Asia Pacific NE 1 \(Tokyo\), use the endpoint in China East 1 \(Hangzhou\).

## API authorization {#section_izn_wbv_zdb .section}

For better security, we recommend that you use a RAM user account to call APIs. Before using a RAM account to call an SLB API, you must grant the RAM user the corresponding permission by creating an authorization policy and attaching the policy to the RAM user.

## API signature {#section_jzn_wbv_zdb .section}

To ensure that the APIs are securely called, Alibaba Cloud authenticates each API request by using the API signature. When you manually initiate an API request, follow the definition of [RFC 2104](https://www.ietf.org/rfc/rfc2104.txt?spm=a2c4g.11186623.2.6.tstgdp&file=rfc2104.txt), and use AccessSecret to evaluate the HMAC values, and use these values as signatures for the encoded and sorted entire request string. For details, see [Sign RPC APIs](https://help.aliyun.com/document_detail/66384.html?spm=a2c4g.11186623.2.7.tstgdp).

When calling an RPC API, you need to add the signature to your API request using the following format:

`https://endpoint/?SignatureVersion=1.0&SignatureMethod=HMAC-SHA1&Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf`

Take QueryMetricList as an example. Assume that the Accesskey ID is `testid` and AccessKey Secret is `testsecret`. The request URL before the signature is as follows:

```
http://metrics.aliyuncs.com/?Action=QueryMetricList&period=60&StartTime=2016-03-22T11:30:27Z&Dimensions={instanceId:'i-abcdefgh123456'}&Timestamp=2017-03-23T06:59:55Z&Project=acs_ecs_dashboard&SignatureVersion=1.0&Format=JSON&SignatureNonce=aeb03861-611f-43c6-9c07-b752fad3dc06&Version=2015-10-20&AccessKeyId=TestId&Metric=cpu_idle&SignatureMethod=HMAC-SHA1
```

The calculated signature string StringToSign is as follows:

```
GET&%2F&AccessKeyId%3DTestId&Action%3DQueryMetricList&Dimensions%3D%257B%2522instanceId%2522%253A%2522i-abcdefgh123456%2522%257D&Format%3DJSON&Metric%3Dcpu_idle&Period%3D60&Project%3Dacs_ecs_dashboard&SignatureMethod%3DHMAC-SHA1&SignatureNonce%3Daeb03861-611f-43c6-9c07-b752fad3dc06&SignatureVersion%3D1.0&StartTime%3D2016-03-22T11%253A30%253A27Z&Timestamp%3D2017-03-23T06%253A59%253A55Z&Version%3D2015-10-20
```

AccessKey Secret is `testsecret`, and the key used for HMAC calculation is `testsecret&`. Then the signature value is as follows:

```
TLj49H/wqBWGJ7RK0r84SN5IDfM=
```

Add the signature as a Signature parameter to the URL request. The final URL is obtained as follows:

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=QueryMetricList&StartTime=2016-03-22T11%3A30%3A27Z&Period=60&Dimensions=%7B%22instanceId%22%3A%22i-abcdefgh123456%22%7D&Timestamp=2017-03-23T06%3A59%3A55Z&Project=acs_ecs_dashboard&SignatureVersion=1.0&Format=JSON&SignatureNonce=aeb03861-611f-43c6-9c07-b752fad3dc06&Version=2015-10-20&AccessKeyId=TestId&Metric=cpu_idle&SignatureMethod=HMAC-SHA1&Signature=TLj49H%2FwqBWGJ7RK0r84SN5IDfM%3D
```

