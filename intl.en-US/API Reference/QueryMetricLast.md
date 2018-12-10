# QueryMetricLast {#reference_kxr_y2z_zdb .reference}

## Description {#section_svh_z2z_zdb .section}

Query the latest monitoring data of a specified monitored object.

## Request Parameters {#section_etr_z2z_zdb .section}

|Name|Type|Mandatory or Not|Description|
|:---|:---|:---------------|:----------|
|Action|String|Yes|The API name specified by the system. Value:  QueryMetricLast|
|Project|String|Yes|Name space. It indicates the product to which the monitoring data belongs, for example,  “acs\_ecs\_dashboard” and “acs\_rds\_dashboard”|
|Metric|String|Yes|Metric name|
|Period|String|No|Time interval, always calculated in seconds, for example, 60, 300, or 900. If this field is not specified, raw data is queried based on the report period stated during metric registration. If this field is specified, corresponding statistics are queried based on the specified period.|
|StartTime|String|No|The start time. It can be a millisecond value counted from 12:00:00 AM, January 1, 1970, or formatted data, for example, 2015-10-20  00:00:00.|
|EndTime|String|No|It can be a millisecond value counted from 00:00:00, January 1, 1970, or formatted data, for example, 2015-10-20 00:00:00.|
|dimensions|String|No|Key-value set used to filter monitoring data. The key can use one or more dimensionKeys  stated during monitoring metric registration and the value is the value corresponding to this key.  Instanceid is required and requires a JSON string to represent the Map  object must be a JSON string and only strings can be input. Dimensions must be input in order|
|Length|String|No|Returns the size of each page of monitoring data for paged queries.  The default value is 1000, that is, 1,000 monitoring data entries per page.|
|cursor|String|No|Cursor|

For how to assign values to input parameters of various cloud products, such as Project, Metric, Period, and Dimensions, see Preset monitoring metric.[Preset metric item reference](reseller.en-US/API Reference/Preset metric item reference.md#)

## Response parameters {#section_wyb_1fz_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|Period|String|Time interval is always calculated in seconds, for example, 60, 300, or 900|
|Cursor|String|Cursor|
|Datapoints|List|Monitoring data list, in the following format: \{ “timestamp”: 1490164200000,”Maximum”:  100,”userId”: “1234567898765432”, “Minimum”: 4.55,”instanceId”: “i-bp18abl200xk9599ck7c”, “Average”: 93.84\}|
|Code|String|Status code. Code 200 is returned if no exception occurs|
|Success|Boolean|Whether the current query is successful. In case of any exception on the server side, the returned value is “false” \(and “true” otherwise\)|
|Message|String|Status description. The message is null when Code is 200|
|RequestId|String|When any issue arises with the request, you can provide this field to our technical support for troubleshooting|

## Example {#section_shl_1fz_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=QueryMetricLast
&EndTime=2017-03-22+14%3A30%3A27
&StartTime=2017-03-22+14%3A20%3A27
&Period=60
&Dimensions=%7BinstanceId%3A%27 i-abcdefgh123456%27%7D
&Project=acs_ecs_dashboard
&Metric=cpu_idle
&<Common Request Parameters>
```

**Response example**

-   XML format

    ```
    <QueryMetricLastResponse>
      <period>1</period>
      <Datapoints>
        <Datapoints>
          <timestamp>1490164200000</timestamp>
          <Maximum>100</Maximum>
          <userId>1234567898765432</userId>
          <Minimum>4.55</Minimum>
          <instanceId>i-bp18abl200xk9599ck7c</instanceId>
          <Average>93.84</Average>
        </Datapoints>
      </Datapoints>
      <RequestId>021472A6-25E3-4094-8D00-BA4B6A5486C3</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </QueryMetricLastResponse>
    ```

-   JSON format

    ```
    {
        "Period": "60", 
        "Datapoints": [
            {
                "timestamp": 1490164200000, 
                "Maximum":100, 
                "userId": "1234567898765432", 
                "Minimum":25, 
                "instanceId":"i-bp18abl200xk9599ck7c", 
                "Average":95.82,
            }
        ], 
        "RequestId": "4E7664F2-9CDE-4212-9318-A0712D345A5E", 
        "Success": true, 
        "Code": "200"
    }
    ```


