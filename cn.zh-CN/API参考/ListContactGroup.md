# ListContactGroup {#reference_hnt_pfy_zdb .reference}

## 描述 {#section_zkx_tfy_zdb .section}

查询云账号下对应的报警规则联系人组。

## 请求参数 {#section_gwj_5fy_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数，取值：ListContactGroup|
|PageNumber|PageNumber|否|页数，默认值为第1页|
|PageSize|PageNumber|否|页大小，默认值为100|

## 返回参数 {#section_hp2_vfy_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|NextToken|Integer|下一页，为空代表没有下一页|
|Datapoints|List< String \>|联系组名称列表|
|Total|Integer|符合条件数据总数|
|Success|Boolean|请求是否成功|
|RequestId|String|请求的uuid，便于查询日志|
|Code|String|请求失败状态码，200为成功，非200为失败|
|Message|String|请求失败的提示信息|

## 示例 {#section_dzf_wfy_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=ListContactGroup
&PageSize=5
&PageNumber=1
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListContactGroupResponse>
      <RequestId>DCE1419F-D60C-441C-81C3-7425B9211AC5</RequestId>
      <ContactGroups>
        <ContactGroup>test4nudou</ContactGroup>
        <ContactGroup>xzytestgroup</ContactGroup>
        <ContactGroup>云账号报警联系人</ContactGroup>
      </ContactGroups>
      <Success>true</Success>
      <Code>200</Code>
      <Total>3</Total>
    </ListContactGroupResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "D3D03B0A-CF1A-4DAB-BF0D-D4B6ACD5677A", 
        "ContactGroups": {
            "ContactGroup": [
                "test4nudou", 
                "xzytestgroup", 
                "云账号报警联系人"
            ]
        }, 
        "Success": true, 
        "Code": "200", 
        "Total": 3
    }
    ```


