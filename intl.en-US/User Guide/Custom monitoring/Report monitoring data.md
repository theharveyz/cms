# Report monitoring data {#concept_b2h_ddb_5db .concept}

Custom monitoring provides the API for reporting monitoring data so that you can report the time series data you have collected to CloudMonitor and configure alarm rules to receive alarm notifications.

CloudMonitor provides three methods for reporting data, namely OpenAPI, Java SDK, and Alibaba Cloud CLI.

## Restrictions {#section_q4b_znk_zdb .section}

-   The QPS limit for an Alibaba Cloud account is 100.
-   A maximum of 100 entries of data can be reported at one time. The body size cannot exceed 256 KB.
-   The `metricName` field only supports letters, numbers, and underscores. The field must start with a letter. A non-letter start is replaced with an uppercase "A" and invalid characters are replaced with underscores \(\_\).
-   The `dimensions` field does not support "=", "&amp;", or ",". Invalid characters are replaced with underscores \(\_\).
-   The Key-value of `metricName` and `dimensions` cannot exceed 64 bytes. Otherwise, the Key-value is truncated.

## Report data using OpenAPI {#section_zym_l4k_zdb .section}

-   Service addresses

    [Internet service address](https://metrichub-cms-cn-hangzhou.aliyuncs.com/?spm=a2c4g.11186623.2.5.220HYi)

    Intranet service addresses are listed in the following table.

    |Region|Endpoint|
    |:-----|:-------|
    |East China 1 \(Hangzhou\)|[http://metrichub-cn-hangzhou.aliyun.com](http://metrichub-cn-hangzhou.aliyun.com/?spm=a2c4g.11186623.2.6.220HYi)|
    |North China 3 \(Zhangjiakou\)|[http://metrichub-cn-zhangjiakou.aliyun.com](http://metrichub-cn-zhangjiakou.aliyun.com/?spm=a2c4g.11186623.2.7.220HYi)|
    |East China 2|[http://metrichub-cn-shanghai.aliyun.com](http://metrichub-cn-shanghai.aliyun.com/?spm=a2c4g.11186623.2.8.220HYi)|
    |North China 2 \(Beijing\)|[http://metrichub-cn-beijing.aliyun.com](http://metrichub-cn-beijing.aliyun.com/?spm=a2c4g.11186623.2.9.220HYi)|
    |North China 1 \(Qingdao\)|[http://metrichub-cn-qingdao.aliyun.com](http://metrichub-cn-qingdao.aliyun.com/?spm=a2c4g.11186623.2.10.220HYi)|
    |South China 1 \(Shenzhen\)|[http://metrichub-cn-shenzhen.aliyun.com](http://metrichub-cn-shenzhen.aliyun.com/?spm=a2c4g.11186623.2.11.220HYi)|
    |Hong Kong|[http://metrichub-cn-hongkong.aliyun.com](http://metrichub-cn-hongkong.aliyun.com/?spm=a2c4g.11186623.2.12.220HYi)|
    |North China 5 \(Hohhot\)|[http://metrichub-cn-huhehaote.aliyun.com](http://metrichub-ap-southeast-5.aliyuncs.com/?spm=a2c4g.11186623.2.13.220HYi)|
    |Middle-East East 1 \(Dubai\)|[http://metrichub-me-east-1.aliyun.com](http://metrichub-me-east-1.aliyun.com/?spm=a2c4g.11186623.2.14.220HYi)|
    |West US 1 \(Silicon valley\)|[http://metrichub-us-west-1.aliyun.com](http://metrichub-us-west-1.aliyun.com/?spm=a2c4g.11186623.2.16.220HYi)|
    |East US 1 \(Virginia\)|[http://metrichub-us-east-1.aliyun.com](http://metrichub-us-east-1.aliyun.com/?spm=a2c4g.11186623.2.15.220HYi)|
    |Asia-Pacific Northeast 1 \(Japan\)|[http://metrichub-ap-northeast-1.aliyun.com](http://metrichub-ap-northeast-1.aliyun.com/?spm=a2c4g.11186623.2.17.220HYi)|
    |Central Europe 1 \(Frankfurt\)|[http://metrichub-eu-central-1.aliyun.com](http://metrichub-eu-central-1.aliyun.com/?spm=a2c4g.11186623.2.18.220HYi)|
    |Asia-Pacific Southeast 2 \(Sydney\)|[http://metrichub-ap-southeast-2.aliyun.com](http://metrichub-ap-southeast-2.aliyun.com/?spm=a2c4g.11186623.2.19.220HYi)|
    |Asia-Pacific Southeast 1 \(Singapore\)|[http://metrichub-ap-southeast-1.aliyun.com](http://metrichub-ap-southeast-1.aliyun.com/?spm=a2c4g.11186623.2.20.220HYi)|
    |Asia-Pacific Southeast 3 \(Kuala Lumpur\)|[http://metrichub-ap-southeast-3.aliyun.com](http://metrichub-ap-southeast-3.aliyun.com/?spm=a2c4g.11186623.2.21.220HYi)|
    |Asia-Pacific South 1 \(Mumbai\)|[http://metrichub-ap-south-1.aliyuncs.com](http://metrichub-ap-south-1.aliyuncs.com/?spm=a2c4g.11186623.2.22.220HYi)|

-   Request syntax

    ```
    POST /metric/custom/upload HTTP/1.1 
    Authorization:&lt;AuthorizationString>
    Content-Length:&lt;Content Length>
    Content-MD5:&lt;Content MD5>
    Content-Type:application/json
    Date:&lt;GMT Date>
    HOST: maid
    x-cms-signature:hmac-sha1
    x-cms-api-version:1.0
    x-cms-ip:30.27.84.196
    User-Agent:cms-java-sdk-v-1.0
    [{"groupId":101,"metricName":"","dimensions":{"sampleName1":"value1","sampleName2":"value2"},"time":"","type":0,"period":60,"values":{"value":10.5,"Sum":100}}]
    ```


-   [Signature Algorithm](https://www.alibabacloud.com/help/doc-detail/60202.htm)
-   Request parameters

    |Name|Type|Required|Description|
    |:---|:---|:-------|:----------|
    |groupId|Long|Yes|ID of an application group|
    |metricName|String|Yes|Name of a monitoring metric, supporting letters, numbers, and connectors "\_-./\\". Others are invalid characters. The maximum length is 64 bytes. The part in excess of the limit is truncated.|
    |dimensions|Object|Yes|The dimension map. Key-values are strings supporting letters, numbers, and connectors "\_-./\\". The maximum number of key-value pairs is 10. The maximum length of keys is 64 bytes. The maximum length of values is 64 bytes. The part in excess of the limit is truncated.|
    |time|String|Yes|Metric occurrence time, supporting two formats, namely, "yyyyMMdd'T'HHmmss.SSSZ" and long timestamp. For example, "20171012T132456.888+0800" and "1508136760000."|
    |type|Integer|Yes|The type of the reported value. 0 is the original value, and 1 is the aggregate data. When reporting aggregate data, it is recommended to report both the data of the 60s period and that of the 300s period. Otherwise, the monitoring data spanning more than 7 days cannot queried normally.|
    |period|String|No|The aggregation cycle, in seconds. If type=1, this field is required. The value can be 60 or 300.|
    |values|Object| Yes|The collection of metric values. If type=0, key must be "value" and the original value is reported. CloudMonitor aggregates original values into multiple values in accordance with cycles, for example, maximum, count, and sum.|

    After original data is reported through the interface, CloudMonitor calculates statistics results of one minute and five minutes in the following statistical methods:

    -   Average: average value
    -   Maximum: maximum value
    -   Minimum: minimum value
    -   Sum: sum value
    -   SampleCount: count
    -   SumPerSecond: sum/the seconds of the corresponding cycle. You can also use the moving average calculation.
    -   CountPerSecond: count/the seconds of the corresponding cycle. You can also use the moving average calculation.
    -   LastValue: the last sampling value in the cycle, which is similar to gauge.
    -   P10: percentile 0.1, greater than 10% of all sampling data in the cycle
    -   P20: percentile 0.2, greater than 20% of all sampling data in the cycle
    -   P30: percentile 0.3, greater than 30% of all sampling data in the cycle
    -   P40: percentile 0.4, greater than 40% of all sampling data in the cycle
    -   P50: percentile 0.5, greater than 50% of all sampling data in the cycle, median
    -   P60: percentile 0.6, greater than 60% of all sampling data in the cycle
    -   P70: percentile 0.7, greater than 70% of all sampling data in the cycle
    -   P75: percentile 0.75, greater than 75% of all sampling data in the cycle
    -   P80: percentile 0.8, greater than 80% of all sampling data in the cycle
    -   P90: percentile 0.9, greater than 90% of all sampling data in the cycle
    -   P95: percentile 0.95, greater than 95% of all sampling data in the cycle
    -   P98: percentile 0.98, greater than 98% of all sampling data in the cycle
    -   P99: percentile 0.99, greater than 99% of all sampling data in the cycle
-   Install Java SDK

    When performing installation through maven, the following dependencies must be added:

    ```
    &lt;dependency>
                &lt;groupId>com.aliyun.openservices&lt;/groupId>
                &lt;artifactId>aliyun-cms&lt;/artifactId>
                &lt;version>0.2.4&lt;/version>
    &lt;/dependency>
    ```

-   Response element

    The system returns the HTTP status code 200.

-   Examples
    -   Request example

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

    -   Return example

        ```
        {
           "code":"200",
           "msg":""//The returned msg is null when the reporting is normal.
        }
        ```


## Code example {#section_y1s_spk_zdb .section}

-   Report original data

    ```
    CMSClientInit.groupId = 101L;//Set the common group ID
            CMSClient cmsClient = new CMSClient(endpoint, accKey, secret);//初始化client
            CustomMetricUploadRequest request = CustomMetricUploadRequest.builder()
                    .append(CustomMetric.builder()
                            .setMetricName("testMetric")//Metric name
                            .setGroupId(102L)//Set the custom group ID
                            .setTime(new Date())
                            .setType(CustomMetric.TYPE_VALUE)//The type is the original value
                            .appendValue(MetricAttribute.VALUE, 1f)//The original value. Key must be an original value
                            .appendDimension("key", "value")//Add a dimension
                            .appendDimension("ip", "127.0.0.1")//Add a dimension
                            .build())
                    .build();
            CustomMetricUploadResponse response = cmsClient.putCustomMetric(request);//Report
            System.out.println(JSONObject.toJSONString(response));
    ```


-   Automatically complete aggregated reporting of multiple cycles

    SDK supports data reporting after local aggregation. The aggregation cycles are one minute and five minutes.

    |Data type|Description|Aggregated value|Memory consumption \(excluding the name, dimension, individual time series, and individual aggregation cycle\)|
    |:--------|:----------|:---------------|:-------------------------------------------------------------------------------------------------------------|
    |value|Typical value type|All properties except LastValue|About 4K|
    |gauge|Sample value|LastValue|4 bytes|
    |meter|Sum and speed|Sum, SumPerSecond|50 bytes|
    |counter|Count|SampleCount|10 bytes|
    |timer|Computing time|SampleCount, CountPerSecond, Average, Maximum, Minimum, PXX\(P10-P99\)|About 4K|
    |histogram|Distribution|SampleCount, Average, Maximum, Minimum, PXX\(P10-P99\)|About 4K|

    ```
    //Initialization
            CMSClientInit.groupId = 0L;
            CMSClient cmsClient = new CMSClient(accKey, secret, endpoint);//Create a client
            CMSMetricRegistryBuilder builder = new CMSMetricRegistryBuilder();
            builder.setCmsClient(cmsClient);
            final MetricRegistry registry = builder.build();//Create a registry which includes two aggregation cycles
            //or final MetricRegistry registry = builder.build(RecordLevel. _60S);//Only create a registry which includes an aggregation cycle of one minute
    //Use value
    ValueWrapper value = registry.value(MetricName.build("value"));
    value.update(6.5);
    //Use meter
    MeterWrapper meter = registry.meter(MetricName.build("meter"));
    meter.update(7.2);
    //Use counter
    CounterWrapper counter = registry.counter(MetricName.build("counter"));
    counter.inc(20);
    counter.dec(5);
    //Use timer
    TimerWrapper timer = registry.timer(MetricName.build("timer"));
    timer.update(30, TimeUnit.MILLISECONDS);
    //Use histogram
    HistogramWrapper histogram = registry.histogram(MetricName.build("histogram"));
    histogram.update(20);
    //Use gauge
    final List list = new ArrayList();
    registry.gauge(MetricName.build("gauge"), new Gauge() {
                            @Override
                            public Number getValue() {
                                return list.size();
                            }
                        });
    ```


## Report data using Alibaba Cloud CLI {#section_ggy_bqk_zdb .section}

```
You have an Alibaba Cloud account and have generated a sub-account AK with CloudMonitor permissions (it is more secure to use a sub-account).
```

-   Create a sub-account.
-   Generate an AccessKey ID and an AccessKey secret for the sub-account.
-   Grant CloudMonitor permissions for the sub-account.

## Operation procedure {#section_wln_wlj_zdb .section}

1.  Install Alibaba Cloud CLI.

    ```
    System requirement: Linux, Unix, or Mac OS. Environment requirement: Python 2.7.x has been installed.
    ```

    1.  Install Python
        -   If your device has Python 2.7.x installed, skip this step.
        -   Otherwise, run the following command in the command line interface to install Python: Make sure that your device is installed with wget.

            ```
            wget https://www.python.org/ftp/python/2.7.8/Python-2.7.8.tgz (or download it in some other way and put it in a certain path)
            tar -zxvf Python-2.7.8.tgz
            cd Python-2.7.8
            ./configure
            make
            sudo make install
            ```

    2.  Install pip
        -   If your device has pip installed, skip this step.
        -   Otherwise, run the following command in the command line interface to install pip:

            ```
            curl "https://bootstrap.pypa.io/get-pip.py" -o "pip-install.py"
            sudo python pip-install.py
            ```

        -   If the system displays information similar to the following, the installation is successful.

            ```
            Successfully installed pip-7.1.2 setuptools-18.7 wheel-0.26.0
            ```

    3.  Install the command line tool

        If the pip version is too low in the system, it will cause an error in the CLI installation. You can use the following command to upgrade the pip software before performing other operations: Use pip 7.x or later. If your pip is already the latest, skip this step.

        1.  Run the following command in the command line interface to upgrade the pip.

            ```
            sudo pip install -U pip
            ```

            If the system displays information similar to the following, the upgrade is successful.

            ```
            Successfully uninstalled pip-7.1.2
            Successfully installed pip-8.1.2
            ```

        1.  Run the following command to install the Alibaba Cloud command line tool:

            ```
            sudo pip install aliyuncli
            ```

            If the system displays information similar to the following, the installation is successful.

            ```
            Successfully installed aliyuncli-2.1.2 colorama-0.3.3 jmespath-0.7.1
            ```

    4.  Configure the command line tool

        ```
        ~ sudo aliyuncli configure
        Aliyun Access Key ID [*******************a]: youraccesskeyid
        Aliyun Access Key Secret [*******************b]: youraccesskeysecret
        Default Region Id [cn-hangzhou]: cn-hangzhou
        Default output format [json]: json
        ```

2.  Install CmsSDK
    -   Installation method for Windows

        ```
        cd C:\Python27\Scripts
        pip install aliyun-python-sdk-cms
        ```

    -   To update the SDK, run the following command:

        ```
        pip install --upgrade aliyun-python-sdk-cms
        ```

    -   Installation method for Linux

        ```
        sudo pip install aliyun-python-sdk-cms
        ```

    -   To update the SDK, run the following command:

        ```
        sudo pip install —upgrade aliyun-python-sdk-cms
        ```

3.  Report monitoring data

    Use the PutCustomMetric interface.

    -   The reporting example for Windows

        ```
        aliyuncli.exe cms PutCustomMetric --MetricList "[{'groupId':1,'metricName':'testMetric','dimensions':{'sampleName1':'value1','sampleName2':'value2'},'type':0,'values':{'value':10.5}}]"
        ```

    -   The reporting example for Linux

        ```
        aliyuncli cms PutCustomMetric --MetricList "[{'groupId':1,'metricName':'testMetric','dimensions':{'sampleName1':'value1','sampleName2':'value2'},'type':0,'values':{'value':10.5}}]"
        ```

    -   After the data is reported successfully, status code 200 is returned.

        ```
        {
        "Code":"200"
        }
        ```


## Error codes {#section_ovd_hqj_zdb .section}

|Error code|Description|
|:---------|:----------|
|200|Normal|
|400|Syntax error in the client request|
|403|Verification failed, speed limit, not authorized|
|500|Internal server error|

## Sub-account authorization description {#section_lvd_lqj_zdb .section}

When you report event data using the AK of the sub-account, you must grant the CloudMonitor management permission to the corresponding sub-account. If the sub-account is not authorized with the CloudMonitor management permission, the system displays "cannot upload, please use ram to auth" during data reporting.

1.  Log on to the [RAM console](https://ram.console.aliyun.com/#/overview).
2.  In the left navigation bar, click **Users**.
3.  Select the sub-account which needs to report data. Click **Authorize** in the Actions column.
4.  On the authorization page, select **Manage CloudMonitor** and click **OK**.

