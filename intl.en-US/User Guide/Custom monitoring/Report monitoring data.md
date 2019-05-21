# Report monitoring data {#concept_b2h_ddb_5db .concept}

This topic describes how to report custom monitoring data.

Custom monitoring allows you to customize metrics and alarm rules to meet your own business needs. Custom monitoring provides APIs for reporting monitoring data. You can use the APIs to report collected time series data to CloudMonitor. You can also configure alarm rules to receive notification when an exception occurs.

CloudMonitor provides APIs, Java SDK, and Alibaba Cloud command line interface \(CLI\) for reporting data.

## Limits {#section_q4b_znk_zdb .section}

-   The number of queries per second \(QPS\) is limited to 200 in China \(Beijing\), China \(Shanghai\), and China \(Hangzhou\), 100 in China \(Zhangjiakou\) and China \(Shenzhen\), and 50 in the other regions.
-   A maximum of 100 data entries can be reported at a time. The body size cannot exceed 256 KB.
-   The `metricName` field can contain letters, digits, and underscores \(\_\). This field must start with a letter. If the starting character is not a letter, it is replaced with an uppercase A. Invalid characters are replaced with underscores \(\_\).
-   The `dimensions` field cannot contain equal signs \(=\), ampersands \(&\), or commas \(,\). Invalid characters are replaced with underscores \(\_\).
-   The string length of the key or value of both `metricName` and `dimensions` cannot exceed 64 bytes. Otherwise, the key or value string is truncated.
-   Reporting raw data is a paid function. The free edition allows you to aggregate data. When you report data, you must enter "1" for the type field in the request parameter.

## Report data through APIs {#section_zym_l4k_zdb .section}

After you report the raw data through APIs, CloudMonitor uses the following statistical methods to calculate the statistics at 1-minute and 5-minute intervals:

-   Average: The average value.
-   Maximum: The maximum value.
-   Minimum: The minimum value.
-   Sum: The sum value.
-   SampleCount: The count.
-   SumPerSecond: The sum divided by the total number of seconds of the corresponding aggregation period. You can also calculate the value by using moving average.
-   CountPerSecond: The count divided by the total number of seconds of the corresponding aggregation period. You can also calculate the value by using moving average.
-   LastValue: The last sampled value in the aggregation period. It is similar to gauge.
-   P10: The value of the 10th percentile. It is greater than 10% of all data in the aggregation period.
-   P20: The value of the 20th percentile. It is greater than 20% of all data in the aggregation period.
-   P30: The value of the 30th percentile. It is greater than 30% of all data in the aggregation period.
-   P40: The value of the 40th percentile. It is greater than 40% of all data in the aggregation period.
-   P50: The value of the 50th percentile. It is the median and greater than 50% of all data in the aggregation period.
-   P60: The value of the 60th percentile. It is greater than 60% of all data in the aggregation period.
-   P70: The value of the 70th percentile. It is greater than 70% of all data in the aggregation period.
-   P75: The value of the 75th percentile. It is greater than 75% of all data in the aggregation period.
-   P80: The value of the 80th percentile. It is greater than 80% of all data in the aggregation period.
-   P90: The value of the 90th percentile. It is greater than 90% of all data in the aggregation period.
-   P95: The value of the 95th percentile. It is greater than 95% of all data in the aggregation period.
-   P98: The value of the 98th percentile. It is greater than 98% of all data in the aggregation period.
-   P99: The value of the 99th percentile. It is greater than 99% of all data in the aggregation period.

