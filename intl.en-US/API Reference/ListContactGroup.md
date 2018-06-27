# ListContactGroup {#reference_hnt_pfy_zdb .reference}

## Description {#section_zkx_tfy_zdb .section}

Query the contact group associated with an alarm rule under an Alibaba Cloud account.

## Request Parameters {#section_gwj_5fy_zdb .section}

|Name|Type|Required or not|Description|
|:---|:---|:--------------|:----------|
|Action|String|Yes| The parameter specified by the system. Value: ListContactGroup|
|PageNumber|PageNumber|No|Page number. The default value is Page 1|
|PageSize|PageNumber|No|Page size. The default value is 100|

## Response parameters {#section_hp2_vfy_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|Nexttoken|Integer|Next page. If the value is null it means no pages are available|
|Datapoints|List< String \>|List of contact group names|
|Total|Integer|Total number of compliant data items|
|Success|Boolean|Whether the request is successful|
|RequestId|String|Requested UUID, which is used for log query|
|Code|String|Request failure status code. The value 200 indicates request is successful, and a non-200 value indicates request failure|
|Message|String|Request failure prompt message|

## Examples {#section_dzf_wfy_zdb .section}

**Request example**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=ListContactGroup
&PageSize=5
&PageNumber=1
&<Common Request Parameters>
```

**Response example**

-   XML format

    ```
    <ListContactGroupResponse>
      <RequestId>DCE1419F-D60C-441C-81C3-7425B9211AC5</RequestId>
      <ContactGroups>
        <ContactGroup>test4nudou</ContactGroup>
        <ContactGroup>xzytestgroup</ContactGroup>
        <ContactGroup>Alarm contacts under an Alibaba Cloud account</ContactGroup>
      </ContactGroups>
      <Success>true</Success>
      <Code>200</Code>
      <Total>6</Total>
    </ListContactGroupResponse>
    ```

-   JSON format

    ```
    {
        "RequestId": "D3D03B0A-CF1A-4DAB-BF0D-D4B6ACD5677A", 
        "ContactGroups": {
            "ContactGroup": [
                "test4nudou", 
                "xzytestgroup", 
                "Alarm contacts under an Alibaba Cloud account"
            ]
        }, 
        "Success": true, 
        "code": "200", 
        "total": 3
    }
    ```


