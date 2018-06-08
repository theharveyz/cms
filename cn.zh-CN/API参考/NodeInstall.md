# NodeInstall {#reference_mps_mxy_zdb .reference}

## 描述 {#section_vlf_4xy_zdb .section}

调用接口为指定ECS 实例安装云监控插件。可参见[主机监控插件介绍](../cn.zh-CN/用户指南/主机监控/主机监控插件介绍.md#)

**说明：** 

-   使用接口前请确保您的实例已安装[服务器安全（安骑士）](https://help.aliyun.com/document_detail/28451.html)插件。安骑士插件目前集成于安全镜像中，在购买ECS后，一般都已经默认安装，您可以进入[安骑士控制台](https://yundun.console.aliyun.com/?p=aqs#/aqs/overviews)，查看每台服务器的在线状态。
-   接口安装云监控插件的成功率约为95%，如安装失败，可登录机器[手工安装](https://help.aliyun.com/document_detail/38859.html)。

## 请求参数 {#section_rxf_qxy_zdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数，取值：NodeInstall|
|UserId|String|是|阿里云userId|
|InstanceId|String|是|实例id，例如：i-22jja5c2l|
|Force|Boolean|否|是否强制安装，如果用户已经安装过云监控，默认值为强制安装|

## 返回参数 {#section_qw5_qxy_zdb .section}

|名称|类型|描述|
|:-|:-|:-|
|Success|Boolean|请求是否成功|
|ErrorCode|Integer|请求失败状态码，200为成功，非200为失败|
|RequestId|String|请求的uuid，便于查询日志|
|ErrorMessage|String|请求失败的提示信息|

## 示例 {#section_wfw_zxy_zdb .section}

**请求示例**

```
http://metrics.cn-hangzhou.aliyuncs.com/?Action=NodeInstall
&InstanceId= i-abcdefgh123456
&Force=true
&UserId= 1234567898765432
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <NodeInstallResponse>
      <ErrorCode>200</ErrorCode>
      <Success>true</Success>
    </NodeInstallResponse>
    ```

-   JSON格式

    ```
    {
        "ErrorCode": 200, 
        "Success": true
    }
    ```


