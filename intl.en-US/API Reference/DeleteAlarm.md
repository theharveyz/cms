# DeleteAlarm {#reference_lgt_cjv_zdb .reference}

## Description {#section_ocv_djv_zdb .section}

Delete an existing alert policy.

## Request Parameters {#section_d4y_ljv_zdb .section}

|Parameter|Type|Required or not|Description|
|:--------|:---|:--------------|:----------|
|Action|String|Yes|System-defined parameters, value: DeleteAlarm|
|Id|String|Mandatory|ID of the alarm rule|

## Response parameters {#section_lrr_vjv_zdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|Data|String|Returned alarm rule ID|
|Success|Boolean|Was the request successful?|
|RequestId|String|Requested UUID, easy to query log|
|Code|String|Request failed status code, 200 is successful, non-200 is failed|
|Message|String|Request failed prompt information|

## Error codes {#section_ths_xjv_zdb .section}

|Error code|Description|Meaning|
|:---------|:----------|:------|
|400|Bad Request|Syntax error in client request|
|403|Forbidden|No permission|
|404|Not Found|Client error, not found|
|500|Internal Server Error|Server error|
|200|OK|Normal|

## Example {#section_adv_djv_zdb .section}

**Request example**

**Response example**

-   XML format

    ```
    <DeleteAlarmResponse>
      <RequestId>A9371CD8-369D-49FA-BED9-35050A0DC6A2</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </DeleteAlarmResponse>
    ```

-   JSON format

    ```
    {
        "RequestId": " A9371CD8-369D-49FA-BED9-35050A0DC6A2", 
        "Success": true, 
        "Code": "200"
    }
    ```