-   **Endpoints** 

    Internet endpoint: `https://metrichub-cms-cn-hangzhou.aliyuncs.com`

    The following table lists the intranet endpoints.

    |Region|Region ID|Endpoint|
    |:-----|:--------|:-------|
    |China \(Hangzhou\)|cn-hangzhou|http://metrichub-cn-hangzhou.aliyun.com|
    |China \(Zhangjiakou\)|cn-zhangjiakou|http://metrichub-cn-zhangjiakou.aliyun.com|
    |China \(Shanghai\)|cn-shanghai|http://metrichub-cn-shanghai.aliyun.com|
    |China \(Beijing\)|cn-beijing|http://metrichub-cn-beijing.aliyun.com|
    |China \(Qingdao\)|cn-qingdao|http://metrichub-cn-qingdao.aliyun.com|
    |China \(Shenzhen\)|cn-shenzhen|http://metrichub-cn-shenzhen.aliyun.com|
    |Hong Kong|cn-hongkong|http://metrichub-cn-hongkong.aliyun.com|
    |China \(Hohhot\)|cn-huhehaote|http://metrichub-cn-huhehaote.aliyun.com|
    |UAE \(Dubai\)|me-east-1|http://metrichub-me-east-1.aliyun.com|
    |US \(Silicon Valley\)|us-west-1|http://metrichub-us-west-1.aliyun.com|
    |US \(Virginia\)|us-east-1|http://metrichub-us-east-1.aliyun.com|
    |Japan \(Tokyo\)|ap-northeast-1|http://metrichub-ap-northeast-1.aliyun.com|
    |Germany \(Frankfurt\)|eu-central-1|http://metrichub-eu-central-1.aliyun.com|
    |Australia \(Sydney\)|ap-southeast-2|http://metrichub-ap-southeast-2.aliyun.com|
    |Singapore|ap-southeast-1|http://metrichub-ap-southeast-1.aliyun.com|
    |Malaysia \(Kuala Lumpur\)|ap-southeast-3|http://metrichub-ap-southeast-3.aliyun.com|
    |India \(Mumbai\)|ap-south-1|http://metrichub-ap-south-1.aliyuncs.com|

-   **Request syntax** 

    ```
    POST /metric/custom/upload HTTP/1.1 
    Authorization:<AuthorizationString> 
    Content-Length:<Content Length> 
    Content-MD5:<Content MD5> 
    Content-Type:application/json
    Date:<GMT Date>
    Host: metrichub-cms-cn-hangzhou.aliyuncs.com
    x-cms-signature:hmac-sha1
    x-cms-api-version:1.0
    x-cms-ip:30.27.84.196
    User-Agent:cms-java-sdk-v-1.0
    [{"groupId":101,"metricName":"","dimensions":{"sampleName1":"value1","sampleName2":"value2"},"time":"","type":0,"period":60,"values":{"value":10.5,"Sum":100}}]
    ```


-   **Signature algorithm** 

    Currently, only the HMAC-SHA1 signature algorithm is supported.

    1.  Prepare an Alibaba Cloud AccessKey pair.

        To generate a digital signature for an API request, you must use an AccessKey pair that is composed of an AccessKey ID and an AccessKey Secret. You can use an existing AccessKey pair or create a new one. The AccessKey pair must be in the **Active** state.

    2.  Generate a signature string for the request.

        An API signature string consists of the Method, Header, and Body fields of an HTTP request.

        ```
        SignString = VERB + "\n"
                     + CONTENT-MD5 + "\n"
                     + CONTENT-TYPE + "\n"
                     + DATE + "\n"
                     + CanonicalizedHeaders + "\n"
                     + CanonicalizedResource
        ```

        In the preceding formula, `\n` indicates the newline escape character and the plus sign \(`+`\) indicates the string concatenation operator. The other parts are defined as follows.

        |Name|Definition|Examples|
        |:---|:---------|:-------|
        |VERB|The method name of the HTTP request.|PUT, GET, and POST|
        |CONTENT-MD5|The MD5 value of the Body field in the HTTP request. The value must be an uppercase string.|875264590688CA6171F6228AF5BBB3D2|
        |CONTENT-TYPE|The type of the Body field in the request.|application/json|
        |DATE|The standard timestamp header of the HTTP request, which follows the RFC 1123 format and uses GMT standard time.|Mon, 3 Jan 2010 08:33:47 GMT|
        |CanonicalizedHeaders|The string constructed by the custom headers prefixed with x-cms and x-acs in the HTTP request.|x-cms-api-version:0.1.0\\nx-cms-signature|
        |CanonicalizedResource|The string constructed by the HTTP request resources, as described in the following section.|/event/custom/upload|

        CanonicalizedHeaders in the preceding table is constructed as follows:

        1.  Convert the names of all HTTP request headers prefixed with `x-cms` and `x-acs` to lowercase letters.
        2.  Sort the CMS custom request headers obtained in the preceding step in ascending lexicographical order.
        3.  Delete any spaces on either side of a delimiter between the request header and content.
        4.  Separate all headers and content with separators `\n` to form the final CanonicalizedHeaders.
        CanonicalizedResource in the preceding table is constructed as follows:

        1.  Set CanonicalizedResource as an empty string \(""\).
        2.  Place the URI that you want to access, such as `/event/custom/upload`, between the quotation marks.
        3.  If the request contains a query string \(`QUERY_STRING`\), add a question mark \(`?`\) and the query string to the end of the CanonicalizedResource string.

            `QUERY_STRING` is the lexicographic string of request parameters included in the URL. Equal signs \(`=`\) are placed between the names and values of parameters to form a string. The key-value pairs are then sorted in ascending lexicographical order and connected with ampersands \(`&`\) to form a string. The formula is as follows:

            ```
            QUERY_STRING = "KEY1=VALUE1" + "&" + "KEY2=VALUE2"
            ```

    3.  Generate a digital signature for the request.

        Currently, only HMAC-SHA1 signature algorithm is supported. The following formula is used to generate a signature:

        ```
        Signature = base16(hmac-sha1(UTF8-Encoding-Of(SignString), AccessKeySecret))
        ```

