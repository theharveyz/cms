# Why is CloudMonitor unavailable after the ECS intranet is disabled? {#concept_sym_jvk_zdb .concept}

The ECS intranet cannot be disabled when ECS uses CloudMonitor. The communication address \(open.cms.aliyun.com\) of CloudMonitor is resolved on the intranet, and CloudMonitor obtains data through intranet communication. If the intranet is disabled, CloudMonitor is unavailable. To use CloudMonitor properly, make sure that ECS can telnet port 80 of open.cms.aliyun.com, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6268/15434730704962_en-US.jpg)

