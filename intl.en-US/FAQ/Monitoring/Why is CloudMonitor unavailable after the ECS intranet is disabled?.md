# Why is CloudMonitor unavailable after the ECS intranet is disabled? {#concept_sym_jvk_zdb .concept}

When the ECS intranet is disabled, the CloudMonitor service becomes unavailable because CloudMonitor resolves the communication address \(open.cms.aliyun.com\) on the intranet, and obtains data through the intranet. To use CloudMonitor properly, make sure that ECS can telnet port 80 of open.cms.aliyun.com, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6268/15511686124962_en-US.jpg)

