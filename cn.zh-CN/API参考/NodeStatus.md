# NodeStatus {#reference_zpd_h2v_zdb .reference}

## 描述 {#section_hjn_p2v_zdb .section}

查询指定实例的云监控插件运行状态。

## 请求参数 {#section_o2g_q2v_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：NodeStatus。|
|InstanceId|String|是|实例id，例如i-22jja5c2l。|

## 返回参数 {#section_nnc_r2v_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|ErrorCode|Integer|错误码，200为成功，其他失败|
|ErrorMessage|String|错误提示|
|Success|String|本次操是否成功,等价与errorCode200|
|RequestId|String|请求的唯一ID用于定位错误|
|InstanceId|String|实例id|
|Status|String|插件运行状态|
|AutoInstall|Boolean|是否可以使用NodeInstall自动安装|

**插件运行状态**

|名称|描述|
|:-|:-|
|running|正在运行中|
|stopped|已停止|
|not\_installed|未安装|
|installing|安装中|
|install\_faild|安装失败|
|need\_to\_upgrade|需要升级|
|uninstalled|已卸载|

## 示例 {#section_nw3_s2v_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=NodeStatus
&InstanceId= i-abcdefgh123456
&<公共请求参数>
```

**返回示例**

-   XML格式
-   ```
<NodeStatusResponse>
  <Status>running</Status>
  <InstanceId> i-abcdefgh123456</InstanceId>
  <ErrorCode>200</ErrorCode>
  <Success>true</Success>
  <AutoInstall>true</AutoInstall>
</NodeStatusResponse>
```


-   JSON格式
-   ```
{
    "Status": "running", 
    "InstanceId": " i-abcdefgh123456", 
    "Success": true, 
    "ErrorCode": 200, 
    "AutoInstall": true
}
```