-   **Request parameters** 

    |Parameter|Type|Required?|Description|
    |:--------|:---|:--------|:----------|
    |groupId|long|Yes|The ID of an application group.|
    |metricName|string|Yes|The name of a metric. A metric name can contain letters, digits, and connectors such as underscores \(\_\), hyphens \(-\), periods \(.\), forward slashes \(/\), and backslashes \(\\\). Other characters are invalid. The maximum length is 64 bytes. Excess characters will be truncated from the string.|
    |dimensions|object|Yes|The dimension map. All key-value pairs are strings. A string can contain letters, digits, and connectors such as underscores \(\_\), hyphens \(-\), periods \(.\), forward slashes \(/\), and backslashes \(\\\). The maximum number of key-value pairs is 10. The maximum length of a key is 64 bytes. The maximum length of a value is 64 bytes. Excess characters will be truncated from the string.|
    |time|string|Yes|The time at which the metric value is generated. It supports timestamps in the "yyyyMMdd'T'HHmmss.SSSZ" format or long format, such as 20171012T132456.888+0800 or 1508136760000.|
    |type|int|Yes| The data type of the reported value. 0 indicates raw data and 1 indicates aggregate data.

 When you report aggregate data, we recommend that you report data for both 60s and 300s aggregation periods. Otherwise, you will not be able to query monitoring data that is older than seven days.

 |
    |period|string|No| The aggregation cycle, in seconds.

 If the value of type is 1, this field is required. The value can be 60 or 300.

 |
    |values|object|Yes|The collection of metric values. If the value of type is 0, the key must be "value" and raw data is reported. CloudMonitor aggregates raw data over the aggregation period into several data types, such as maximum, count, and sum.|


## Report data through the Java SDK {#section_ecw_2h5_xfb .section}

-   **Install Java SDK** 

    When you install Java SDK through Maven, add the following dependencies:

    ```
    <dependency>
                <groupId>com.aliyun.openservices</groupId>
                <artifactId>aliyun-cms</artifactId>
                <version>0.2.4</version>
    </dependency>
    ```

-   **Response elements** 

    The system returns the HTTP status code 200.

-   **Samples** 
    -   Sample request

        ```
        POST /metric/custom/upload HTTP/1.1 
        Host: metrichub-cms-cn-hangzhou.aliyuncs.com
        x-cms-api-version:1.0
        Authorization:yourAccessKeyId:yourAccessKeySecret  
        Host:metrichub-cms-cn-hangzhou.aliyuncs.com"
        Date:Mon, 23 Oct 2017 06:51:11 GMT
        Content-Length:180
        x-cms-signature:hmac-sha1
        Content-MD5:E9EF574D1AEAAA370860FE37856995CD
        x-cms-ip:30.27.84.196
        User-Agent:cms-java-sdk-v-1.0
        Content-Type:application/json
        [{"groupId":101,"metricName":"","dimensions":{"sampleName1":"value1","sampleName2":"value2"},"time":"","type":0,"period":60,"values":{"value":10.5,"Sum":100}}]
        ```

    -   Sample response

        ```
        {
           "code":"200",
           "msg":""//The returned msg is null when the reporting is normal.
        }
        ```

