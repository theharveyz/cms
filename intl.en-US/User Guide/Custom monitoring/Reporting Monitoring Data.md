# Reporting Monitoring Data {#concept_b2h_ddb_5db .concept}

Custom monitoring features provide you with interfaces for reporting monitoring data, it is convenient for you to report the time-series data collected by yourself to cloud monitoring, and configure alarm rules to receive alarm notifications.

CloudMonitor supports data reporting using open APIs, Java SDK, and AliCloudCLI.

## Limits {#section_q4b_znk_zdb .section}

-   A single cloud account QPS is limited to 100.
-   Report up to 100 data in a single time, and the body is up to 256kb.
-   The metricname field only supports letters, numbers, and underscores. You need to start with a letter, and the non-letter starts with an upper case of "", the illegal character is replaced with "\_".
-   The dimensions field does not support "=", "&", "," ",". illegal characters are replaced with "\_".
-   Key-value for metricname and dimensions The maximum is 64 bytes, and more than 64 bytes are truncated.
-   For other restrictions, please pay attention to the billing method.

## Report data using open APIs {#section_zym_l4k_zdb .section}

-   Endpoint

    Public service address: https://metrichub-cms-cn-hangzhou.aliyuncs.com

    Internal network service address

    |Region|Endpoint|
    |:-----|:-------|
    |East China 1 \(Hangzhou\)|[http://metrichub-cn-hangzhou.aliyun.com](http://metrichub-cn-hangzhou.aliyun.com/?spm=a2c4g.11186623.2.6.220HYi)|
    |China North 3 \(Zhangjiakou\)|[http://metrichub-cn-zhangjiakou.aliyun.com](http://metrichub-cn-zhangjiakou.aliyun.com/?spm=a2c4g.11186623.2.7.220HYi)|
    |East China 2 \(Shanghai\)|[http://metrichub-cn-shanghai.aliyun.com](http://metrichub-cn-shanghai.aliyun.com/?spm=a2c4g.11186623.2.8.220HYi)|
    |North China 2 \(Beijing\)|[http://metrichub-cn-beijing.aliyun.com](http://metrichub-cn-beijing.aliyun.com/?spm=a2c4g.11186623.2.9.220HYi)|
    |North China 1 \(Qingdao\)|[http://metrichub-cn-qingdao.aliyun.com](http://metrichub-cn-qingdao.aliyun.com/?spm=a2c4g.11186623.2.10.220HYi)|
    |South China 1 \(Shenzhen\)|[http://metrichub-cn-shenzhen.aliyun.com](http://metrichub-cn-shenzhen.aliyun.com/?spm=a2c4g.11186623.2.11.220HYi)|
    |cn-hongkong|[http://metrichub-cn-hongkong.aliyun.com](http://metrichub-cn-hongkong.aliyun.com/?spm=a2c4g.11186623.2.12.220HYi)|
    |China North 5 \(Hohhot\)|[http://metrichub-ap-southeast-5.aliyuncs.com](http://metrichub-ap-southeast-5.aliyuncs.com/?spm=a2c4g.11186623.2.13.220HYi)|
    |Middle East 1 \(Dubai\)|[http://metrichub-me-east-1.aliyun.com](http://metrichub-me-east-1.aliyun.com/?spm=a2c4g.11186623.2.14.220HYi)|
    |美国西部 1（硅谷 ）|[http://metrichub-us-east-1.aliyun.com](http://metrichub-us-east-1.aliyun.com/?spm=a2c4g.11186623.2.15.220HYi)|
    |Eastern United States 1 \(Virginia\)|[http://metrichub-us-west-1.aliyun.com](http://metrichub-us-west-1.aliyun.com/?spm=a2c4g.11186623.2.16.220HYi)|
    |Asia-Pacific Northeast 1 \(Japan\)|[http://metrichub-ap-northeast-1.aliyun.com](http://metrichub-ap-northeast-1.aliyun.com/?spm=a2c4g.11186623.2.17.220HYi)|
    |Germany 1 \(Frankfurt\)|[http://metrichub-eu-central-1.aliyun.com](http://metrichub-eu-central-1.aliyun.com/?spm=a2c4g.11186623.2.18.220HYi)|
    |Asia Pacific SE 2 \(Sydney\)|[http://metrichub-ap-southeast-2.aliyun.com](http://metrichub-ap-southeast-2.aliyun.com/?spm=a2c4g.11186623.2.19.220HYi)|
    |Asia Pacific Southeast 1 \(Singapore\)|[http://metrichub-ap-southeast-1.aliyun.com](http://metrichub-ap-southeast-1.aliyun.com/?spm=a2c4g.11186623.2.20.220HYi)|
    |Asia Pacific SE 3 \(Kuala Lumpur\)|[http://metrichub-ap-southeast-3.aliyun.com](http://metrichub-ap-southeast-3.aliyun.com/?spm=a2c4g.11186623.2.21.220HYi)|
    |Asia Pacific SOU 1 \(Mumbai\) |[http://metrichub-ap-south-1.aliyuncs.com](http://metrichub-ap-south-1.aliyuncs.com/?spm=a2c4g.11186623.2.22.220HYi)|

-   Request syntax

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


-   Request Parameters

    |Name|Type|Required|Description|
    |:---|:---|:-------|:----------|
    |groupId|long|Yes|ID of the apply grouping|
    |metricName|string|Yes.|Monitor item name, support letter, number, connector '\_-. /\\ ", The other characters are illegal, with a maximum length of 64 bytes, intercept the first 64 bytes when more than 64 bytes|
    |dimensions|object|Yes.|The dimension map, key-value are all strings, Support letter, number, connector "\_-. /\\ ", The maximum number of key value pairs is 10, the maximum length of key is 64 bytes, value is a maximum length of 64 bytes, with the first 64 bytes taken when the length exceeds 64 bytes|
    |time|string|Yes.|Indicator occurrence time, support for "yyyymmdd't 'hmmmss. sssz "and long-type timestamps in 2 ways, such "20171012t132456. 888 + 0800" or "1508136760000"|
    |type|int|Yes.|The type of the reported value, 0 is the original value, and 1 is the aggregate data. Recommended 60 s, 300 s when reporting aggregate data The data for the cycle is reported, otherwise the monitoring data that is longer than 7 days old is not available for normal query.|
    |Period|string|No|The aggregation cycle, in seconds. Required to pass this field if type = 1, value 60, 300|
    |values|object|Yes|Indicator value collection, when type = 0, key can only be "value ", the original values are reported, and cloud monitoring aggregates the original values to multiple values by period, such as maximum, Count, sum, etc.|

    When the raw data is reported through the interface, cloud monitoring calculates the results for 1 minute and 5 minutes according to the following statistics:

    -   Average: Average
    -   Maximum: Maximum
    -   Minimum: Minimum
    -   Sum: Sum
    -   SampleCount: Count
    -   SumPerSecond: count the number of seconds for the sum/corresponding period, or you can use the sliding average calculation
    -   CountPerSecond: the number of seconds for the count/corresponding period, or you can use the sliding average calculation
    -   Lastvalue: The last sample value of the cycle, similar to gauge
    -   Pt10: percentile 0.1, more than 10% all sampling data for this cycle
    -   P20: percentile 0.2, more than 20% all sampling data for this cycle
    -   P30: percentile 0.3, more than 30% all sampling data for this cycle
    -   P40: percentile 0.4, more than 40% all sampling data for this cycle
    -   P50: percentile 0.5, greater than 50% all sampling data for this cycle, median
    -   P60: percentile 0.6, more than 60% all sampling data for this cycle
    -   P70: percentile 0.7, more than 70% all sampling data for this cycle
    -   P75: percentile 0.75, more than 75% all sampling data for this cycle
    -   P80: percentile 0.8, more than 80% all sampling data for this cycle
    -   P90: percentile 0.9, more than 90% all sampling data for this cycle
    -   P95: percentile 0.95, more than 95% all sampling data for this cycle
    -   P98: percentile 0.98, more than 98% all sampling data for this cycle
    -   P99: percentile 0.99, more than 99% all sampling data for this cycle
-   Response Element

    The system returns the HTTP status code 200.

-   Example
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

    -   Response example

        ```
        {
           "code":"200",
           "msg": "// return MSG is empty when reporting normally
        }
        ```


## Sample code {#section_y1s_spk_zdb .section}

-   Reporting raw data

    ```
    Cmsclientinit. groupid = 101l; // set common application group ID
            CMSClient cmsClient = new CMSClient(endpoint, accKey, secret);//initializeclient
            CustomMetricUploadRequest request = CustomMetricUploadRequest.builder()
                    .append(CustomMetric.builder()
                            . setMetricName ("testmetric") // Indicator Name
                            . Setgroupid (102l) // set customized grouping ID
                            . Settime (new date ())
                            .setType(CustomMetric.TYPE_VALUE)//type is default value,
                            .appendValue(MetricAttribute.VALUE, 1f)//key value can only be default，key
                            .appendDimension("key", "value")//add dimension
                            .appendDimension("ip", "127.0.0.1")//add dimension
                            .build())
                    .build();
            CustomMetricUploadResponse response = cmsClient.putCustomMetric(request);//report
            System.out.println(JSONObject.toJSONString(response));
    ```


-   Automatic multi-cycle aggregation escalation

    The SDK supports the ability to post data after aggregation locally, the aggregation cycle is 1 minute, 5 minutes.

    |Data types|Description|The value of the aggregate|Memory consumption does not include name, dimension, single time series, single aggregation cycle\)|
    |:---------|:----------|:-------------------------|:--------------------------------------------------------------------------------------------------|
    |value|General Value Type|除了LastValue外的所有属性|About 4 K|
    |gauge|采样值|Lastvalue|4 bytes|
    |meter|Sum and Rate|Sum，SumPerSecond|50 bytes|
    |Counter|Count|SampleCount|10 bytes|
    |Timer|Calculation time|SampleCount、CountPerSecond、 Average、Maximum、Minimum、PXX\(P10-P99\)|About 4 K|
    |Histogram|Distribution|SampleCount、Average、Maximum、Minimum、PXX\(P10-P99\)|About 4 K|

    ```
    //初始化
            Cmsclientinit. groupId = 0L;
            CMSClient cmsClient = new CMSClient(accKey, secret, endpoint);//create client
            CMSMetricRegistryBuilder builder = new CMSMetricRegistryBuilder();
            builder.setCmsClient(cmsClient);
            final MetricRegistry registry = builder.build();//registry contains 2 aggregation cycles
            //or final MetricRegistry registry = builder.build(RecordLevel. _ 60 s); // create only 1 minute of aggregation cycle
    // Use value
    ValueWrapper value = registry.value(MetricName.build("value"));
    value.update(6.5);
    // Use meter
    MeterWrapper meter = registry.meter(MetricName.build("meter"));
    meter.update(7.2);
    // use counter
    CounterWrapper counter = registry.counter(MetricName.build("counter"));
    counter.inc(20);
    counter.dec(5);
    // Use Timer
    TimerWrapper timer = registry.timer(MetricName.build("timer"));
    timer.update(30, TimeUnit.MILLISECONDS);
    //use histogram
    HistogramWrapper histogram = registry.histogram(MetricName.build("histogram"));
    histogram.update(20);
    // Use Gauge
    final List list = new ArrayList();
    registry.gauge(MetricName.build("gauge"), new Gauge() {
                            @ Override
                            public Number getValue() {
                                return list.size();
                            }
                        });
    ```


## Command Line \(CLI\) method to report data {#section_ggy_bqk_zdb .section}

```
With an Ali cloud account, and generate Sub-Account AK with cloud monitoring privileges (with Sub-Account Security better ).
```

-   Create a subaccount.

    ![](images/4830_en-US.png)

-   Generate an accesskeyid for the sub-account.

    ![](images/4831_en-US.png)

-   Authorize cloud monitoring permissions for sub-accounts.

    ![](images/4832_en-US.png)


## Procedure {#section_wln_wlj_zdb .section}

1.  Installing the aliyuncli Tool

    ```
    System Requirements: Linux, Unix or Mac OS. Environmental requirements: Python 2. 7. X is installed.
    ```

    1.  Installing Python
        -   Skip this step if your device has a version of Python 2. 7. x installed.
        -   If your device does not have a version of Python 2..x installed, execute the following command in the command line window, install Python. Note that make sure that your device is installed wget.

            ```
            wget https://www.python.org/ftp/python/2.7.8/Python-2.7.8.tgz (or download it in another way and put it on a path)
            tar -zxvf Python-2.7.8.tgz
            cd Python-2.7.8
            ./configure
            make
            sudo make install
            ```

    2.  Install pip
        -   Skip this step if your device has pip installed.
        -   If your device does not have pip installed, install the following command in the command line window: pip.

            ```
            curl "https://bootstrap.pypa.io/get-pip.py" -o "pip-install.py"
            sudo python pip-install.py
            ```

        -   The system displays similar information, indicating that the installation was successful.

            ```
            Successfully installed pip-7.1.2 setuptools-18.7 wheel-0.26.0
            ```

    3.  Install command line tools

        If the pip version is too low on the system, it will cause errors in the CLI installation. The user can use the following command to first pair the pip After the software is upgraded, the relevant operation will be performed. Use pip 7.x or later. If you are already in the latest version of pip, skip this step.

        1.  Upgrade by executing the following command in the command line window pip.

            ```
            sudo pip install -U pip
            ```

            The system displays similar information, indicating that the upgrade was successful.

            ```
            Successfully uninstalled pip-7.1.2
            Successfully installed pip-8.1.2
            ```

        1.  Install the Ali cloud command line tool by performing the following commands.

            ```
            sudo pip install aliyuncli
            ```

            The system displays similar information, indicating that the installation was successful.

            ```
            Successfully installed aliyuncli-2.1.2 colorama-0.3.3 jmespath-0.7.1
            ```

    4.  Configure command-line tools

        ```
        ~ sudo aliyuncli configure
        Aliyun Access Key ID [*******************a]: youraccesskeyid
        Aliyun Access Key Secret [*******************b]: youraccesskeysecret
        Default Region Id [cn-hangzhou]: cn-hangzhou
        Default output format [json]: json
        ```

2.  Installing CmsSDK
    -   Windows is installed as follows.

        ```
        cd C:\Python27\Scripts
        pip install aliyun-python-sdk-cms
        ```

    -   To update the SDK, run the following command:

        ```
        pip install --upgrade aliyun-python-sdk-cms
        ```

    -   Linux The installation method is as follows.

        ```
        sudo pip install aliyun-python-sdk-cms
        ```

    -   To update the SDK, run the following command:

        ```
        sudo pip install —upgrade aliyun-python-sdk-cms
        ```

3.  Reporting Monitoring Data

    Use the PutEvent interface.

    -   Windows reporting example

        ```
        aliyuncli.exe cms PutEvent --EventInfo "[{'content':'helloworld','time':'20171013T170923.456+0800','name':'ErrorEvent','groupId':'27147'}]"
        ```

    -   Linux Reporting example

        ```
        aliyuncli cms PutEvent --EventInfo "[{'content':'helloworld','time':'20171023T180923.456+0800','name':'ErrorEvent','groupId':'27147'}]"
        ```

    -   Returns a 200 status code after the report is successful.

        ```
        {
        "Code":"200"
        }
        ```


## Error Code {#section_ovd_hqj_zdb .section}

|Error code|Meaning|
|:---------|:------|
|200|Normal|
|400|Syntax Error in client request|
|403|Calibration FAILED, speed limit, no authorization|
|500|Server internal error|

## Sub-account authorization instructions {#section_lvd_lqj_zdb .section}

Subaccount authorization description When the AccessKey of a subaccount is used to report an event, the subaccount must be authorized to manage CloudMonitor. The "cannot upload event" prompt when reporting data if the sub-account is not authorized for cloud monitoring administration, Please use ramto auth ".

1.  Logon to thel[RAM console](https://ram.console.aliyun.com/#/overview) .
2.  Enter the **user management menu** .
3.  Click **authorize** next to the sub-account that is used to report data.

    ![](images/4851_en-US.png)

4.  On the authorization page, select **Manage CloudMonitor**, and click **OK**to save the authorization.

    ![](images/4852_en-US.png)


