# Report monitoring data {#concept_b2h_ddb_5db .concept}

This topic describes how to report custom monitoring data.

Custom monitoring allows you to customize metrics and alarm rules to meet your business requirements. Custom monitoring provides API operations for reporting monitoring data. You can use the API operations to report collected time series data to CloudMonitor \(CMS\). You can also configure alarm rules to receive notifications of corresponding exceptions.

CloudMonitor provides API operations, Java SDKs, and Alibaba Cloud command line interface \(CLI\) for reporting data.

## Limits {#section_q4b_znk_zdb .section}

-   The upper limit of queries per second \(QPS\) is 200 QPS in China \(Beijing\), China \(Shanghai\), and China \(Hangzhou\), 100 QPS in China \(Zhangjiakou-Beijing Winter Olympics\) and China \(Shenzhen\), and 50 QPS in all other regions.
-   The system reports a maximum of 100 data entries at one time. The body size is 256 KB or less.
-   The `metricName` field can only contain letters, digits, and underscores \(\_\). This field must start with a letter. If the starting character is not a letter, this character is replaced with an uppercase A. Invalid characters are replaced with underscores \(\_\).
-   The `dimensions` field cannot contain equal signs \(=\), ampersands \(&\), or commas \(,\). Invalid characters are replaced with underscores \(\_\).
-   The string length of the key or value of both `metricName` and `dimensions` is 64 bytes or less. Otherwise, the key or value string is truncated.
-   You have to pay for reporting raw data. You can obtain aggregated data free of charge. To obtain the free data, set the Type field to 1 in the request parameters.

## Report data by using API operations {#section_zym_l4k_zdb .section}

After you report the raw data by using API operations, CloudMonitor uses the following statistical methods to calculate the statistics at 1-minute and 5-minute intervals:

-   Average: the average value.
-   Maximum: the maximum value.
-   Minimum: the minimum value.
-   Sum: the sum value.
-   SampleCount: the count.
-   SumPerSecond: the sum divided by the total number of seconds of the corresponding aggregation period. You can also use the moving average calculation.
-   CountPerSecond: the count divided by the total number of seconds of the corresponding aggregation period. You can also use the moving average calculation.
-   LastValue: the last sampled value in the aggregation period.
-   P10: the value of the 10th percentile. This value is greater than 10% of all data in the aggregation period.
-   P20: the value of the 20th percentile. This value is greater than 20% of all data in the aggregation period.
-   P30: the value of the 30th percentile. This value is greater than 30% of all data in the aggregation period.
-   P40: the value of the 40th percentile. This value is greater than 40% of all data in the aggregation period.
-   P50: the value of the 50th percentile. This value is a median value and greater than 50% of all data in the aggregation period.
-   P60: the value of the 60th percentile. This value is greater than 60% of all data in the aggregation period.
-   P70: the value of the 70th percentile. This value is greater than 70% of all data in the aggregation period.
-   P75: the value of the 75th percentile. This value is greater than 75% of all data in the aggregation period.
-   P80: the value of the 80th percentile. This value is greater than 80% of all data in the aggregation period.
-   P90: the value of the 90th percentile. This value is greater than 90% of all data in the aggregation period.
-   P95: the value of the 95th percentile. This value is greater than 95% of all data in the aggregation period.
-   P98: the value of the 98th percentile. This value is greater than 98% of all data in the aggregation period.
-   P99: the value of the 99th percentile. This value is greater than 99% of all data in the aggregation period.