-   **Sample code** 

    -   **Report raw data**
    ```
    CMSClientInit.groupId = 101L;//Set the common group ID.
            CMSClient cmsClient = new CMSClient(endpoint, accKey, secret);//Initialize the client.
            CustomMetricUploadRequest request = CustomMetricUploadRequest.builder()
                    .append(CustomMetric.builder()
                            .setMetricName("testMetric")//The metric name
                            .setGroupId(102L)//Set the custom group ID.
                            .setTime(new Date())
                            .setType(CustomMetric.TYPE_VALUE)//The type is raw data.
                            .appendValue(MetricAttribute.VALUE, 1f)//The original value. Key must be an original value.
                            .appendDimension("key", "value")//Add a dimension.
                            .appendDimension("ip", "127.0.0.1")//Add a dimension.
                            .build())
                    .build();
            CustomMetricUploadResponse response = cmsClient.putCustomMetric(request);//Report data.
            System.out.println(JSONObject.toJSONString(response));
    ```

    -   **Automatically report aggregate data for multiple aggregation periods**
    SDK supports data reporting after local aggregation. Data can be aggregated in periods of 1 minute or 5 minutes.

    |Data type|Description|Aggregate value|Memory consumption \(excluding the name, dimension, individual time series, and individual aggregation periods\)|
    |:--------|:----------|:--------------|:---------------------------------------------------------------------------------------------------------------|
    |value|Typical value type|All properties except LastValue|About 4 KB|
    |gauge|Sample value|LastValue|4 bytes|
    |meter|Sum and speed|Sum, SumPerSecond|50 bytes|
    |counter|Count|SampleCount|10 bytes|
    |timer|Computing time|SampleCount, CountPerSecond, Average, Maximum, Minimum, PXX\(P10-P99\)|About 4 KB|
    |histogram|Distribution|SampleCount, Average, Maximum, Minimum, PXX\(P10-P99\)|About 4 KB|

    ```
    //Initialization
            CMSClientInit.groupId = 0L;
            CMSClient cmsClient = new CMSClient(accKey, secret, endpoint);//Create a client.
            CMSMetricRegistryBuilder builder = new CMSMetricRegistryBuilder();
            builder.setCmsClient(cmsClient);
            final MetricRegistry registry = builder.build();//Create a registry, which includes two aggregation periods.
            //Or final MetricRegistry registry = builder.build(RecordLevel. _60S);//Create a registry that only includes aggregate data with an aggregation period of 1 minute.
    //Use value.
    ValueWrapper value = registry.value(MetricName.build("value"));
    value.update(6.5);
    //Use meter.
    MeterWrapper meter = registry.meter(MetricName.build("meter"));
    meter.update(7.2);
    //Use counter.
    CounterWrapper counter = registry.counter(MetricName.build("counter"));
    counter.inc(20);
    counter.dec(5);
    //Use timer.
    TimerWrapper timer = registry.timer(MetricName.build("timer"));
    timer.update(30, TimeUnit.MILLISECONDS);
    //Use histogram.
    HistogramWrapper histogram = registry.histogram(MetricName.build("histogram"));
    histogram.update(20);
    //Use gauge.
    final List list = new ArrayList();
    registry.gauge(MetricName.build("gauge"), new Gauge() {
                            @Override
                            public Number getValue() {
                                return list.size();
                            }
                        });
    ```


## Report data through Alibaba Cloud CLI {#section_ggy_bqk_zdb .section}

 **Prepare an Alibaba Cloud account** 

Ensure that you have created an Alibaba Cloud account, created a RAM user for your account, and generated a RAM user AccessKey with CloudMonitor permissions.

-   **Create a RAM user.**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/155840525647465_en-US.png)

-   **Generate an AccessKey ID and an AccessKey Secret for the RAM user.**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/155840525647466_en-US.png)

-   **Grant CloudMonitor permissions to the RAM user.**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/155840525647474_en-US.png)


 **Install Alibaba Cloud CLI** 

System requirement: Linux, Unix, or macOS.

-   Method 1: Download the installation package.

    You can download the latest CLI from Alibaba Cloud CLI GitHub. The CLI can work with MacOS, Linux, and Windows \(x64\). After decompressing the package, you can move the file to the/usr/local/bin directory or add it to the $PATH environment variables.

