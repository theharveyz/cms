# QueryMetricList {#reference_uq4_mfz_zdb .reference}

## Description {#section_a2c_pfz_zdb .section}

Query the monitoring data of a specified product instance during a time period.

## Request parameters {#section_xwj_pfz_zdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|Operation API name, which is a parameter specified by the system. The value is QueryMetricList.|
|Project|String|Yes|Name space, indicating the product to which the monitoring data belongs, for example, acs\_ecs\_dashboard and acs\_rds\_dashboard.|
|Metric|String|Yes|Metric name|
|Period|String|No|Time interval, calculated in seconds, for example, 60, 300, or 900. If this parameter is not specified, raw data is queried according to the report period specified during metric registration. If this parameter is specified, corresponding statistics are queried according to the specified period.|
|StartTime|String|No|Start time, which can be a millisecond value counted from 00:00:00, January 1, 1970, or a formatted value, for example, 2015-10-20 00:00:00.|
|EndTime|String|No|End time, which can be a millisecond value counted from 00:00:00, January 1, 1970, or a formatted value, for example, 2015-10-20 00:00:00.|
|Dimensions|String|No|Key-value set for filtering monitoring data, for example, "instanceId:XXXXXX" A key-value set must be a JSON string. Dimensions must be inputted in sequence.|
|Length|String|No|Number of data records on a page. This parameter is used for paging query. Default value: 1000.|
|Cursor|String|No|Cursor|

**Parameter description**

-   For details about how to set the values of Project, Metric, Period, and Dimensions, see [Preset metric item reference](reseller.en-US/API Reference/Preset metric item reference.md#).
-   The value of StartTime cannot be greater than or equal to that of EndTime.
-   Cursor is a parameter in paging mode. If this parameter has a value, the current page is not the last page. If this parameter is null, the current page is the last page.
-   The value of Period can be 60 \(1 minute\), 300 \(5 minutes\), or 900 \(15 minutes\). You can set the Period parameter according to the document requirements and query scenario. For example, if you set Period to 60, 1000 data records are returned. \(Note that if you have more than 1000 data records, for example 1440 records, the maximum return value cannot be greater than 1000. Therefore, the first 1000 records are returned.\) If you set Period to 300, 288 data records are returned.
-   This API can also be called by using an authorized RAM user account. During authorization, the operation descriptor is `cms:QueryMetricList`, and the resource descriptor is `*`.

## Response parameters {#section_imy_pfz_zdb .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|Period|String|Time interval, calculated in seconds, for example, 60, 300, or 900.|
|Cursor|String|Cursor|
|Datapoints|String|Monitoring data list, in the following format: \{ "timestamp": 1490164200000, "Maximum": 100, "userId": 1234567898765432, "Minimum": 4.55, "instanceId": "i-bp18abl200xk9599ck7c", "Average": 93.84 \}.|
|Code|String|Status code. Code 200 is returned if no exception occurs.|
|Success|Boolean|Indicates whether an operation is performed successfully. If there is an exception on the server, the value "false" is returned. If no exception occurs, the value "true" is returned.|
|Message|String|Status description. The Message parameter is null when the code is 200.|
|RequestId|String|If a problem occurs during querying, you can provide this field to a technical engineer for troubleshooting.|

## Examples {#section_up5_qfz_zdb .section}

**Request example**

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

**Response examples**

-   XML format

    ```
    <QueryMetricListResponse>
      <Period>60</Period>
      <Datapoints>
        <Datapoints>
          <timestamp>1490152860000</timestamp>
          <Maximum>100</Maximum>
          <userId> 1234567898765432</userId>
          <Minimum>93.1</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.52</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490152920000</timestamp>
          <Maximum>100</Maximum>
          <userId> 1234567898765432 </userId>
          <Minimum>92.59</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.49</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490152980000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>92.86</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.44</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153040000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>91.43</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.36</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153100000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>93.55</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.51</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153160000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>93.1</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.52</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153220000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>92.59</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.42</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153280000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>91.18</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.34</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153340000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>92.86</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.46</Average>
        </Datapoints>
        <Datapoints>
          <timestamp>1490153400000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>91.18</Minimum>
          <instanceId>i-abcdefgh123456</instanceId>
          <Average>99.35</Average>
        </Datapoints>
      </Datapoints>
      <RequestId>6661EC50-8625-4161-B349-E0DD59002AB7</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </QueryMetricListResponse>
    ```

-   JSON format

    ```
    {
        "Period": "60", 
        "Datapoints": [
            {
                "timestamp": 1490152860000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 93.1, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.52
            }, 
            {
                "timestamp": 1490152920000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 92.59, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.49
            }, 
            {
                "timestamp": 1490152980000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 92.86, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.44
            }, 
            {
                "timestamp": 1490153040000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 91.43, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.36
            }, 
            {
                "timestamp": 1490153100000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 93.55, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.51
            }, 
            {
                "timestamp": 1490153160000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 93.1, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.52
            }, 
            {
                "timestamp": 1490153220000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 92.59, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.42
            }, 
            {
                "timestamp": 1490153280000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 91.18, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.34
            }, 
            {
                "timestamp": 1490153340000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 92.86, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.46
            }, 
            {
                "timestamp": 1490153400000, 
                "Maximum": 100, 
                "userId": "1234567898765432", 
                "Minimum": 91.18, 
                "instanceId": "i-abcdefgh123456", 
                "Average": 99.35
            }
        ], 
        "RequestId": "6A5F022D-AC7C-460E-94AE-B9E75083D027", 
        "Success": true, 
        "Code": "200"
    }
    ```


