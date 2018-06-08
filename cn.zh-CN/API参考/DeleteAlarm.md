# DeleteAlarm {#reference_lgt_cjv_zdb .reference}

## 描述 {#section_ocv_djv_zdb .section}

删除已创建的报警规则。

## 请求参数 {#section_d4y_ljv_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数，取值：DeleteAlarm|
|Id|String|必选|报警规则的id|

## 返回参数 {#section_lrr_vjv_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|Data|String|返回的报警规则id|
|Success|Boolean|请求是否成功|
|RequestId|String|请求的uuid，便于查询日志|
|Code|String|请求失败状态码，200为成功，非200为失败|
|Message|String|请求失败的提示信息|

## 错误编码 {#section_ths_xjv_zdb .section}

|错误代码|描述|语义|
|:---|:-|:-|
|400|Bad Request|客户端请求中的语法错误|
|403|Forbidden|没有权限|
|404|Not Found|客户端错误，未找到|
|500|Internal Server Error|服务器内部错误|
|200|OK|正常|

## 示例 {#section_adv_djv_zdb .section}

**请求示例**

**返回示例**

-   XML格式

    ```
    <DeleteAlarmResponse>
      <RequestId>A9371CD8-369D-49FA-BED9-35050A0DC6A2</RequestId>
      <Success>true</Success>
      <Code>200</Code>
    </DeleteAlarmResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": " A9371CD8-369D-49FA-BED9-35050A0DC6A2", 
        "Success": true, 
        "Code": "200"
    }
    ```