-   Method 2: Compile source code.

    Install and configure the Golang environment, and follow the steps to download and compile the source code.

    ``` {#codeblock_7zi_2ns_6p1}
    ...
    $ mkdir -p $GOPATH/src/github.com/aliyun
    $ cd $GOPATH/src/github.com/aliyun
    $ git clone http://github.com/aliyun/aliyun-cli.git
    $ git clone http://github.com/aliyun/aliyun-openapi-meta.git
    $ cd aliyun-cli
    $ make install
    ...
    ```


 **Configure Alibaba Cloud CLI** 

Before using Alibaba Cloud CLI, you must run the aliyun configure command to configure the AccessKey, region, and language for calling Alibaba Cloud resources. You can create and view your AccessKey on the AccessKey page of the Alibaba Cloud console, or obtain the AccessKey form your system administrator.

``` {#codeblock_p1q_xwi_969}
$ aliyun configure
Configuring profile 'default' ...
Aliyun Access Key ID [None]: <Your AccessKey ID>
Aliyun Access Key Secret [None]: <Your AccessKey Secret>
Default Region Id [None]: cn-hangzhou
Default output format [json]: json
Default Language [zh]: zh
```

Alibaba Cloud CLI supports multi-user configuration. You can run the $ aliyun configure --profile user1 command to specify the RAM user that can call Alibaba Cloud APIs. You can run the `$ aliyun configure list` command to view the RAM user configurations as described in the following table. The asterisk \(\*\) in the Profile column indicates that the configuration is used.

|Profile|Credential|Valid|Region|Language|
|-------|----------|-----|------|--------|
|default \*|AK:\*\*\*f9b|Valid|cn-beijing|zh|
|aaa|AK:\*\*\*\*\*\*|Invalid| | |
|test|AK:\*\*\*456|Valid| |en|
|ecs|EcsRamRole:EcsTest|Valid|cn-beijing|en|

Alibaba Cloud CLI can use different authentication methods by adding the --mode <authenticationMethod\> parameter after the configure command. Currently, the following authentication methods are supported.

|Authentication method|Description|
|---------------------|-----------|
|AK|Includes an AccessKey ID and an Access Key Secret.|
|StsToken|The STS token.|
|RamRoleArn|Calls the AssumeRole action of the RAM user.|
|EcsRamRole|Calls the EcsRamRole action on an ECS instance.|

 **Report monitoring data** 

Use the PutCustomMetric API to report the monitoring data.

``` {#codeblock_mby_6op_2wl}
aliyun cms PutCustomMetric  --MetricList. 1.MetricName cpu_total --MetricList. 1.Dimensions '{"sampleName1":"value1","sampleName2":"value2"}' --MetricList. 1.Time 1555390981421 --MetricList. 1.Type 0 --MetricList. 1.Period 60 --MetricList. 1.Values '{"value":10.5}' --MetricList. 1.GroupId "0"
```

If the data is reported successfully, status code 200 is returned.

``` {#codeblock_f46_e4v_gbz}
{
  "Message": "success",
  "RequestId": "F69F5623-DDD6-42AE-AE59-87A2B841620B",
  "Code": "200"
}
```

 **Error codes** 

|Error code|Description|
|:---------|:----------|
|200|Normal.|
|206| Partially successful.

 If "reach Max time series num" is returned, you have reached the maximum amount of time series. We recommend that you purchase a higher quota or remove unnecessary time series.

 If "not allowed original value, please upgrade service" is returned, you are using the free edition, which cannot support raw data.

 If "type is invalid" is returned, the value of the type parameter is invalid. Ensure that the value of this parameter is 0 or 1.

 |
|400|Syntax error in a client request.|
|403|Verification failure, speed limit, or not authorized.|
|500|Internal server error.|

 **RAM user authorization** 

You must grant CloudMonitor permissions to the corresponding RAM user before event data can be reported with the RAM user AccessKey. If these permissions are not granted, the prompt "cannot upload, please use ram to auth" will be displayed when you report data.

1.  Log on to the [RAM console](https://partners-intl.console.aliyun.com/#/ram).
2.  In the left-side navigation pane, select **Users**. The Users page is displayed.
3.  Select the target RAM user and click **Add Permissions**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/155840525647475_en-US.png)

4.  On the displayed page, select **AliyunCloudMonitorFullAccess** and click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/155840525647476_en-US.png)