-   **Endpoints** 

    Internet endpoint: `https://metrichub-cms-cn-hangzhou.aliyuncs.com`.

    The following table lists the intranet endpoints.

    |Region|Region ID|Endpoint|
    |:-----|:--------|:-------|
    |China \(Hangzhou\)|cn-hangzhou|http://metrichub-cn-hangzhou.aliyun.com|
    |China \(Zhangjiakou-Beijing Winter Olympics\)|cn-zhangjiakou|http://metrichub-cn-zhangjiakou.aliyun.com|
    |China \(Shanghai\)|cn-shanghai|http://metrichub-cn-shanghai.aliyun.com|
    |China \(Beijing\)|cn-beijing|http://metrichub-cn-beijing.aliyun.com|
    |China \(Qingdao\)|cn-qingdao|http://metrichub-cn-qingdao.aliyun.com|
    |China \(Shenzhen\)|cn-shenzhen|http://metrichub-cn-shenzhen.aliyun.com|
    |China \(Hong Kong\)|cn-hongkong|http://metrichub-cn-hongkong.aliyun.com|
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

    ``` {#codeblock_vvl_wxz_iig}
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

    CloudMonitor only supports the HMAC-SHA1 signature algorithm.

    1.  Prepare an Alibaba Cloud AccessKey pair.

        To generate a digital signature for an API request, you must use an AccessKey pair that consists of the AccessKey ID and AccessKey Secret. You can use an existing AccessKey pair or create a new one. The AccessKey pair must be in **Active** status.

    2.  Generate a signature string for the request.

        An API signature string consists of the Method, Header, and Body fields of the HTTP request.

        ``` {#codeblock_lk9_0p2_umf}
        SignString = VERB + "\n"
                     + CONTENT-MD5 + "\n"
                     + CONTENT-TYPE + "\n"
                     + DATE + "\n"
                     + CanonicalizedHeaders + "\n"
                     + CanonicalizedResource
        ```

        In this formula, `\n` indicates the newline escape character and the plus sign \(`+`\) indicates the string concatenation operator. The other parts are defined as follows:

        |Parameter|Description|Example|
        |:--------|:----------|:------|
        |VERB|The method name of the HTTP request.|PUT, GET, and POST|
        |CONTENT-MD5|The MD5 value of the Body field in the HTTP request. This value must be an uppercase string.|875264590688CA6171F6228AF5BBB3D2|
        |CONTENT-TYPE|The type of the Body field in the request.|application/json|
        |DATE|The standard timestamp header of the HTTP request. This timestamp header follows the RFC 1123 specification and uses GMT standard time.|Mon, 3 Jan 2010 08:33:47 GMT|
        |CanonicalizedHeaders|The string constructed by the custom headers that are prefixed with x-cms and x-acs of the HTTP request.|x-cms-api-version:0.1.0\\nx-cms-signature|
        |CanonicalizedResource|The string constructed by the HTTP request resources, as described in the following section.|/event/custom/upload|

        The CanonicalizedHeaders string in the preceding table is constructed as follows:

        1.  Convert the names of all HTTP request headers that are prefixed with `x-cms` and `x-acs` to lowercase letters.
        2.  Sort the CMS custom request headers generated in the preceding step in lexicographic order.
        3.  Delete any space on either side of a delimiter between a request header and the corresponding content.
        4.  Separate all headers and content with separators \(`\n`\) to form the final CanonicalizedHeaders string.
        The CanonicalizedResource string in the preceding table is constructed as follows:

        1.  Set CanonicalizedResource as an empty string \(""\).
        2.  Place the URI that you want to access, such as `/event/custom/upload`, between the quotation marks.
        3.  If the request contains a query string in `QUERY_STRING`, add a question mark \(`?`\) and the query string to the end of the CanonicalizedResource string.

            In the request, `QUERY_STRING` is the lexicographically sorted string of the request parameters included in the URL. Equal signs \(`=`\) are used between the names and values of parameters to form a string. The parameter name-parameter value pairs are then sorted in lexicographic order and connected with ampersands \(`&`\) to form a string. The formula is as follows:

            ``` {#codeblock_vvg_kdn_0bs}
            QUERY_STRING = "KEY1=VALUE1" + "&" + "KEY2=VALUE2"
            ```

    3.  Generate a digital signature for the request.

        The default signature algorithm is HMAC-SHA1. You can use the following formula to generate a signature:

        ``` {#codeblock_1ik_e52_zzi}
        Signature = base16(hmac-sha1(UTF8-Encoding-Of(SignString), AccessKeySecret))
        ```

-   **Request parameters** 

    |Parameter|Type|Required|Description|
    |:--------|:---|:-------|:----------|
    |groupId|Long|Yes|The ID of your application group.|
    |metricName|String|Yes|The name of a metric that you want to monitor. A metric name can contain letters, digits, and connectors such as underscores \(\_\), hyphens \(-\), periods \(.\), forward slashes \(/\), and backslashes \(\\\). Other characters are invalid. The maximum length is 64 bytes. Excess characters are truncated from the string.|
    |dimensions|Object|Yes|The dimension map. All key-value pairs are strings. A string can contain letters, digits, and connectors such as underscores \(\_\), hyphens \(-\), periods \(.\), forward slashes \(/\), and backslashes \(\\\). The maximum number of key-value pairs is 10. The maximum length of a key is 64 bytes. The maximum length of a value is 64 bytes. Excess characters are truncated from the string.|
    |time|String|Yes|The time when the metric value was generated. The time supports timestamps in the yyyyMMdd’T’HHmmss.SSSZ format or long format, such as 20171012T132456.888+0800 or 1508136760000.|
    |type|Integer|Yes| The data type of the reported value. A value of 0 specifies raw data and a value of 1 specifies aggregate data.

 When you report aggregate data, we recommend that you report data for both 60s and 300s aggregation periods. Otherwise, you cannot query monitoring data in a time span that is more than seven days.

 |
    |period|String|No| The aggregation period. Unit: seconds.

 If the type parameter is set to 1, this field is required. Valid values: 60 and 300.

 |
    |values|Object|Yes|The collection of metric values. If the type parameter is set to 0, the key of this parameter must be set to value, so raw data is reported. CloudMonitor aggregates raw data over the aggregation period into several data types, such as maximum, count, and sum.|


## Report data by using the Java SDK {#section_ecw_2h5_xfb .section}

-   **Install the Java SDK** 

    When you install the Java SDK based on Maven, add the following dependency:

    ``` {#codeblock_938_pi6_ts1}
    <dependency>
                <groupId>com.aliyun.openservices</groupId>
                <artifactId>aliyun-cms</artifactId>
                <version>0.2.4</version>
    </dependency>
    ```

-   **Response elements** 

    The system returns the HTTP status code 200.

-   **Examples** 
    -   Sample request

        ``` {#codeblock_2bc_snk_e6y}
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

        ``` {#codeblock_o6h_bed_2pe}
        {
           "code":"200",
           "msg":""//The returned msg is null when the reporting is normal.
        }
        ```

-   **Code examples** 

    -   **Report raw data**
    ``` {#codeblock_jbi_19v_xsu}
    CMSClientInit.groupId = 101L;//Set a common group ID.
            CMSClient cmsClient = new CMSClient(endpoint, accKey, secret);//Initialize the client.
            CustomMetricUploadRequest request = CustomMetricUploadRequest.builder()
                    .append(CustomMetric.builder()
                            .setMetricName("testMetric")//The metric name.
                            .setGroupId(102L)//Set a custom group ID.
                            .setTime(new Date())
                            .setType(CustomMetric.TYPE_VALUE)//The type is raw data.
                            .appendValue(MetricAttribute.VALUE, 1f)//The raw data. The key must be MetricAttribute.VALUE.
                            .appendDimension("key", "value")//Add a dimension.
                            .appendDimension("ip", "127.0.0.1")//Add a dimension.
                            .build())
                    .build();
            CustomMetricUploadResponse response = cmsClient.putCustomMetric(request);//Report data.
            System.out.println(JSONObject.toJSONString(response));
    ```

    -   **Automatically report aggregate data for multiple aggregation periods**
    The Java SDK supports data reporting after local aggregation. Aggregation periods can be 1 minute and 5 minutes.

    |Data type|Description|Aggregate value|Memory consumption \(excluding the name, dimension, individual time series, and individual aggregation periods\)|
    |:--------|:----------|:--------------|:---------------------------------------------------------------------------------------------------------------|
    |value|Typical value type|All attributes except LastValue|Approximately 4 KB|
    |gauge|Sample value|LastValue|4 bytes|
    |meter|Sum and rate|Sum, SumPerSecond|50 bytes|
    |counter|Count|SampleCount|10 bytes|
    |timer|Computing time|SampleCount, CountPerSecond, Average, Maximum, Minimum, and PXX\(P10-P99\)|Approximately 4 KB|
    |histogram|Distribution|SampleCount, Average, Maximum, Minimum, and PXX\(P10-P99\)|Approximately 4 KB|

    ``` {#codeblock_f8c_coi_yjq}
    //Initialization
            CMSClientInit.groupId = 0L;
            CMSClient cmsClient = new CMSClient(accKey, secret, endpoint);//Create a client.
            CMSMetricRegistryBuilder builder = new CMSMetricRegistryBuilder();
            builder.setCmsClient(cmsClient);
            final MetricRegistry registry = builder.build();//Create a registry that includes two aggregation periods.
            //Or final MetricRegistry registry = builder.build(RecordLevel. _60S);//Create a registry that only includes aggregate data in a 1-minute aggregation period.
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


## Report data by using Alibaba Cloud CLI {#section_ggy_bqk_zdb .section}

 **Prepare an Alibaba Cloud account** 

Make sure that you have created an Alibaba Cloud account, created a RAM user for your account, and generated an AccessKey pair for the RAM user to grant CloudMonitor permissions.

-   **Create a RAM user.**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/156281993847465_en-US.png)

-   **Generate an AccessKey ID and an AccessKey Secret for the RAM user.**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/156281993847466_en-US.png)

-   **Grant CloudMonitor permissions to the RAM user.**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/156281993947474_en-US.png)


 **Install Alibaba Cloud CLI** 

Required operation systems: Linux, Unix, or MacOS.

-   Method 1: download the installation package

    You can download the installation package of the latest CLI tool from Alibaba Cloud CLI GitHub, and decompress the package to use the CLI. The CLI supports Mac, Linux, and Windows \(x64\) terminals. After decompression, you can move the aliyun file to the /usr/local/bin directory or add the file to the $PATH environment variable.

-   Method 2: compile source code

    Install and configure the Golang environment, and follow these steps to download and compile the source code:

    ``` {#codeblock_7zi_2ns_6p1}
    ```
    $ mkdir -p $GOPATH/src/github.com/aliyun
    $ cd $GOPATH/src/github.com/aliyun
    $ git clone http://github.com/aliyun/aliyun-cli.git
    $ git clone http://github.com/aliyun/aliyun-openapi-meta.git
    $ cd aliyun-cli
    $ make install
    ```
    ```


 **Configure the CLI** 

Before using Alibaba Cloud CLI, you must run the aliyun configure command to configure the AccessKey pair, region, and language. You use the configured data to call Alibaba cloud resources. You can create and view your AccessKey pair on the AccessKey page in the Alibaba Cloud console, or contact your system administrator to obtain the AccessKey pair.

``` {#codeblock_p1q_xwi_969}
$ aliyun configure
Configuring profile 'default' ...
Aliyun Access Key ID [None]: <Your AccessKey ID>
Aliyun Access Key Secret [None]: <Your AccessKey Secret>
Default Region Id [None]: cn-hangzhou
Default output format [json]: json
Default Language [zh]: zh
```

Multi-user configuration: Alibaba Cloud CLI supports multi-user configuration. You can run the $ aliyun configure --profile user1 command to specify the account used to call API operations of cloud services. Run the `$ aliyun configure list` command to view the current user configuration, as shown in the following table. The asterisk \(\*\) next to the Profile field value indicates the default user configuration.

|Profile|Credential|Valid|Region|Language|
|-------|----------|-----|------|--------|
|default \*|AK:\*\*\*f9b|Valid|cn-beijing|zh|
|aaa|AK:\*\*\*\*\*\*|Invalid| | |
|test|AK:\*\*\*456|Valid| |en|
|ecs|EcsRamRole:EcsTest|Valid|cn-beijing|en|

To specify the authentication method, you can add the --mode <authenticationMethod\> parameter to the end of the configure command in the CLI. Supported authentication methods are listed as follows:

|Authentication method|Description|
|---------------------|-----------|
|AK|Use the AccessKey ID and AccessKey Secret to authorize access permissions.|
|StsToken|Use the Security Token Service \(STS\) token to authorize access permissions.|
|RamRoleArn|Use AssumeRole of the RAM user to authorize access permissions.|
|EcsRamRole|Use EcsRamRole on an ECS instance to access the instance with no password.|

 **Report monitoring data** 

Call the PutCustomMetric API operation to report the monitoring data.

``` {#codeblock_mby_6op_2wl}
aliyun cms PutCustomMetric  --MetricList. 1.MetricName cpu_total --MetricList. 1.Dimensions '{"sampleName1":"value1","sampleName2":"value2"}' --MetricList. 1.Time 1555390981421 --MetricList. 1.Type 0 --MetricList. 1.Period 60 --MetricList. 1.Values '{"value":10.5}' --MetricList. 1.GroupId "0"
```

The system returns Status code 200 to indicate successful reporting.

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
|200|The error message returned because you reported data successfully.|
|206| The error message returned because some data failed to be reported.

 If the system returns "reach Max time series num", you have used up the time series quota. We recommend that you purchase a higher quota or remove unnecessary time series.

 If the system returns "not allowed original value, please upgrade service", you have used a free edition. You cannot use this edition to report raw data.

 If the system returns "type is invalid", the value of the type parameter was invalid. Make sure that the value of this parameter is 0 or 1.

 |
|400|The error message returned because a syntax error has occurred in the client request.|
|403|The error message returned because the verification failed, the target rate reached the upper limit, or the target permission was not authorized.|
|500|The error message returned because an internal server error has occurred.|

 **Create a RAM user** 

To use the AccessKey pair of the corresponding RAM user to report event data, you must grant CloudMonitor permissions to the RAM user. If you have not granted the permissions, the system returns the error "cannot upload data, please use ram to auth" when you report data.

1.  Log on to the [RAM console](https://partners-intl.console.aliyun.com/#/ram).
2.  In the left-side navigation pane, click **Users** to go to the Users page.
3.  On the Users page that appears, select the RAM user that you use to report data, and click **Add Permissions** in the Actions column next to the target RAM user.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/156281993947475_en-US.png)

4.  On the Add Permissions page, select **AliyunCloudMonitorFullAccess** and click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6219/156281993947476_en-US.png)


