# 禁用ECS的内网后不能使用云监控 {#concept_sym_jvk_zdb .concept}

本文为您介绍为何禁用ECS的内网后不能使用云监控。

ECS服务器使用云监控服务，是不能禁用内网的。

因云监控的通讯地址 open.cms.aliyun.com 是解析在内网上的，通过内网来进行通讯获取数据，如果禁用了内网云监控服务会出现无法正常使用，所以为了能够正常的使用云监控服务，必须要确保能在服务器上能telnet 通open.cms.aliyun.com 的80端口，如下图所示：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6268/15619490534962_zh-CN.jpg)

